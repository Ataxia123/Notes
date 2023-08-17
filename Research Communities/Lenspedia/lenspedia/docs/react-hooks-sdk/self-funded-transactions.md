---
description: >-
  Handle NOT_ALLOWED error by using user's wallet to pay for gas as fallback for
  a rejected operation
---

# Self-funded transactions

{% hint style="info" %}
The feature described in this guide is available by upgrading `@lens-protocol/react-web` (or `@lens-protocol/react` in case of RN integrations) to version `1.1.0`.
{% endhint %}

One of the great features offered by the Lens API is [gasless](https://docs.lens.xyz/docs/gasless), the ability to execute blockchain operations with gas costs covered by the Lens API.

There are scenarios were a request from given profile could be refused to be executed in a gasless fashion. The reason could vary, from hitting usage limit to being flagged as low-signal (see eligibility details [here](https://docs.lens.xyz/docs/gasless#eligibility-requirements.) ).

In those cases you might observe an error like the following one coming back from the SDK hook you used.

{% code title="BroadcastingError" %}
```
BroadcastingError: broadcasting failed with reason: NOT_ALLOWED
    at handleRelayError (relayer.ts:26:22)
    at ProfileMetadataCallGateway.broadcast (ProfileMetadataCallGateway.ts:104:14)
    at async ProfileMetadataCallGateway.createDelegatedTransaction (ProfileMetadataCallGateway.ts:52:20)
    at async UpdateProfileDetails.execute (DelegableSigning.ts:38:22)
    at async useUpdateProfileDetailsController.ts:62:5
    at async useUpdateProfileDetails.ts:59:16
    at async execute (operations.ts:38:24)
```
{% endcode %}

In this guide we are going to show you a technique that will let you unblock the user experience by executing the failing transaction using user's wallet funds (MATIC) to cover for the gas costs.

We are going to use `useFollow` hook in our example but bear in mind it works the same exact way for all these hooks as they implement the same interface:

* `useCollect`
* `useCreateComment`
* `useCreateEncryptedPost`
* `useCreateEncryptedComment`
* `useCreateMirror`
* `useCreatePost`
* `useFollow`
* `useUnfollow`
* `useUpdateDispatcherConfig`
* `useUpdateFollowPolicy`
* `useUpdateProfileDetails`
* `useUpdateProfileImage`

### In practice

We are going to compose the `useFollow` hook with the `useSelfFundedFallback` hook into a new React hook. This new hook will encapsulate how we intend to communicate and handle the rejection scenario.

{% code title="useFollowWithSelfFundedFallback.tsx" %}
```typescript
import { FollowOperation, Profile, ProfileOwnedByMe, SelfFundedOperation, supportsSelfFundedFallback, useFollow, useSelfFundedFallback } from '@lens-protocol/react-web';

type UseFollowWithSelfFundedFallbackArgs = {
  followee: Profile;
  follower: ProfileOwnedByMe;
}

type PossibleError = FollowOperation['error'] | SelfFundedOperation['error']

export function useFollowWithSelfFundedFallback({ followee, follower }: UseFollowWithSelfFundedFallbackArgs) {
  const [error, setError] = useState<PossibleError>(undefined);
  const gasless = useFollow({ followee, follower });

  const selfFunded = useSelfFundedFallback();
  
  const execute = async () => {
    // it won't ask to sign if can be performed via proxy-action
    const gaslessResult = await gasless.execute();

    // did the gasless request fail?
    if (gaslessResult.isFailure()) {
      
      // was it rejected? is there an fallback?
      if (supportsSelfFundedFallback(gaslessResult.error)) {

        // ask your confirmation before using their funds
        const shouldPayFor = window.confirm(
          'It was not possible to cover the gas costs at this time.\n\n' +
          'Do you wish to continue with your MATIC?'
        );

        if (shouldPayFor) {
          // initiate self-funded, will require signature
        	const selfFundedResult = await selfFunded.execute(gaslessResult.error.fallback);
          
          if (selfFundedResult.isFailure()) {
            setError(selfFundedResult.error)
          }
        }
        return;
      }
      
      // any other error from 
      setError(gaslessResult.error)
    }
  };
  
  return {
    execute,
    error,
    isPending: gaslessResult.isPending || selfFundedResult.isPending,
  }
}
```
{% endcode %}

#### What's happening?

* we defined the new React hook signature mimicking what `useFollow` does:
  * it accepts a `followee` and `follower` profiles
  * it returns an `execute` callback, an `error`, and an `isPending` flag
* inside the hook we defined an internal `error` state
* still inside the hook we run both `useFollow` and `useSelfFundedFallback`. We don't bother with destructuring the return values but we simply assign them to variables with meaningful names (i.e. `gasless`, `selfFunded`)
* in our new `execute` callback we do (in order):
  * execute the `gasless` follow
  * if it fails we use the `supportsSelfFundedFallback` helper to determine if the error is one that can be retried in a self-funded fashion
  * we ask the user via a `window.confirm` if the wish to continue. This is were you decide how to involve the user. Adapt this to your UI needs.
  * if so we execute the `selfFunded` follow passing the opaque `gaslessResult.error.fallback`. We handle possible `selfFundedResult` failures by updating the internal `error` state.
  * finally we handle any other errors by updating the internal `error` state
* the new `isPending` is a OR condition between `gasless` and `selfFunded` pending statuses

#### Replace `useFollow` with our new hook

Now we can take our `FollowButton` and replace `useFollow` with our newly create hook and ... job done!

{% code title="FollowButton.tsx" %}
```typescript
import { Profile, ProfileOwnedByMe  } from '@lens-protocol/react-web';

import { useFollowWithSelfFundedFallback } from './useFollowWithSelfFundedFallback';

type FollowButtonProps = {
  followee: Profile;
  follower: ProfileOwnedByMe;
}

export function FollowButton({ followee, follower }: FollowButtonProps) {
  const { execute: follow, error, isPending } = useFollowWithSelfFundedFallback({ followee, follower });
  
  return (
    <>
      <button disabled={!followee.followStatus.canFollow || isPending} onClick={follow}>
        Follow
      </button>
         
      {error && <small>{error.message}</small>}
    </>
  );
}
```
{% endcode %}

In the `FollowButton` above we used the most simplified example from the [Follow a profile](https://docs.lens.xyz/docs/follow-a-profile) guide. Refer to that guide for more comprehensive examples.
