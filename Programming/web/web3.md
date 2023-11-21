

Here are some notes about what I've learnt so far about web3

### Digital signatures

The goal of digital signature is to be able to certify the origin of some content (who's written it)
as well as being able to encrypt it.
The main to encryption systems used nowadays are RSA and ECDSA. RSA is all about arithmetics, it
uses proprieties about primes numbers to make anything easy to encrypt and impossible to decrypt
without a private key.
ECDSA uses proprieties about elliptic curves. I don't understand how this works but it's even
stronger in terms of security than RSA.

---

Both theses systems use the concept of public/private key. The public key is accessible by
everybody, it's used to encrypt the message. To decrypt it you need the private key that is owned
only by the recipient of the message.

This concept is also useful to certify the origin of a message. The sender (let say bob) has to encrypt is with
his private key, everybody will be able to decrypt it with his (bob's) public key and the fact that
this public key decrypts it proves that bob was effectively the sender.

Anyway cryptographic functions must satisfy five properties :

 + **Deterministic** - One specific input always maps to the same specific output
 + **Pseudorandom** - It is not possible to guess the output based on the output of similar inputs
 + **One-way** - If someone gives you a new output, you could not determine an input without guessing
 + **Fast to Compute** - It must be a quick calculation for a computer
 + **Collision-resistant** - The chance of a collision should be infinitesimally small

## Cryptocurrency consensus

A consensus mechanism is a method for validating entries into a distributed database and keeping the database secure.
In the case of cryptocurrency, the database is called a blockchain—so the consensus mechanism secures the blockchain.

### Proof of Work (PoW)

Proof-of-Work uses a competitive validation method to confirm transactions and add new blocks
to the blockchain. When a miner wants to validate a block (to mine it), they need to provide a hash
with respect to certain rules. Bitcoin provides a difficulty, which is a number (at the time I
write this it is 51,234,338,863,442.89) and the hash has to be a 32bytes (so 256bits or 64hex chars)
number smaller than this. This means that the hash has to start with a certain number of 0s.
The last block mined for now is [the block 793,376](https://www.blockchain.com/explorer/blocks/btc/793376).
his hash is :
```
000000000000000000021828b5b457957e433090af4a2a6e1986714720188ad5
```
As you can see there is 19 leading 0s !

---

To come up with a different hash every time, miners have to change something about the block everytime before
putting it back into the cryptographic function. This is called the nonce. It's litteraly a number that is
there only to be changed everytime. So what miners do in fact is simply to encrypt some data, see whether the
hash is smaller than the difficulty and if not they increase the nonce by one and try again.
The thing is the nonce is a 32bit value, so it is possible that no nonce satifies the requirements. If it is
the case then the miners have to change something else about the block and try again.

### Proof of Stake (PoS)

Proof-of-Stake uses randomly selected validators to confirm transactions and create new blocks.

The problem with PoW is that it is demanding a lot of ressources to mine a block. This is an environmental issue
as well as a security one. Since you need a very big setup not many people can mine bitcoin which makes it
less decentralised.

With PoS, you can "stack" some crypto (32ETH for ethereum) to become a validator. By doing so you aquire the
right to validate nodes. Validators are selected randomly to check block, if at least two thirds of them agree
that they are valid then this block is added to the blockchain. The validators then share the tip (see the part)
on gas.

If a validator can not be trusted, if he validates incorrect nodes for example, he risks his whole stack of crypto
to be burned.

## UTXO vs Account Model

What kept people form builing blockchains before bitcoin was the problem of double spending (also called replay attacks).
What would keep people from reusing the same transaction over and over again. Bitcoin and ethereum bring two different
solution to prevent this from happening.

---

#### UTXO

UTXO means Unspent Transaction Output. It is used by bitcoin (and most blockchains).
With this system the blockchain keeps track of every transaction that has ever happened.
The amount of Bitcoin you own is in fact an UTXO or a sum of UTXO making up the whole amount.
Let's say you want to send some BTC to a friend, say you have 50BTC and you want to send him 10. You will send it all to
the blockchain (as you can't divide yourself your UTXO) and from that will be created an UTXO of 40BTC and another of 10.
The blockchain takes care of all thoses "sub-transactions" so there is no trust issue, and since everything is traced
you can't create money out of thin air therefore you cannot double spend.

Now you want all your nodes to have acces to the same state of the blockchain, but as transaction are more and more
frequent it becomes nearly impossible for everyone to be constantly synchronised. That's why transactions are put
together into blocks. To give you an idea there is a new block on bitcoin every (aprox.) 10 minutes, every block a an
average of 2000 transactions.

---

#### Account Model

The account-based transaction model represents assets as balances within accounts, similar to bank accounts. Ethereum
uses this transaction model.
It's pretty straight forward model, it works pretty much like a normal bank account in fact. How is it safe against
repay attack you may ask. Well to every transaction is attached a nonce, this one increase with every transaction. Since
all the transactions are public, if a validator sees an old nonce from someone (one that has already been used) it knows
that this transaction is incorrect and does not validates it.


### Tree data structures in the blockchain

Trees are used a lot in the blockchain. They allow us to store data outside the blockchain and still be able to
authentify it. To do so you need Merkle trees.

---


### Gas in ethereum

Ethereum is like a computer, it's not very fast but being fast is not the point, the point is to be secure. Anyway you
need a way to determine who is going to use this computer. You also need to pay the validators. So every time you do a
transaction you pay some gas. The gas is measured in Gwei (giga-wei, which is a small amount of ETH). First there is a base fee
that gets burn (to prevent validators from abusing the system) and then there's a "tip" that gets shared among
validators of the block.

The gas values for every operation (like addition or substraction) used to be set by humans,
but this led to possible abuse (it wasn't well balanced), so now it changes with every transaction. Every block has a
limit of 30 Million gas and a goal of 15 Million (this means that if your program cost more than 30M of operations you
won't be able to run in on ethereum). If a block goes over the goal of 15M it means that the demand if higher and the
gas price increases, on the other hand if a block does not reach the goal of 15M it means that the demand is not high
enough and the price of gas decreases.


## Glossary

| Word | Meaning |
| :----: | ------- |
| UTXO | Unspent Transaction Output |
| wei | Unit of Ether, 1 Ether = 2^18 wei |
| JSON-RPC | the remote procedure call protocol used to read from ethereum |
| nonce | A number used only once, it's used as a transaction ID to prevent from double spending |
| gas | The cost of every transaction, measured in wei or gwei |
| EVM | Ethereum Virtual Machine |
