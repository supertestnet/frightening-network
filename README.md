# Frightening network 👻
Like the lightning network but you'll probably lose all your money

# Is this real life?

No because it doesn't really work yet. It's an in-progress implementation of something like the lightning network in vanilla javascript.

# Something like the lightning network? What does that mean?

Well, originally I wanted to write an actual lightning implementation, but then I started reading the bolts. And I found them confusing and daunting to both understand and then implement. So I decided to make something else, something easier. I flipped to page 23 of the lightning network whitepaper and decided to just implement that my own way. So it works like the lightning network but it doesn't follow any of the bolt specs.

# Why are you doing this?

For fun. Also because there are some things about the lightning network that I want to change and it will be easier to do that if I have my own version.

# Why does it not work?

Most of the stuff that happens in the current version happens in the browser console. And some of that doesn't work either. Also, it's all running on regtest, not even testnet, and certainly not mainnet yet, so it's very hard to get this running. Maybe eventually it will work more fully.

# Does any of it work right now?

If you can connect it to your own regtest node the following things work:
- two users can create a channel
- fund it
- create commitment transactions
- send as many second layer payments as they like to and from one another
- and then force close the channel. Also,
- second layer payments are compatible with the "real" lightning network, so you can do stuff like:
- have the first user send the second user a payment only if the second user pays a "real" lightning invoice
- or have the first user "accept" a real lightning payment via the second user, who gets to settle the "real" lightning payment only if they forward an equal amount to the first user

# What doesn't work?

- Neither party detects cheating attempts
- cooperative closures don't work
- user balances are not yet displayed
- multiple channels don't work
- channel history isn't saved so don't refresh the page
- there are no buttons for doing anything listed in the section on stuff that works

Due to the last issue, to use this app you sort of have to sift through the source code and identify some esoteric commands. But it's all good, I'm just throwing this stuff up on github early so people can see what I'm working on in the open. Stay tuned for more.

# Message types

An important aspect of the frightening network is that message types are indicated numerically. Here they the numbers currently in use:

0. Paul sends Vicky info on how to open a channel with him. Includes his pubkey, a publication hash, and a revocation hash
1. Vicky sends Paul info indicating she wants to open a channel with him. Inludes her utxo and key data to indicate what utxo she will fund the channel with
2. Paul sends Vicky info establishing a "refund state" i.e. the initial state of the channel. Includes 3 signatures.
3. Unused
4. Unused
5. Paul sends Vicky info requesting a payment. Includes a payment hash.
6. Vicky sends Paul info requesting a payment. Includes a payment hash.
7. 
