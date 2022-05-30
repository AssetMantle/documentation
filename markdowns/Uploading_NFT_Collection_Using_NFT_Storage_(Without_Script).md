# Uploading NFT Collection Using NFT.Storage (Without Script)

[NFT.Storage](http://NFT.Storage) is an IPFS node operator that can be used to pin data in IPFS.

To begin with, creators are required to create directories that would hold their images and metadata.

These would then be compiled into a single IPFS CAR (Content Addressable aRchive) file that can be uploaded.

Consolidate all images into the `/images` folder.

This documentation will use sample images for the purposes of explanation.

## Uploading Assets to NFT.Storage

Pack the assets into a `.CAR` file or upload each of them manually.

### 1. Visit [NFT.Storage](http://NFT.Storage) and Click ‘Get Started’

![nft storage ss5.png](..\assets\images\nft storage ss5.png)

### 2. Click ‘Upload’

![nft storage ss6.png](..\assets\images\nft storage ss6.png)

### 3. Click ‘Choose File’

If the file chosen is a `.CAR` file, check the box before “is CAR?”

![nft storage ss7.png](..\assets\images\nft storage ss7.png)

![nft storage ss8.png](..\assets\images\nft storage ss8.png)

### 4. Click ‘Upload’ After The File Has Been Chosen

If the file chosen is a `.CAR` file, check the box before “is CAR?”

![nft storage ss9.png](..\assets\images\nft storage ss9.png)

### 5. View The Details

Here, the creator will be able to view details such as CID, Pin Status, and more.

![nft storage ss10.png](..\assets\images\nft storage ss10.png)

The creator can also perform actions like deleting the file or copying the IPFS URL as illustrated below.

![nft storage ss11.png](..\assets\images\nft storage ss11.png)

## Uploading Metadata to NFT.Storage

Pack the metadata files into a `.CAR` file or upload each of them manually.

### 1. Structure the Metadata

```jsx
// 1.json
{
  "properties": [
    {
      "name": "Block",
      "type": "String",
      "value": "Flash"
    },
    {
    "name": "Eyes",
    "type": "String",
    "value": "black"
    },
    {
    "name": "edition",
    "type": "number",
    "value": 1
    },
    {
    "name":"rare",
    "type": "bool",
    "value": true
    },
  ],
  "description": "This is the sample metadata file",
  "image": "ipfs://baadasdalasdas/images/1.png",
  "name": "Sample Metadata"
}
```

### 2. Upload Metadata Files to NFT.Storage

Repeat steps 2 through 5 as shown above.