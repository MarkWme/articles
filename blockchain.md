# Blockchain - The High Level Overview

If you work in technology, or these days even outside of technology, it's likely the term "Blockchain" is something you've heard with increasing regularity over the past year or so. You've probably also heard how it's going to change everything, from how you conduct your financial affairs to how you deal with your local government to how you make your morning coffee.  Well, maybe not the last one, but there is certainly a lot of hype around Blockchain.

Blockchain is being touted as the solution to a wide number of problems, but as with most new and emerging technologies it's important to understand when to use Blockchain or when to use established technologies. In this article, I'll explain what Blockchain is, how it works, where the technology is today and what the potential uses are. Blockchain is one of those technologies that currently has an air of mystery around it, but the concepts are really quite straightforward. So, I'll aim to keep this high level and not delve into the more technical aspects in order to help you get a good overview of things.

Blockchain isn't that new. It's the underlying technology that supports Bitcoin, whose roots can be traced back to 2008. Bitcoin is the result of several years research and many previously unsuccessful attempts to develop digital currencies. Bitcoin provides a secure, distributed, immutable ledger. Cryptography is heavily used, hence why Bitcoin and other digital currencies are usually referred to as Cryptocurrencies. Cryptography is used to verify identities, to validate transactions and prove data integrity.

The Bitcoin ledger provides a record of every Bitcoin transaction that has ever taken place. Once transactions are committed to a block, they can never be changed. If you make an erroneous payment, the only way to correct that is to make another payment to reverse the transaction. The ledger information is stored in encrypted data blocks which ensure that the contents cannot be tampered with. Approximately every ten minutes, the latest batch of transactions are gathered up into a new data block and each new block is linked to it's predecessor, creating a chain of blocks that are linked together in such a way that any modification, intentional or accidental, malicious or well-intentioned, will be immediately obvious. 

Bitcoin is decentralised, there is no central authority providing validation of transactions. The Bitcoin network consists of thousands of nodes, each of which holds a full copy of the chain and each of which provides validation of transactions. The network of nodes uses a consensus algorithm to ensure that they all agree with each other and that invalid or malicious blocks are rooted out.

Bitcoin, therefore, has many desirable features and it wasn't long before people started to think whether the technology that underpins Bitcoin - those multiple, distributed blocks of data linked together in a secure, unchangeable, tamper-evident chain, the Blockchain - could be applied to other areas.

The Blockchain that supports Bitcoin contains more than just blocks of transaction data. Each block also contains scripts that are executed by each node of the Bitcoin Blockchain. The script language is specific to Bitcoin, designed to support the essential operations required for a Bitcoin transactions. So, ideas have been forming as to how the Blockchain could support more complex transactions. 

The implementation of Blockchain in Bitcoin is commonly referred to as Blockchain 1.0. Blockchain 2.0 has been around for a couple of years now and it generally refers to implementations of Blockchain that allow data and code to be stored. The code moves beyond the scripts of Bitcoin, in an effort to provide more complete programming languages that move beyond confirmation of Bitcoin transactions and allow more operations to be performed. This is known as a SmartContract.

Let's say that you wanted to execute some financial transaction at a future date if certain conditions are met. The code for that transaction would be written and stored in the Blockchain. Because we know that the Blockchain cannot be changed, we know that either the conditions will never be met and the code never executed, or the conditions will be met and the code we stored will get executed and will be the exact code we committed to the Blockchain.

As we explore the idea of storing and executing code in the Blockchain, other considerations come to mind. In the Blockchain, every node in the network will execute the code. So, how do we stop long running code from excuting? Imagine if someone coded an endless loop and that got executed by every node. Also, the Blockchain is secure and immutable, so how do we maintain the security and trust inherent within the Blockchain if, for example, the SmartContract code needed to reach out to an external source to confirm a value, such as a price or an exchange rate. How do we know those external sources can be trusted?

Ethereum? Others?

Bletchley?

The Bitcoin Blockchain is public. Anyone can inspect the information held there - for example here at [blockchain.info](https://blockchain.info/). It also means that anyone can join and become a member of the Bitcoin network. In some scenarios, it may not be desirable to use a public Blockchain. Private Blockchain implementations can be used inside of organisations, or Consortium Blockchains where many organisations with a common interest work to implement a shared Blockchain. 

The Consortium idea is the one being actively pursued by a number of financial services organisations. These firms have to deal with each other on a daily basis. You probably make payments to other individuals and companies from your personal bank account several times a month, but it's highly unlikely they're with the same bank. So, when you make one of these seemingly simple payments, a lot of activity goes on behind the scenes to transfer the money between banks and accounts, to make sure you have sufficient funds, to make sure you are who you say you are and are authorised to make the payment, to make sure that your account gets debited and the other party's account gets credited. Consortium Blockchains would provide a shared infrastructure to allow these transactions to happen more easily, simply checking the Blockchain to confirm availability of funds, to verify identities, detect fraud and providing an audit trail of transactions.

Besides banks and financial services, the Blockchain is being considered for use in property, manufacturing, governments and numerous other areas. Anywhere there's a need to track things, prove identities or ownership, prevent fraud or provide audit trails and more.

----------

# Blockchain - The Technical Overview

What is Blockchain?

The first thing to understand is that Blockchain is a technology, not a product. In the same way that you would say you are builidng a solution using SQL Server or DocumentDB and not "I am building a solution using database", you would not say "I am building a solution using Blockchain". 

(check back on the Marley Grey TR24 pres - he covers this)

Blockchain is a technology and there are several products and solutions that implement Blockchain technology. The most widely known implementation of Blockchain is Bitcoin. Bitcoin provides a means to ….  But the use of Blockchain is not just limited to currencies.

In Bitcoin, Blockchain is the ledger

Immutable, distributed, secure, ledger (decentralised ledger)

https://blockchain.info

Blockchain is infrastructure?

There are multiple Blockchains

Maybe a short paragraph on what Bitcoin is, what it does and why it's "better" than banks etc.

"The blockchain as the architecture for a new system of decentralized trustless transactions is the key innovation. The blockchain allows the disintermediation and decentralization of all transactions of any type between all parties on a global basis."

Following is a description of key Blockchain concepts at a high level. This isn't exactly how any particular Blockchain implementation works, but they are all based on these concepts.

Blockchain Concept 1 - Hashes

Hashes feature a lot in Blockchains. They're used for identification and verifying data integrity. A hash is produced as the result of a cryptographic function. Any data, of any size, can be passed to a hashing function to produce a result of a fixed size. Passing the same data to a hashing function always produces the same result. Passing different data to a hashing function will produce a different result. A hash provides a quick way to verify that data has not been tampered with. Also, hashes are one-way functions. This means that it is not possible to reverse the hash and retrieve the original data.

There are several hashing algorithms in use. A popular one is known as SHA-256 - (SHA - Secure Hash Algorithm, 256 - returns a value 256 bits wide). Let's use that algorithm to demonstrate how hashing works.

If I pass a simple value, such as my name, through an SHA-256 hashing function, I will get the following result

Mark Whitby --> 150a1c607b69eef0aeeec21cc291b73bb5cf48fc9cbe29af6a27994866f18d65

Every time I run my name through the hash algorithm, I will get that same hash value back.  However, if I make one small change:

Mike Whitby --> a98c78ca85dca6e45d4c940ab4a8ff107a2b59d0167b3bc70260d39739759694

By changing the first name the hashing function now returns a completely different result. This is a simple example and it's rather easy to see what I changed in the original data before it was hashed, so what if I have a lot more data? I found the text to the book "Great Expectations" by Charles Dickens online.  When I passed the entire text of that book into a hashing function, I got the following:

Great Expectations Book --> 2b5856272ee09c2dfbdcfc78939acd84aa0976784c67047f3b619ae2bff297ad

Notice that even though I'm now hashing the entire contents of a book rather than just two words, the value returned by the hashing function is still the same length.

Next, at random, I changed one character somewhere in the middle of the book

Modified text --> 27cf6b7181699a6358ca927f09eb8c765810fed44167aa47147f1c7466cfb298

Instantly you can see that this now returns a different hash value. The text I passed to the hash function contained 138,883 words. If I were to review the text myself, it would take me a very long time to find what had changed, if I managed to find it at all. But with the hash value, I can instantly see that something is not right.

Now imagine that the data we're working with is not a name or the text of a book, but it's a set of financial transactions or some other sensitive information. With a hashing function applied to those transactions we have a simple way to instantly know whether anyone has interfered with that data.



Blockchain Concept 2 - Blocks

A block contains our data and the hash of the data.

<picture of block>

Which is straightforward enough. However, most Blockchains introduce another idea here, which is Mining. Why mining takes place will be discussed later, but for now it's enough to say that it's one of the tactics employed to ensure the integrity of the data in the Blockchain.
We saw earlier that my name produced a particular hash value. But let's say that we've decided that we will only accept a hash value as being valid if it starts with a zero. We know that by changing the data passed to the hashing function we get a different hash result. So, what happens if I place a numeric value before my name.

1-Mark Whitby --> 349a51c2bded8507194cb1c0c66d9c8bd7ad734c1bd03c6509cd1bb0625c2d1e

We get a different hash value, which starts with a "3".  Let's increment that number until we end up with a hash that starts with "0".

13-Mark Whitby --> 03621d54dcf2096141841ea5fb5f61076f6f1c41b326f9768fb43640ccfc4d53

After 13 attempts, we find what we're looking for.

Blockchains implement this using a number, known as a "nonce", which is combined with the data and hashed. Blockchain miners modify the nonce and recalculate the hash until they find a hash value which is below a certain value - or to visualise simply, contains a certain number of zeros at the start of the hash.  For example, at the time of writing, the hash value associated with the most recently mined Bitcoin block is 000000000000000001eb04b147468c20e4853daf6e87e6c45b07ecdb518abec6, which has 17 zeros at the start. To find a nonce which when combined with the data produces a hash with 17 zeros at the start takes a lot of processing power, and depending on how much processing power you have can take a very long time to calculate.
Blockchain Concept 3 - Blockchains

[Blockchains are immutable, resistant to change]
Now we get into why it's called a Blockchain! We have a block which contains some data, a hash we can use to verify the integrity of the data and a nonce value that causes the hash to start with a zero, which in our scenario confirms that our block is valid. So what about the next block of data we want to store?  Well, we'll just do the same again, get the data and a nonce value and keep calculating hashes until we end up with a value starting with zero.

So, let's say I now have five such blocks. If I need to make sure that none of the data in those blocks has been tampered with, then I'd need the original data and the nonce value, I could then generate a hash and compare it to the hash stored in the block and see if they match. If they do, then we're all good. I'd have to do that for every block to make sure everything is in order. This might not be too bad with five blocks, but what about 500 blocks? Or 5,000 blocks? That could take a while to confirm.

So, in each block that we create, we'll include the hash value from the block that was created before it.  We now take the data for our new block, the previous block's hash value, join these together and then go figure out the nonce value that will give us a hash with a zero at the start.

Now, I have 5 blocks that are linked together in a chain, with each one referencing the previous block's hash value. Now, if I deliberately modify the data in the third block in the chain, what does that do?

It instantly invalidates the data in block 3, because the modified data no longer generates a hash value that starts with a zero, breaking our rule for what constitutes a valid block.  We can calculate a new nonce value to fix this, but the hash value will be different. And because we used block 3's original hash to create the hash value for block 4, that means that even though the data in block 4 is still good, the modified block 3 hash value now causes block 4's hash to become invalid. And this will replicate all the way to the end of the chain. It doesn't matter where in the chain data has been modified, we only need to look at the last block to see that something is broken.

You could fix this by generating new hashes all the way along the block. But that's where the next part of Blockchain comes into play.

Blockchain Concept 4 - Distributed

Blockchains solve the potential problem of someone modifying data and then re-mining the hash values throughout the chain to cover their tracks by maintaining multiple distributed copies.

Here we can see that if one copy of the Blockchain has been modified, then it will stand out from other copies as being different. Exactly how the various Blockchain based technologies determine which chain is the bad one and which are the good ones has a bit more to it than simply comparing copies, but by maintaining multiple distributed copies each owned by different independent entities, it will be obvious if someone attempts to maliciously interfere with the Blockchain.

This isn't replication as you'd typically see with traditional databases.

Trust / trustless

Private key / public key to prove ownership

From the four concepts introduced here, it should be easy to see how Blockchain technology provides …

Blockchain v1 - Bitcoin

Bitcoin is a public Blockchain and maintains a public ledger which anyone can view.

Just currency transactions.

Bitcoin is first and most well known.  Others - http://coinmarketcap.com/
Blockchain v2 - Public, Private and Consortium, Smart Contracts
Assets beyond currencies. Taking the decentralised immutable ledger to register all different kinds of things. (Examples of things?) Forgery prevention. Proof of ownership or identity.

Usage (potential ideas in email), banks, reducing need for intermediaries.

In short, the idea is that Blockchain can be used in any scenario where something can be tracked, cannot be changed …

Car key?

The data contained within a Bitcoin transaction isn't just a record of a transfer of currency from one place to another, it also contains code in the form of Bitcoin Scripts. These scripts are used in the validation of each transaction, making sure that the parties involved in a transaction are who they say they are (and that they have the funds available) for example.

Remember that the Blockchain is immutable - once data is in a block, it cannot be changed. Therefore, code could be inserted into a block which is configured to execute under certain circumstances. At a future date, which could be seconds, hours, days or years into the future, those conditions are met and the code is executed.

Blockchain v3 …

Getting Started with Blockchain in Azure

The Blockchain is not for everything.
	- 
