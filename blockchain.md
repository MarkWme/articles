# Blockchain - The High Level Overview

It's likely the term "Blockchain" is something you've heard with increasing regularity over the past year or so. You've probably also heard how it's going to change everything, from how you conduct your financial affairs to how you deal with your local government to how you make your morning coffee.  Well, maybe not the last one, but there is certainly a lot of hype around Blockchain.

It feels like Blockchain is being touted as the solution to everything right now. A lot of that is linked to the success of Bitcoin, a digital currency which started out in 2008 and is built on Blockchain technology. But as with most new and emerging technologies it's important to understand when to use Blockchain or when an established technology would suffice. Undoubtedly, some new and innovative uses for Blockchain will emerge, but not everything will benefit.

Blockchain is one of those technologies that has an air of mystery around it, but the concepts are really quite straightforward. In this article, I'll help you to understand what the Blockchain is, keeping the discussion at a high level to aid understanding and not get too bogged down in the exact technical implementation.

First, a bit of history. I mentioned Bitcoin earlier and that is probably the most well known implementation of Blockchain technology. Bitcoin is the result of several years research and lessons learned from other previously unsuccessful attempts to develop digital currencies. Bitcoin provides a secure, distributed, immutable ledger. Cryptography is heavily used, hence why Bitcoin and other digital currencies are often referred to as Cryptocurrencies. Cryptography is used to verify identities, to validate transactions and prove data integrity, amongst other things.

The Bitcoin ledger provides a record of every Bitcoin transaction that has ever taken place. Once transactions are committed, they can never be changed. If you make an erroneous payment, the only way to correct that is to make another payment to reverse the transaction. The ledger information is stored in encrypted data blocks which ensure that the contents cannot be tampered with. Approximately every ten minutes, the latest batch of transactions are gathered up into a new data block and each new block is linked to it's predecessor, creating a chain of blocks that are linked together in such a way that any modification, intentional or accidental, malicious or well-intentioned, will be immediately obvious. 

Bitcoin is decentralised, there is no central authority providing validation of transactions. The Bitcoin network consists of thousands of nodes, each of which holds a full copy of the chain and each of which maintains the ledger, provides validation of transactions, creates (mints) new currency and determines the system's rules. The network of nodes uses a consensus algorithm to ensure that they all agree with each other and that invalid or malicious blocks are rooted out.

Bitcoin, therefore, has many desirable features and it wasn't long before people started to think whether the technology that underpins Bitcoin - those blocks of data linked together in a secure, unchangeable, tamper-evident chain could be applied to other areas.

The Blockchain that supports Bitcoin contains more than just blocks of transaction data. Each block also contains scripts that are executed by each node of the Bitcoin network. The script language is specific to Bitcoin, designed to support the essential operations required for Bitcoin transactions and nothing more. So, ideas have been forming as to how the Blockchain could support more complex transactions. 

### Introduce mining, proof of work, move Blockchain 2.0 stuff to part 3.

Mining
If we had access to a trustworthy centralized service, this system would be trivial to implement; it could be coded exactly as described, using a centralized server's hard drive to keep track of the state. However, with Bitcoin we are trying to build a decentralized currency system, so we will need to combine the state transition system with a consensus system in order to ensure that everyone agrees on the order of transactions. Bitcoin's decentralized consensus process requires nodes in the network to continuously attempt to produce packages of transactions called "blocks". The network is intended to create one block approximately every ten minutes, with each block containing a timestamp, a nonce, a reference to (i.e., hash of) the previous block and a list of all of the transactions that have taken place since the previous block. Over time, this creates a persistent, ever-growing, "blockchain" that continually updates to represent the latest state of the Bitcoin ledger.

The one validity condition present in the above list that is not found in other systems is the requirement for "proof of work". The precise condition is that the double-SHA256 hash of every block, treated as a 256-bit number, must be less than a dynamically adjusted target, which as of the time of this writing is approximately 2187. The purpose of this is to make block creation computationally "hard", thereby preventing Sybil attackers from remaking the entire blockchain in their favor. Because SHA256 is designed to be a completely unpredictable pseudorandom function, the only way to create a valid block is simply trial and error, repeatedly incrementing the nonce and seeing if the new hash matches.

Compensation / reward

### End new stuff

The implementation of Blockchain in Bitcoin and other cryptocurrencies is commonly referred to as Blockchain 1.0. The idea of Blockchain 2.0 has been around for a couple of years now and it generally refers to implementations that allow data and code to be stored together in the Blockchain. The code is more advanced than Bitcoin scripts, attempting to provide more complete programming languages that move beyond confirmation of Bitcoin transactions and allow more operations to be performed. These are called Smart Contracts.

Let's say that you wanted to execute some financial transaction at a future date if certain conditions are met. The code for that transaction would be written and stored in the Blockchain. Because we know that the Blockchain cannot be changed, we know that either the conditions will never be met and the code never executed, or the conditions will be met and the code we stored will get executed and will be the exact code we committed to the Blockchain. Even if the conditions are met several years into the future, we can be assured that the code being run will not have changed.

As we explore the idea of storing and executing code in the Blockchain, other considerations come to mind. In the Blockchain, every node in the network executes the code. So, how do we stop long running code from excuting? Imagine if someone coded an endless loop and that got executed by every node. Also, the Blockchain is secure and immutable, so how do we maintain the security and trust inherent within the Blockchain if, for example, the Smart Contract code needs to reach out to an external source to confirm a value, such as a price or an exchange rate. How do we know those external sources can be trusted? And because nodes are distributed potentially anywhere on the planet, the exact timing of a request to an external source could result in nodes getting different results. The [Ethereum](https://www.ethereum.org/) project is one such effort to build a public Blockchain which tries to solve some of these problems.

The Bitcoin Blockchain is public. Anyone can inspect the information held there - for example here at [blockchain.info](https://blockchain.info/). It also means that anyone can join and become a member of the Bitcoin network. 

There is also the concept of private Blockchain implementations, which could be used inside of an organisation and the data stored on the Blockchain could be used across different business units. Or, there are consortium Blockchains where many organisations with a common interest work to implement a shared Blockchain. Neither private or consortium Blockchains would be generally accessible to the public.

The Consortium idea is the one being actively pursued by a number of financial services organisations. These firms have to deal with each other on a daily basis. You probably make payments to other individuals and companies from your personal bank account several times a month, but it's highly unlikely they're with the same bank. So, when you make one of these seemingly simple payments, a lot of activity goes on behind the scenes to transfer the money between banks and accounts, to make sure you have sufficient funds, to make sure you are who you say you are and are authorised to make the payment, to make sure that your account gets debited and the other party's account gets credited. Consortium Blockchains would provide a shared infrastructure to allow these transactions to happen more easily, simply checking the Blockchain to confirm availability of funds, to verify identities, detect fraud and providing an audit trail of transactions.

Besides banks and financial services, the Blockchain is being considered for use in property, manufacturing, governments and numerous other areas. Anywhere there's a need to track things, prove identities or ownership, prevent fraud or provide tamper-proof audit trails and more.

----------

# Blockchain - The Technical Overview

Having given an overview of what the Blockchain is and how it is evolving, this article delves into some of the technical details. For the purpose of making this easy to understand the details have been somewhat simplified, but they still reflect how Blockchains work.

## Blockchain Concept 1 - Hashes

Hashes feature a lot in Blockchains. They're used for identification and verifying data integrity. A hash is produced as the result of a cryptographic function. Any data, of any size, can be passed to a hashing function to produce a result of a fixed size. Passing the same data to a hashing function always produces the same result. Passing different data to a hashing function will produce a different result. A hash provides a quick way to verify that data has not been tampered with. Also, hashes are one-way functions. This means that it is not possible to reverse the hash and retrieve the original data.

There are several hashing algorithms in use. A popular one is known as SHA-256 - (SHA - Secure Hash Algorithm, 256 - returns a value 256 bits wide). Let's use that algorithm to demonstrate how hashing works.

If I pass a simple value, such as my name, through an SHA-256 hashing function, I will get the following result

    Mark Whitby --> 150a1c607b69eef0aeeec21cc291b73bb5cf48fc9cbe29af6a27994866f18d65

Every time I run my name through the hash algorithm, I will get that same hash value back.  However, if I make one small change:

    Mike Whitby --> a98c78ca85dca6e45d4c940ab4a8ff107a2b59d0167b3bc70260d39739759694

By changing the first name the hashing function now returns a completely different result. This is a simple example and it's rather easy to see what I changed in the original data before it was hashed, so what if I have a lot more data? I found the text to the book "Great Expectations" by Charles Dickens online.  When I passed the entire text of that book into a hashing function, I got the following:

    (Entire text of "Great Expectations") --> 2b5856272ee09c2dfbdcfc78939acd84aa0976784c67047f3b619ae2bff297ad

Notice that even though I'm now hashing the entire contents of a book rather than just two words, the value returned by the hashing function is still the same length.

Next, at random, I changed one character somewhere in the middle of the book

    (Modified text of "Great Expectations") --> 27cf6b7181699a6358ca927f09eb8c765810fed44167aa47147f1c7466cfb298

Instantly you can see that this now returns a different hash value. The text I passed to the hash function contained 138,883 words. If I were to review the text myself, it would take me a very long time to find what had changed, if I managed to find it at all. But with the hash value, I can instantly see that something is not right.

Now imagine that the data we're working with is not a name or the text of a book, but it's a set of financial transactions or some other sensitive information. With a hashing function applied to those transactions we have a simple way to instantly know whether anyone has interfered with that data.

## Blockchain Concept 2 - Blocks

A block contains our data and the hash of the data.

Which is straightforward enough. However, most Blockchains introduce another idea here, which is Mining. Mining is one of the tactics employed to ensure the integrity of the data in the Blockchain. 

We saw earlier that my name produced a particular hash value. But let's say that we've decided that we will only accept a hash value as being valid if it starts with a zero. We know that by changing the data passed to the hashing function we get a different hash result. So, what happens if I place a numeric value before my name.

    1-Mark Whitby --> 349a51c2bded8507194cb1c0c66d9c8bd7ad734c1bd03c6509cd1bb0625c2d1e

We get a different hash value, which starts with a "3".  Let's increment that number until we end up with a hash that starts with "0".

    13-Mark Whitby --> 03621d54dcf2096141841ea5fb5f61076f6f1c41b326f9768fb43640ccfc4d53

After 13 attempts, we find what we're looking for.

Blockchains implement this using a number, known as a "nonce", which is combined with the data and hashed. Blockchain miners modify the nonce and recalculate the hash until they find a hash value which is below a certain value - or to visualise simply, contains a certain number of zeros at the start of the hash.  For example, at the time of writing, the hash value associated with the most recently mined Bitcoin block is ````000000000000000001eb04b147468c20e4853daf6e87e6c45b07ecdb518abec6````, which has 17 zeros at the start. To find a nonce which when combined with the data produces a hash with 17 zeros at the start takes a lot of processing power, and depending on how much processing power you have can take a very long time to calculate.

## Blockchain Concept 3 - Blockchains

Now we get into why it's called a Blockchain. We have a block which contains some data, a hash we can use to verify the integrity of the data and a nonce value that causes the hash to start with one, or more, zeros which in our scenario confirms that our block is valid. So what about the next block of data we want to store?  Well, we'll just do the same again, get the data and a nonce value and keep calculating hashes until we end up with a value starting with zero.

So, let's say I now have five such blocks. If I need to make sure that none of the data in those blocks has been tampered with, then I'd need the original data and the nonce value, I could then generate a hash and compare it to the hash stored in the block and see if they match. If they do, then we're all good. I'd have to do that for every block to make sure everything is in order. This might not be too bad with five blocks, but what about 500 blocks? Or 5,000 blocks? That could take a while!

So, in each block that we create, we'll include the hash value from the block that was created before it.  We now take the data for our new block, the previous block's hash value, join these together and then go figure out the nonce value that will give us a hash with a zero at the start.

Now, I have 5 blocks that are linked together in a chain, with each one referencing the previous block's hash value. Now, if I deliberately modify the data in the third block in the chain, what does that do?

It instantly invalidates the data in block 3, because the modified data no longer generates a hash value that starts with a zero, breaking our rule for what constitutes a valid block.  We can calculate a new nonce value to fix this, but the hash value will be different. And because we used block 3's original hash to create the hash value for block 4, that means that even though the data in block 4 is still good, the modified block 3 hash value now causes block 4's hash to become invalid. And this will replicate all the way to the end of the chain. It doesn't matter where in the chain data has been modified, we only need to look at the last block to see that something is broken somewhere.

You could fix this by generating new hashes all the way along the block. But that's where the next part of Blockchain comes into play.

## Blockchain Concept 4 - Distributed

Blockchains solve the potential problem of someone modifying data and then re-mining the hash values throughout the chain or a rogue node adding a fraudulent block by maintaining multiple distributed copies.

If one copy of the Blockchain has been modified, then it will stand out from other copies as being different. Exactly how the various Blockchain based technologies determine which chain is the bad one and which are the good ones has a bit more to it than simply comparing copies, but by maintaining multiple distributed copies each owned by different independent entities, it will be obvious if someone attempts to maliciously interfere with the Blockchain.

# Blockchain - The Enterprise

In part one of this series, I introduced Bitcoin. Bitcoin is exclusively used as a digital currency 

Proof of work / mining is too resource intensive


automatically sending money from one person to another but only when a certain set of conditions are met.

With Ethereum, a piece of code could automatically transfer the home ownership to the buyer and the funds to the seller after a deal is agreed upon without needing a third party to execute on their behalf.

Identity
There are many websites a person can create a digital identity on (e.g. Facebook, Twitter, LinkedIn). This is cumbersome to manage and at the end of the day you are not in full control of your information as it is still owned by a centralized entity. With Ethereum you can have a decentralized identity management system like uPort that allows you to be in full control of your data. There is no centralized server that has access to your private data, can get hacked, edit your information, or get shut down.

Proof of work / no economic barrier to entry / just need hardware

Building solutions on top of Bitcoin's blockchain vs. creating new blockchains

Scripting, lacks features, in some cases intentionally to prevent abuse / errors causing problems

Ethereum provides a full featured programming language which theoretically allows the implementation of any scenario, not just the exchange of digital currencies.

Smart contracts, cryptographic "boxes" that contain value and only unlock it if certain conditions are met, 

Ether pays for transaction fees.

Gas prevents denial of service attacks, prevents accidental or malicious infinite loops.

