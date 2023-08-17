# Authentication Quickstart

## Authentication Quickstart

This tutorial walks you through the recommended way to build an authentication flow on Lens, leveraging the [Lens React Hooks SDK](https://docs.lens.xyz/docs/sdk-react-intro).

The Lens React Hooks SDK abstracts away the need to write a lot of lower level GraphQL boilerplate for API calls to Lens, making it much easier to build web and mobile apps on Lens.

It's worth noting that this tutorial only supports React and React Native. If you'd like to build with other frameworks or clients such as other JavaScript frameworks or native iOS, consider using the [Lens Client SDK](https://docs.lens.xyz/docs/client-sdk-reference), or the [Lens API](https://docs.lens.xyz/docs/introduction) directly.

#### Why authentication?

While reading data from the Lens API is as simple as sending a query, but in order to post updates to the network the user needs to be authenticated.

This includes any state change, like following, unfollowing, creating a post, and creating a mirror.

This is why authentication is important, and why we have created this guide for you to learn how to set up a simple authentication flow.

### Tutorial overview

In this tutorial you'll learn how to use Next.js, TypeScript, Lens Protocol, and the Lens SDK to build out a simple authentication flow.

The app we'll be building will have the following features:

1. When the app loads, it will prompt the user to sign in.
2. Once the user is signed in, we will display some information about their profile, and a button to sign out.
3. When the user signs out, the UI will update and the session will be removed, showing the user the sign in button again.

By the end of this tutorial you should be able to easily authenticate users in a Lens application with TypeScript and the Lens SDK.

#### Getting started

To get started, create a new Next.js application:



{% code title="Shell" %}
```sh
npx create-next-app lens-app

✔ Would you like to use TypeScript with this project? Yes
✔ Would you like to use ESLint with this project? Yes
✔ Would you like to use Tailwind CSS with this project?  Yes
✔ Would you like to use `src/` directory with this project? No
✔ Use App Router (recommended)? Yes
✔ Would you like to customize the default import alias? No
```
{% endcode %}

Next, change into the new directory:

{% code title="Shell" %}
```sh
cd lens-app
```
{% endcode %}

and then install the following dependencies:

{% code title="Shell" %}
```sh
npm install @lens-protocol/react-web @lens-protocol/wagmi wagmi viem
```
{% endcode %}

{% hint style="info" %}
#### Supported versions wagmi & viem

We currently support the versions:

`wagmi: ^1.0.0`

`viem: ^1.0.0`

The caret symbol (^) indicates that you can use a version of each package from 1.x.x but not with version 2.0.0 or higher.
{% endhint %}

### app/layout.tsx

Next, we want to configure our app to use the Lens SDK.

This is typically done at the entrypoint of the app, and only needs to be done once.

This is a decent amount of code, but once it's set up it makes using the SDK very easy in the rest of your app.

Update `app/layout.tsx` with the following code:

{% code title="TypeScript" %}
```tsx
"use client";
import "./globals.css";
import { polygonMumbai, polygon } from "wagmi/chains";
import { configureChains, createConfig, WagmiConfig } from "wagmi";
import { publicProvider } from "wagmi/providers/public";
import { InjectedConnector } from "wagmi/connectors/injected";
import { LensProvider, LensConfig, production } from "@lens-protocol/react-web";
import { bindings as wagmiBindings } from "@lens-protocol/wagmi";

const { publicClient, webSocketPublicClient } = configureChains(
  [polygonMumbai, polygon],
  [publicProvider()]
);

const config = createConfig({
  autoConnect: true,
  publicClient,
  webSocketPublicClient,
  connectors: [
    new InjectedConnector({
      options: {
        shimDisconnect: false,
      },
    }),
  ],
});

const lensConfig: LensConfig = {
  bindings: wagmiBindings(),
  environment: production,
};

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <WagmiConfig config={config}>
        <LensProvider config={lensConfig}>
          <body>{children}</body>
        </LensProvider>
      </WagmiConfig>
    </html>
  );
}
```
{% endcode %}

### app/page.tsx

Now that the app is successfully configured with the Lens SDK, let's create the authentication flow.

To do so, open `app/page.tsx` and add the following code:

{% code title="TypeScript" %}
```tsx
"use client";
import {
  useWalletLogin,
  useWalletLogout,
  useActiveProfile,
} from "@lens-protocol/react-web";
import { useAccount, useConnect, useDisconnect } from "wagmi";
import { InjectedConnector } from "wagmi/connectors/injected";

export default function Authentication() {
  const { execute: login, isPending: isLoginPending } = useWalletLogin();
  const { execute: logout } = useWalletLogout();
  const { data: wallet, loading } = useActiveProfile();
  const { isConnected } = useAccount();
  const { disconnectAsync } = useDisconnect();

  const { connectAsync } = useConnect({
    connector: new InjectedConnector(),
  });

  const onLoginClick = async () => {
    if (isConnected) {
      await disconnectAsync();
    }

    const { connector } = await connectAsync();

    if (connector instanceof InjectedConnector) {
      const walletClient = await connector.getWalletClient();

      await login({
        address: walletClient.account.address,
      });
    }
  };

  return (
    <div className="flex flex-col p-12 items-start">
      {loading && <p>Loading...</p>}
    
      {!wallet && !loading && (
        <button
          className="mt-2 px-6 py-1 bg-white text-black rounded"
          disabled={isLoginPending}
          onClick={onLoginClick}
        >
          Sign in
        </button>
      )}
      
      {wallet && !loading && (
        <div>
          <h3 className="text-3xl">{wallet.handle}</h3>
          <p>{wallet.bio}</p>
          <button
            onClick={logout}
            className="mt-2 px-6 py-1 bg-white text-black rounded"
          >
            Sign out
          </button>
        </div>
      )}
    </div>
  );
}
```
{% endcode %}

**What's happening?**

In this component, we are using 3 Lens Hooks:

`useWalletLogin` allows you to sign a user in by passing in an `address`.

`useWalletLogout` provides a simple way to sign a user out.

`useActiveProfile` allows you to easily get the profile details of a signed in user.

In the UI itself, there are three main views:

1. If the app is in a loading state, we show a loading indicator.
2. If there is no signed in user, we show the **Sign In** button
3. If the user is signed in, we show the **Sign Out** button.

#### Testing it out

To run the app, run the following command:

{% code title="Shell" %}
```sh
npm run dev
```
{% endcode %}

Now that you've authenticated a user, try creating a post. Check out [this guide](https://docs.lens.xyz/docs/create-first-post) to get you started.
