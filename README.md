
# Astreum: A Next Generation Blockchain for Computing, Storage and Networking

## Author

Roy R. O. Okello

[Email](mailto:royokello@protonmail.com)

[Github](https://github.com/royokello)

[Twitter](https://twitter.com/RealOkello) 

## Content

- Introduction

- Why Another Blockchain
  - Security
  - Privacy
  - Usability
  - Extensibility
  - Trust

- Astreum
  - Accounts
  - Blocks
  - Transactions
  - Relay Protocol
  - Consensus Protocol

- Roadmap
  - Programmable Accounts
  - Signature Abstraction
  - Relay Privacy & Security
  - Zero Knowledge Validation
  - Storage Protocol
  - Compute Protocol
  - Gateway Protocol
  - Account & Transaction Privacy
  - Treasury Protocol

- Applications

- References

## Introduction
 
The development of blockchain technology has revolutionized the way that we store and share information. Originally used as a platform for the digital currency Bitcoin, blockchain technology can now been applied to a wide range of applications.

One area where blockchain technology has the potential to make a significant impact is in the field of computing, storage, and networking. By using an accounts-based blockchain, it is possible to create a decentralized and distributed platform that enables users to securely share and access computing, storage, and networking resources.

This white paper presents an overview of the concept of an accounts-based blockchain for computing, storage, and networking. We will describe the key features and benefits of this approach. We will also explore the roadmap to acheive such a network.

## Why Another Blockchain

There is a growing need for a new blockchain that is secure, private, usable, and extensible. This is because the current generation of blockchain technology has limitations and challenges that make it difficult to use in many real-world applications.

For example, many existing blockchain systems are vulnerable to security attacks, and are not able to protect the privacy of users on the platform. This can make it difficult to trust and use these systems for sensitive applications, such as financial transactions or personal data storage.

In addition, many existing blockchain systems are not user-friendly, and can be difficult for non-technical users to understand and use. This can limit the adoption and use of these systems, and can prevent them from reaching their full potential.

Finally, many existing blockchain systems are not extensible, and do not provide the flexibility and adaptability needed to support the development of new and innovative applications. This can limit the capabilities of these systems, and can prevent them from evolving and adapting to changing needs and requirements.

### Security

Blockchain technology is often considered to be highly secure, but it is vulnerable to attacks by quantum computers. These powerful machines are capable of performing calculations that are beyond the reach of classical computers, and they could potentially be used to break the cryptographic algorithms that are used to secure blockchain systems.

Post-quantum cryptography is a field of research that is focused on developing cryptographic algorithms that are resistant to attacks by quantum computers. By using post-quantum secure algorithms, it is possible to protect blockchain accounts and messages from being compromised by quantum computers.

By using post-quantum secure algorithms, it is possible to protect blockchain accounts and messages from being compromised by quantum computers. This can help to ensure the long-term security and integrity of the blockchain, and can help to prevent the loss of sensitive information or funds.

### Privacy

Mix networks are a type of privacy-enhancing technology that can be used to protect the privacy of users on a blockchain. Mix networks work by routing data through a series of intermediate nodes, known as mixers, before it reaches its final destination. This makes it difficult for attackers to track the origin or destination of the data, and can help to protect the privacy of users on the blockchain.

One of the key benefits of mix networks is that they can provide strong privacy guarantees without requiring users to trust any specific party. This is because the mixers in a mix network do not have access to the full end-to-end path of the data, and cannot therefore link the origin and destination of the data.

### Usability

Signature abstraction improves the usability of the platform by making it easier for users to interact with the blockchain and manage their accounts and assets. This can make the platform more accessible to a wider range of users, which can help drive adoption and increase the value of the platform.

### Extensibility

The Fusion Language is a dialect of Lisp Language. This means that it can be easily extended with new features and capabilities, allowing programmers to tailor the language to their specific needs. Some of the benefits of this extensibility include:

- Increased flexibility: Fusion can be customized to suit a wide range of programming tasks. This makes it a versatile language that can be used for a variety of purposes, including artificial intelligence, natural language processing, and other domains.

- Improved productivity: The ability to easily extend Fusion with new features can help programmers be more productive. For example, they can create custom functions and data structures that are specifically designed to solve the problem at hand, rather than being limited to the features provided by the language itself.

- Greater expressiveness: Fusion's extensibility allows programmers to express their ideas and solutions in a more natural and intuitive way. This can make the code easier to read and understand, and can also help to reduce the amount of time and effort required to write and maintain the code.

- Stronger support for dynamic environments: Fusion can be used in dynamic environments, such as user interfaces, where the structure and behavior of the system can change at runtime. The language's extensibility can make it easier to deal with these changes, allowing programmers to quickly and easily adapt to new requirements and conditions.

### Trust

Zero-knowledge validation is a cryptographic technique that allows one party to prove to another party that a statement is true, without revealing any additional information about the statement or the underlying data.

Benefits of using zero-knowledge validation are:

- Greater scalability: Zero-knowledge validation allows for the verification of data on the blockchain without requiring the entire network to participate in the process. This can help to reduce the computational overhead of the blockchain, and can make it more scalable and efficient.

- Enhanced trust and confidence: By using zero-knowledge validation, it is possible to build trust and confidence in the security of the blockchain as all nodes validate the blockchain.

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
                                . - - - - - - - - - - - - - - - - - - - - - - - .
                                ^                       ^                       ^
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                        |    balance    |       |    counter    |       |    storage    |
                        + - - - - - - - +       + - - - - - - - +       + - - - - - - - +

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


### Relay Protocol

                        + - - - - - - - +
                        |   Envelope    |
                        + - - - - - - - +
                                ^
                        . - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - .
                        ^                       ^                       ^                       ^
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                |    Message    |       |     Nonce     |       |      Ping     |       |     Time      |
                + - - - - - - - +       + - - - - - - - +       + - - - - - - - +       + - - - - - - - +
                        ^
                . - - - - - - - - - - - .
                ^                       ^
        + - - - - - - - +       + - - - - - - - +
        |     Body      |       |     Topic     |
        + - - - - - - - +       + - - - - - - - +

`Routes`

- Validation

`Topics`

- Block
- BlockRequest
- RouteRequest
- RouteResponse
- Transaction

### Consensus Protocol

Astreum uses a proof of stake consensus protocol for executing transactions and creating new blocks by validators.

A validators must be staked, by sending `Solar` to the `Consensus Account`, to participate in the protocol.

The block time target is three seconds. A slot is the three seconds period when new blocks are created.

Slots are allocated pro-rata to a validator's stake.

A slot miss occurs when a validator does not create or submits a malicious block when selected.

Slot selection determines the validator for the next block at any time:

- Check slot misses from the latest block
- If no slot miss, the latest block delay output is used as the seed in the weighted random address selector
- If slot misses, the linear-feedback shift register, shifted to the number of slot misses, of the latest block delay output is used as the seed in the weighted random address selector

Validators who miss a slot get half their stake returned until 1 `Solar` is left.

Transactions are ordered by the validator.

Validators spend 1-3 seconds computing a delay output from a verifiable delay function(vdf).

The vdf difficulty is determined by the time taken to create the previous 100 blocks.

The creator of a new block is payed a fee of 10^12 `Solar`.

The cost of a new account is 2 * 10^9 `Solar`.

The transaction cost is set at 10^6 `Solar`.

The valid chain is the longest chain.

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
        |     Leaf?     |       |    <= 32kb    |
        + - - - - - - - +       + - - - - - - - +
```

- 📜 Fusion Language
- ⚙️ Astreum Machine
- ✅ Add Code to Account Details

### Signature Abstraction

- 🔒 Digital Signature Algorithm Abstraction enables Post Quantum Security and Social Recovery.

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

### Zero Knowledge Astreum Machine

- ✅ Zero Knowledge Block Validation

### Storage Protocol

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
                |  storage proof & pricing 
                |
               \|/
        + - - - - - - - +
        |    Indexer    |
        + - - - - - - - +
                |
                |  index proof
                |
               \|/
        + - - - - - - - +
        |   Contract    |
        + - - - - - - - +
```

Storage
- 🏷 Object Ownership, Storage Type(Perpetual/Limited) & Funding
- 🤝 Retreival Payment Channels

#### Relay
- ☁ Storage Route
- 🗃 Get & Object Message Topic

### Compute Protocol

- ⚡ Compute Relay Route
- 🏷️ Compute Pricing
- 🤝 Compute Payment Channels

### Gateway Protocol

- 📡 Gateway Connections
- 🏷️ Networking Pricing
- 🤝 Gateway Payment Channels

### Account & Transaction Privacy

- 🔒 Confidential Transactions
- 👤 Private Accounts

### Treasury Protocol

- 💵 Solar Creation
- 📊 Supply Control

## Applications

- Perpetual Archives
- Self Hosting
- Confidential Accounts
- ML Acceleration
- zkML
- Open Networking
- App Acceleration
- User Powered Apps
- Deploy Anything

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
