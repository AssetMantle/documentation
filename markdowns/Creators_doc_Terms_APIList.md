# Creators Documentations

## Key Terminologies

* **Bonding Tokens** - The assets on the AssetMantle chain can be created in a permissionless environment. The nominal gas fees for on-chain transactions might create an attack vector to possibly unnecessarily mint transactions/spam the assets or related transactions on-chain. One such mechanism is to tackle the bonding fees for the purchases. Bonding is the process of locking the tokens for a certain period of time. The bonding fees per asset would be **directly proportional to the number of on-chain metadata properties**.

* **Burn** - An NFT being stored on-chain can't be 'deleted', however it can be 'burned'. Due to the immutability nature of blockchain, the asset, once minted, will exist on-chain forever. Thus, the Burn mechanism enables you to burn an NFT that can be sent to an inaccessible address that is not accessible by anyone as it is removed from circulation. Utilizing the MantleModules, creators can also set up the burn block height as the parameter, which enables them to burn an asset once the particular height is reached. You can find more information about the usage of the same [here](#insburnassetburnins) 

## Types of NFTs and advanced capabilities using MantleModules

* **Fractionalization**
  * Fractional NFTs(F-NFTs), in simple terms, divide the ownership of an NFT into smaller fractions. Thus, enabling the possibility for several users to own a fraction of the NFT/Collection
  * **Use - Cases** 
    * **Metaverse** : Buy Virtual Land and similar digital assets within the virtual world
    * **Real Estate** : Multiple parties sharing the rights/ownership of the property.
  
* **Composable/Decomposable**
  
  * **Composable NFTs** : Composable NFTs initially introduced in [ERC998](https://www.nftstandards.wtf/Standards/ERC998+Composable+NFT), allow the creation of a composed version of more than one asset and add more utilities on top of the existing assets. 
  * **Use-Cases**
    * **P2E & Gaming** : Combine the rare traits of two different skins in the game to make your character stronger and rarer, and mint the composed assets as NFTs.
    * **Metaverse** :For all the in-app characters, you can buy a hat, boot, and jacket for your avatar and mint it as a unique asset.
  * **Decomposable NFTs** : Decompose the greatest assets or their associated properties into multiple individual assets. 



* **1/1s**
  * 1/1, often framed as one-of-one, is an NFT that has been issued as a single, unique edition. One-of-ones are more scarce and provide a more valuable set of utilities due to the singular ownership of the asset
* **1-of-many**
  * Multiple copies of the single edition exist wherein the user can own a single collection piece with a fixed set of utilities/properties.


## API List and Definition
The following API lists provides an high-level overview about the transactions possible utilizing the MantleModules. For more info, please refer to [MantleModules](https://github.com/AssetMantle/modules)

### Transaction / Identity
<p> APIs pertaining to manipulating the 'identity', a DID based entity used to represent identity of user. </p>

#### <ins>defineIdentity.define</ins>
<p>used to define an identity entity. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`define: (address: string, chain_id: string, mnemonic: string, fromID: string, mutableTraits: string, immutableTraits: any, mutableMetaTraits: any, immutableMetaTraits: any, feesAmount: any, feesToken: any, gas: any, mode: any, memo: string) => Promise<any>;`
<p>---------------</p>


#### <ins>defineIdentity.createIdentityDefineMsg</ins>
<p>used to define an identity entity. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createIdentityDefineMsg: (address: string, chain_id: string, fromID: string, mutableTraits: string, immutableTraits: any, mutableMetaTraits: any, immutableMetaTraits: any, feesAmount: any, feesToken: any, gas: any, memo: string) => Promise<any>;`
<p>---------------</p>



#### <ins>issueIdentity.issue</ins>
<p>used to issue an identity entity. Defines a message and initiates the transaction.</p>
<p><strong>Function Signature</strong></p>

`issue: (address: string, chain_id: string, mnemonic: any, to: any, fromID: string, classificationID: any, mutableProperties: string, immutableProperties: any, mutableMetaProperties: any, immutableMetaProperties: any, feesAmount: any, feesToken: any, gas: any, mode: any, memo: string) => Promise<any>;`
<p>---------------</p>



#### <ins>issueIdentity.createIdentityIssueMsg</ins>
<p>used to issue an identity entity. Only defines and outputs a message object.</p>
<p><strong>Function Signature</strong></p>

`createIdentityIssueMsg: (address: string, chain_id: string, to: any, fromID: string, classificationID: any, mutableProperties: string, immutableProperties: any, mutableMetaProperties: any, immutableMetaProperties: any, feesAmount: any, feesToken: any, gas: any, memo: string) => Promise<any>;`
<p>---------------</p>



#### <ins>nubIdentity.nub</ins>
<p>used to create a nub ID, which is the simplest but complete and valid unit of identification. Defines a message and initiates the transaction.</p>
<p><strong>Function Signature</strong></p>

`nub: (address: string, chain_id: string, mnemonic: any, nubID: any, feesAmount: any, feesToken: any, gas: any, mode: any, memo: string) => Promise<any>;`
<p>---------------</p>




#### <ins>nubIdentity.createIdentityNubMsg</ins>
<p>used to create a nub ID, which is the simplest but complete and valid unit of identification. Only defines and outputs a message object.</p>
<p><strong>Function Signature</strong></p>

`createIdentityNubMsg: (address: string, chain_id: string, nubID: any, feesAmount: any, feesToken: any, gas: any, memo: string) => Promise<any>;`
<p>---------------</p>




#### <ins>provisionIdentity.provision</ins>
<p>used to create a provision address which is used to control / operate an identity. a nub ID, which is the simplest but complete and valid unit of identification. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`provision: (address: string, chain_id: string, mnemonic: any, identityID: any, to: any, feesAmount: any, feesToken: any, gas: any, mode: any, memo: string) => Promise<any>;`
<p>---------------</p>




#### <ins>provisionIdentity.createIdentityProvisionMsg</ins>
<p>used to create a provision address which is used to control / operate an identity. Only defines and outputs a message object</p>
<p><strong>Function Signature</strong></p>

`createIdentityProvisionMsg: (address: string, chain_id: string, identityID: any, to: any, feesAmount: any, feesToken: any, gas: any, memo: string) => Promise<any>;`
<p>---------------</p>




#### <ins>queryIdentities.queryIdentity</ins>
<p>used to query the list of all identities. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`queryIdentity: () => Promise<any>;`
<p>---------------</p>




#### <ins>queryIdentities.queryIdentityWithID</ins>
<p>used to query the list of all identities pertaining to a certain ID argument passed. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`queryIdentityWithID: (id: any) => Promise<any>;`
<hr>

### transaction / assets
<p> APIs pertaining to manipulating the 'assets', a DID based entity used to represent NFTs. </p>

#### <ins>burnAsset.burn</ins>
<p>used to burn an Asset. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`burn: (address: string, chain_id: string, mnemonic: string, fromID: string, assetID: string, feesAmount: any, feesToken: any, gas: any, mode: any, memo: string,  ) => Promise<any>;`
<p>---------------</p>




#### <ins>burnAsset.createAssetBurnMsg</ins>
<p>used to burn an Asset. Only defines and outputs a message object</p>
<p><strong>Function Signature</strong></p>

`createAssetBurnMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    assetID: string,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>

#### <ins>defineAsset.define</ins>
<p>used to define the schema of an Asset. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`define: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    mutableTraits: string,
    immutableTraits: any,
    mutableMetaTraits: any,
    immutableMetaTraits: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>defineAsset.createAssetDefineMsg</ins>
<p>used to define the schema of an Asset. Only defines and outputs a message object</p>
<p><strong>Function Signature</strong></p>

`createAssetDefineMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    mutableTraits: string,
    immutableTraits: any,
    mutableMetaTraits: any,
    immutableMetaTraits: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>

#### <ins>mintAsset.mint</ins>
<p>used to mint an asset using the defined schema. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

` mint: (
    address: string,
    chain_id: string,
    mnemonic: any,
    toID: any,
    fromID: string,
    classificationID: any,
    mutableProperties: string,
    immutableProperties: any,
    mutableMetaProperties: any,
    immutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>mintAsset.createAssetMintMsg</ins>
<p>used to mint an asset using the defined schema. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createAssetMintMsg: (
    address: string,
    chain_id: string,
    toID: any,
    fromID: string,
    classificationID: any,
    mutableProperties: string,
    immutableProperties: any,
    mutableMetaProperties: any,
    immutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>

#### <ins>mutateAsset.mutate</ins>
<p>used to change the mutable properties of an Asset. These specific properties must be already defined as mutable in the schema of asset. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`mutate: (
    address: string,
    chain_id: string,
    mnemonic: any,
    fromID: string,
    assetID: any,
    mutableProperties: string,
    mutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>mutateAsset.createAssetMutateMsg</ins>
<p>used to change the mutable properties of an Asset. These specific properties must be already defined as mutable in the schema of asset. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createAssetMutateMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    assetID: any,
    mutableProperties: string,
    mutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>


#### <ins>queryAssets.queryAsset</ins>
<p>used to change the mutable properties of an Asset. These specific properties must be already defined as mutable in the schema of asset. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`queryAsset: () => Promise<any>;`
<p>---------------</p>




#### <ins>queryAssets.queryAssetWithID</ins>
<p>used to change the mutable properties of an Asset. These specific properties must be already defined as mutable in the schema of asset. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`queryAssetWithID: (id: any) => Promise<any>;`


<hr>

### transaction / classification
<p> APIs pertaining to manipulating the Classifications or schemas of entities created </p>

#### <ins>cls.queryClassification</ins>
<p>used to query the details of all Classifications IDs. </p>
<p><strong>Function Signature</strong></p>

`queryClassification: () => Promise<any>;`
<p>---------------</p>




#### <ins>cls.queryClassificationWithID</ins>
<p>used to query the details of Classification IDs pertaining to the ID argument provided in the function</p>
<p><strong>Function Signature</strong></p>

`queryClassificationWithID: (id: any) => Promise<any>;`
<p>---------------</p>


<hr>

### transaction / maintainer
<p> APIs pertaining to managing the maintainers and access control lists of various entities </p>

#### <ins>deputizeMaintainer.deputize</ins>
<p>used to provide or revoke access controls to new maintainer roles. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`deputize: (
    address: string,
    chain_id: string,
    mnemonic: string,
    identityID: string,
    clsID: string,
    toID: string,
    maintainedTraits: string,
    addMaintainer: any,
    removeMaintainer: any,
    mutateMaintainer: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>deputizeMaintainer.createDeputizeMsg</ins>
<p>used to provide or revoke access controls to new maintainer roles. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createDeputizeMsg: (
    address: string,
    chain_id: string,
    identityID: string,
    clsID: string,
    toID: string,
    maintainedTraits: string,
    addMaintainer: any,
    removeMaintainer: any,
    mutateMaintainer: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>



#### <ins>queryMaintainer.queryMaintainerWithID</ins>
<p>used to query the details of Classification IDs pertaining to the ID argument provided in the function</p>
<p><strong>Function Signature</strong></p>

`queryMaintainerWithID: (id: any) => Promise<any>;`


<hr>

### transaction / order
<p> APIs pertaining to manipulating the 'order', a DID based entity used to represent orders created to perform a transfer of value between 'identities' and 'assets'. </p>

#### <ins>defineOrder.define</ins>
<p>used to define a schema for an order type.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`define: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    mutableTraits: string,
    immutableTraits: any,
    mutableMetaTraits: any,
    immutableMetaTraits: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>defineOrder.createOrderDefineMsg</ins>
<p>used to define a schema for an order type. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createOrderDefineMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    mutableTraits: string,
    immutableTraits: any,
    mutableMetaTraits: any,
    immutableMetaTraits: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>

#### <ins>makeOrder.make</ins>
<p>used to issue an order pertaining to a specific classification.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`make: (
    address: string,
    chain_id: string,
    mnemonic: any,
    fromID: string,
    classificationID: any,
    makerOwnableID: string,
    takerOwnableID: string,
    expiresIn: any,
    makerOwnableSplit: any,
    mutableProperties: string,
    immutableProperties: any,
    mutableMetaProperties: any,
    immutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>makeOrder.createOrderMakeMsg</ins>
<p>used to issue an order pertaining to a specific classification. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createOrderMakeMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    classificationID: any,
    makerOwnableID: string,
    takerOwnableID: string,
    expiresIn: any,
    makerOwnableSplit: any,
    mutableProperties: string,
    immutableProperties: any,
    mutableMetaProperties: any,
    immutableMetaProperties: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>


#### <ins>takeOrder.take</ins>
<p>used to accept an issued order pertaining to a specific order ID.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`take: (
    address: string,
    chain_id: string,
    mnemonic: any,
    fromID: string,
    takerOwnableSplit: any,
    orderID: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>takeOrder.createOrderTakeMsg</ins>
<p>used to accept an issued order pertaining to a specific order ID. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createOrderTakeMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    takerOwnableSplit: any,
    orderID: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>


#### <ins>cancelOrder.cancel</ins>
<p>used to cancel an issued order pertaining to a specific order ID.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`cancel: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    orderID: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>cancelOrder.createOrderCancelMsg</ins>
<p>used to cancel an issued order pertaining to a specific order ID. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createOrderCancelMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    orderID: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>


#### <ins>queryOrders.queryOrder</ins>
<p>used to query for the list of all orders available </p>
<p><strong>Function Signature</strong></p>

`queryOrder: () => Promise<any>;`
<p>---------------</p>




#### <ins>queryOrders.queryOrderWithID</ins>
<p>used to query for a specifc order pertaining to an order ID </p>
<p><strong>Function Signature</strong></p>

`queryOrderWithID: (id: any) => Promise<any>;`


<hr>

### transaction / meta
<p> APIs pertaining to querying a certain meta property across the entities </p>

#### <ins>queryMeta.queryMetaWithID</ins>
<p>used to query for a meta property of entities of a certain ID </p>
<p><strong>Function Signature</strong></p>

`queryMetaWithID: (id: any) => Promise<any>;`
<p>---------------</p>




#### <ins>revealMeta.reveal</ins>
<p>used to cancel an issued order pertaining to a specific order ID.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`reveal: (
    address: string,
    chain_id: string,
    mnemonic: any,
    metaFact: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>revealMeta.createMetaRevealMsg</ins>
<p>used to cancel an issued order pertaining to a specific order ID. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createMetaRevealMsg: (
    address: string,
    chain_id: string,
    metaFact: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`

<hr>

### transaction / splits
<p> APIs pertaining to creating and manipulating fractionalizing of NFTs and their correlation with FTs </p>

#### <ins>querySplits.querySplitsWithID</ins>
<p>used to query a split (fractional NFT) using a specific ID </p>
<p><strong>Function Signature</strong></p>

`querySplitsWithID: (id: any) => Promise<any>;`
<p>---------------</p>




#### <ins>sendSplits.send</ins>
<p>used to send a split from one identity to another.  Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`send: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    toID: string,
    ownableID: string,
    split: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>sendSplits.createSplitsSendMsg</ins>
<p>used to send a split from one identity to another. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createSplitsSendMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    toID: string,
    ownableID: string,
    split: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
  <p>---------------</p>
  
#### <ins>wrapSplits.wrap</ins>
<p>used to wrap a coin into a split, which is then used for transacting (transfer of value) in AssetMantle's NFT Economy. Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`wrap: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    coins: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>wrapSplits.createSplitsWrapMsg</ins>
<p>used to wrap a coin into a split, which is then used for transacting (transfer of value) in AssetMantle's NFT Economy. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createSplitsWrapMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    coins: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
  <p>---------------</p>
  
#### <ins>unwrapsplits.unwrap</ins>
<p>used to unwrap a split back into a coin, which is then used for transacting (transfer of value) in Cosmos Economy and beyond.   Defines a message and initiates the transaction. </p>
<p><strong>Function Signature</strong></p>

`unwrap: (
    address: string,
    chain_id: string,
    mnemonic: string,
    fromID: string,
    ownableID: string,
    split: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    mode: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>unwrapsplits.createSplitsUnwrapMsg</ins>
<p>used to unwrap a split back into a coin, which is then used for transacting (transfer of value) in Cosmos Economy and beyond. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createSplitsUnwrapMsg: (
    address: string,
    chain_id: string,
    fromID: string,
    ownableID: string,
    split: any,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
  <p>---------------</p>



<hr>

### Transaction / accounts
<p> APIs pertaining to creating an account in AssetMantle chain for storing and transacting on coins </p>

#### <ins>createAccount.create</ins>
<p>used to create and initiate an account in the AssetMantle chain</p>
<p><strong>Function Signature</strong></p>

`create: (
    address: string,
    chain_id: string,
    mnemonic: string,
    name: string,
    denom: string,
    amount: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>recoverAccount.recover</ins>
<p>used to recover an existing account using a mnemonic</p>
<p><strong>Function Signature</strong></p>

`recover: (mnemonic: string, name: string) => Promise<any>;`


  
<hr>
  
### transaction / bank
<p> APIs pertaining to transfer of value of coins in the AssetMantle chain and beyond. </p>

#### <ins>bank.sendCoin</ins>
<p> APIs pertaining to transfer of value of coins in the AssetMantle chain and beyond. </p>
<p><strong>Function Signature</strong></p>

`create: (
    address: string,
    chain_id: string,
    mnemonic: string,
    name: string,
    denom: string,
    amount: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
<p>---------------</p>




#### <ins>bank.createSendCoinMsg</ins>
<p> APIs pertaining to transfer of value of coins in the AssetMantle chain and beyond. Only defines and outputs a message object. </p>
<p><strong>Function Signature</strong></p>

`createSendCoinMsg: (
    from_address: string,
    chain_id: string,
    to_address: string,
    denom: string,
    amount: string,
    feesAmount: any,
    feesToken: any,
    gas: any,
    memo: string,
  ) => Promise<any>;`
  <p>---------------</p>

  
<hr>

### utilities / keys
<p> APIs pertaining to creation of wallets and keystores in the AssetMantle chain. </p>

#### <ins>createWallet</ins>
<p>used to create a wallet using a mnemonic and a bip39 passphrase. </p>
<p><strong>Function Signature</strong></p>

`createWallet: (
  mnemonic: string,
  bip39Passphrase: string,
) => Promise<{
  address: string;
  mnemonic: string;
}>;`
<p>---------------</p>




#### <ins>createRandomWallet</ins>
<p>used to create a wallet using a bip39 passphrase, while the mnemonic is generated automatically. </p>
<p><strong>Function Signature</strong></p>

`createRandomWallet: (bip39Passphrase: string) => Promise<{
  address: string;
  mnemonic: string;
}>;`
<p>---------------</p>



#### <ins>getWallet</ins>
<p>used to get the object pertaining to already created wallet, pertaining to a certain mnemonic and bip39 passphrase </p>
<p><strong>Function Signature</strong></p>

`getWallet: (mnemonic: string, bip39Passphrase: string) => Promise<any>;`
<p>---------------</p>




#### <ins>createStore</ins>
<p>used to create a encrypted keystore using a specified mnemonic and password </p>
<p><strong>Function Signature</strong></p>

`createStore: (
  mnemonic: string,
  password: string,
) => {
  Response: any;
  error: any;
};`
<p>---------------</p>




#### <ins>decryptStore</ins>
<p>used to decrypt / open and encrypted keystore file, by specifying the file path and a password to decrypt. </p>
<p><strong>Function Signature</strong></p>

`decryptStore: (
  fileData: any,
  password: string,
) => {
  mnemonic: any;
};`
<p>---------------</p>



<hr>
