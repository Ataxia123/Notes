---
description: Integrate Snapshot voting into your Lens app
---

# Snapshot integration

With version 1.2 of the Lens SDK we introduced an integration with [Snapshot](https://snapshot.org/) voting system. In this guide we will show you how to add, visualize, and vote for a Snapshot Proposal from your Lens app.

This guide will assume you have familiarity with Snapshot. Refer to their [documentation](https://docs.snapshot.org/introduction) for more details.

### Add Snapshot proposal to a publication

We will assume you know how to create a [Snapshot Proposal](https://docs.snapshot.org/user-guides/proposals/create). Just paste the Proposal URL into the `content` of a Post or Comment and publish it.

{% code title="Composer.tsx" %}
```typescript
import { ContentFocus, ProfileOwnedByMe, useCreatePost } from '@lens-protocol/react-web';
import { uploadJson } from './upload'

function Composer({ publisher }: { publisher: ProfileOwnedByMe }) {
  const { execute: create, error, isPending } = useCreatePost({ publisher, upload: uploadJson });

  const onSubmit = async (content: string) => {
    await create({
      content: `
      	Vote my proposal here:
		https://snapshot.org/#/aave.eth/proposal/0xb17b3294dcb08316cb623c717add7f82df54948d558992f886be59d0958e9b24
	  `,
      contentFocus: ContentFocus.TEXT,
      locale: 'en',
    });
  };
  // ...
}
```
{% endcode %}

See [create your first post](https://docs.lens.xyz/docs/create-first-post) guide for more details on how to create a post.

> #### 📘Demo Snapshot
>
> Use real Snapshot Proposal URLs when using Lens `production` environment and [https://demo.snapshot.org](https://demo.snapshot.org/) Proposals when using `development` or `sandbox` environments.

### Visualize Snapshot Proposal details

When rendering a `Publication` you can check if it contains a Snapshot Proposal and extract its details for rendering a Twitter-like polls UI:

{% code title="PublicationContent.tsx" %}
```typescript
import { isPollPublication, PollPublication, Publication, usePollDetails } from '@lens-protocol/react-web';

function Poll({ publication }: { publication: PollPublication }) {
  const { data, error, loading } = usePollDetails({ publication });
  
  if (loading) {
    return <p>Loading...</p>;
  }

  if (error) {
    return <p>{error.message}</p>;
  }

  return (
    <div>
      <h2>{data.title} ({data.isActive ? 'active' : 'closed'})</h2>

      <ul>
        {data.choices.map((choice, idx) => (
          <li key={idx}>
            {choice.label} ({choice.percentage.toPrecision(3)}%) - {choice.didVote ? '✅' : null}
          </li>
        ))}
      </ul>
    </div>
  );
}

export function PublicationContent({ publication }: { publication: Publication }) {
	if (isPollPublication(publication)) {
    return <Poll publication={

  // render other publications as usual
  return (
    
  );
}
```
{% endcode %}

#### What's happening?

* we use the `isPollPublication` to determine if the publication is of type `PollPublication` and render the publication with a dedicated `<Poll>` component. `PollPublication` is a special type of `Post | Comment` that contains opaque metadata used by the SDK to fetch data and, later on, vote on a given poll.
* we use the `usePollDetails` to fetch details about the Snapshot Proposal.

In the specific the `data` have the following details:

{% code title="" %}
```typescript
type SnapshotDetails = {  
    author: EthereumAddress;  
    choices: TwoAtLeastArray<PollChoice>;  
    eligibility: VoteEligibility; // CAN_VOTE | CANNOT_VOTE | UNKNOWN
    endAt: Date;  
    isActive: boolean;  
    isSingleChoice: boolean;  
    quorum: number;  
    snapshot: string | null;  
    space: SnapshotSpace;  
    startAt: Date;  
    system: SnapshotVotingSystem;
    title: string;  
    totalVotes: number;  
    url: Url;  
};
```
{% endcode %}

Each item in `choices` has the following shape:

{% code title="TypeScript" %}
```typescript
type PollChoice = {
  label: string;
  votes: number; // the total numbers of votes
  didVote: boolean; // a boolean representing if the logged-in wallet has voted or not
  percentage: number; // a decimal number between 0 and 100
};
```
{% endcode %}

The `error` could be of type `NotFoundError` indicating the given Snapshot Proposal no longer exist (or the URL was malformed and lead to a not existent proposal ID).

See Lens SDK [reference document](https://lens-protocol.github.io/lens-sdk/modules/\_lens\_protocol\_react\_web.html) for more details on these types.

### Vote a Snapshot Proposal

In the following we will focus on the `PollPublication` component from the previous example by changing the UI into a form and adding voting capability to it.

{% code title="Poll.tsx" %}
```typescript
import { PollPublication, Publication, usePollDetails, usePollVote } from '@lens-protocol/react-web';

function Poll({ publication }: { publication: PollPublication }) {
  const { data } = usePollDetails({ publication });
  const { execute, error, isPending } = usePollVote({ publication });
  
  // omitted loading and fetching error for brevity
  
  const onSubmit = async (event: React.FormEvent<HTMLFormElement>) => {
    event.preventDefault();

    const form = event.currentTarget;
    const formData = new FormData(form);

    const choice = parseInt((formData.get('choice') as string) ?? never());

    await execute(choice);
  };

  return (
    <form onSubmit={onSubmit}>
      <fieldset>
        <legend>{data.title} ({data.isActive ? 'active' : 'closed'})</legend>

        {data.choices.map((choice, idx) => (
          <label key={idx}>
            <input
              disabled={!poll.isActive}
              type={data.isSingleChoice ? 'radio' : 'checkbox'}
              defaultChecked={data.didVote}
              name="choice"
              value={idx}
            />
            &nbsp;{choice.label} ({choice.percentage.toPrecision(3)}%)
          </label>
        ))}

        <button disabled={!data.isActive || isPending} type="submit">
          Vote
        </button>

        {error && <pre>{error.message}</pre>}
      </fieldset>
    </form>
  );
}
```
{% endcode %}

#### What's happening?

* we wired a second React hook called `usePollVote` into the previous example UI
* we render the polls choices as mutually exclusive (radio buttons) or not (checkboxes) according to `data.isSingleChoice` flag.
* we use a `<form>` to let the user express their choice and submit it
* we vote by calling `execute` callback with the user's choice(s).
