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

If you can connect it to your own regtest node the following things work: two users can create a channel, fund it, create commitment transactions, send a payment from the channel opener to the other person, and then force close the channel. I'm working on the other stuff, and also on some automation around justice transactions and detecting incoming payments, and I will hopefully eventually display a balance and similar stuff you'd expect in a bitcoin wallet. But I'm just throwing this stuff up on github early so people can see what I'm working on in the open. Stay tuned for more.
