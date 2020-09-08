# **Legend of Features / Topics**

## Jump table to categories
1. [General](#General)
2. [Definitions](#Definitions)
3. [Userinterface](#Userinterface)
4. [Import](#Import)
5. [Export](#Export)
6. [Wallets](#Wallets)
7. [Connection](#Connection)
8. [Transactions](#Transactions)
9. [Optional feature to compare](#Optional-feature-to-compare-(not-yet-listed!))


### Definitions

- FN : Fully Noded app
- FN2 : Fully Noded 2 app, new name is Gordian Wallet, The original name FN2 was a misnaming because it is a different app than FN from its inception. [This comparison](./Docs/FN2_Comparison.md) tries to explain the differences between Fully Noded and Gordian Wallet. 
- signed raw transaction : [Wikipage](https://en.bitcoin.it/wiki/Raw_Transactions) explains it all
- Bitcoin-cli: Bitcoin *CommandLine Interface*; just like Bitcoin Core app the CLI uses RPC calls to give your node and the bitcoin network commands and get results back.
- Bitcoin Core (Wallet) App, also known as `Bitcoin-qt`: Software running on MacOS, Windows and Linux that offers a **Graphical User Interface** to your Bitcoin Wallet and, if you wish, to your node. Just like Bitcoin CLI the Core app uses RPC calls to give your node and the bitcoin network commands and get results back.
- Bitcoin-qt: another name for Bitcoin Core (Wallet) App.
- bitcoind: Bitcoin Deamon, background process running a bitcoin node. Bitcoind is a program that implements the Bitcoin protocol for remote procedure call (RPC) use. It is also the second Bitcoin client in the network's history. It is available under the MIT license in 32-bit and 64-bit versions for Windows, GNU/Linux-based OSes, and Mac OS X. [Read more](https://en.bitcoin.it/wiki/Bitcoind)
- psbt: Partially signed bitcoin transactions (PSBTs) Also covering BIP174. Partially Signed Bitcoin Transactions (PSBTs) are a data format that allows wallets and other tools to exchange information about a Bitcoin transaction and the signatures necessary to complete it.
- rbf; Replace-By-Fee (RBF) is a node policy that allows an unconfirmed transaction in a mempool to be replaced with a different transaction that spends at least one of the same inputs and which pays a higher transaction fee. **For newbies:** a transaction that can't get through because of too low fee, can be overridden (replaced) with a higher fee to maybe succeed instead.
- pure bitcoin core wallets: traditional bitcoin wallet, that has to be manually backed up, recovered etc using bitcoin-cli. Your node will sign transactions and will hold the private key.
- Fully Noded wallets: support BIP39 recovery words, the seed is encrypted and stored on your device **not** on the node. The node will only ever hold public keys. Your node will build psbt for us that FN will sign (not your Node). Your node verifies the UTXO's
- Libwally : an open source library (https://github.com/ElementsProject/libwally-core) used by Fully Noded, (https://github.com/blockchain/libwally-swift/blob/master/README.md) which allows us to utilize BIP39 directly in the app meaning you can easily recover your Fully Noded wallet with Electrum for example. Now when you create a wallet you will get a 12 word recovery phrase (no passphrase by default) to backup and keep safe.
- legacy bitcoin address (p2pkh): refers to the accepted common standard to derive non segwit addresses. These addresses always begin with a 1.
- bech32  bitcoin address(p2wpkh):BIP49 refers to the accepted common standard of deriving segwit "compatibility" addresses. These addresses begin with a 3.
- segwit wrapped  bitcoin address (p2sh-p2wpkh) : BIP49 refers to the accepted common standard of deriving segwit "compatibility" addresses. These addresses begin with a 3.
- BIP84 keys : BIP84 refers to the accepted common standard of deriving native segwit addresses. These addresses always begin with bc1 - and are referred to bech32 addresses.
- Segwit addresses: – Segregated Witness – or SegWit in short – reduced the transaction data’s size to allow for faster transactions, better scalability and decreased fees. Native SegWit (bech32) enhanced this even further and includes even lower fees. Not all exchanges and wallet providers support sending Bitcoin to a Native SegWit address yet, which is why you are presented both options in Ledger Live. Transactions between all 3 address types are possible
- keypool : The keypool is a collection of unused addresses in your wallet. The keypool parameter tells the client how many unused addresses to keep in its pool. The original purpose of the keypool is to allow you to backup your wallet file less frequently and still have access to all your funds in the event of a hard drive failure. However since the invention of Hierarchical Deterministic Wallets (HD wallets, [BIP32](https://en.bitcoin.it/wiki/Deterministic_wallet)): If you have a HD wallet (check the icon on the bottom-right corner in Bitcoin Core), it doesn't matter. If you've created your wallet in an older version of Bitcoin Core, it's not an HD wallet. If that's the case, your keypool is important for backups: your backup has the same 1000 keys, which means you only need to make a new backup after using many different new addresses. If you would limit the keypool size to 20, you'll quickly run out of addresses, and you need to make new backups very often. That's the reason the keypool was increased from 100 to 1000. An important distinction with regrads to FN and Bitcoin Core is that Bitcoin Core is not able to add multisig addresses to the keypool, therefore we rely on the `bitcoin-cli` command `deriveaddresses` to derive multisig addresses on the fly using your multisig descriptors.
- Output descriptors: Descriptors are a clever way of importing specific keys into your node from any derivation, for any (or all) address types, single or multi signature, along with a fingerprint so offline psbt signers like a Coldcard and Fully Noded can sign the psbt if they hold the correct seed.
- coldcard : a type of hardware wallet to store, send and receive crypto currencies
- ledger Nano S/X: types of hardware wallets to store, send and receive crypto currencies
- Keepkey : a type of hardware wallet to store, send and receive crypto currencies
- Trezor : a type of hardware wallet to store, send and receive crypto currencies
- Tor:Tor is free and open-source software for enabling anonymous communication. The name derived from the acronym for the original software project name "The Onion Router". [Read more in Wikipedia](https://en.wikipedia.org/wiki/Tor_(anonymity_network))
- Node: A bitcoin full Node is a independent entity in a peer to peer ecosystem. A Node independently checks and verifies all protocol rules for incoming broadcasted transactions. A full node does not trust, but verifies. Technically speaking a *node* is a computer connected to other computers which follows rules and shares information. A *'full node'* is a computer in Bitcoin's peer-to-peer network which hosts and synchronises a copy of the entire Bitcoin blockchain. [Here](https://medium.com/@gloriazhao/map-of-the-bitcoin-network-c6f2619a76f3) is an excellent read on nodes, what they are and the differences between types of nodes.
- Gordian Server / Standup app: is a personal one-click Mac OS installer for Bitcoin Core and Tor that will present a QuickConnect QR code that can be used to pair mobile wallets for remote use over Tor V3. [Read more](https://github.com/BlockchainCommons/GordianSystem)
- Nodl: A hardware box with to run a non-preloaded bitcoin node on it, [commercial site](https://www.nodl.it/). 
- RPC: Remote Procedure Calls
- bitcoind: Bitcoin Deamon, background process running a bitcoin node. Bitcoind is a program that implements the Bitcoin protocol for remote procedure call (RPC) use. It is also the second Bitcoin client in the network's history. It is available under the MIT license in 32-bit and 64-bit versions for Windows, GNU/Linux-based OSes, and Mac OS X. [Read more](https://en.bitcoin.it/wiki/Bitcoind)

- EPS : TBW
- CoinJoin : CoinJoin is a trustless method for combining multiple Bitcoin payments from multiple spenders into a single transaction to make it more difficult for outside parties to determine which spender paid which recipient or recipients. More on [wikipedia](https://en.bitcoin.it/wiki/CoinJoin)

## Knowledge you should be confidently applying
- The definitions above
- Output Descriptors : https://github.com/bitcoin/bitcoin/blob/master/doc/descriptors.md
- BIP32, BIP39, BIP44, BIP47, BIP49, BIP84, BIP174
- derivation paths, keypools
## Actions you should be comfortable with
- Amend knowledge and keep existing knowledge up to date
- recover from a seed
- sweep to a new wallet
- use bitcoin-cli
- install, sync, start and stop your own full node
- connect your TOR V3


# Jump table to categories
1. [General](#General)
2. [Standup](#Standup)
3. [Userinterface](#Userinterface)
4. [Import](#Import)
5. [Export](#Export)
6. [Wallets](#Wallets)
7. [Connection](#Connection)
8. [Transactions](#Transactions)
9. [Optional feature to compare](#Optional-feature-to-compare-(not-yet-listed!))


### General

#### Ownership
Describe ownership structure and developers.

#### Open Source License
Open-source software releases source code under a license in which the copyright holder grants users the rights to use, study, change, and distribute the software to anyone and for any purpose. Open-source software may be developed in a collaborative public manner.<br/>
* License
A software license is a legal instrument (usually by way of contract law, with or without printed material) governing the use or redistribution of software. A typical software license grants the licensee, typically an end-user, permission to use one or more copies of software in ways where such a use would otherwise potentially constitute copyright infringement of the software owner's exclusive rights under copyright.

#### Free and open source software licenses:

* *Public domain:*  
The public domain consists of all the creative work to which no exclusive intellectual property rights apply. Those rights may have expired, been forfeited, expressly waived, or may be inapplicable.  
	  * *PD: Public Domain:*  
	  * *CC0: Creative Commons:*  
	A Creative Commons (CC) license is one of several public copyright licenses that enable the free distribution of an otherwise copyrighted "work". A CC license is used when an author wants to give other people the right to share, use, and build upon a work that they (the author) have created. CC provides an author flexibility (for example, they might choose to allow only non-commercial uses of a given work) and protects the people who use or redistribute an author's work from concerns of copyright infringement as long as they abide by the conditions that are specified in the license by which the author distributes the work.  
* *Permissive license:*   
A permissive software license, sometimes also called BSD-like or BSD-style license,is a free-software license with only minimal restrictions on how the software can be used, modified, and redistributed, usually including a warranty disclaimer.  
	  * *MIT License:*  
	A permissive free software license originating at the Massachusetts Institute of Technology (MIT) in the late 1980s. As a permissive license, it puts only very limited restriction on reuse and has, therefore, high license compatibility. It is compatible because it can be re-licensed under other licenses. The MIT license is compatible with many copyleft licenses, such as the GNU General Public License (GPL);  
	  *Apache License:*  
	The Apache License is a permissive free software license written by the Apache Software Foundation (ASF).[5] It allows users to use the software for any purpose, to distribute it, to modify it, and to distribute modified versions of the software under the terms of the license, without concern for royalties. The ASF and its projects release their software products under the Apache License. The license is also used by many non-ASF projects.  
	  * *MPL: Mozilla Public License:*  
	  * *BSD Lisence:*  
	BSD licenses are a family of permissive free software licenses, imposing minimal restrictions on the use and distribution of covered software. This is in contrast to copyleft licenses, which have share-alike requirements. The original BSD license was used for its namesake, the Berkeley Software Distribution (BSD).    
	  * *Apple Public Source License:*    
* *Copyleft (protective license):*  
Copyleft is the practice of granting the right to freely distribute and modify intellectual property with the requirement that the same rights be preserved in derivative works created from that property. 
Copyleft software licenses are considered protective or reciprocal in contrast with permissive free software licenses, and require that information necessary for reproducing and modifying the work must be made available to recipients of the software program, or binaries. This information is most commonly in the form of source code files, which usually contain a copy of the license terms and acknowledge the authors of the code.  
	  * *GPL: GNU General Public License:*  
	A series of widely-used free software licenses that guarantee end users the freedom to run, study, share, and modify the software. The GPL series are all copyleft licenses, which means that any derivative work must be distributed under the same or equivalent license terms. GPL was the first copyleft license for general use.    
	  * *AGPL: GNU Affero General Public License:*  
	 The GNU Affero General Public License is a modified version of the ordinary GNU GPL version 3. It has one added requirement: if you run a modified program on a server and let other users communicate with it there, your server must also allow them to download the source code corresponding to the modified version running there. The purpose of the GNU Affero GPL is to prevent a problem that affects developers of free programs that are often used on servers.  

#### Coordinator to be trusted
Do we need to trust a centralised authority like coordinator somewhere in the process of starting, using or quitting the service of the wallet?

#### Devices
The availability on distinctive devices and operating systems

#### Bitcoin Core Node
Which bitcoin Core node on your own system will be installed and used?  
Either a DIY installed node, Nodl, Raspiblitz, Embassy, MyNode or via Electrum Personal Server (or similar).  
#### Net available 
Which bitcoin networks are availalbe in the wallet via the Bitcoin Node connected? Mainnet, Testnet, Regtestnet, Lightning Network.

### Objective
What was the explicit intial idea to start the project?

#### Utilizes 2FA
Two-factor authentication (also known as 2FA) is a type, or subset, of multi-factor authentication. It is a method of confirming users' claimed identities by using a combination of two different factors. Does the wallet support 2FA? Which types of 2FA (like Google, Apple, Yubi, ....)?
#### Cloud integration
Like iCloud, DropBox, etc....
#### Account xprv can be synced to cloud service
TBW
#### Does accounting
TBW
#### Buy and sell bitcoin
Can you directly buy and sell bitcoin from the wallet? Either via (decentralized) exchanges or peer-to-peer.  
#### Signs psbt with
Partially Signed Bitcoin Transactions (PSBTs) are a data format that allows wallets and other tools to exchange information about a Bitcoin transaction and the signatures necessary to complete it (BIP-174).
A PSBT can be created that identifies a set of UTXOs to spend and a set of outputs to receive that spent value. Then information about each UTXO that’s necessary to generate a signature for it can added, possibly by a separate tool, such as the UTXO’s script or its precise bitcoin value.  
The PSBT can then be copied by any means to a program that can sign it. For multisig wallets or cases where different wallets control different inputs, this last step can be repeated multiple times by different programs on different copies of the PSBT. Multiple PSBTs each with one or more necessary signatures can be integrated into a single PSBT later. Finally, that fully signed PSBT can be converted into a complete ready-to-broadcast transaction.  
#### Multisig wallet creation  
A multi-signature system (or multisig) would require n participants to sign the same transaction and send the n signatures to the system. This is much better, except for the fact that n signatures means that the transaction size increases linearly with the number of signers required.  
Read for more details: https://www.cryptologie.net/article/486/difference-between-shamir-secret-sharing-sss-vs-multisig-vs-aggregated-signatures-bls-vs-distributed-key-generation-dkg-vs-threshold-signatures/  
#### Uses hot wallets on your node
TBW
#### Decentralized identity creation  
Decentralized identifiers (DIDs) are a new type of identifier that enables verifiable, decentralized digital identity. A DID identifies any subject (e.g., a person, organization, thing, data model, abstract entity, etc.) that the controller of the DID decides that it identifies. In contrast to typical, federated identifiers, DIDs have been designed so that they may be decoupled from centralized registries, identity providers, and certificate authorities.  
Read for more details: https://www.w3.org/TR/did-core/  
#### Developer community 
An important part of decentralisation is the number of skilled developers involved to oversee the whole codebase and who are able to contribute to code, test and document the system.

### Type of wallet
* Desktop:
Is the wallet available as a desktop version? If so, what operatinng systems are supported (Mac-OS / Windows / Linux)? Are there any minimum specifications concerning versions and developer frameworks.
* Mobile:
Is the wallet available as a mobile version? If so, for what devices and operating systems (IOS / Android)?. Are there any minimum requirements for the devices or operating systems?
* Docker
Is the wallet available as (part of) a self hosted Docker based suite of software.
#### Difference
Main distinctive feature of a wallet compared to the others

#### Import
Importing keys
#### Node wallet access: Trusted nodes
Gordian Wallet does not give you access to every wallet on the node, Fully Noded does
#### Mix or coinjoin
Broadly speaking, coin mixing could refer to any activity that involves the obfuscation of funds by substituting them with others. However, in the cryptocurrency space, coin mixing commonly denotes a service provided by a third-party. Typically,  the service providers take users’ coins (and a small fee), and return coins that have no link to the sent ones. These services are also known as tumblers or mixers.
CoinJoin is a trustless method for combining multiple Bitcoin payments from multiple spenders into a single transaction to make it more difficult for outside parties to determine which spender paid which recipient or recipients. Unlike many other privacy solutions, coinjoin transactions do not require a modification to the bitcoin protocol.
#### Pricing mechanism
How is the project financed, does the wallet generate license fees or receive donation?

### Hardware wallet integration
Is the wallet compatible with hardware wallets? If so, which hardware wallets: Trezor / Ledger / Cold Card / KeepKey / BitBox / Others?<br/>
Several products listed in rows below the header in [comparison](./FNcompGordian#Differences-and-simularities-matrix)

### Node connection
Several products listed in rows below the header in [comparison](./FNcompGordian#Differences-and-simularities-matrix)
#### Node wallet access
Is the wallet software able to control the Node's own wallets?

#### Central servers: 
Does the wallet use central servers at all, for example for coinjoin.
#### Spectrum of privacy measures
Like new addresses for each transaction, avoiding Sybill attacks, Tor and VPN support, Ricochet

### Technical
Several topic listed in rows below the header in [comparison](./FNcompGordian#Differences-and-simularities-matrix)

#### Github  
The address of the project's virtual working place on the internet.  
At the heart of GitHub is Git, an open source project started by Linux. GitHub manages and stores revisions of projects. Although it’s mostly used for code, Git could be used to manage any other type of file. Think of it as a filing system for every draft of a document.  
#### Coinjoin mixing vulnerability
Samourai Wallet has disclosed a couple of Wasabi vulnerabilities. Essentially, the coinjoin mixing for Wasabi cancels itself out if done consecutively. There are some assumptions in the coinjoin code that unfortunately make mixing vulnerable to disclosure. There's some tensions between the two companies which has been ongoing for some time. That said, the competition between them seems to have created better products for both of them.
#### Lightning Enabled  
Answer with Yes/No.  
Is this a Lightning Wallet (too)?  
Lightning is a decentralized network using smart contract functionality in the blockchain to enable instant payments across a network of participants.  
Read more: https://lightning.network/  
#### BIP Support  
Mention unique privacy and security enhancing BIPs used by the wallet.  
A Bitcoin Improvement Proposal (BIP) is a standard for proposing changes to the Bitcoin protocol, or in some cases a source for information for the Bitcoin community. Additionally, some BIPs are proposed changes to the BIP process itself.  
Read more:  https://github.com/bitcoin/bips  

# Optional feature to compare (not yet listed!)
#### Stealth mode feature
Stealth Mode will hide your Wallet install from the Android or IOS home screen and launcher. While in stealth mode you will not receive notifications of deposits into your wallet. Stealth Mode is good for hiding the fact you have a wallet on your device from casual observers. Anyone who has extended unrestricted access to your device would be able find the Wallet on the device. 