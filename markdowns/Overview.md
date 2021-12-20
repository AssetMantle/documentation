# Why AssetMantle?

The mission of assetMantle is to build an infrastructure for NFT marketplaces where artists and collectors can exchange value. The NFT industry is witnessing immense adoption from all and sundry with the Cosmos ecosystem being one of the platforms leading adoption for different utilities. Based on available data, the NFT market is worth more than $7 billion with a projection for more expansion in the near future.
AssetMantle Advantages

- **Cost-efficient Minting** - It is cheaper and faster to mint NFTs on assetMantle due to the blockchain infrastructure it utilises— Tendermint Core. 

- **Green NFTs** - Minting NFTs on assetMantle uses less energy unlike marketplaces built around a PoW blockchain infrastructure. As PoS blockchain engines, including Tendermint, require less energy to process transactions, creators can mint “Green NFTs” using assetMantle.

- **Privacy Protection** - AssetMantle allows creators to protect their NFTs and their associated metadata through a privacy protection functionality. They can also revoke privacy settings for their assets at will. 

- **Customise/ Build/ Launch Own Store** - AssetMantle's main selling point— as a Shopify of NFTs is aimed at promoting aggregation, unlike most NFT marketplaces. Creators and developers alike will be able to build, customise and launch stores where they can brand their creations with a fully custom-made user interface, determine the percentage of royalties and control the structure of the NFTs to be minted.AssetMantle also allows for maintainers’ access to be assigned to multiple users, giving them the rights to customise a storefront or build it jointly.

- **Fractionalized Ownership** - AssetMantle supports fractional ownership of assets, whereby several parties have existing rights to a valuable NFT, analogous to shares of a public limited company. Ownership rights are calculated in percentage and can be sold among the parties involved. Royalties on secondary sales are also divided among the fractional owners of an NFT, this is done based on variable splits and to the extent of their ownership rights.

- **Commoditization** - The NFTs in the individual marketplaces on assetMantle are identified by class or classification. As such, transactions involving these NFTs are addressed by class rather than through their owners' direct addresses. This enables NFT commoditization.

- **Division of Responsibility** - The NFT functionality is divided into two modules: NFT and NFT wallet. The NFT module is in charge of the mint, mutation, and burn logic, whereas the NFT wallet module is in charge of the ownership transfer operations. Both modules are capable of operating independently on distinct chains.

- **Singular Representation/ Instantiation** - The NFTs are addressed by the same hash of the immutable properties, enforcing singular representation/instantiation of NFT across chains.

- **Singular Wallet Implementation** - The NFT wallet module implements the wallet and transfers logic that is agnostic to other custom logic of the NFTs, allowing for a singular wallet implementation for all the NFT types.

- **Implementation Flexibility** - The NFT module implements all the basic functional requirements of an NFT with no restrictions on the extension of the functionalities for more complex application logic, as long as the implementation satisfies the NFT interface.

- **Reduced Load on Interchain Protocol** - The two modules comprising the NFT functionality do not need to communicate with each other to sync the state at each transaction. They can function independently with only a few transactions requiring interchain operability (interchain send and burn transactions).