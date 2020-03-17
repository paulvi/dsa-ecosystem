# DeFi Smart Accounts Overview
DeFi Smart Accounts (DSA) are [contract accounts](https://medium.com/@markmuskardin/mastering-the-fundamentals-of-ethereum-for-new-blockchain-devs-part-iii-wallets-keys-and-4cd3175b535b) trustlessly owned by the users, designed to allow developers to build extensible products and business models on top of DeFi with maximum security and composability. This guide provides a brief overview of the key entities involved in the system. 

Coming:
- Integration options for frontends
- How DeFi devs can build for DSA users
- How protocols can make their systems accessible to DSA users and devs.

## Key Entities
There are 3 key entities to understand:

1. **Defi Accounts**, which are trustlessly owned by the users. Assets are stored here. DSAs can execute composed transactions across connectors.
2. **Connectors**, which are standardized modules that interact with the various protocols, and make the important actions accessible to smart accounts. 
3. **Permission Modules**, which users can use to set guardians, managers or automation bots to manage their DSA. Permissions can be modular down to connector levels. For example, users can allow the wallet provider to rebalance his assets to minimize interest payment or maximize yields, but nothing else. 

<img width="763" alt="Screenshot 2020-03-15 at 6 41 46 PM" src="https://user-images.githubusercontent.com/173707/76699907-d7f9aa80-66ec-11ea-8bb1-d7d508ef44e0.png">

Let us review each of these in more detail:

## DeFi Smart Accounts
DSAs are created by regular Ethereum accounts (or EOAs). Each Ethereum can create as many DeFi accounts as they want. DeFi accounts are fully trustless, so users can choose to withdraw their assets anytime to the owners.

(diagram for one EOA owning several accounts)

DeFi accounts can compose and execute any number of actions from connectors in a single web3 transaction. Using only web3 calls, frontend developers will be able to string together the available actions in the connectors to create innovative new transactions.

For example, to build the protocol bridge function, the DSA will string together functions across the compound, maker and liquidity bridge connectors. We call these “spells”, and we will be elaborating on them in more detail.

(Diagram for executing functions across connections)

To get started, the `build` function will be called, after which a DeFi smart account will be created belonging to the EOA. The developer can also help user build custom DSAs with one transaction, for example, create a DSA and deposit assets directly, or provide a 3rd party or bot with permissions to manage the assets for example.

(Diagram for build and buildwithcast)

## Connectors
DSAs are powerful because they can easily be extended with connectors. Every new connector that is added is immediately usable by any developer building on top of DSAs. Connectors can either be base connectors to protocols, auth connectors, higher level connectors with more specific use cases like optimized lending, or connectors to native liquidity pools. 

Let's review what these are, and then we will give an example of how they can be used to allow developers to build complex cross protocol transactions. 

### Types Of Connectors
Different types of connectors provide different set of capabilities towards DSAs. Each connector has a set of functions that can be executed by the DSA owner or managers (depending on permissions).

1. Protocol connectors: Access key protocol functions directly. 
2. Auth connectors: Update permissions of the smart accounts.
3. Use case specific connectors: Execute higher level use cases that cannot be done or expensive with stringing basic functions. 
4. Instant liquidity pools connectors<sup>*</sup>: Access the short term liquidity pool for features that require asset porting, or "flash loans" for example, porting debt positions, interest payment minimization or yield maximization. 

* Liquidity pools is free to use.

### Casting Spells
(give examples of casting)

### Adding New Connectors
(give examples of guidelines)

## Permission Modules 
(explain auth modules)
