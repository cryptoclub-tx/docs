# Wallets
The phrase "wallet" is frequently used to describe a few different
(but often used together) concepts. In general, a "wallet" refers to some
combination of:
- a keypair
- software
- Optionally: a device to manage the keypair (i.e. a "hardware wallet")

This document will delve into these.

## Where are the coins?
To understand a wallet, you must first understand how cryptocurrencies are stored.
Unlike a traditional wallet (where cash is stored inside the wallet) or a digital file
(where the data is stored in a file that can be copied/moved/deleted), cryptocurrency
is stored on a _blockchain_, and that blockchain is stored by everyone who runs a
node for that cryptocurrency network. This means that your coins are actually
_stored everywhere_.

What actually makes those coins _yours_ is ownership of a "keypair". The keypair
is what allows you to spend those coins. Without the keypair, you would be unable
to have control over the coins and they wouldn't be "yours".

The keypair gives you control, and because you have control, you have ownership.
A cryptocurrency wallet isn't actually resonsible for "storing" coins like a flashdrive
would store files. It just contains the keys for the coins. When people talk about
"I lost my bitcoin", what they actually mean is "I lost the key for my bitcoin".

Most wallet software will guide you through setting up a keypair via a process that
will have you write down 12-24 words. This set of words is known as a "seed". This seed
can be used to regenerate your keys should they be lost. 

If your wallet ever failed, you could take your seed and restore them into the same
wallet software as before, or use new software entirely.
The seed (and the keypair(s) it generates) are not tied to the software you used to
generate them. _This is very important to remember_. Even if you first setup your wallet
using Electrum, you can use that same key to restore a Trezor device (or vice-versa).

## How do I use a keypair?
A keypair by itself does not do a lot of good. You need some software to talk to the
cryptocurrency network. This is your "wallet software" and it is generally responsible
for things like:
- Checking balances
- Sending cryptocurrency
- Getting addresses for people to send to

The wallet software is generally the thing you will interact with the most. You may
use the same app every time, you may use different apps. You may use the Trezor
wallet for basic things but use Electrum when you want fine-grained control.

As long as both software wallets use the same key, they will see the same transactions
as any other wallet software. If you are using entirely software, your key is likely
stored as a file on the computer. If you are using a hardware wallet, it will be stored
on a device like a Trezor. Regardless of where the key comes from, the wallet software
operates the same.

## Recap
The term "wallet" can refer to either the software you are using or a specific keypair/account
within the software. Since the keypair in the wallet can be generated with the seed, the seed
itself may be referred to as a "wallet". 

The "seed" and "keypair" are generally interchangeable. The software wallet can generate these
for you or you can import your own. The software and the key are (usually) not tied to each other.


## Suggested Software
For Bitcoin
- [Electrum](https://electrum.org/#home)

For Ethereum
- [Metamask](https://metamask.io/)

If you use a Trezor, you may also be interested in the [Trezor Suite](https://suite.trezor.io/)
