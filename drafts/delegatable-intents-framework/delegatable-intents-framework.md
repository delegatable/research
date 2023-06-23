
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

## Where We Stand Today

I want my ETH deposited into the highest earning LSD vault, but I don't want my ETH deposited in the largest liquid staking vault.

The implicit intent is I want my ETH deposited in highest yield vault possible.

The explicit intent is I don't want my ETH deposited in the largest LSD protocol.

Something that captures my intentions to balance profit motives and values of decentralization. A natural and healthy tension between implicit and explicit intents.

The world isn't black and white. We live in a world of spectrums.

We need a guide to help us navigate these spectrums.

# EVM State Mutation Snapshots

When I look at the spectrum of intents. From explicit to implicit. One thing becomes clear to me.

Explicit intents have minimal state conditions.

Implicit intents have maximal state conditions.

If I want to limit my transaction execution between two timestamps I only need 2 data points.

If I want to find the highest yield vault for ETH, there is N data points, relative to the number of actors/entities providing yield for ETH. In other words, to accurately interpret implicit requests, we require larger and more comprehensive snapshots of state mutations across time.

But blockchains aren't good at long-running computations!

This is true, but they are great at long-running state mutations.

What if we could run offchain computations of onchain data, and use the results as inputs for fulfilling implicit intent with levels of accuracy?

### Succinct Proofs

Succinct proofs are cryptographically verifiable artifacts of long-running computations.

For example let's say I want to cryptographically prove the average price of stETH for last 90 days across 3 of the biggest money market protocols on 10 of the largest rollups.

That's a lot of data. Like a lot. No smart contract ever will be able to consume that raw data and output the desired results. It's simply not how smart contracts are designed.

But what if we could compress that data? What if we could make it succinct?

> **Succinct:** briefly and clearly expressed

A succinct zero-knowledge proof is the answer we're looking for.

We are still early in the zero-knowledge computation meta, but the proof is in the pudding. Succinct proofs are going to change the course of blockchains, wallets and protocols.

## Elastic Discrete Time Range Inputs

Let's talk about "elastic discrete time range inputs" as the foundation for implicit intents.

We've informally established implicit intents require context. Context means large amounts of data. Blockchains aren't good at processing large amounts of data. But... blockchains are great at validating cryptographic artifacts.

Succinct proofs can be thought of as complex state (mutations occurring in elastic discrete time ranges) represented as optimally compressed cryptographically verifiable artifacts.

**WTF does that mean?** Let's start with an example.

The Lido protocol generates Merkle Patricia proofs ( i.e. elastic discrete time range inputs) from Curve protocol EVM state mutations, to create a snapshot of the average stETH price.

[https://github.com/lidofinance/curve-merkle-oracle](https://github.com/lidofinance/curve-merkle-oracle "https://github.com/lidofinance/curve-merkle-oracle")

If you extrapolate out this trend/pattern you end up in a world with a rich ecosystem of Open Finance protocols using elastic discrete time range inputs to represent complex EVM state mutation snapshots as maximally compressed succinct proofs.

For example if I want to create a better fiat currency, I may want to aggregate data from multiple global open financial protocols, whose collective usage represents a majority of the world's economic activity, and use those succinct proofs to act as cryptographically verifiable signals for adjusting a digitally native fiat currency.

But for simplicities sake let's start with a more tangible example.

Let's say I want the average price of stETH for last 90 days, using state mutation snapshots from 3 of the biggest protocols, on 10 of the largest rollup. Why you might ask? I want to create the world's biggest synthetics marketplace without relying on oracles.

And the only way to achieve this at scale, without the potential for abuse and capture, is to build financial algorithms that take raw state inputs from sibling money market protocols, to determine the spot price of our algorithmically generated synthetics.

But blockchains are limited by calldata size.

We simply can't express high-fidelity representations of reality (digital or physical) as smart contract protocol inputs.

Let's start with the naive example of how me implement our hypothetical synthetics protocol.

<img width="1360" alt="naive-approach" src="https://github.com/delegatable/research/assets/3408362/7a26f494-e98f-4c8b-9e15-82fd6026e647">


If we continue to build blockchain protocol like we have been for the last several years, our architecture diagrams might look like the above example. In short, our hypothetical synthetics protocols is taking artificial inputs from external money markets through oracle feeds.

Basically an absolutely terrible, and naive way, to build global and open financial markets, when the alternative is cryptographically verifiable succinct proofs. 

<img width="1360" alt="succinct-approach" src="https://github.com/delegatable/research/assets/3408362/a437bc67-f0d9-4a36-a83c-60ff96da3784">

Instead of taking a naive approach to building a synthetics marketplace let's say I want to build an elegant, robust and autonomous Open Finance protocol that will stand the test of time, than I would probably choose to build a protocol that uses cryptographically verifiable elastic discrete time range inputs in the form of succinct zero-knowledge proofs.

Why!? Because it's the future.

# Preparing for The Future

Blockchains are evolving. New rollups are emerging everyday.  

The future is exciting. But also complex.

> "Despite the challenges, achieving scalability, wallet security, and privacy for regular users is crucial for Ethereum's future. It is not just about technical feasibility but about actual accessibility for regular users. We need to rise to meet this challenge."
> - Vitalik Buterin - [The Three Transitions](https://vitalik.ca/general/2023/06/09/three_transitions.html)

We need a better way for users to express their preferences and desires in this future world powered by cryptography. A simple and elegant way to capture the wants, needs and preferences of people that can be processed by advanced computer technology. And we need a framework for developers and engineers to formally express these human desires. Humans aren't robots. We don't speak in code. Our desires are abstract and multi-faceted.

We have to operate in a mechanistic world. A universe represented as succinct proofs. A world with long running operations that get us from point A to point Z.

## Delegatable -- An Intents Framework
Delegatable is an EVM smart contract framework for composing intents.

More precisely, up until this point in time, it's been a framework for defining and composing explicit intents. But it's unique approach to intent composition, means implicit intents are also possible.

#### What Makes Delegatable Unique?
Delegatable has a unique approach to rules enforcement.

Unlike other EVM rules frameworks, [Uniswap V4 hooks](https://github.com/Uniswap/v4-periphery) and [Safe Modules](https://docs.safe.global/learn/safe-core/safe-core-protocol/modules), delegatable doesn't require anything to be installed. Whenever a new Enforcer is deployed on a blockchain, it instantly becomes available to any smart contract inheriting the Delegatable framework, though counterfactual statements and offchain intent signatures.

### How It Works
When a user decides to construct an "intent based transaction" they first decide what type of rules and intents they want to enforce.

Explicit intents includes things like blocknumbers, timestamps and other raw data that can be read from the blockchain storage during runtime.

Implicit intents are more abstract representations of past and future EVM state mutations represented as succinct proofs, and acting as context anchors for informally expressed desires.

### Explicit Enforcers
The [Giftee Cards](https://www.giftee.cards/) proof of concept the "TimestampAfterEnforcer" and "TimestampBeforeEnforcer" enforcers are used to limit the dates when a digital cryptocurrency gift card can be used.

![image](https://github.com/delegatable/research/assets/3408362/891f0701-2773-4d0c-923c-a6fbc4767ae7)

The intents are very explicit.

Examples of other explicit Enforcer modules:

- [BlockNumberAfterEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/BlockNumberAfterEnforcer.sol)
- [BlockNumberBeforeEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/BlockNumberBeforeEnforcer.sol)
- [TimestampAfterEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/TimestampAfterEnforcer.sol)
- [TimestampBeforeEnforcer](https://github.com/delegatable/delegatable-sol/blob/main/contracts/enforcers/TimestampBeforeEnforcer.sol)

<img width="2016" alt="delegable-explicit-enforcers" src="https://github.com/delegatable/research/assets/3408362/944d7eb7-4d27-47e7-8268-7653052f300f">


### Implicit Enforcers

Examples of potential implicit intent modules:
- Dollar Cost Averaging Enforcer
- Highest Yield Vault Enforcer
- Multi-Chain Average Price Enforcer

<img width="2016" alt="delegable-implicit-enforcers" src="https://github.com/delegatable/research/assets/3408362/211488c3-c41b-4f3f-b678-b3962346db9c">

