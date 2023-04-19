# Flows 

---

 ## Conceptual Understanding - Shortform
**What is a Blockchain? What are the various kinds of Blockchain?** 
A blockchain is a distributed database that maintains a continuously growing list of transactions, ordered in intervals called blocks. These blocks are linked using cryptography technology. Each block contains a cryptographic hash of the previous block, a timestamp, and transaction data. A blockchain is a digital ledger of transactions that is duplicated and distributed across the entire network of computer systems on the blockchain. Each block in the chain contains a number of transactions, and every time a new transaction occurs on the blockchain, a record of that transaction is added to every participant's ledger. The decentralized database managed by multiple participants is known as a distributed ledger. The validation of new blocks on a blockchain is done through a consensus mechanism such as Proof-of-Work (PoW), Proof-of-Stake (PoS) & Delegated-Proof-of-Stake (dPoS). Bitcoin, Ethereum, and Cosmos-based AssetMantle are examples of cryptocurrencies that use blockchain consensus technology. There are Layer 1 (Bitcoin), Layer-2 (Polygon) and Layer-3 (Cosmos, AssetMantle) blockchains harboring their respective traits.  

**What are DIDs - Decentralized Identities on MantlePlace?** 
* Interchain Identifiers (IIDs) are a family of Decentralized Identifier methods which are purpose-designed to identify, refer to, and interact with digital assets within blockchain namespaces. 
* The IID specification builds on the Decentralized Identifier (DID) Core specification from the World Wide Web Consortium (W3C) . IIDs are fully conformant DIDs and therefore are DIDs. IID Documents are DID documents. Unlike DIDs, IIDs only reference on-chain assets—which we will refer to as tokens—but should be taken as any type of tokens, such as NFTs, fungible tokens, tokenized namespace records, or other on-chain assets.
***did:cosmos is an IID method designed to refer to Cosmos-compatible on-chain assets.***
 ![](https://i.imgur.com/TCGRFWY.png)

* Restricted to on-chain assets, IIDs are a new class of identifier uniquely suited to the requirements of fungible tokens, non-fungible tokens, and other chain-native components. IID methods can be developed for any compatible blockchain, making them suitable for interoperable representations of assets (and the cryptography that secures those tokens) regardless of the underlying chain. 
* This particular specification, did:cosmos applies the IID approach to assets on blockchains made with the Cosmos SDK. IIDs also introduce a few new features—conformant extensions to the DID Core specification—that provide for privacy-respecting options for the full range of expected token functionality, including Linked Resources, On-chain Service Endpoints, and Accorded Rights. We describe those here, capturing their definition at the time this specification was developed. See the IID specification for current normative definitions. 
* DID Methods which conform to the IID specification resolve to a DID document representing how to securely interact with a uniquely identified digital asset, within a unique blockchain namespace. Because IIDs are DIDs, software applications that are conformant with the W3C specification will be able to inter-operate with IIDs and IID documents, although some IID-specific features may require additional tooling. 
* did:cosmos DIDs are IIDs intended identify assets on Cosmos application chains.

***What standard does MantlePlace use for NFTs, how is MantlePlace different than the other NFT Marketplaces?***
* AssetMantle is different from the NFT (Non-Fungible-Token) standards that dictate the platform operations such as Cosmos ecosystem-based ICS 721 or CW 721 or Ethereum-based ERC 721 or ERC 1155 & other less-mainstream NFT ERC formats. AssetMantle uses the interNFT standard coupled with DIDs to regulate platform operations on MantlePlace. 
* CW721 and ERC721 are NFT standards that have been implemented with smart contracts in mind and not interchain module-based implementation for NFTs or NFTs that can interact with applications on the other chains. CW721 and ERC721 are more focused on the use-cases that can interact with other smart contracts and not chain level applications. 
* MantlePlace is a multi-tenant interNFT standard & Decentralized Identities-based NFT marketplace framework that enables creators and collectors to securely mint, own, and trade digital assets on its fast finality blockchain. The interchain foundation ICF commissioned the research & development of the interNFT standard – ICF did this to implement an NFT standard that would essentially define the majority use-cases in Cosmos and make it interoperable with other app-chains in the Cosmsos-hub.  
* The exact reason to adopt DIDs (coupled with interNFTs) was that the metadata associated with the NFTs could be variable and that the size of this metadata could be quite big. In some cases, the size could be bigger than what a block could accommodate in a NFT mint transaction or an IBC transfer transaction. The volume of metadata could not be accommodated in the following in some cases. The metadata is implemented as a DID document while the ownership of the metadata is represented as a DID itself (DID identifier string). The metadata sits on the native chain itself. Since the ownership token is as simple as CosmosSDK coin for reference, the current implementation of IBC can be used to transfer the NFT ownership tokens without any changes in the IBC implementation. Any chain that supports CosmosSDK coins and have IBC enabled can transfer the NFT ownership via DIDs. DID (denom) points towards both NFT Asset (DID Object - image, audio, video, gif) and Metadata document (DID-subject - properties & their values). Through DID pointers referencing to form an Ownership token across chains: the metadata document (DID Subject) defines the NFT Asset (DID Object) that are amalgamated into an Ownership document/token via the DID (denom) pointer.

***Assuming InterNFT was operationally on one chain, can it communicate with a chain that has partially implemented ICS721?***
Irrespective of any chain that communicates with ICS721, the interNFT specs are that we would be utilizing the bank module itself to issue the ownership tokens with denoms as DID and amount as the smallest deck if it is non splitable NFT and a decimal if it is splitable NFT. Any chain with a bank module should be able to receive this NFT. With ICS721 the NFTs would indirectly be interoperable with InterNFTs. ICS721 spec says that an IBC transfer of an NFT would transfer the metadata as well to the other chain. The transferring of the metadata to the other chain may not be the best idea as it could be an attack vector where chains can spin up and transfer over a large amount of metadata and increase the state size, reducing query and transaction speed. 

***Is there a reason/use case where someone will use InterNFT over ICS721?*** 
* There are 6-7 ERC (ERC1155, ERC-223, ERC-827, ERC777 etc.) standards but we all stick to 721 because it is the most used standard. ICS721 spec says that an IBC transfer of an NFT would transfer the metadata as well to the other chain. There could be confusion over ICS721 implementation NFT and interNFT implementation of NFT. Someone can act maliciously to exploit it or accidentally have two representations of the same NFT. 
* At a core level, ICS721 wallet will look very different from interNFT wallet. ICS721 NFT will require a more specialized wallet. So, there is enough differentiation in the UX/UI for people to differentiate. One of the main aims of the interNFT working group spearheaded by AssetMantle and commissioned by Inter-Chain Foundation ICF is to implement a standard to incorporate the majority of the use-cases that projects are building NFTs around into one standard that we all can use. It can go onto the standardization track to contribute back to ICS721 and/or CosmosSDK. There are some use-cases that cannot be solved with the current implementation of ICS721. Some use-cases like IXO’s impact bound use-case, comdex’s shipfi, carbon credit use-cases, and some AssetMantle use-cases etc... cannot be solved with current existing implementations of NFT. Hence new standards will emerge to be adopted, standardized and solves use-cases currently unfathomable. 

***What is NFT Asset (Image) and its related Metadata?***
* NFT metadata refers to the additional information that is stored on the blockchain alongside the unique identifier of a non-fungible token (NFT). The metadata of an NFT document can include a variety of information about the asset, such as the artist's name, the title of the work, a description of the asset, and the date it was created. Other information that can be included in the metadata of an NFT might be the digital file type, the resolution, the dimensions, layers/property of the art and any other relevant technical details.  
* According to the interNFT standard-based NFT Collection schema provisions on MantlePlace ; for metadata - there are allotment for 22 total properties of which #1(Image Name), #2(Image Description), #3(fileHash) and #4 (Classification ID) are initialized during the NFT (schema) Collection creation process. Metadata-properties #1 and #2 are part of the Basic Information NFT schema-editable when creating an NFT & Property #4 and 5# are part of the Advanced Information NFT schema (not editable). Similarly, 18 additional Metadata-properties (type: Boolean, String, Number) can be added, which can then be initialized when creating NFT’s within the respective collection with respect to the defined NFT Collection schema. 
* An NFT can have many elements or layers with various property types & values within it, for example in a BAYC NFT there are Apes with accessories, Chains (shiny black) being one of the many accessories (layer with a metadata) of the Collection NFT schema. There can be more than one trait/layer/metadata in the form of accessories, background, entities etc... for a single NFT such as Red-background, Guns, Cap, Cigarette, Chain, Sun, Pets & side-kick and other layers serving as a Layer of metadata (with property-type & property-value) to be initialized which will demarcate NFTs within a Collection. And for NFT Collections that don't have a plethora of layer-based metadata, you can define the NFT Collection schema with the standard (4) basic & advanced properties which will serve as the metadata-base. 
* Overall, NFT metadata plays a crucial role in verifying the authenticity and uniqueness of an NFT, and it can provide important information about the asset's provenance, ownership, and technical details. You should ideally add complete information about each of your NFTs to tell collectors more about the individual assets and to facilitate future utility. 
 
*Metadata or Properties can also be made to have a default value such as, if its Boolean type it can always be true or false, if it is an integer and it is of a rare category it can always say 1 or if it is a string with color red, it can be set red for all future NFT creations by default. Metadata (property-type-name & it's value) can also be made to be hidden from consumer view and can also be set to mutable which will entail that the particular metadata is subject to change-based evolution in the future timelines.*

**Bond Amount (Fees):**
![](https://i.imgur.com/9vQIuex.png)

* Bonding fees, also called Bond Amount is the inherent value of an NFT, measured intrinsically by the metadata contained within the asset.  Burning of the NFT document i.e., to send the NFT (asset) to an empty/non-existent address will ‘burn’ the NFT and return the inherent bond-amount to the creator/owner. 
* Metadata within an NFT document (Asset) is the number of layers which holds a property-name and property value attached to it. There are 3 types of properties within metadata structure, namely;  
A. String - occupies 256 bytes 
B. Boolean - occupies 1 byte 
C. Integer - occupies 4 bytes
* An NFT document schema on MantlePlace can have 22 properties initialized within them. First 2 are basic (predefined & mutable) property - name of the asset(string) and Description of the asset (string), Next 2 are Advanced (predefined & immutable properties resolved by the protocol) which are fileHash and ClassificationID. AssetMantle’s MantlePlace Assets can have a maximum of 22 properties including the 4 previously mentioned properties defined while creating an NFT document. The rest of the 16 property additions are optional whose types are extended to String, Boolean & Integer, additionally these properties can be made to have default values, mutable and hidden from user-view. 

*For example, if an NFT document Y has 7 total properties, 4 of which are (Basic & Advanced) pre-defined and 3 are further initializedd acoording to their type String (1), String (2) and Integer (3). As you have observed above string takes up a lot more space than Integers or Boolean, burning this particular NFT document Y will return the bond-amount that is proportional to the property type & value attached to the many metadata inherently baked into it.*

***Modalities of uploading NFT Assets & Metadata***  
 ![](https://i.imgur.com/paMiWxq.png)

**A. MantlePlace Frontend (NFT Asset &) Metadata Upload:**  
Frontend NFT assets upload and initializing NFT assets with metadata requires no structuring and done with a sense of ease, the template for initializing metadata into NFT assets to make it into a complete NFT is facilitated via the Create Collection NFT Schema. Once you create a collection and have added the NFT assets, you can click on various NFT assets within a said collection and initialize their metadata one-by-one while inputting the value for property-types according to NFT Collection schema. Frontend uploads are recommended for NFT Collection with less than 100 NFT assets. For more than > 100 assets MantlePlace backend upload via Assetmantle team is recommended or via the structured-upload through web3.storage or nft.storage. 
 ![](https://i.imgur.com/w4JCf7G.png)


**B. Backend (NFT Asset &) Metadata upload structure:** 
* Image Asset source-link & its filename (required): This tells us which NFT asset you're referring to values should be the name of the file for the NFT image and Json file (metadata) in an accurate order 

***Structure the collection for metadata upload alongside the image assets in the following manner:*** 
* Make a project folder and within it make two sub-folders with one being Image (assets) and the JSON file containing the metadata of the image asset. Arrange the Asset file and JSON File in an accurate & parallel-sequential format - the Image asset and JSON file (metadata) relating to each other 
*For example, if the collection has 7 properties, in excess to the 4 (Basic & Advanced), make 3 columns, heading of the Column containing the Property-number, Property-name and Property-type with the image-file link/name in the row section. For each image-file input the property values of...*
* #1 property-name & its value (Basic Metadata-property) 
* #2 property-description & its value (Basic Metadata-property) 
* #5 property-Name-type& its value (Addon Metadata-property) 
* #6 property-Name-type & its value (Addon Metadata-property) 
* #7 property-Name-type & its value (Addon Metadata-property)

***Structuring metadata for backend upload:***
* AssetMantle recommends metadata submission via .csv file (synthesized by an Excel sheet). For structure, refer image below. First, Input Trait Category & their Metadata-property-type. Next, input the additional properties of the various NFTs in addition to the .......... 
* ADD #1NAME, #2DESCRIPTION (BASIC 2 PROPERTIES)  
* CAN LEAVE THE #3FILEHASH & #4CLASSIFICATIONID (ADVANCED 2 PROPERTIES) 
* As defined during the NFT Schema – Make as many Columns for the pre-defined meta data property-name and input their respective values (string/Boolean/number). Property #3(fileHash) & #4(ClassificationID) will be churned automatically by the algorithm, creators do not have to input it either on the front/backend 
* On MantlePlace’ interNFT standard creators have the freedom of instantiating 18 novel properties (optional) in addition to the 4 properties (Basic & Advanced) pre-defined while the Collection was created.  
* Fill in all the NFT asset links and initialize them with property values according to Collection’s defined NFT schema, post which you can extract the sheet into a .csv file and send it to the AssetMantle team alongside the image files. Within 24 hours you can see your full Collection with its metadata ingrained into the image mobilized and ready for sales-listing. 
 
***Self-Upload via Shared Storage Mechanisms***
* Once the NFT assets and metadata files are ready, the next step is to upload the same via a storage mechanism given that you have a big NFT Collection and you are not going with MantlePlace front-end or backend-based upload. It is recommended to use a decentralized storage solution such as IPFS as a modality to upload NFT assets in a distributed format. Highlighting the pathways of uploading NFT assets and their metadata to IPFS; via 1. NFT.Storage (with UI and script) and 2. Web3.Storage (with UI and script). 3. Pinata & NFT.UP Upload coming soon... 
* For NFT collections with a large number of assets, using a script is ideal via the following mechanisms or can send the sequenced images (image-file) & .csv file (containing ordered metadata) to the AssetMantle team who will do the upload from the backend. 

**Reserved Properties:** The following properties are reserved at the protocol level so creators are requested to avoid using the following properties as the metadata-property(traits) while naming property-name to avoid conflict of interest. [Deep Dive Into Filer Structuring Here](https://docs.assetmantle.one/Assets_and_Metadata_File_Structuring/)
* Authentication
* Burn
* Expiry
* ExchangeRate
* Lock
* MaintainedProperties
* MakerOwnableSplit
* NubID
* Permissions
* Supply
* MakerID

**1. NFT.Storage** 
NFT.Storage is a service that lets you upload off-chain NFT data for free with & without a script, with the goal to store all non-fungible tokens as a public good. The user's uploaded content will be permanently stored in IPFS aka Filecoin’s decentralized storage network and made available over IPFS via its unique content ID so it can easily persist across different versions of THE website or mobile application (if any). Creators are able to upload a virtually unlimited amount of NFT assets & its metadata. However, there currently exists a limit of 31 GB per individual upload. There are namely 2 modes of operations entailed below; 
**A. Using [[NFT.Storage UI]](https://docs.assetmantle.one/Uploading_NFT_Collection_Using_NFT_Storage_%28Without_Script%29/)**
**B. Using [[NFT.Storage via Scripts]](https://docs.assetmantle.one/Uploading_NFT_Collection_Using_NFT_Storage_%28With_Script%29/)**
 
**2. Web3.Storage** 
Web3.Storage provides a simple way (with a script) for developers to integrate IPFS aka Filecoin's decentralized storage system into their apps and websites without having any technical knowledge of how it all works. Just upload the content once using the platform’s client libraries, then pin it on different nodes around the world! The data is protected by 3 redundant copies that can be cryptographically verified. There are namely 2 modes of operations entailed below; 
A. Using [Web3.Storage UI](https://docs.assetmantle.one/Uploading_Web3_Collection_Using_NFT_Storage_%28Without_Script%29/) 
B. Using [Web3.Storage Script](https://docs.assetmantle.one/Uploading_Web3_Collection_Using_NFT_Storage_%28With_Script%29/) 
 
**Deployment & Decentralizing the Metadata, what does it mean?**
![](https://i.imgur.com/lXRRcU5.png)

* The majority of the services you use today keep their data on servers managed by third-party corporations like Amazon, Google, or Microsoft. In actual use, it performs flawlessly. They rarely experience outages and have been around long enough to alleviate any concerns about their potential disappearance tomorrow along with your data. 
* What would occur if, for example, one of these mega-cloud-based enterprises failed tomorrow? Who would maintain their servers? Where does your info go? Or, to put it another way, what would happen if the individual whose NFT Collection I purchased ceased paying their monthly storage fees to one of these organizations or altered or erased the data? 
* For NFTs and Web3 in general, we prefer to explore more deeply due to NFT assets and their metadata, which contain vital info about an NFT and its programmability and must be held on-chain. We desire for the metadata to be stored as securely and in a decentralised manner as feasible, and to be immutable; hence, on-mantleChain. 
* Decentralizing your metadata by putting it on-chain via NFT creation: If you decentralize your NFT asset, you will no longer be able to change it. You will only be able to look at it and trade it with previously inputted property-values(metadata) according to NFT Schema that is now immortalized unless subjected to unioque metadata mutations. This is where progressive decentralization of metadata comes in. Metadata that is stored across multiple endpoints is permanent and can't be changed or taken down, even by the person who put it there in the first place. We can't take it down or change it, and it's currently stored in different end-points that have nothing to do with each other. This kind of behavior makes metadata pertaining to NFTs less risky for the other party to manage and trade with.  
* Put your collection out there; It's time to send your NFTs on-chain with all of the information you've initialized up to this point, which will be used to get your Collection ready to be minted. Create Public or Private Sale (Whitelist) and list your Collection live. To make your collection live on MantlePlace via listing it in a Private or a Public sale your Collection would have to be vetted & verified by the AssetMantle team to be given backend approval to list the same. 
* FYI, up until this point in building your Collection I.e., adding images to your collection, the image-metadata (property-values) for your Collection (Frontend / backend-via-team / web3-share-storage) has been stored on Amazon servers owned by AssetMantle and the associated metadata on-chain (mantleChain).  After NFT deployment as Private or Public sale, most of your information about your Collection (metadata properties) will no longer be able to be changed unless it is programmed to evolve (mutable metadata) via Collections NFT schema. Changes to details such as the price of NFT in a Listed Private / Public Sale in your collection cannot be edited until the sale has expired since it is on-chain, post which a new Sale with revamped prices with the leftover NFTs from expired sales and newly added-NFTs to the Collections randomized general-pool can be re-listed. 



---

## Creator Flow Turorials:
![](https://i.imgur.com/ppGelT2.png)

**1. Creating a Unique MantlePlace Account (Decentralized Identity - DID)**

**A. SIGN UP**
[CLICK HERE FOR A VIDEO GUIDE... ](https://youtu.be/gPOxuqSedpo)
* Click on Sign Up on the top-right corner 
* Provide a unique MantlePlace username as your decentralized identity (DID) which you will be used as for Loggin-in 
**B. SIGN IN**
[CLICK HERE FOR A VIDEO GUIDE](https://youtu.be/fxY4ISt0kpw)
* Notedown the provided MantlePlace wallet-address (& the 4-part seed/recovery phrases) tied to the MantlePlace decentralized identity aka username - write it down physically 
* Confirm the MantlePlace address, Input & Confirm a viable password, Verify by inputting the seed/recovery phrase to conclude the account creation process 
* Post account creation – you can now begin collating your Collections & Creating NFTs, to do so - SignIn with the unique username and password & head on over to Create 

**2. Creating Your Collections via Creator Interface** 
The MantlePlace Creator Dashboard is designed to provide Creators with the most seamless, simple, efficient and code-free experience possible. In this tutorial, we will walk through the procedures necessary to create an end-to-end NFT collection using the MantlePlace, from artwork creation to minting to management and everything in between! 

[CLICK HERE FOR A VIDEO GUIDE...](https://youtu.be/LoqxXMV9zew)

***What do I need to launch my own collection?***
* NFT assets (Image, Video, Gif, Audio), & their properties (metadata-layers) to generate your NFT 
* 5-10 minutes of your time - that’s how long it should take to launch your collection if you have all the collection information ready to go, given it is not a gigantic collection – if so, we recommend a structured backend MantlePlace upload 

***How to create an NFT Collection (define its NFT Schema)?***
* Sign in to MantlePlace  
* Click on Create on the MantlePlace sub-section  
* Select Create New Collection from the drop-down menu  
* Create NFT Schema: Input the Collection Name, Collection Description (more than 3 characters capped with a limit of 256 characters), Signify the NSFW status of collection via a checkbox. Add the ancillary information such as project website, Twitter and Instagram handle. 
* Internalize & Sign the Terms & Conditions and the MoU post analysis
* Upload the Profile Picture & Cover Image for the Collection
* Calibrate the NFT Schema of the Collection, instantiate the properties (metadata-layers) of the collection, given that 4 of the properties are pre-set as Basic & Advanced Properties; 
    * 1.Name-of-collection (Basic Information Schema) 
    * 2.Description-of-collection (Basic Information Schema) 
    * 3.fileHash-of-collection (Advanced Information Schema) 
    * 4.classificationId-of-collection (Advances Information Schema) 
* Basic Information Schema based properties are subject to edits only when creating the NFT Asset (not post creating or minting an NFT) and the Advanced Information Schema is not editable whilst Collection creation or after)  
* Input & Define the additional properties of the NFT Schema within the collection by defining a Property Name & Type (String, Number, Bool). Similarly, by leveraging the Advanced Details drop-down you can alter the nature of NFT (metadata) mutability, hide the property-name & values or set the default value for a property. 

*If you have more than 4 properties (metadata-layers) including the Basic & Advanced Properties in your NFT collection, Add more by using the Add More option and following the previously mentioned step for instantiation*

* NFT Collection with the defined NFT schema for creating individual NFTs is now created successfully: A Collection-link is presented – that can be propagated within the community and across the ecosystem 


**3. Creator Dashboard**
After successfully entering MantlePlace, navigate to NFT Wallet using the User Symbol in the top-right area. The Creator dashboard gives you a high-level view of your purchased collections, generated collections, Whitelists, and NFT Wishlist. Provides comprehensive information on the overall number of NFTs acquired and the total number of collections within which created NFTs that can be listed for Public or Private (whitelist) sale. 
 
**Collected NFTs:**
Can calculate NFT data for prior purchases made through Private or Secondary Sales. You may evaluate the NFT artworks of that collection by clicking on various Collection-Names on their thumbnails, which are also mobilized for secondary sales on MantlePlace with the press of a button from within. 
 
**Created NFTs:** 
You can view the Collection you generated here, and the NFT statistics are displayed on the Collection-thumbnail. Similarly, clicking on the Thumbnail displays the Total-created-NFT under the corresponding collection metrics and allows creators to Add more NFT assets to the Collection. Finally, it enables authors to generate a complete NFT from added assets by initializing it with Metadata (property-values) in accordance with the Collections (pre-defined) NFT Schema. 
 
**Whitelists:**  
A Whitelist is a list of approved addresses or accounts that are permitted to access certain resources or participate in certain activities. Exclusive audience & loyal buyers who want to get their hands on NFTs before the public sale are prime contenders for Whitelist invitation. This sub-section allows for the creation of new Whitelists as well as the evaluation of already produced Whitelist & their metrics such as member (wallet-addresses) and timelines. Created-Whitelists may also be modified and shared using a Whitelist link. 
 
**Wishlist(ed) NFTs:** 
Users may measure their favorite wishlisted NFTs they would have hearted while window-shopping on the MantlePlace in this sub-section. By clicking on a certain project's thumbnail inside the Wishlist area, all of the hearted (wishlisted) NFTs from that collection will be shown. 


**4. Building Your Collection**
[CLICK HERE FOR A VIDEO GUIDE...](https://youtu.be/LoqxXMV9zew)

**A. Creating NFTs within (a created) Collection?**

* Select on Create and choose Create New NFT from the drop-down or Select NFT Wallet on the top-righthand corner, access Created collections ulteriorly  
* Select the relevant Collection to populate NFT assets  
* Select Create a New NFT 
* Select one or multiple NFT assets from the local-drive 
* For each of the uploaded NFT asset, select edit: 
* Enter NFT-name and Description (These are #1 and #2 metadata-property of the NFT) NFT Name can be a short identifier of the Image and NFT Description can be a short summary of the nature of the contents of the image with respect to the larger Collection 
 
*Piece of Advice: If you have a large collection of NFTs, say more than 100 pieces, MantlePlace team can upload the NFTs from the back-end, provided that relevant NFT assets, NFT Assets Name, Description and their Metadata Properties according to Collection NFT schema has been provided via a .csv file from an excel sheet.*

* Select Add Tags (Up to 5) for unique identification TAGS of the NFT images 
* Initialize the Property-values according to the Property Type – Name-of-NFT (#1), Description-of-NFT (#2), Add the required tags for demarcation, initialize metadata-values of the additional properties (5-22) of the NFT assets based on the schema-metrics defined while Creating New NFT Collection 
 
***NFT Collection Schema & Metadata***
While defining an NFT Collection schema (Create NFT Collection): you have chosen and defined 3 properties in excess of 4 default basic (2) & advanced properties (2). Initialize values for additional metadata-layers: input values (Boolean, Number, String) to the property/properties according to previously defined NFT Collection Schema. Property calibration is facilitated according to the property structure defined during the Create Collection phase, the metadata-structure for a collection cannot be re-defined during Creating an NFT. 
 
*For Example, if an X World of Warcraft based artwork has 3 additional properties set while Creating Collection: 
Property 5 with type Boolean: Sword – True/False (Character has a sword) 
Property 6 with type String: Creature; Werewolf/Human/Elf/Orc (Character Build) 
Property 7 with type Number: Rarity; 9 (Character Category by Rarity) 
White Creating an NFT, Joe can only add values for Property 5, 6 & 7, He can’t edit the property type of 5, 6 & 7, neither inter-change property order, nor append more properties to the NFT Collection schema. Joe can only define the property-values according to the NFT Schema set during Collection creation process.* 
* Now your NFT is successfully created armoring itself with its metadata, geared for a Sales listing. After initializing each NFT asset with its metadata(properties) & Tags, you can list a Sale. \
*If only a part of your NFT assets is created into an NFT wioth respect to the total collection: your fully Created NFTs (initialized with their metadata according to NFT Collection Schema) will be pushed below (the non-initialized metadata-based NFT assets). A Wishlist button will be enabled for all the complete NFT assets within their respective creative-previews signifying their completeness.*
 
***B. How to create Whitelist and why is it important?*** 
[CLICK HERE FOR A VIDEO GUIDE](https://youtu.be/LGIBPF2YZgE)
* A Whitelist is a list of approved addresses or accounts that are permitted to access certain resources or participate in certain activities. To create a Whitelist, you can follow these general steps. Determine the purpose of the Whitelist: Before creating a Whitelist, you should determine what it will be used for. For example, you might create a Whitelist to limit access to a certain website, or to allow only certain individuals to participate in a private sale of NFTs. 
* Exclusive audience & loyal buyers who want to get their hands on NFTs before the public sale are prime contenders for Whitelist invitation. When an upcoming NFT Collection receives a lot of hype during the pre-sale stage, Whitelist mechanism can be facilitated to open a portion of the Collection to Collectors, who would then compete to get their hands on an NFT before the supply runs dry and the NFT hits the primary sale and the resell market. Whitelists are an efficient because the network gets very busy, and gas fees go up during primary and secondary sales. Pre-sales and Private-sales by defining a Whitelist a great way of guaranteeing NFT allocation to your most loyal & exclusive followers.  
 
Artists can create a Whitelist via the Creator Dashboard (NFT Wallet) consisting of their most loyal supporters by ensuring a crypto wallet address will be pre-approved for NFT pre-sales. Here is how to go about it:


* Sign in to MantlePlace and arrive on the Creator Interface aka the NFT Wallet 
* Select the Whitelist Option (sub-section) from the NFT Wallet Dashboard 
* Input Whitelist-name, Whitelist-description, maximum members for Whitelist aka Whitelist wallet-cap, Whitelist joining-time & ending-time, verify the information and Confirm 
* You will be presented with the Whitelist invitation link;  
* You can propagate this invite-link to respective members, using it as an exclusive access to private sales for NFT Collections on MantlePlace 
* You can create many Whitelists and gauge the metrics of the created Whitelists under this section 
* How To Add Wallets to Whitelist? 
* Wallets are added to whitelists automatically when a person you have sent the whitelist-link clicks on it. In the future developments of MantlePlace chain-upgrades, a visual dashboard to add wallet-addresses to the whitelist and gauge the added wallets facility will be appended. 

**C. Creating a Sale**
After adding the all the metadata to the NFT assets & transforming it to a complete NFT, verify the statistics of the collection, post which you can create & list a Sale; 
Sales can be of 2 types, namely; 
 
**1. Private Sale:** 
[CLICK HERE FOR A VIDEO GUIDE...](https://youtu.be/t33Ycly_3SQ)
* Pre-requisite for creating a Private-sale is to create a Whitelist (Refer Guide Above) 
* Select Create Sale from the collections tab.  
* Select the total number of (RANDOMIZED) NFTs for sales-listing.  
* Set the ($MNTL) price for blind mint of NFTs and the maximum purchase of tokens (NFTs) per buyer. Select the relevant (Created) Whitelist with unique addresses.  
* Lastly, Set Collection Start & End Time. Click Confirm and Listing for the private sale for minting is live. 


**2. Public Sale:**  
[CLICK HERE FOR AVIDEO GUIDE...](https://youtu.be/BcJmB6Eagrc)
* Select Create Sale from the collections tab.  
* Select the appropriate collection and total number of RANDOMIZED NFTs for public listing. 
* Set the ($MNTL) price for blind mints of NFTs and the Maximum tokens to purchase (NFTs) per buyer, Lastly, Set Collection Start & End Time.  
* Click Confirm and the Listing for the public sale for minting is live. 

*Additional (new) NFT assets can be added to the (self) Created Collection & transformed into an NFT (with metadata initialization) after the listing of a Private (Whitelist) or Public Sale- not affecting the said pool of randomized NFTs. Post sales-listing timeline expiration, the residue unsold NFTs from the previously listed Private and the Public Sale & the newly added NFTs (during the sale) will be available for new sales listings within the randomized NFT pool.*

**5. Managing Your Collections**
![](https://i.imgur.com/Lrn145I.png)

* NFT Wallet is a multi-faceted creator centric dashboard facilitating trading & gauging of NFTs belonging to various collections that have been purchased in secondary market or minted via primary sales. Further, the multi-facet creator dashboard is centralized location to view the metrics of (self-created) Collections (assets: created NFTs); Add new NFT assets to Collection, create new NFTs from the Collection, List & Manage Public & Private Sales.  
* Similarly, the latter-half of the dashboard contains the Whitelist facility where creator can create exclusive address-gated whitelist, edit whitelists, gauge & edit metrics such as address and timelines. Lastly, the next-gen dashboard contains the Wishlist section that displays the hearted or wishlisted NFTs across various NFT collections while window-shopping (exploring) on MantlePlace, with an added option to procure your favorite NFTs from the secondary marketplace (given the NFT is sales-listed) via the Wishlists. 

**6. Verification**
* Creating a collection & creating NFTs are free to use but to trade through the primary markets (minting), Collection ID needs be verified and made live from MantlePlace backend. The stringent but worthy process is an extension of quality control and a spam-proof mechanism on MantlePlace. 
* For your created NFTs with a collection to be listed for Sales via Public or Private sales backed by Whitelist; the Collection ID needs to be vetted and authorized to go ‘live’ by the AssetMantle team’s backend. To become a MantlePlace Genesis/Post-Genesis Creator, send an email with collection details and NFT asset (art) samples here: communications@assetmantle.one 

# FLows 

