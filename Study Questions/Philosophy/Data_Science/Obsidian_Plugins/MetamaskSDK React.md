
# Use MetaMask SDK with React

You can import [MetaMask SDK](/wallet/concepts/sdk/) into your React dapp to enable your users to easily connect to the MetaMask browser extension and MetaMask Mobile. The SDK for React has the [same prerequisites](/wallet/#prerequisites) as for standard JavaScript.

## Steps[​](#steps "Direct link to Steps")

### 1. Install the SDK[​](#1-install-the-sdk "Direct link to 1. Install the SDK")

In your project directory, install the SDK using Yarn or npm:

```
yarn add @metamask/sdk
```

or

```
npm i @metamask/sdk
```

### 2. Import the SDK[​](#2-import-the-sdk "Direct link to 2. Import the SDK")

In your project script, add the following to import the SDK:

```
import { MetaMaskSDK } from '@metamask/sdk';
```

### 3. Instantiate the SDK[​](#3-instantiate-the-sdk "Direct link to 3. Instantiate the SDK")

Instantiate the SDK using any [options](/wallet/reference/sdk-js-options/):

```
const MMSDK = new MetaMaskSDK(options);const ethereum = MMSDK.getProvider(); // You can also access via window.ethereum
```

### 4. Use the SDK[​](#4-use-the-sdk "Direct link to 4. Use the SDK")

Use the SDK by calling any [provider API methods](/wallet/reference/provider-api/). Always call [`eth_requestAccounts`](/wallet/reference/rpc-api/#eth_requestaccounts) using [`ethereum.request()`](/wallet/reference/provider-api/#ethereumrequestargs) first, since it prompts the installation or connection popup to appear.

```
ethereum.request({ method: 'eth_requestAccounts', params: [] });
```
