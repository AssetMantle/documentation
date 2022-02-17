
# Quick Setup Docs for AssetMantle


## Overview
Asset Mantle is an application implementing the minimum clique of PersistenceSDK modules enabling interNFT definition, issuance, ownership transfer and decentralized exchange.
Through Asset Mantle, we aim in providing the infrastructure for the creation of niche-specific marketplaces for interoperable NFTs, supporting use cases ranging from digital art to tokenized tickets & much more.


## Prerequisites
*     go v1.15+ (Install amd64 versions)
    Note: Setup GoPath & env correctly in your project directory for the binaries to be successfully executed
    
    

## Steps to run Asset Mantle
1. Clone the Asset Mantle Repo
        ```$ git clone https://github.com/AssetMantleOne/node```
2. Checkout to latest stable tagged version
``` $ git checkout tags/v0.1.0```
3. If you are running for the first time
``` $ make install ```
4. Once the above step is done, next steps would be running the ready-made scripts to setup & consume the commands in CLI
``` $ bash .script/setup.sh
    $ bash .script/startup.sh ```    

At the end of the above code you should get the following output:
Node and Client started up. For logs

```
tail -f ~/.assetNode/log
tail -f ~/.assetClient/log
**assetNode** : Persistence Hub Node Daemon (server)
**assetClient**: Command line interface for interacting with node
```


5. On a new terminal, run the transactions.sh script
``` $ bash .script/transactions.sh ```

```
To know more about the cli commands available :
$ assetNode --help
$ assetClient --help
```

## Understanding .script structure

``` 
1.  setup.sh
    => make & build executable binaries -> initialize the node -> add keys -> add genesis account -> add genesis transactions -> collect genesis transactions
2.  startup.sh 
    => assetNode start & assetClient start
3.  transactions.sh 
    => Core components
        - Users
        - Send Coins
        - identities issue, provision, unprovision
        - metas reveal (reveal the data w.r.t the given identity)
        - Assets mint, mutate burn
        - order make and cancel
        - order make and take private
        - order make and take public
        - splits send
4. shutdown.sh 
    => To shutdown the running blockchain node & client (killall)
```


## References Links
[Github Repo](https://github.com/persistenceOne/assetMantle/tree/v0.1.0)
[Persistence SDK](https://github.com/persistenceOne/persistenceSDK)
[Asset Mantle DApp](https://github.com/persistenceOne/assetMantle-webApplication)
[Open-API Docs](http://52.32.196.159:1317/swagger/index.html#/)
### FAQs / Common Issues

```
'SecTrustedApplicationCreateFromPath' is deprecated:
github.com/keybase/go-keychain
 first deprecated in macOS 10.15 - No longer supported [-Wdeprecated-declarations]
 
 * The above watning occurs for macOS >10.15 due to the deprecated dependancies in keychain , can ignore this warning for this setup
```

```
go version with arm64 may face issues while running this application, it is recommended to use amd64 based go version  for the deployment 
```
