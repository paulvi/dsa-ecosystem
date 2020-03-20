# DeFi Smart Accounts
DeFi Smart Accounts (DSA) are [contract accounts](https://medium.com/@markmuskardin/mastering-the-fundamentals-of-ethereum-for-new-blockchain-devs-part-iii-wallets-keys-and-4cd3175b535b) developed by [Instadapp](http://instadapp.io) and trustlessly owned by the users. 

## Developers
- Front end developers can build smart wallet capabilities on top of their existing products. As new connectors and permission modules are added, they can easily extend their DeFi capabilities and business model with no requirements for smart contract or security expertise.
- DeFi developers can create complex cross protocol transactions, for example  
Instadapp’s protocol bridge, leverage flash loans with web2 code. 
- Protocol developers can make their systems accessible all DSA users and devs by collaborating with us to build connectors.

For further context about motivation and likely use cases, read the accompanying [blog post](https://blog.instadapp.io/defi-smart-accounts/).


## Overview
There are 3 key types of entities: the DeFi smart accounts, connectors and permission modules. This guide provides a brief overview of the key entities involved in the system, with more comprehensive guides to come in time.


## Key Entities
There are 3 key entities in DSAs:

1. **Defi Accounts**, which are trustlessly owned by the users. Assets are stored here. DSAs can execute composed transactions across connectors.
2. **Connectors**, which are standardized modules that interact with the various protocols, and make the important actions accessible to smart accounts. 
3. **Permission Modules**, which users can use to set guardians, managers or automation bots to manage their DSA. Permissions can be modular down to connector levels. For example, users can allow the wallet provider to rebalance his assets to minimize interest payment or maximize yields, but nothing else. 

<img width="763" alt="Screenshot 2020-03-15 at 6 41 46 PM" src="https://user-images.githubusercontent.com/173707/76699907-d7f9aa80-66ec-11ea-8bb1-d7d508ef44e0.png">

Let us review each of these in more detail:

## DeFi Smart Accounts
DSAs are created by regular Ethereum accounts (or EOAs). Each Ethereum can create as many DeFi accounts as they want. DeFi accounts are **fully trustless**, so users can choose to withdraw their assets anytime to the owners.

DeFi accounts can compose and execute any number of actions from connectors in a single web3 transaction. Using only web3 calls, frontend developers will be able to string together the available actions in the connectors to create innovative new transactions.

For example, to build the protocol bridge function, the DSA will string together functions across the compound, maker and liquidity bridge connectors. We call these “spells”, and we will be elaborating on them in more detail.

(Diagram for executing functions across connections)

To get started, the `build` function will be called, after which a DeFi smart account will be created belonging to the EOA. The developer can also help user build custom DSAs with one transaction, for example, create a DSA and deposit assets directly, or provide a 3rd party or bot with permissions to manage the assets for example.

## Connectors
DSAs are powerful because they can easily be extended with connectors. Every new connector that is added is immediately usable by any developer building on top of DSAs. Connectors can either be base connectors to protocols, auth connectors, higher level connectors with more specific use cases like optimized lending, or connectors to native liquidity pools. 

Let's review what these are, and then we will give an example of how they can be used to allow developers to build complex cross protocol transactions. 

### Types Of Connectors
Different types of connectors provide different set of capabilities towards DSAs. Each connector has a set of functions that can be executed by the DSA owner or managers (depending on permissions).

1. Protocol connectors: Access key protocol functions directly. 
2. Auth connectors: Update permissions of the smart accounts.
3. Use case specific connectors: Execute higher level use cases that cannot be done or expensive with stringing basic functions. 
4. Instapool connectors<sup>*</sup>: Access the native short term liquidity pool for features that require asset porting, or "flash loans" for example, porting debt positions, interest payment minimization or yield maximization. 

<sup>*</sup> Liquidity pools is not launched at the moment. It will be free to use.

### Casting Spells
For example, to build the protocol bridge to migrate debt from Maker To Compound, the DSA will `cast` the following `spell`, which denotes a sequence of connector functions that achieve a given use case.

1. Instapool: Access liquidity
2. Maker: Payback DAI 
3. Maker: Withdraw ETH 
4. Compound: deposit ETH 
5. Compound: borrow DAI 
6. Instapool: Return liquidity

Spells can be called from web2 code (or just the chrome console). They can also be called by someone who has the right permissions delegated to them by the main account. 

## Permission Modules

- types of permission modules
- examples of casting permission (and what it enables)


## Coming Up
- Getting started guide
- Security considerations
- Connector docs
- Permission module docs
- More spell examples
