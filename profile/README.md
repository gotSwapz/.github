<p align="center">
  <img src="/profile/images/logo_full.png" title="gotSwapz logo">
</p>

**A project for the Polygon blockchain that consists of a factory contract that can be used to create new NFT collections.**

**NFTs of gotSwapz collections can be purchased in packages whose content is random.**

**Users can also exchange their NFTs with other users in order to complete a collection.**

[![screenshot](/profile/images/video.png)](https://youtu.be/6igufetjgv4)

**Live app**: https://www.gotswapz.online

**Alternative link**: https://falling-flower-1161.on.fleek.co

# :large_blue_diamond: How it works

![diagram](/profile/images/diagram.png)

## :flower_playing_cards: Create a collection

Anyone can create a collection through the factory contract, specifying its **name**, a **URI** for the metadata of the NFTs, the **size and price for each package** and a **rarity** value for each NFT that will determine the likelihood of receiving it in a package.

When a package of the collection is sold, the owner of the collection gets the amount Matic paid by the buyer, minus a **service fee** established in the creation of the collection.

## :shopping_cart: Buy items

Each collection can have one or more package sizes with different prices. To buy a package users call the collection contract specifying the **size of the package** and sending the required **amount of Matic** to purchase it. The order is forwarded to the factory contract, which will **request random words to Chainlink**. Once the random words are returned, they are sent back to the collection contract, where the **NFTs for the package that the user receives are chosen randomly and proportionally to the rarity** of each NFT.

## :handshake: Swap items

NFT owners will probably receive duplicated NFTs when they buy a package, so they can swap their NFTs with other users for **free** (paying just the gas fees). To do so a user can create a swap offer to another user, indicating the NFTs that are offered and the NFTs of the other user that they want in return.

The receiver of a swap offer can **accept** it or **reject** it and the creator of the swap offer can **cancel** at any time while it is still open.

# :large_blue_diamond: Architecture

![architecture](/profile/images/stack.png)

## :scroll: Smart contracts

The smart contracts are written in **Solidity** and **Foundry** has been used for testing and deployment.

The NFTs use the **ERC1155** standard.

**Chainlink VRF** service is used to achieve randomness.

They have been deployed to Mumbai and the Polygon mainnet.

|         |                                                        |
| ------- | ------------------------------------------------------ |
| Mumbai  | [0x4cd94a3f94b3cb6c623dff21437b1b5755c6df66](https://mumbai.polygonscan.com/address/0x4cd94a3f94b3cb6c623dff21437b1b5755c6df66#code) |
| Mainnet | [0x5d7addd96b0ca979b86e5eeb34b45b21cd671027](https://polygonscan.com/address/0x5d7addd96b0ca979b86e5eeb34b45b21cd671027#code)        |
|         |                                                        |

## :desktop_computer: Front end

The client application has been built with **React** and **Tailwind CSS**.

It is hosted in **IPFS** though **Fleek**.

## :electric_plug: Back end

The backend is a **NodeJS** application built with **Express.js**.

It is hosted in **AWS** with its **Elastic Beanstalk** service.

## :file_cabinet: Database

Object-relational **PostgreSQL** database, managed with **AWS RDS** service.

## :floppy_disk: NFT storage

The NFTs metadata and media files are stored in **IPFS** with **NFT.Storage**.
