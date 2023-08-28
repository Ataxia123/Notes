## Backend

### Requirements:
1. Implement a service that interacts with the MetaMask SDK.
2. Handle Ethereum transactions - making transactions, awaiting confirmations, etc.
3. Store and Retrieve user wallet information using Obsidian's data persistence methods (saving to files).

### Architecture:
1. Services: Create a `walletService` which will be responsible for interacting with the MetaMask SDK, handling Ethereum transactions and dealing with account management.
2. Data Storage: Use Obsidian's API functions for saving and loading user data to the local device. 