# KYC Verification System Using Blockchain

## Introduction to Blockchain
A blockchain is a digital and distributed ledger of transactions, recorded and replicated in realtime across a network of computers or nodes.
Every transaction must be cryptographically validated via a consensus mechanism executed by the nodes before
being permanently added as a new “block” at the end of the “chain.”
There is no need for a central authority to approve the transaction, which is why blockchain is sometimes
referred to as a ```peer-to-peer trustless mechanism```.

Blockchain can be thought of as a linked list with each node containing multiple transactions.
Each transaction has a hash that depends on the previous transactions hash as well.
So, we can see that the order of transactions is important. If we were to change one transaction somewhere,
it would have a ripple effect and change the hash of all subsequent transactions. This is one of the reasons
why blockchain is a powerful medium for storing transactions.

The placing of a transaction in a block is called a successful conclusion to a proof of work challenge,
and is carried out by special nodes called ```miners```.
Proof of Work is a system that requires some work from the service requester, usually meaning processing time by a computer.
Producing a proof of work is a random process with low probability, so normally a lot of trial and error is
required for a valid proof of work to be generated. When it comes to Bitcoins, hash is what serves as a proof of work.
Miners on a Blockchain are nodes that produce blocks by solving proof of work problems.
If a miner produces a block that is approved by an electronic consensus of nodes then the miner is rewarded with coins.
This essentially is the crux of blockchain. ```Proof of Work``` is what is keeping all transactions on the blockchain secure
and protecting it from malicious attempts to alter these transactions.

## Problem Statement
The banks are responsible for completing the KYC procedure while opening accounts. Banks also are required to periodically update their customers’ KYC details. KYC may be a manual, time-consuming, and redundant across institutions.

Blockchain would enable financial institutions to deliver better compliance outcomes, increase efficiency, and improve customer experience.

## Our Solution to the Problem
Users can verify their KYC with any bank of their choice, once verification is successful the transaction is put in a block which after mining is added to the blockchain, from now onwards if user wants to open bank account with any other bank he/she needs to submit only their user id which will be used to trace the earlier KYC verification transaction stored in the blockchain.

## Zero Knowledge Proof
Zero-Knowledge Proofs (ZKP) refer to a proof construction that allows you to convince someone that you know something without
revealing any information about what it is you know in the process. To explain ZKPs with the help of an example consider the following scenario:

### Scenario

Imagine two friends, Alice & Bob. Bob is color-blind. Alice has two identical balls that only differ in color: red and green.
To Bob they seem completely identical and he is skeptical that they are actually distinguishable. Alice wants to prove to him they are in fact differently-colored, but nothing else, thus he does not reveal which one is red and which is green.

Alice gives the two balls to Bob and he hides it. Next, he takes out one ball and displays it. After that he hides the ball again and shows a ball.
There is a 50% probability that he switched the balls. Alice is asked if the ball was switched. She could guess and answer correctly with
a probability of 50% but if this exercise is repeated multiple times, we can see that this probability will eventually become negligible.
So with 5 rounds, he will have a 1 in 32 chance of successfully faking.
With 10 rounds, it is 1 in 1024, and with 20 rounds, it is about one in a million.
This way one can reach any probabilistic level of proof that is desired, although an absolute certainty can never be achieved.

The above proof is zero-knowledge because Bob never learns which ball is green and which is red; but he can indeed verify that the balls differ in color.

### Algorithm for Zero Knowledge Proof

Alice has sensitive data 𝑥 for which she chooses two numbers 𝑝 and 𝑔 . ```𝑝``` can be a large prime and ```𝑔 is a generator for 𝑝```. 
She calculates $y$ as $y = g^xmod(p)$ . Now she performs the following steps to create a zero knowledge proof for 𝑥.

1. Alice chooses a random number 0 ≤ 𝑟 < 𝑝 − 1 and sends it to Bob as $h = g^r mod(p)$
2. Bob receives ℎ and sends back a random bit 𝑏 (could be 0/1).
3. Alice sends 𝑠 = ( 𝑟 + 𝑏𝑥 )𝑚𝑜𝑑(𝑝 − 1 ) to Bob.
4. Bob computes $g^s mod(p)$ which should equal $hy^b mod(p)$

Here Bob acts as a verifier and checks if Alice knows the value of 𝑥 without actually getting to know what 𝑥 is.

## Control Flow of Blockchain

![Cryptography Project](https://user-images.githubusercontent.com/97559428/227742407-250e4b9d-4756-43b4-acd9-afdb7c7f569c.png)

## Screenshots of the working Application

### Register User <br>
<img width="1103" alt="add" src="https://user-images.githubusercontent.com/97559428/232873498-ee57895e-e982-4168-a470-217445b3ef4b.png">

### KYC Verification <br>
<img width="1124" alt="KYC Verification" src="https://user-images.githubusercontent.com/97559428/232873041-d650c71b-20b1-41a8-b3ef-2c04bbf9e49e.png">

### View All Transactions of User
<img width="1109" alt="view user" src="https://user-images.githubusercontent.com/97559428/232874843-c513236a-94b6-4270-a5b8-bb1e5580b208.png">

### Update User (Unsuccessful Transaction)
<img width="1103" alt="Update Details (Unsuccessful)" src="https://user-images.githubusercontent.com/97559428/232877754-701da7e0-e07c-466a-9791-07a8ccabbe0b.png">

### Show Blockchain
<img width="1305" alt="Printing Blockchain" src="https://user-images.githubusercontent.com/97559428/232878692-40664a6f-37c7-454c-9319-823512854452.png">

## Installation

```bash
    node test.js
```

## Authors

- [Pavas Garg](https://www.github.com/pavas23)
- [Saksham Bajaj](https://github.com/SakshamBajaj18)
- [Prachi Shah](https://github.com/pks03)

