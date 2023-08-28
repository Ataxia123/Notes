Creating a simple integration of MetaMask into an Obsidian plugin involves leveraging MetaMask's provider API to connect to an Ethereum account from Obsidian. Before proceeding, ensure that you have a working knowledge of JavaScript/TypeScript, and that you have NodeJS installed on your machine. 

A base structure for this could look like this:

```javascript
import { Notice, Plugin } from 'obsidian';

declare module "global" {
    interface Window { ethereum: any; web3: any; }
}

export default class MetamaskPlugin extends Plugin {
    async onload() {
        if (window.ethereum) {
            window.web3 = new Web3(window.ethereum);
            try {
                // Request account access if needed
                await window.ethereum.enable();
                // Acccounts now exposed
                new Notice('Metamask is connected');
            } catch (error) {
                // User denied account access
                new Notice('Metamask connection was denied');
            }
        }
        // Legacy dapp browsers
        else if (window.web3) {
            window.web3 = new Web3(window.web3.currentProvider);
            // Acccounts always exposed
            new Notice('Metamask is connected');
        }
        // Non-dapp browsers
        else {
            console.log('Non-Ethereum browser detected. You should consider trying MetaMask!');
        }
    }

    onunload() {
        console.log('unloading plugin');
    }
}
```

Please note that Obsidian runs in Electron (which is a Chromium-based framework). MetaMask, on the other hand, is an extension, but it must be installed in the browser where it runs. Thus, while MetaMask can easily be included and used in typical web development scenarios, using MetaMask in an Electron app like Obsidian requires some workarounds and may not be possible without further support from the Obsidian developers.

As the proposed implementation is an MVP, implementing and handling the MetaMask functionalities such as sending transactions, showing account balances, etc., would require expanding this base structure. 

The Ethereum network interactions and the UI within Obsidian should be developed in ways that are consistent with the practices of Obsidian plugin development. Please look at [Obsidian Sample Plugin](https://github.com/obsidianmd/obsidian-sample-plugin) for a better understanding of the Obsidian plugin skeleton.