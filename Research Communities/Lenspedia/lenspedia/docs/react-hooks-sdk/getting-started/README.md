# Getting Started

{% hint style="info" %}
Have a look at our [troubleshooting](https://docs.lens.xyz/docs/troubleshooting) section which highlight some well know pain points that can happen during initial setup.
{% endhint %}

### Installation

Install `@lens-protocol/react-web` and [ethers](https://ethers.org/) dependency.

For this configuration of packages we recommend installing using either **yarn** or **pnpm**.

{% tabs %}
{% tab title="yarn" %}
```shell
yarn add @lens-protocol/react-web ethers@legacy-v5
```
{% endtab %}

{% tab title="pnpm" %}
```
pnpm add @lens-protocol/react-web ethers@legacy-v5
```
{% endtab %}

{% tab title="npm" %}
```
npm install @lens-protocol/react-web ethers@legacy-v5
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
If you are eager to test new coming features offered by the Lens SDK, install the pre-release version via the `next` tag.

yarnpnpmnpm

<pre class="language-shell"><code class="lang-shell"><strong>yarn add @lens-protocol/react-web@next
</strong></code></pre>

Bear in mind that the pre-releases are not stable for production use and there could be breaking changes between different pre-releases before they get promoted into a stable release version.
{% endhint %}

### Integrate with [wagmi](https://wagmi.sh/)

Although `@lens-protocol/react-web` only depends on [ethers](https://ethers.org/) (and React ofc), we created a companion package called `@lens-protocol/wagmi` which makes it easier to integrate it with the popular [wagmi](https://wagmi.sh/) library.

{% tabs %}
{% tab title="yarn" %}
```shell
yarn add wagmi viem @lens-protocol/wagmi
```
{% endtab %}

{% tab title="pnpm" %}
```shell
pnpm add wagmi viem @lens-protocol/wagmi
```
{% endtab %}

{% tab title="npm" %}
```shell
npm install wagmi viem @lens-protocol/wagmi
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
We currently support the versions:

`wagmi: ^1.0.0`

`viem: ^1.0.0`

The caret symbol (^) indicates that you can use a version of each package from 1.x.x but not with version 2.0.0 or higher.
{% endhint %}

Ensure you have Polygon in the wagmi chains configuration

{% code title="TypeScript" %}
```typescript
import { WagmiConfig, configureChains, createConfig } from 'wagmi';
import { polygon, polygonMumbai } from 'wagmi/chains';
import { InjectedConnector } from 'wagmi/connectors/injected';
import { publicProvider } from 'wagmi/providers/public';

const { publicClient, webSocketPublicClient } = configureChains(
  [polygonMumbai, polygon],
  [publicProvider()],
);

const config = createConfig({
  autoConnect: true,
  publicClient,
  webSocketPublicClient,
  connectors: [
    new InjectedConnector({
      options: {
        shimDisconnect: false, // see https://github.com/wagmi-dev/wagmi/issues/2511
      },
    }),
  ],
});
```
{% endcode %}

Refer to [wagmi](https://wagmi.sh/) docs to see how to set up custom chains, providers and work with their client.

{% hint style="info" %}
If your integration uses wagmi 0.x install `@lens-protocol/wagmi@1.1.1` instead.
{% endhint %}

### Create the `LensConfig`

{% code title="TypeScript" %}
```typescript
import { LensConfig, development } from '@lens-protocol/react-web';
import { bindings as wagmiBindings } from '@lens-protocol/wagmi';

const lensConfig: LensConfig = {
  bindings: wagmiBindings(),
  environment: development,
};
```
{% endcode %}

The environment variables comes in 2 flavours:

* `production` is the environment config variable to be used in the live instance of your application (real users, real profiles, real data).
* `development` is the environment config variable to be used when you develop and test your application (test users, test profiles, test data).

See our [react-native integration](https://docs.lens.xyz/docs/cyan-nails-turn-react-native-integration) guide.

### Wrap app with `LensProvider`

{% code title="TypeScript" %}
```typescript
import { LensProvider } from '@lens-protocol/react-web';
```
{% endcode %}

{% code title="JSX" %}
```jsx
<WagmiConfig config={config}>
  <LensProvider config={lensConfig}>
    <YourRoutes />
  </LensProvider>
</WagmiConfig>
```
{% endcode %}

It's not strictly necessary to have the `LensProvider` as a child of the `WagmiConfig`.

You are good to go!

{% hint style="info" %}
That's perfect! We have a fully fledged example app showcasing the integration with wagmi. Our example app has authentication built-in and it's using pretty much all Lens SDK hooks.

You can find it on GitHub: [https://github.com/lens-protocol/lens-sdk/tree/main/examples/web-wagmi](https://github.com/lens-protocol/lens-sdk/tree/main/examples/web-wagmi)
{% endhint %}

**WHAT’S NEXT**

* [Our example app on GitHub](https://github.com/lens-protocol/lens-sdk/tree/main/examples/web-wagmi)
* [Authentication](authentication-quickstart.md)
* [Troubleshooting](https://docs.lens.xyz/docs/troubleshooting)
* [React Native integration](react-native-integration.md)
