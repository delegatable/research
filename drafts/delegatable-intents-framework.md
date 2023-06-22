# Delegatable as an Intents Framework

### Defining Intents
First, let's take a moment to define "intents" as they're understood today.

Let's start with the informal definition of intents provided by Paradigm

> Informally, **an intent is signed a set of declarative constraints which allow a user to outsource transaction creation to a third party without relinquishing full control to the transacting party.**

And also a more formal definition of intents.

> **Signed messages which allow for a set of state transitions from a given starting state, a special case of which is a transaction which allows for a unique transition**.

The [# Intent-Based Architectures and Their Risks](https://www.paradigm.xyz/2023/06/intents) includes these references and additional context regarding how intents are applied today.

As we start to explore intents an axiom clearly emerges.

Specifically the spectrum between explicit and implicit intents.

Let's start with one of the examples of ["declarative programming"](https://twitter.com/CannnGurel/status/1663292583550803969) referenced in the Paradigm article.

> intent (declarative): I will pay 20 bucks for a Hawaiian pizza at my door by 8pm tx 
> 
> (imperative): hop on to ur scooter, go to Domino's around the corner, order item#4, and bring it. here is your 20 bucks; 18 for pizza, and 2 for gas.

The intent example includes a combination of both explicit and implicit intents.

The explicit intent example being "hawaiian pizza at my door by 8pm" which states very clearly when the user expects the pizza to arrive.

And the implicit intent being "pay 20 bucks for a Hawaiian pizza" which includes second order inferences: 
- what is a pizza?
- will the pizza include standard ingredients? (i.e. wheat dough vs cauliflower dough)
- what makes it hawaiian?

A clear axiom presents itself. Even in a basic example.

Intents live on a spectrum -- from highly explicit to vaguely implicit.

And we need both if we're going built robust blockchain infrastructure that handles user intents.

## Searching for a Better Tomorrow
Let's imagine a hypothetical universe. A universe with advanced computer technology catering to billions of users all around the world. It's a future where people only interact with advanced computer technology with strong cryptographic guarantees. 

If X happens digitally, it can be cryptographically verified using Y proving method.

Users love this approach. They don't have to sit around a computer all day clicking buttons.

Instead they can express intents about how they want their digital assets to be utilized. **What future they're interested in.** And they can let the advanced computer technology to handle the boring implementation details. 

What's matter is results. Cryptographically provable results.

Whether it's from a economic, technical or legal perspective users want to trigger actions that adhere to explicit rules and through implicit intents. The actions use a combination of explicit and implicit intents.

### Where We Stand Today

I want my ETH deposited into the highest earning LSD vault, but I don't want my ETH deposited in the largest liquid staking vault.

The implicit intent is I want my ETH deposited in highest yield vault possible.

The explicit intent is I don't want my ETH deposited in the largest LSD protocol.

Something that captures my intentions to balance profit motives and values of decentralization. A natural and healthy tension between implicit and explicit intents.

The world isn't black and white. We live in a world of spectrums.

We need a framework to help us navigate these spectrums.

## Delegatable -- An Intents Framework
Delegatable is an EVM smart contract framework for composing intents.

More precisely, up until this point in time, it's been a framework for defining and composing explicit intents. But it's unique approach to intent composition, means implicit intents are also possible.

Examples of explicit intents modules:

- [BlockNumberAfterEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/BlockNumberAfterEnforcer.sol)
- [BlockNumberBeforeEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/BlockNumberBeforeEnforcer.sol)
- [TimestampAfterEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/TimestampAfterEnforcer.sol)
- [TimestampBeforeEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/TimestampBeforeEnforcer.sol)

Examples of potential implicit intent modules:
- HighestEthYieldVaultDeposit

#### What Makes Delegatable Unique?
Delegatable has a unique approach to rules enforcement.

Unlike other EVM rules frameworks, like Uniswap V4 hooks and Safe Modules, delegatable doesn't require installing modules. Instead rules are validated at runtime using references stored in an offchain signature.

# Preparing for The Future

Blockchains are evolving. New rollups are emerging everyday.  

The future is bright. But also complex.

> "Despite the challenges, achieving scalability, wallet security, and privacy for regular users is crucial for Ethereum's future. It is not just about technical feasibility but about actual accessibility for regular users. We need to rise to meet this challenge."
> - Vitalik Buterin - [The Three Transitions](https://vitalik.ca/general/2023/06/09/three_transitions.html)

We need a better way for users to express their intents. To communicate their wants, needs and preferences in human language. A framework for expressing desired outcomes. Humans aren't robots. We don't speak in code. Our desires are abstract and multi-faceted.

But we have to operate in a mechanistic world.

A world with long running operations for how to get from point A to point Z.

# EVM State Mutation Snapshots

When I look at the spectrum of intents. From explicit to implicit. One thing becomes clear to me.

Explicit intents have minimal state conditions.

Implicit intents have maximal state conditions.

If I want to limit my transaction execution between two timestamps I only need 2 data points.

If I want to find the highest yield vault for ETH there is N data points, relative to the number of actors/entities providing yield for ETH. In other words, to accurately interpret implicit requests, we require larger and more comprehensive snapshots of state mutations across time.

But blockchains aren't good at long-running computations!

This is true, but they are great at long-running state mutations.

What if we could run offchain computations of onchain data, and use the results as inputs for fulfilling implicit intent with levels of accuracy?

### Succinct Proofs

Succinct proofs are cryptographically verifiable artifacts of long-running computations.

For example let's say I want to cryptographically prove the average price of stETH for last 90 days across 3 of the biggest money market protocols on 10 of the largest rollups.

That's a lot of data. Like a lot. No smart contract ever will be able to consume that raw data and output the desired results. It's simply not how smart contracts are designed.

But what if we could compress that data? What if we could make it succinct?

> **Succinct:** briefly and clearly expressed

A succinct zero-knowledge proof is the solution we're looking for.

We are still early in the zero-knowledge computation meta, but the proof is in the pudding. Succinct proofs are going to change the course of blockchains, wallets and protocols.