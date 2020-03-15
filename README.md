# DeFi Smart Accounts Overview
DeFi Smart Accounts (DSA) are [contract accounts](https://medium.com/@markmuskardin/mastering-the-fundamentals-of-ethereum-for-new-blockchain-devs-part-iii-wallets-keys-and-4cd3175b535b) trustlessly owned by the users, designed to allow developers to build extensible products and business models on top of DeFi with maximum security and composability.

This guide provides a brief overview of the key entities involved in the system.

## Key Entities
There are 3 key entities to understand:

1. **Defi Accounts**, which are trustlessly owned by the users. Assets are stored here. DSAs can execute composed transactions across connectors.
2. **Connectors**, which are standardized modules that interact with the various protocols, and make the important actions accessible to smart accounts. 
3. **Permission Modules**, which users can use to set guardians, managers or automation bots to manage their DSA. Permissions can be modular down to connector levels. For example, users can allow the wallet provider to rebalance his assets to minimize interest payment or maximize yields, but nothing else. 


<img width="763" alt="Screenshot 2020-03-15 at 6 41 46 PM" src="https://user-images.githubusercontent.com/173707/76699907-d7f9aa80-66ec-11ea-8bb1-d7d508ef44e0.png">


## Connectors
Connectors can either be base connectors to protocols, higher level connectors with more specific use cases like optimized lending, or connectors to native liquidity pools. 

The last type of connector will allow developers to seamlessly access the short term liquidity pool, which enables any developer to help the users seamlessly port instant porting of positions across protocols, for instance for interest payment minimization or yield maximization. 

DeFi accounts can compose and execute any number of actions from connectors in a single web3 transaction. Using only web3 calls, frontend developers will be able to string together the available actions in the connectors to create innovative new transactions.
