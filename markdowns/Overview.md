# Overview

## What is Non-Fungible Tokens (NFTs)?
Starting as colored coins on the Bitcoin Network in 2017, NFTs quickly grew in popularity with the viral project called CryptoKitties on the Ethereum Network. Since then, NFTs have continuously increased in popularity. However, NFTs gained momentum in March 2021, when Beeple sold his digital artwork for $69 million.
 
An NFT or a Non-fungible Token is a structured unit of data representing the properties of a unique entity, or it is the entity itself (if it is a digital asset, then all its properties might be contained in the NFT).
 
NFTs are used to represent real-world assets like arts & collectibles, identity, commoditization, etc.

## Challenges Of Existing NFT Marketplaces
NFT marketplaces are online platforms that bridge the gap between buyers and sellers. They function more like an exchange, with people minting and selling NFTs at a set price.
However, these markets face several significant challenges, including:

 - **They have entry barriers such as acquiring crypto to pay the gas fees (rate on-ramps for first-time users)**
- **Data Persistence**: -   They do not guarantee the security and privacy of the assets minted as NFTs.
- **Interoperability**: -   Most NFT marketplaces do not support cross-chain or cross-platform transactions.
- **Limited support for asset creation**: -   Most NFT markets focus only on art and collectible use-cases, thus limiting the growth of the assets.

### AssetMantle | How We Solve The Above Problems 

AssetMantle is a framework for NFT marketplaces that provides all the elements required to create individual marketplaces. It facilitates the creation (minting) of interoperable NFTs that flow between blockchains. Moreover, it also supports NFTs ranging from digital art collectibles to tokenized tickets.

With AssetMantle, One can easily create dedicated marketplaces for selections of products from specific sellers or groups of sellers. Consider it as Shopify for NFTs where instead of listing one's products on an 'Amazon for NFTs' (such as OpenSea), entrepreneurs and artists can create their Shopify-style stores for their specific NFT assets.

## Why Choose Asset Mantle ?

- **Division Of Responsibility** 
We have divided NFT functionality into two modules: 
	1. **NFT** - The NFT module is in charge of the mint, mutation, and burn logic.
	2. **NFT Wallet** - NFT wallet module is in charge of the ownership transfer operations. 

	Both modules are capable of operating independently on distinct chains.

* **Singular Representation/Instantiation**
The NFTs are addressed by the exact hash of the immutable properties across all chains, enforcing singular representation/instantiation of NFT across chains.

* **Singular Wallet Implementation**
The NFT wallet module implements the wallet and transfers logic that is agnostic to other custom logic of the NFTs, allowing for a singular wallet implementation for all the NFT types.

* **Flexibility In Implementation** 
The NFT module implements all the basic functional requirements of an NFT with no restrictions on the extension of the functionalities to account for more complex application logic, as long as the implementation satisfies the NFT interface.

* **Reduced Load On Interchain Protocol** 
The two modules comprising the NFT functionality do not need to communicate to sync the state at each transaction. They can function independently with only a few transactions requiring inter-chain operability (inter-chain send, burn transactions).


* **Commoditization** 
All the NFTs are represented with a class or classification, allowing for transactions to handle NFTs through classes instead of direct addresses, allowing the commoditization of the NFTs.

* **Trusted Minting, Mutation, Burn-Execution, And Interoperability With Private Chains** 
The minting, mutation, and burn logic is implemented natively on the issuing chain and is always handled by the same chain, rather than turning over the mutation logic to the recipient chain during an NFT transfer to a new chain. As a result, privately validated chains can exchange their NFTs with other chains while ensuring the trust of the execution environment and logic privacy (if required).

* **Native Implementation And Interoperability** 
The NFT module is implemented at the native chain application logic level instead of the Smart Contract level, leveraging the chain’s native interoperability protocols to transfer NFTs between chains instead of permissioned bridge Smart Contracts.


## Why Did AssetMantle Choose Cosmos Ecosystem?
### Strategically Ahead
* To be the pioneers in the inter-chain NFT space.
* The NFT market is currently untapped in the Cosmos ecosystem, and despite the rapid demand in the NFT space, there is no concrete Cosmos native marketplace.

### Economical Compared To Other Networks

* The Cosmos network's gas fees are incredibly cheap, and minting assets will be almost free of cost (as compared to Ethereum, which requires massive investment in minting the assets)
* Users not paying a high gas fee for each transaction results in skyrocketed adoption.


### Environment Friendly Approach
* The NFTs on AssetMantle can be referred to as Green NFTs because they consume very little energy. In contrast, Ethereum NFTs have faced an enormous backlash from the environment-conscious community for using more energy resulting in pollution.

* Many artists and celebrities have opted for PoS powered marketplaces over marketplaces on Ethereum due to the same fact. Moreover, ETH2.0 is very far from full implementation at the moment.

### Best in class User-Experience
* The AssetMantle allows for the integration of Web2.0 experience so that complications of Web3.0 can be abstracted away.
* AssetMantle allows user to create your own store-front using user-friendly drag-and-drop experience. 
