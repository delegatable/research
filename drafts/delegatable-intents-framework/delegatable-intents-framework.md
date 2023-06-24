
Contents

1. Introduction
	1. Searching for a Better Tomorrow
	2. Where We Stand Today
2. Defining Intents
	1. Spectrum of Capabilities
	2. Explicit Intents
	3. Implicit Intents
	4. User Consent
3. Formalizing Implicit Intents
	1. EVM State Mutation Snapshots
	2. Succinct Proofs
	3. Elastic Discrete Time Range Inputs
4. Preparing for the Future
	1. Delegatable - An Intents Framework
	2. Explicit Enforcers
	3. Implicit Enforcers

# Introduction
As mentioned in [Intent-Based Architectures and Their Risks](https://www.paradigm.xyz/2023/06/intents) post, intents are quickly becoming an important topic. Potentially transforming the Internet user experience at the core.

This article aims to establish a shared language for describing intents. 

Exploring the full spectrum of intents -- from explicit to implicit. While also examining the technologies that will drive these innovations forward and how that will ultimately impact the user experience.

Let's start with the why. A better tomorrow.

## Searching for a Better Tomorrow
Let's imagine a hypothetical universe. A universe with advanced computer technology catering to billions of users all around the world. It's a future where people choose only to interact with advanced computer technology with strong cryptographic guarantees. 

If X happens it can be cryptographically verified using Y proving method.

Users love this approach. They don't have to sit around a computer all day clicking buttons.

Instead they can express intents about how they want the computer to act on the their behalf. User describe what future they want an let this advanced computer technology acting out these requests.

What's matter is results. Cryptographically provable results.

This is the default user experience of the Internet in the year 2035. A combination of machine learning and cryptographically verifiable distributed compute powers this future Internet.

The Internet is alive. It's emergent. And it responds to people's wants and needs.

It's a tomorrow that will exist. We simply have to keep building.

## Where We Stand Today

Let's talk about today. The problems we can solve right now.

I want my ETH deposited into the highest earning liquid staking vault, but I don't want my ETH deposited in the largest liquid staking vault. I'm motivated by profit (within reason) and driven by values of decentralization.

**My intents are clear.**

The implicit intent is I want my ETH deposited in highest yield vault possible.

The explicit intent is I don't want my ETH deposited in the largest LSD protocol.

Keep this example in mind as you continue to read. We're going to expand it's scale and scope.

But first, what can we take away from this example, that may appear simple at first glance, yet is deceivingly complex? One take-away is that a natural, and healthy, tension exists between implicit and explicit intents.

**Intents undoubtedly live on a spectrum.** And consent is the bedrock for these intents.

# Defining Intents
First, let's take a moment to define "intents" as they're understood today.

Let's start with the informal definition of intents provided by Paradigm in the [# Intent-Based Architectures and Their Risks](https://www.paradigm.xyz/2023/06/intents) post.

> Informally, **an intent is signed a set of declarative constraints which allow a user to outsource transaction creation to a third party without relinquishing full control to the transacting party.**

And a more formal definition of intents.

> **Signed messages which allow for a set of state transitions from a given starting state, a special case of which is a transaction which allows for a unique transition**.

## Spectrum of Capabilities

Let's start with the ["declarative programming"](https://twitter.com/CannnGurel/status/1663292583550803969) referenced in the Paradigm article.

Imperative - What we have today
> (imperative): hop on to ur scooter, go to Domino's around the corner, order item#4, and bring it. here is your 20 bucks; 18 for pizza, and 2 for gas.

Declarative - What we want
> intent (declarative): I will pay 20 bucks for a Hawaiian pizza at my door by 8pm.

The declarative example is perfect. Including a combination of explicit and implicit intents.

The explicit intent is "pizza at my door by 8pm" which states very clearly the user expects the pizza to arrive by 8pm... today.

And the implicit intent is "pay 20 bucks for a Hawaiian pizza" which loosely describes what the user wants. Even though we as humans take it for granted, because it happen automatically, the following questions have to be formally answered in a way that a machine understands:
- what is a buck?
- what is a pizza?
	- what makes it hawaiian?
	- will the pizza include standard ingredients? (i.e. wheat dough vs cauliflower dough)

A clear axiom presents itself. Intents live on a spectrum -- from highly explicit to vaguely implicit.

And this spectrum deeply impacts how engineers can approach the problem of "acting out" user intents.

Spectrums can be hard to formally describe, but let's do our best

## Explicit Intents
Explicit intents are clear instructions.

> Explicit: stated clearly and in detail, leaving no room for confusion or doubt.

When and who statements tend to be explicit.
- Execute this transaction between Timestamp A and Timestamp B elapses
- Execute this transaction if Governance Proposal A or Z passes. 
- Execute this transaction in Protocol A,B, C and/or D on Optimism or Arbitrum

## Implicit Intents
Implicit intents are vague instructions.

> Implicit: something is understood although not clearly or directly expressed or conveyed

Where and what statements tend to implicit
- Move assets into the highest yield bearing liquid staking derivative protocol for ETH.

## User Consent
Core to declarative programming is delegated user consent.

If a computer doesn't have permissions to act on behalf of user's intentions, nothing is possible.

# Formalizing Implicit Intents
I have no doubt we can solve explicit intent execution in blockchain environments. It's easy to enforce and formally describe "execute this transaction on between this timestamps or if this governance proposal passes."

The bigger challenge is implicit intents.

How is it possible for computers to interpret implicit intents?

**Data. And lots of it. Plus succinct proofs.**

Proofs that cryptographically verify the output of long-running computations.

## EVM State Mutation Snapshots

When I look at the spectrum of intents. From explicit to implicit. One thing becomes clear to me.

Explicit intents have minimal state conditions.

Implicit intents have maximal state conditions.

If I want to limit my transaction execution between two timestamps I only need 2 data points.

If I want to find the highest yield vault for ETH, there is N data points, relative to the number of actors/entities providing yield for ETH. In other words, to accurately interpret implicit requests, I'm also required to have snapshots of EVM state mutations across discrete time ranges, represented as succinct proofs, which can than be used as cryptographically verifiable smart contract function inputs, that verify the output of long-running computations, not suitable for blockchain environments.

The question becomes... *How can we generate these succinct proofs?*

## Succinct Proofs

Succinct proofs are cryptographically verifiable artifacts of long-running computations.

For example let's say I want to cryptographically prove the average price of stETH for last 90 days across 3 of the biggest money market protocols on 10 of the largest rollups. That's a lot of data. No smart contract **ever** will be able to consume that amount of raw data. It's simply not how blockchains and smart contracts are designed.

But what if we could compress that data? What if we could make it succinct?

> **Succinct:** briefly and clearly expressed

A succinct zero-knowledge proof is the answer we're looking for.

Vitalik Buterin recently [outlined](https://vitalik.ca/general/2023/06/20/deeperdive.html#what-kinds-of-proof-schemes-can-we-use) types of proofs that can be used for managing cross-chain keystores, for when Account Abstraction wallets become the default, instead of externally owned accounts (EOA).

- **Merkle proofs**
- **General-purpose ZK-SNARKs**
- **Special-purpose proofs (eg. with KZG)**
- **[Verkle proofs](https://vitalik.ca/general/2021/06/18/verkle.html)**, which are somewhere between KZG and ZK-SNARKs on both infrastructure workload and cost.

While Vitalik states he believes these types of proofs aren't suitable for Decentralized Finance, due to the speed.

> Some of these speeds for trustless cross-chain operations are unacceptably slow for many defi use cases; for those cases, you do need faster bridges with more imperfect security models. For the use case of updating wallet keys, however, longer delays are more acceptable: you're not _delaying transactions_ by hours, you're delaying _key changes_.

The counter-argument could also be made most of today's DeFi protocols won't last another couple of years, and the Open Finance protocols of tomorrow, will use elastic discrete time range inputs as protocol feedback loops (e.x. [RAI PID Controller](https://medium.com/reflexer-labs/summoning-the-money-god-2a3f3564a5f2)) and slowness is actually a desirable property for most global open finance protocols of the future.

And in a world with 100's or 1,000's of rollups, all with highly-valuable economic signals, the only reasonable answer is to accommodate for this complexity via succinct proofs.

### Real-World Example

The Lido protocol generates Merkle Patricia proofs ( i.e. elastic discrete time range inputs) from Curve protocol EVM state mutations, to create a snapshot of the average stETH price.

[https://github.com/lidofinance/curve-merkle-oracle](https://github.com/lidofinance/curve-merkle-oracle "https://github.com/lidofinance/curve-merkle-oracle")

We are still early in the zero-knowledge computation meta, but the proof is in the pudding. Succinct proofs are going to change the course of blockchains, wallets and protocols.

## Elastic Discrete Time Range Inputs

Let's talk about "elastic discrete time range inputs" as the foundation for implicit intents.

We've informally established implicit intents require context. Context means large amounts of data. Blockchains aren't good at processing large amounts of data. But... blockchains are great at validating cryptographic artifacts.

Succinct proofs can be thought of as complex state (mutations occurring in elastic discrete time ranges) represented as optimally compressed cryptographically verifiable artifacts.

As referenced above, Lido uses Merkle Patricia proofs to generate cryptographically verifiable artifacts to proving the average cost of stETH using EVM state mutations happening in the Curve protocol.

If we extrapolate out this trend/pattern you end up in a world with a rich ecosystem of Open Finance protocols using elastic discrete time range inputs to represent complex EVM state mutation snapshots as maximally compressed succinct proofs.

For example if I want to create a better fiat currency, I may want to aggregate data from multiple global open financial protocols, whose collective usage represents a majority of the world's economic activity, and use those succinct proofs to act as cryptographically verifiable signals for adjusting a digitally native fiat currency.

But for simplicities sake let's start with a more tangible example.

Let's say I want the average price of stETH for last 90 days, using state mutation snapshots from 3 of the biggest protocols, on 10 of the largest rollup. Why you might ask? I want to create the world's biggest synthetics marketplace without relying on oracles.

And the only way to achieve this at scale, without the potential for abuse and capture, is to build financial algorithms that take raw state inputs from sibling money market protocols, to determine the spot price of our algorithmically generated synthetics.

But blockchains are limited by calldata size.

We simply can't express high-fidelity representations of reality (digital or physical) as smart contract protocol inputs.

Let's start with the naive example of how me implement our hypothetical synthetics protocol.

<img width="100%" alt="naive-approach" src="https://github.com/delegatable/research/assets/3408362/7a26f494-e98f-4c8b-9e15-82fd6026e647">

If we continue to build blockchain protocol like we have been for the last several years, our architecture diagrams might look like the above example. In short, our hypothetical synthetics protocols is taking artificial inputs from external money markets through oracle feeds.

Basically an absolutely terrible, and naive way, to build global and open financial markets, when the alternative is cryptographically verifiable succinct proofs. 

<img width="100%" alt="succinct-approach" src="https://github.com/delegatable/research/assets/3408362/a437bc67-f0d9-4a36-a83c-60ff96da3784">

Instead of taking a naive approach to building a synthetics marketplace let's say I want to build an elegant, robust and autonomous Open Finance protocol that will stand the test of time, than I would probably choose to build a protocol that uses cryptographically verifiable elastic discrete time range inputs in the form of succinct zero-knowledge proofs.

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

<img width="100%" alt="delegable-explicit-enforcers" src="https://github.com/delegatable/research/assets/3408362/944d7eb7-4d27-47e7-8268-7653052f300f">


### Implicit Enforcers

Examples of potential implicit intent modules:
- Dollar Cost Averaging Enforcer
- Highest Yield Vault Enforcer
- Multi-Chain Average Price Enforcer

<img width="100%" alt="delegable-implicit-enforcers" src="https://github.com/delegatable/research/assets/3408362/211488c3-c41b-4f3f-b678-b3962346db9c">

