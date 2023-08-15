# Lens Widgets

[Lens Widgets](https://github.com/lens-protocol/lens-widgets) enable developers to easily integrate social features into their web applications with just a few lines of code.

### Lens Widgets React

To view the library on GitHub click [here](https://github.com/lens-protocol/lens-widgets/).

* [Share to Lens](https://docs.lens.xyz/docs/lens-widgets#share-to-lens)
* [Follow on Lens](https://docs.lens.xyz/docs/lens-widgets#follow-on-lens)
* [Sign in With Lens](https://docs.lens.xyz/docs/lens-widgets#sign-in-with-lens)
* [Profile](https://docs.lens.xyz/docs/lens-widgets#profile)
* [Publication](https://docs.lens.xyz/docs/lens-widgets#publication)
* [Publications](https://docs.lens.xyz/docs/lens-widgets#publications)
* [ProfileListItem](https://docs.lens.xyz/docs/lens-widgets#profilelistitem)

#### Installation

{% code title="Shell" %}
```sh
npm install @lens-protocol/widgets-react
```
{% endcode %}

#### Share to Lens

{% code title="TypeScript" %}
```typescript
import {
  ShareToLens, Theme, Size
} from '@lens-protocol/widgets-react'

<ShareToLens
  content="Hello World!"
/>

/* Optional parameters */
url: string = "https://your-awesome-app.com"
hashtags: string = "web3,social,blockchain"
via: string =  "YourAwesomeApp"
title: string = "Share your post on Lens 🌿"
theme: Theme (default, dark, light, mint, green, peach, lavender, blonde)
size: Size (small, medium, large)
```
{% endcode %}

#### Follow on Lens

{% code title="TypeScript" %}
```typescript
import {
  FollowOnLens, Theme, Size
} from '@lens-protocol/widgets-react'

<FollowOnLens
  handle="stani"
/>

/* Optional parameters */
theme: Theme (default, dark, light, mint, green, peach, lavender, blonde)
size: Size (small, medium, large)
title: string = "Follow me on Lens"
```
{% endcode %}

#### Sign in with Lens

{% code title="TypeScript" %}
```typescript
import {
  SignInWithLens, Theme, Size
} from '@lens-protocol/widgets-react'

async function onSignIn(tokens, profile) {
  console.log('tokens: ', tokens)
  console.log('profile: ', profile)
}

<SignInWithLens
  onSignIn={onSignIn}
/>

/* Optional parameters */
provider: Provider
title: string
theme: Theme (default, dark, light, mint, green, peach, lavender, blonde)
size: Size (small, medium, large)
```
{% endcode %}

#### Profile

{% code title="TypeScript" %}
```typescript
import {
  Profile, Theme
} from '@lens-protocol/widgets-react'

<Profile
  handle="stani"
/>

/* Optional parameters */
handle: string
ethereumAddress: string
profileId: string
theme: Theme (default, dark)
onClick: () => void
containerStyle: css style
```
{% endcode %}

#### Publication

{% code title="TypeScript" %}
```typescript
import {
  Publication, Theme
} from '@lens-protocol/widgets-react'

<Publication
  publicationId="0x9afd-0x02e8"
  theme={Theme.dark}
/>

/* Optional parameters */
theme: Theme (default, dark)
```
{% endcode %}

#### Publications

{% code title="TypeScript" %}
```typescript
import {
  Publications, Theme
} from '@lens-protocol/widgets-react'

<Publications
  handle="nader"
  theme={Theme.dark}
/>

/* Optional parameters */
profileId: string
handle: string
theme: Theme (default, dark)
```
{% endcode %}

#### ProfileListItem

{% code title="TypeScript" %}
```typescript
import {
  ProfileListItem
} from '@lens-protocol/widgets-react'

<ProfileListItem
  handle="christina"
/>

/* Optional parameters */
profileId: string
handle: string
profile: Profile
theme: Theme (default, dark)
onClick: () => void
onFollowPress: () => void
isFollowing: boolean
containerStyle: {}
followButtonContainerStyle: {}
followButtonStyle: {}
```
{% endcode %}

#### With Next.js

If you are using Next.js `pages` directory please update your `next.config.js` with the following:

{% code title="JavaScript" %}
```javascript
transpilePackages: ['@lens-protocol'],
```
{% endcode %}

So the final configuration might look like this:

{% code title="JavaScript" %}
```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true,
  transpilePackages: ['@lens-protocol']
}
module.exports = nextConfig
```
{% endcode %}

Once this update is made, please re-run the server:

{% code title="Shell" %}
```shell
npm run dev
```
{% endcode %}

Another option when working with Next.js `pages` directory apps is using a Dynamic Import:

{% code title="TypeScript" %}
```typescript
/* Profile created in separate component */
import {
  Profile
} from '@lens-protocol/widgets-react'

export default function ProfileComponent() {
  return (
    <Profile handle='christina' />
  )
}

/* ProfileComponent imported using a dynamic import */
import dynamic from 'next/dynamic'
const ProfileComponent = dynamic(() => import('../components/ProfileComponent'), { ssr: false })

export default () => {
  return (
    <div>
      <ProfileComponent />
    </div>
  )
}
```
{% endcode %}
