# Uploading NFT Collection Using Web3.Storage (Script)

This guide is best suited for creators who wish to automate the process of uploading their NFT assets and metadata using NFT.Storage.

It is particularly useful for collections with a very large number of assets.

## 1. Create an API Token

On the [Web3.Storage](http://Web3.Storage) home page, hover over “ACCOUNT” and click on “Create an API Token”.

![web3 storage ss1.png](..\assets\images\web3 storage ss1.png)

Now click on “Create your first API token”.
Alternatively, creators can choose to click on “Create a new API Token” if they have created API tokens before.

![web3 storage ss2.png](..\assets\images\web3 storage ss2.png)

Give a name to this API key.

In the example below, the API token as been named “Mantle” for illustration purposes.

![web3 storage ss3.png](..\assets\images\web3 storage ss3.png)

Now, the creators can view their API key and perform actions such as copying or deleting the same.

![web3 storage ss4.png](..\assets\images\web3 storage ss4.png)

## 2. Install Node.js

Please ensure that all assets are named numerically in a sequential manner.

```jsx
sudo npm i -g npm@latest
sudo npm i -g yarn@latest
sudo npm i -g ts-node@latest
```

## 3. Create Project Directory

Create an nft-upload-project directory.

Move your images and metadata folders there.

```jsx
mkdir nft-upload-project
cd nft-upload-project
```

```jsx
# Folder Structure
Project
├── nft-upload (tool folder)
    ├── images (assets/images folder)
    ├── metadata (metadata folder)
```

## 4. Install Dependencies

```jsx
# Install dependencies
# Change your directory to script folder
cd nft-upload
yarn install
```

## 5. Use API

Now, use the API that was created in step 1.

Paste that APIKey in config.js file (web3StorageAPIKey) there.


## 6. Run the Script

```jsx
yarn web3-storage-upload
```


## Summing Up

```jsx
Note: Steps are same as NFT.Storage.upload
Note: Install nodejs in your system
sudo apt install nodejs npm -y
sudo npm i -g npm@latest
sudo npm i -g yarn@latest
sudo npm i -g ts-node@latest

# Create a nft-upload-project directory
# Move your images and metadata folders there
mkdir nft-upload-project
cd nft-upload-project

# Folder Structure
Project
├── nft-upload (tool folder)
    ├── images (assets/images folder)
    ├── metadata (metadata folder)

# Install dependencies
# Change your directory to script folder
cd nft-upload
yarn install

# Create an API on web3.storage and Copy that API key

# Paste that APIKey in config.js file (web3StorageAPIKey) there.
yarn web3-storage-upload
```