
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
  - Secure Savings and Earnings
  - Microtransactions

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
                | - - - |     aster     |
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

Astreum employs a Proof of Stake (PoS) consensus protocol for executing transactions and creating new blocks. This consensus protocol involves validators who are responsible for creating new blocks and ensuring the validity of transactions. Validators must stake a certain amount of Astreum's native cryptocurrency, Aster, by sending it to the Consensus Account, to participate in the protocol.

The target block time for Astreum is three seconds, and this period is divided into slots. Validators are allocated slots based on their stake, with higher stakes receiving a proportionally greater number of slots. In the event that a validator fails to create or submits a malicious block during their allocated slot, a slot miss occurs.

Slot selection for the next block is determined by checking the slot misses from the latest block. If there are no slot misses, the latest block delay output is used as the seed in the weighted random address selector. If slot misses have occurred, the latest block delay output is hashed to the number of slot misses to produce the seed for the weighted random address selector.

Validators who miss a slot are refunded half their stake until only 1 Aster is left. Transactions are ordered by the validator, and validators spend 1-3 seconds computing a delay output from a verifiable delay function (VDF) to create a new block. The VDF difficulty is determined by the time taken to create the previous 100 blocks.

The creator of a new block is paid a fee of 10^12 Aster, and the cost of creating a new account is set at 2 * 10^9 Aster. The transaction cost is fixed at 10^6 Aster.

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

- 💵 Aster Creation
- 📊 Supply Control

## Applications

### Perpetual Storage
Astreum's innovative storage protocol allows users to store data securely on the blockchain indefinitely. This feature provides long-term data preservation without the risk of data loss, be it due to system failures, hacking, or security breaches. The perpetual storage capability opens the door to new possibilities in data sharing and collaboration. Organizations, in particular, benefit from a secure and reliable solution for long-term data storage, making Astreum's offering highly attractive for their needs.

### Self Hosting
With Astreum's storage protocol, users gain the ability to self-host their data while only paying for indexing. This approach empowers users to retain control over their data, enhancing data security and reducing storage costs significantly. Simultaneously, data remains globally accessible, which is essential in today's interconnected world. Self-hosting can lead to substantial savings, making it a cost-effective solution for secure data storage.

### Confidential Apps
Astreum introduces confidential apps, a groundbreaking approach to application development. These apps conceal their procedures, allowing only their results to be verified. This innovation is particularly valuable for the creation of confidential programmable accounts on the blockchain, ensuring enhanced privacy and security. Users can create accounts with confidential procedures, such as confidential smart contracts, which is a game-changer for those who prioritize transaction confidentiality and anonymity.

### User Powered Apps
With Astreum, developers and creators can build user-powered content platforms without the burden of paying hosting fees. Instead, users cover the costs associated with the retrieval, running, and storage of applications. This approach eliminates the financial barriers typically associated with content creation and distribution. Users actively contribute to content creation, fostering more equitable rewards and reducing reliance on centralized servers, making it easier for creators and developers to bring their content to a global audience.

### App Acceleration
Astreum's compute protocol accelerates the execution of large computations on the blockchain. This efficiency is achieved through the use of the Fusion language and virtual machines, enabling faster and more cost-effective processing of complex applications, including machine learning and artificial intelligence. The versatility and extensibility of the Fusion language make it a versatile choice for various applications.

### Secure Savings
Within the Astreum blockchain ecosystem, users can stake their native currency, Aster, to secure their savings and earn rewards. Staking Aster contributes to network stability and the support of Aster's price stability. This staking system provides a secure and sustainable alternative to the traditional practice of storing funds on exchanges, which can be risky.

### Microtransactions
Aster, Astreum's native currency, serves as a catalyst for microtransactions in the digital realm. Its inherent stability and small denomination make it an attractive choice for digital businesses looking to embrace microtransactions. Aster enables efficient transactions even for the smallest units of value, which is pivotal for pricing services such as the storage and retrieval of minuscule data amounts, transforming digital commerce and enabling new opportunities in the evolving online landscape.

### Enhanced Security
Astreum takes security seriously by implementing signature and key abstraction. This approach allows the integration of various cryptographic algorithms, prioritizing practical security and user-friendliness. This ensures that Astreum remains secure even in the face of challenges posed by quantum computing, making it a trusted choice for individuals and organizations looking to safeguard their digital assets. The support for Digital Signature Algorithms (DSA) with advanced features such as account recovery further enhances security.

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

