# Bitcoin Mining
In the Bitcoin ecosystem, miners primarily serve 3 purposes:
1. Processing of new transactions into the blockchain
2. Creation of new bitcoin
3. Securing the network

This is great and all, but what are they actually doing and how does it
fulfil these 3 purposes?

## Topic Primer
In computer cryptography you will frequently see the term "hash". You may need
to "get a hash" or you may "check a hash". Creating a new hash may be referred to
as "hashing". In this guide, we will be using the _SHA-256_ hashing algorithm,
but do note that other algorithms do exist. They generally work the same.

A _hash_ is a string representation of data derived from input data. For example,
the hash of the word "hello" is `2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824`.
The hash of the word "howdy" is `0f1128046248f83dc9b9ab187e16fad0ff596128f1524d05a9a77c4ad932f10a`.
The hash of a Windows 10 disc file is `6c6856405dbc7674eda21bc5f7094f5a18af5c9bacc67ed111e8f53f02e7d13d`.

In the case of SHA256, the output will always be a 64-character string. It doesn't matter if you input
a single character or a 20GB movie file, you will always wind up with a 64-character string. 

The purpose of a hash is to validate the _integrity_ of data. Two people hashing the same file
should always wind up with the same hash. Even a single _1_ flipped to a _0_ would result in a
completely different hash. 

It is important to note that hashing is a _one-way_ function. You cannot work backwards from a hash
to find the input data. It's only useful to verify that the data you already have is correct.

## Mining Process
In Bitcoin, transactions get grouped up into "blocks". New blocks get created approximately every 10 minutes.
Miners are resonsible for creating these blocks.

For a miner to create a block, they must "find a valid hash". In terms of Bitcoin, a hash is considered valid
when it starts with a certain number of zeros. The amount of zeros required is referred to as the "difficulty"
of the network (More zeros = more difficult).

To do this task, miners compile as many pending transactions as they can fit into a block then they add in 2
pieces of data, hash of the previous block and a random value called the _nonce_ ("Number used once"). 
This looks like:
```
((transaction data) + (last block hash) + nonce) = 444931804e5a57407c1e7635b63c259a2ddaffd8910ace2634a6e9bb5e39d5a5
```

In the above example. the hash isn't valid because it doesn't start with any zeros. So the miner will change the value of
the nonce and check it again. The miner will repeat this process until they find a valid block. At a micro-scale, mining
could be viewed similar to a lottery that is played thousands of times every second. Each entry to the lottery costs
the electricity required to make a hash.

Once a valid block is found, the miner broadcasts it to the network and all nodes in the network will add it to their copy of the blockchain.
The miner also gets a "block reward" and all the transaction fees in their block.

This whole process is what we call "proof of work" and it is how Bitcoin has rules without an authority. To mine a block, you must
show proof that you did the work required. The hash serves as proof, since we know it requires a certain amount of effort (on average)
to generate a random hash with _n_ zeros at the beginning. 

## Difficulty
So our network has the goal of creating a new block every 10 minutes. If the network is being mined by a single person
on a single-core processor, it may take them 10 minutes to find a hash with two zeroes. If the network were being mined
by 10 billion cores, they may find a valid hash in 10 seconds. 

This presents a problem, because we always want to hit a 10 minute block time but if we add in more power, we will find blocks faster.
Enter _difficulty_. Every 2016 blocks the Bitcoin network will look at the previous set of blocks and determine how fast they were generated,
on average. If the average is over 10 minutes, the difficulty will decrease. If it is less than 10 minutes, it will increase. 

More difficulty = more zeros requried on your hash.

This mechanism has a few interesting implications:
1. If you are a bad guy wanting to take over the network, you will need enough computing power to override all the other miners
  - This is called a "51% attack" and is something that the whole network works to prevent
  - The idea is that if you control over 50% of the network total hash power, you can dictate what data exists in the blocks by outpacing other miners
  - Even if you successfully pulled of a 51% attack, you could not steal coins. The extent of your power is to control what goes into the blocks (say, you want to block all bitcoin transactions from American IP addresses)
2. Regardless of how much power you throw at it, the network will rebalance itself to hit the 10 minute target

