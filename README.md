
# Astreum: A Next Generation Blockchain for Computing, Storage and Networking

## Author

- Roy R. O. Okello: [Email](mailto:royokello@protonmail.com), [GitHub](https://github.com/royokello) & [Twitter](https://twitter.com/RealOkello)

## Abstract

## Content

- Introduction

- Why Another Blockchain
  - Security
  - Privacy
  - Usability
  - Extensibility
  - Trust
  - Tokenomics

- Astreum
  - Accounts
  - Blocks
  - Transactions
  - Relay
  - Consensus
  - Synchronization

- Roadmap
  - Programmable Accounts
  - Signature Abstraction
  - Relay Privacy & Security
  - Zero Knowledge Synchronization
  - Storage
  - Compute
  - Gateway
  - Account & Transaction Privacy
  - Treasury

- Applications
  - Perpetual Storage
  - Self Hosting
  - Confidential Apps
  - User Powered Apps
  - App Acceleration
  - Finance

- References

## Introduction

Astreum is a next generation blockchain designed to address the challenges of storage, compute, and networking in the modern digital landscape. With the exponential growth of data and the increasing demand for secure, scalable, and decentralized solutions, Astreum offers a unique approach to these issues by leveraging the power of blockchain technology. Astreum provides a fast and secure platform for storing and processing data, while also enabling seamless integration with existing networks. In this white paper, we will explore the technical features and benefits of Astreum, as well as its potential applications.

## Why Another Blockchain

The blockchain ecosystem has revolutionized many industries, offering a range of benefits including security, transparency, and decentralization. However, there are several challenges that need to be addressed in order to maximize the potential of blockchain technology. One of the most significant challenges is the potential security vulnerability of traditional cryptographic algorithms to attacks by quantum computers. This is a pressing issue, as quantum computing capabilities continue to advance rapidly, and could potentially render current cryptographic algorithms obsolete.

Another key challenge is the lack of account privacy in blockchain. While blockchain technology offers a high degree of transparency, this can also mean that users' personal information and transaction data can be publicly accessible. This poses a significant privacy risk and can make users vulnerable to fraud and identity theft.

In addition to these challenges, the complexity of user interfaces can also be a barrier to the adoption of blockchain technology. Many blockchain platforms have complex user interfaces that require technical expertise, which can be a significant hurdle for users with limited technical knowledge.

Furthermore, the extensibility of the blockchain is also a critical issue that needs to be addressed. Many blockchain platforms have limitations on the types and formats of data that can be represented on the blockchain, which can limit their usefulness and potential applications.

Finally, trust in the validation of the blockchain is a crucial issue that needs to be addressed. Many blockchain networks rely on a small number of validators, which can create potential vulnerabilities if the validators are compromised. Ensuring trust in the validation of the blockchain is essential to maintaining the integrity and reliability of a blockchain.

### Security

Currently, one of the major security concerns of blockchains is the potential vulnerability of traditional cryptographic algorithms to attacks by quantum computers. This vulnerability could lead to the compromise of private keys, allowing hackers to access and manipulate the blockchain. To address this issue, Astreum aims to use post-quantum secure algorithms for both account and message security. This means that the cryptographic algorithms used by Astreum are resistant to attacks by both classical and quantum computers. By using these advanced algorithms, Astreum is aiming to provide a higher level of security for its users, making it more resistant to attacks and fraud.

### Privacy

The current lack of privacy in blockchain technology is a major concern for users. Although blockchain transactions are visible to all participants, the transparent nature of these transactions makes it easy to trace and identify users. This is a significant issue as it could lead to the loss of privacy and security for blockchain users. To address this problem, Astreum aims to use private accounts that keep account details such as the balance hidden from other users. Additionally, the platform will incorporate confidential transactions that conceal transaction data, making it difficult for anyone to identify the parties involved in a transaction. Furthermore, Astreum will employ mixing techniques on messages sent on the network to further enhance privacy. By utilizing these features, Astreum is aiming to provide a higher level of privacy for its users, making it a more secure and reliable platform for transactions.

### Usability

One of the main issues with blockchain technology is the complexity of its user interface, which makes it difficult for many users to manage their accounts effectively. To address this problem, Astreum aims to introduce account signature abstraction. This feature will enable better account management for users, including account recovery and theft mitigation. With account signature abstraction, users will be able to manage multiple accounts with ease, without the need for complex and time-consuming management procedures. Additionally, the feature will enable users to recover lost or stolen accounts more efficiently and securely, reducing the risk of fraudulent activities. This innovative approach to usability could significantly improve the user experience of blockchain technology, making it more accessible and user-friendly for everyone.

### Extensibility

Extensibility is a major concern for blockchain technology as it limits the type and variety of data that can be represented on the blockchain. To address this problem, Astreum aims to represent everything as Astreum Objects. This means that any kind of data or program can be represented on the blockchain, making it more flexible and adaptable to different use cases. Additionally, Astreum uses a Lisp programming language dialect called Fusion, which can be easily extended with new features and capabilities. This allows developers to create smart contracts that are highly customizable and can evolve over time as new requirements emerge. With Astreum's approach to extensibility, the platform has the potential to become a highly versatile and adaptable blockchain technology that can be used in a wide range of applications, including finance, healthcare, supply chain management, and more.

### Trust

Another concern with blockchain technology is trust, specifically in the validation of the blockchain. Many blockchain networks rely on a small number of validators, which can lead to centralization and the potential for fraudulent activity. To address this problem, Astreum aims to use zero-knowledge cryptography to enable the validation of the blockchain by every node. This means that every node in the network can validate the authenticity of the transactions on the blockchain without having to process all the transactions. This approach to validation ensures that the blockchain is decentralized, transparent, and secure.

### Tokenomics

## Astreum

### Accounts

                + - - - - - - - +
                |    account    |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |    address    |       |    details    |
        + - - - - - - - +       + - - - - - - - +
                                        ^
                                . - - - - - - - - - - - - - - - - - - - - - - - . - - - - - - - - - - - .
                                ^                       ^                       ^                       ^
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                        |    balance    |       |      code     |       |    counter    |       |    storage    |
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

### Blocks

                + - - - - - - - +
                |     block     |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |    details    |       |   signature   |
        + - - - - - - - +       + - - - - - - - +
                ^
                |
                |       + - - - - - - - +
                | - - - |    accounts   |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     chain     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     data      |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |   difficulty  |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     delay     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |    number     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |    previous   |
                |       + - - - - - - - +
                |       
                |       + - - - - - - - +
                | - - - |    receipts   |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     solar     |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |     time      |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                | - - - |  transactions |
                |       + - - - - - - - +
                |
                |       + - - - - - - - +
                + - - - |   validator   |
                        + - - - - - - - +

### Transactions

                        + - - - - - - - +
                        |  transaction  |
                        + - - - - - - - +
                                ^
                        . - - - - - - - - - - - .
                        ^                       ^
                + - - - - - - - +       + - - - - - - - +
                |    details    |       |   signature   |
                + - - - - - - - +       + - - - - - - - +
                        ^
                        |
                        |       + - - - - - - - +
                        | - - - |     chain     |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |    counter    |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |     data      |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |   recipient   |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        | - - - |    sender     |
                        |       + - - - - - - - +
                        |
                        |       + - - - - - - - +
                        + - - - |     value     |
                                + - - - - - - - +


### Relay

                        + - - - - - - - +
                        |   Envelope    |
                        + - - - - - - - +
                                ^
                        . - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - .
                        ^                       ^                       ^                       ^
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                |   Encrypted   |       |    Message    |       |     Nonce     |       |     Time      |
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                                                ^
                                    . - - - - - - - - - - - .
                                    ^                       ^
                             + - - - - - - - +       + - - - - - - - +
                             |     Body      |       |     Topic     |
                             + - - - - - - - +       + - - - - - - - +

`Routes`

- Peer
- Validation

`Topics`

- Object Request
- Object Response
- Ping
- Route
- Route Request
- State
- State Request
- Transaction

### Consensus

Astreum employs a Proof of Stake (PoS) consensus protocol for executing transactions and creating new blocks. This consensus protocol involves validators who are responsible for creating new blocks and ensuring the validity of transactions. Validators must stake a certain amount of Astreum's native cryptocurrency, Solar, by sending it to the Consensus Account, to participate in the protocol.

The target block time for Astreum is three seconds, and this period is divided into slots. Validators are allocated slots based on their stake, with higher stakes receiving a proportionally greater number of slots. In the event that a validator fails to create or submits a malicious block during their allocated slot, a slot miss occurs.

Slot selection for the next block is determined by checking the slot misses from the latest block. If there are no slot misses, the latest block delay output is used as the seed in the weighted random address selector. If slot misses have occurred, the latest block delay output is hashed to the number of slot misses to produce the seed for the weighted random address selector.

Validators who miss a slot are refunded half their stake until only 1 Solar is left. Transactions are ordered by the validator, and validators spend 1-3 seconds computing a delay output from a verifiable delay function (VDF) to create a new block. The VDF difficulty is determined by the time taken to create the previous 100 blocks.

The creator of a new block is paid a fee of 10^12 Solar, and the cost of creating a new account is set at 2 * 10^9 Solar. The transaction cost is fixed at 10^6 Solar.

The valid chain is determined by the longest chain, and any other chain will be discarded. This ensures that the network will always converge on a single valid chain. The PoS consensus protocol used in Astreum ensures the security and integrity of the network while allowing for efficient transaction processing and block creation.

### Synchronization

## Roadmap

`Overview`

```
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
        |  Fusion       |       |  Storage      |       |  Compute      |
        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        |  Consensus & Accounts                                         |
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        |  Relay                                                        |
        + - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
        + - - - - - - - - - - - - - - +   + - - - - - - - - - - - - - - +
        |  Gateway                    |   |  Internet                   |
        + - - - - - - - - - - - - - - +   + - - - - - - - - - - - - - - +
```

### Programmable Accounts

- 🎄 Astreum Objects

`Object Structure`

```
                + - - - - - - - +
                |    Object     |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |     Type      |       |     Data      |
        + - - - - - - - +       + - - - - - - - +
                                
```

- 📜 Fusion Language
- ⚙️ Astreum Machine
- ✅ Add Code to Account Details

### Signature Abstraction

- 🔒 Digital Signature Algorithm Abstraction enables Post Quantum Security and Account Recovery.

`New Address Structure`

```
                + - - - - - - - +
                |    Address    |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |  DSA Fusion   |       |   Public Key  |
        |  App Object   |       + - - - - - - - +
        + - - - - - - - +
```

### Relay Privacy & Security

- 🔀 Address Mixing
- 🔒 Public Key Exchange Abstraction enabling more algorithms including Post Quantum Secure.

`New Sender Structure`

```
                + - - - - - - - +
                |    Sender     |
                + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |  PKE Fusion   |       |   Public Key  |
        |  App Object   |       + - - - - - - - +
        + - - - - - - - +
```

### Zero Knowledge Synchronization

### Storage

#### Storage Contract

Logic
- 🗄 Object Put
- 🗑️ Object Delete
- ✅ Storage Verification & Payment

```
        + - - - - - - - +
        |    Storer     |
        + - - - - - - - +
                |
                |  storage proof
                |
               \|/
        + - - - - - - - +
        |    Indexer    |
        + - - - - - - - +
                |
                |  index & storage proofs
                |
               \|/
        + - - - - - - - +
        |   Validator   |  verification & payment
        + - - - - - - - +
```

Storage
- 🏷 Object Ownership, Storage Type(Perpetual/Limited) & Funding
- 🤝 Retreival Payment Channels

#### Relay
- ☁ Storage Route
- 🗃 Get & Object Message Topic

### Compute

- ⚡ Compute Relay Route
- 🏷️ Compute Pricing
- 🤝 Compute Payment Channels

### Gateway

- 📡 Gateway Connections
- 🏷️ Networking Pricing
- 🤝 Gateway Payment Channels

### Account & Transaction Privacy

- 🔒 Confidential Transactions & Account Apps
- 👤 Private Accounts

### Treasury

- 💵 Solar Creation
- 📊 Supply Control

## Applications

- Perpetual Storage

Astreum has a unique storage protocol that allows users to pay for data to be stored perpetually on the blockchain. This perpetual storage feature has significant implications for data storage as it enables users to store critical data securely and for an indefinite period. With the perpetual archive feature, users can be assured that their data will be stored safely and securely, without the risk of data loss due to system failure, hacking, or other security breaches. Additionally, the perpetual archive feature has the potential to create new opportunities for data sharing and collaboration, as it provides a secure and reliable platform for the storage of critical information. With the ability to pay for perpetual storage, Astreum's storage protocol has the potential to become a highly attractive solution for businesses and organizations that require secure and reliable data storage for the long term.

- Self Hosting

Astreum's storage protocol enables users to host their own data and only pay for indexing. This self-hosting feature is a significant innovation in the field of data storage, as it provides users with greater control over their data while minimizing storage costs. With self-hosting, users can host their data on their own servers and only pay for indexing, which means that the data is searchable and accessible from anywhere in the world. This approach to data storage can provide users with greater security and privacy as their data is stored on their own servers, reducing the risk of data breaches and cyber attacks. Additionally, self-hosting can significantly reduce storage costs, as users only pay for indexing, which is much cheaper than traditional data storage methods. With the ability to self-host and only pay for indexing, Astreum's storage protocol has the potential to become a highly attractive solution for businesses and individuals who require secure and reliable data storage at a lower cost.

- Confidential Apps

Astreum includes confidential apps, which are applications whose procedures are concealed, but their results can be proved. This innovative approach to application development has significant implications for the creation of confidential programmable accounts on the blockchain. Confidential programmable accounts provide users with enhanced privacy and security by enabling them to create accounts with confidential procedures, such as confidential smart contracts. With confidential programmable accounts, users can keep their account details private, including their application code and data, while still being able to conduct transactions and execute smart contracts. This approach to accounts can significantly enhance privacy and security, particularly for users who require greater confidentiality and anonymity in their transactions

- User Powered Apps

Astreum's blockchain technology has many applications in creating user-powered content, enabling developers and creators to avoid the initial large capital expenditure on hosting and networking fees while scaling distribution automatically. With the Astreum blockchain, developers and creators can build decentralized platforms for content creation and distribution, allowing users to directly contribute and participate in the creation and curation of content. By leveraging the decentralized infrastructure provided by Astreum, developers can build platforms that are scalable and cost-effective, eliminating the need for centralized servers and reducing the associated costs. This makes it easier for creators and developers to bring their content to market, while also enabling a more equitable distribution of rewards to users who contribute to the platform.

- App Acceleration

Astreum, a new blockchain platform, introduces a unique compute protocol that provides application acceleration. With Astreum's compute protocol, all applications are written in the Fusion language, and every node can provide a Fusion virtual machine, which is a runtime for Fusion applications. This innovative approach to application development has significant implications for accelerating large computations on the blockchain. With the ability to use a Fusion virtual machine, users can execute large computations more efficiently and with greater speed, resulting in significant time and cost savings. 

Additionally, the Fusion language is highly versatile and can be easily extended with new features and capabilities, making it an ideal choice for complex computations and sophisticated applications. Fusion language is a Lisp dialect that provides a high level of expressiveness, flexibility, and efficiency. It enables the creation of complex and sophisticated applications that require significant computational power, such as machine learning algorithms, artificial intelligence systems, and financial models. Moreover, the language is highly extensible, which means that new features and capabilities can be easily added to it, making it an ideal choice for a wide range of applications.

<!-- - Finance -->

## References

- Bitcoin: A Peer-to-Peer Electronic Cash System - Satoshi Nakamoto
- Ethereum White Paper - Vitalik Buterin
- Ethereum Yellow Paper - Gavin Wood
- Kademlia: A Peer-to-Peer Information System Based on the XOR Metric - Petar Maymounkov & David Mazières
- Recursive Functions of Symbolic Expressions and Their Computation by Machine - John McCarthy
- PostScript Language Reference Manual - John Warnock, Charles Geschke, Doug Brotz, Ed Taft and Bill Paxton
- High-speed high-security signatures - Daniel J. Bernstein, Niels Duif, Tanja Lange, Peter Schwabe and Bo-Yin Yang
- CRYSTALS-Dilithium - Shi Bai, Léo Ducas, Eike Kiltz, Tancrède Lepoint,Vadim Lyubashevsky, Peter Schwabe, Gregor Seiler and Damien Stehlé
- CRYSTALS-Kyber - Roberto Avanzi, Joppe Bos, Léo Ducas, Eike Kiltz, Tancrède Lepoint, Vadim Lyubashevsky, John M. Schanck, Peter Schwabe, Gregor Seiler, and Damien Stehlé.
- Efficient verifiable delay functions - Benjamin Wesolowski
- PLONK: Permutations over Lagrange-bases for Oecumenical Noninteractive arguments of Knowledge - Ariel Gabizon, Zachary J. Williamson and Oana Ciobotaru
- Aurora: Transparent Succinct Arguments for R1CS - Eli Ben-Sasson, Alessandro Chiesa, Michael Riabzev, Nicholas Spooner, Madars Virza and Nicholas P. Ward

