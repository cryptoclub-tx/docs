# Ethereum
This document is going to describe the Ethereum blockchain in terms of how
it differs from Bitcoin. If you don't understand Bitcoin, come back later.

-----

Ethereum is a blockchain network that uses proof-of-work (for now, later will swap to proof-of-stake)
to secure its blockchain. It has a base currency called _ether_. Ether is used to pay transaction fees,
which in Ethereum are called "gas". Unlike Bitcoin, Ethereum uses the same address over and over. Your
address/wallet/key is essentially your "account".

## Smart Contracts
Ether has it's own "programming language" that is part of the blockchain network itself. This allows
for certain code to be written into the blockchain and executed by miners without relying on an external
server. Since the code is written to the blockchain, everyone can read them and see how they work.
These programs are referred to as _smart contracts_ and make up most of the interesting things
on the Ethereum blockchain.

## Tokens
In addition to ether itself, Ethereum has a popular concept known as "ERC20 tokens", or "tokens"
for short. Tokens live atop the Ethereum blockchain themselves, they do not exist on a standalone network.

ERC20 is a programming specification for a smart contract.
It allows for generic use of these tokens like you would a currency. You can hold
a balance, you can send them, you can receive them, etc (all using the same ether address). 

Many apps on the Ethereum blockchain will work with _any_ ERC20 token interchangeably. 
This does not mean that all tokens are "money". Some tokens represent dollars, some tokens
represent bitcoin. Some tokens represent voting rights for various protocols (like a board member vote).
Some tokens represent real-world things like gold or stock.

These tokens are made in a varieity of fashions and they are not all created equal. You probably
do not want to buy Compound token (COMP) if you don't care to vote on the COMP governance proposals.

At the time of writing (Feb 2020) tokens on Ethereum are the _hot thing_. 11 out of 20 of the top
coins listed on Coinbase are ERC20 tokens.
