---
layout: post
title: Annotated Ethereum Roadmap
toc: true
---

This document aims to serve as an entry point for the various items on [the Ethereum roadmap](/images/roadmap.jpg), with a quick summary along with links for those who want to dive deeper.

It is meant as a living document, feel free to [contact me](https://twitter.com/domothy) if any of the information presented here is unclear, inaccurate, outdated or missing better links.

**Note:** As indicated by arrows on the roadmap, the various stages listed are *not* consecutive, various efforts are happening in parallel.

## The Merge

*Goal: Have an ideal, simple, robust and decentralized proof-of-stake consensus*

### What's done

* December 1st, 2020 - **Beacon chain launch** 
    * The introduction of Ethereum's *consensus layer* secured by the ETH staked by validators
    * Known as *Phase 0* in the [consensus specifications](https://github.com/ethereum/consensus-specs/tree/dev/specs/phase0) (annotated version by [Vitalik](https://github.com/ethereum/annotated-spec/blob/master/phase0/beacon-chain.md) and [Danny Ryan](https://notes.ethereum.org/@djrtwo/Bkn3zpwxB))
* October 27th, 2021 - **Warmup fork (Altair)** – Consensus client developpers had a trial run at coordinating a hard fork upgrade
    * Altair introduced *[sync committees](https://github.com/ethereum/annotated-spec/blob/master/altair/sync-protocol.md#introduction)* to support light clients, and tweaked some penalties.
    * [Altair Announcement](https://blog.ethereum.org/2021/10/05/altair-announcement)
    * [Altair specifications](https://github.com/ethereum/consensus-specs/tree/dev/specs/altair) ([annotated version](https://github.com/ethereum/annotated-spec/blob/master/altair/beacon-chain.md))
    * ["What's new in ETH2" edition about Altair](https://hackmd.io/@benjaminion/eth2_news/https%3A%2F%2Fhackmd.io%2F%40benjaminion%2Fwnie2_211105)
* September 15, 2022 - **Merge! No more PoW** – The big merge between the consensus layer and the execution layer, at [block number 15,537,394](https://etherscan.io/block/15537394)
* April 12th, 2023 - **Withdrawals** – Enabling validators to withdraw all or part of their stake - happened at [slot #6,209,536](https://beaconcha.in/slot/6209536)
    * [Capella fork](https://github.com/ethereum/consensus-specs/tree/dev/specs/capella) specifies the changes on the consensus layer
    * [EIP-4895](https://eips.ethereum.org/EIPS/eip-4895) specifies the changes on the execution layer
    * [Tim Beiko's FAQ about withdrawals](https://github.com/timbeiko/eth-roadmap-faq#withdrawals)
    * [Technical FAQ for validators](https://notes.ethereum.org/@launchpad/withdrawals-faq)
* **Distributed validators** – "*multisig but for staking*", where `n` people share the same validator and `m-of-n` have to agree on how it behaves
    * Enhances staking by protecting against accidental slashing, and making it more accessible (e.g. by trustlessly splitting the 32 ETH required among multiple participants)
    * This is not an in-protocol thing (yet?), teams such as [SSV](https://ssv.network) and [Obol](https://obol.tech/) are leading the R&D effort

### What's next

* **Secret leader election** (SLE)
    * Today, the validator selected to propose a block (the *leader* of the slot) is known a bit ahead of time, enabling a potential DoS attack specifically targetting leaders of upcoming blocks
    * [ethresear.ch](https://ethresear.ch/t/whisk-a-practical-shuffle-based-ssle-protocol-for-ethereum/11763) post about a Single SLE protocol based on random shuffling: No one knows who will be the slot's leader except the leader themselves, until they reveal their block along with a proof of their leadership
    * [non-single secret leader election](https://ethresear.ch/t/secret-non-single-leader-election/11789) might be an option too
* **Single Slot Finality** — Finalize the chain every slot (12 seconds) instead of every other epoch (12.8 minutes), relies on:
  * **Per-slot participation selection** — Figure out the best SSF-compatible way to choose how validators are selected to attest to slots, aggregate signatures, etc.
    * [Sticking to 8192 signatures per slot](https://ethresear.ch/t/sticking-to-8192-signatures-per-slot-post-ssf-how-and-why/17989) outlines a few ideas for overhauling how signatures are handled
  * **SSF specification** — Figure out the best way to do Single Slot Finality
      * [Paths toward SSF](https://notes.ethereum.org/@vbuterin/single_slot_finality) for musings on how to reach SSF
* **Increase validator count** — Once we have SSF, having more validators participate as hardware/bandwidth becomes better is a good ongoing goal (somewhat similar to gas limit increases, etc.)
* **Quantum-safe aggregation-friendly signatures** - Part of the long-term effort to make Ethereum safe from quantum computers before it becomes a plausible concern
    * The cryptography underlying the BLS signature scheme used is known to be broken by quantum computers, but the alternative signatures schemes known to be quantum-safe aren't as efficiently aggregated as BLS (Hence the need for a scheme that is both quantum-safe and aggregation-friendly)
    * The two leading quantum-safe approaches are [STARK-based](https://hackmd.io/@vbuterin/stark_aggregation) and Lattice-based

## The Surge

*Goal: 100,000 transactions per second and beyond (on rollups)*

"on rollups" is key – The Surger will not result in 100,000 TPS on Layer 1. Changes made to Ethereum's core protocol all aim at helping rollups scale massively.

A key concept underlying The Surge is **Data Availability** (or DA): the endgame involves making *the availability of data itself* a validity check: Just like nodes won't follow a fork containing an invalid state transition (e.g. someone arbitrarility printing themselves millions of ETH), nodes won't follow a fork with unavailable data – which is critical for fully trustless scaling via rollups.

Here are some relevant links to familiarize yourself with the concepts underlying The Surge:

* [Ethereum's rollup-centric roadmap](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698)
* [Blobspace 101](https://domothy.com/blobspace)
* [Explain Like I'm 12: How Ethereum scales](https://www.reddit.com/r/ethereum/comments/skb5h6/how_ethereum_scales_eli12/)
* [An incomplete guide to rollups](https://vitalik.ca/general/2021/01/05/rollup.html)
* [Why rollups + data shards are the only sustainable solution for high scalability](https://www.reddit.com/r/ethfinance/comments/pk57n7/why_rollups_data_shards_are_the_only_sustainable/)
* [On the importance of shared security](https://www.reddit.com/r/ethereum/comments/sgd3zt/a_quick_reminder_of_what_shared_security_means/)
* [Ethereum.org article on Data Availability](https://ethereum.org/en/developers/docs/data-availability/)
* [On the role of Polynomial Commitment Schemes in scaling Ethereum](https://scroll.io/blog/kzg)
* [Devcon danksharding workshop](https://www.youtube.com/watch?v=8L2C6RDMV9Q)

### What's done

* **EIP-4844 specification** - see [eip4844.com](https://eip4844.com) for more info and a [FAQ](https://www.eip4844.com/#faq)
    * Specs found [here](https://eips.ethereum.org/EIPS/eip-4844) for the execution layer and [here](https://github.com/ethereum/consensus-specs/tree/dev/specs/deneb) for consensus layer
    * The [KZG ceremony](https://ceremony.ethereum.org) also happened flawlessly
* (Prototype) **Optimistic rollup fraud provers** – Allows anyone to submit a proof that a rollup sequencer acted maliciously
* (Prototype) **ZK-EVMS** – A single rollup sequencers creates a proof of EVM computation that can be verified quickly and cheaply by everyone else (including a smart contract on L1)

### What's next

* **EIP-4844 implementation** – roll out EIP-4844 to mainnet (schedule for the Dencun upgrade ~Q1 2024)
    * [Overview of EIP4844 implementation timeline](https://twitter.com/liamihorne/status/1595592154650288129)
* **Basic rollup scaling** - relies on the following:
    * EIP-4844 - The scaling is still deemed basic/limited, due to the nature of "every node downloads all the data" restricting the viable capacity of blobspace
    * *Limited training wheels* for rollups (see the [proposed milestones](https://ethereum-magicians.org/t/proposed-milestones-for-rollups-taking-off-training-wheels/11571/6))
* **Full rollup scaling** - relies on:
    * **peerDAS** — a [design](https://ethresear.ch/t/peerdas-a-simpler-das-approach-using-battle-tested-p2p-components/16541) for safely expanding Ethereum's blobspace beyond 4844's parameters
        * Also included in the [proposed path toward full danksharding](https://ethresear.ch/t/from-4844-to-danksharding-a-path-to-scaling-ethereum-da/18046)
    * **Efficient DA self-healing**: Being able to efficiently reconstitute all the data in the harshest network conditions (e.g. malicious validators attacking, or prolonged downtime of a big chunk of nodes)
    * *No training wheels* for rollups: fully decentralized sequencers, trustless fraud provers, immutable contracts, etc.
* **Quantum-safe, trusted-setup-free commitments** — Part of the long-term effort to make Ethereum safe from quantum computers before it becomes a plausible concern
    * While efficient and powerful, the polynomial commitment used everywhere (KZG) is not quantum-safe and requires a trusted setup. Research into a more ideal commitment suitable for the long term is ongoing, with the eventual goal to "hot swap" KZG under the hood (it'll probably be STARKs)

## The Scourge

*Goal: mitigate **centralization concerns** in the Ethereum PoS design, particularly around **MEV** and **liquid staking / pooling***

Relevant links:

* [Credible Neutrality as a Guiding Principle](https://nakamoto.com/credible-neutrality/)
* [Various twitter threads about MEV](https://twitter.com/bertcmiller/status/1402665992422047747)
* [Write-up about MEV and PBS](https://pseudotheos.mirror.xyz/i7sv9SFb1e64W2ax_kYwp68O0M2NdACtOu9Hj12SPP8)
* [List of links about PBS](https://notes.ethereum.org/@domothy/pbs_links)

### What's done

* **Extra-protocol MEV markets** – The [MEV-Boost](https://github.com/flashbots/mev-boost) middleware allows the average validator to profit from MEV without having to run sophisticated MEV strategies themselves. 
    * This solution by itself incomplete as it has [issues with censorship](https://www.mevwatch.info/)
    * See [the Cost of Resilience](https://writings.flashbots.net/the-cost-of-resilience/) and [SUAVE](https://writings.flashbots.net/the-future-of-mev-is-suave/) for ideas and plans to make these extra-protocol markets more resilient

### What's next

**MEV track**

* **Enshringed PBS** — MEV-Boost but directly enforced by the protocol, relies on:
    * **Enshrined PBS spec** — Coming up with a foolproof ePBS design is no easy task. Here are several proposed designs:
        * [A viable path to ePBS](https://ethresear.ch/t/why-enshrine-proposer-builder-separation-a-viable-path-to-epbs/15710)
        * [Payload timeliness committee](https://ethresear.ch/t/payload-timeliness-committee-ptc-an-epbs-design/16054)
        * [Single-Slot PBS using attesters as distributed availability oracle](https://ethresear.ch/t/single-slot-pbs-using-attesters-as-distributed-availability-oracle/11877)
  * **Inclusion lists** – Let proposers put restrictions on block builders, namely to force them to include transactions
      * ["No free lunch" inclusion list design](https://ethresear.ch/t/no-free-lunch-a-new-inclusion-list-design/16389)
      * [Inclusion list notes](https://notes.ethereum.org/@fradamt/H1ZqdtrBF)
      * [Research into constraining builders without burdening proposers](https://ethresear.ch/t/how-much-can-we-constrain-builders-without-bringing-back-heavy-burdens-to-proposers/13808)
* **MEV burn** – Letting the blockchain capture value that is otherwise extracted from the on-chain economy
    * Design based on committees: [MEV burn design](https://ethresear.ch/t/mev-burn-a-simple-design/15590)
    * Design based on multiple proposers: [MEV burn proposal through proposer auction](https://ethresear.ch/t/burning-mev-through-block-proposer-auctions/14029)
    * [Committee-driven MEV smoothing](https://ethresear.ch/t/committee-driven-mev-smoothing/10408) would render the protocol aware of MEV, mixed with [capping the validator set through economic incentives](https://notes.ethereum.org/@vbuterin/single_slot_finality#Economic-capping-of-total-deposits) would indirectly burn MEV through negative issuance
* **Application-layer MEV minimization** — Not directly L1-related, this item involves developpers keeping MEV in mind when designing their dapps. [Here are a few examples](https://www.mev.wiki/solutions/mev-minimization) of dapps that employ MEV minimization tactics
* **Explore execution tickets** — A new design for explicitly separating the two duties from validators: *attesting to blocks* and *proposing new blocks*
    * (formely known as *Attester-Proposer Separation*)
    * [ethresear.ch post](https://ethresear.ch/t/execution-tickets/17944)
    * [Justin Drake's talk](https://youtu.be/IrJz4GZW-VM?t=153) at Columbia CryptoEconomics Workshop
* **Distributed block building**
    * Talk on [Block building after the merge](https://www.youtube.com/watch?v=KP5ppCRH0iM) which mentions decentralized block building
    * Talk on [decentralizing builders](https://www.youtube.com/watch?v=fAgrIdyWIqc)
    * [Some ideas regarding distributed block building](https://github.com/flashbots/mev-boost/issues/139)
* **Explore preconfirmations** — Enable proposers and/or builders to commit to including transactions, in order to enhance user experience
    * [Based preconfirmations](https://ethresear.ch/t/based-preconfirmations/17353)

**Staking economics / experience track**

* **Raise max effective balance** – Enable the consolidation of large stakers into a single validator, drastically lowering the number of attestations to reduce bandwidth load on the beacon chain
    * [ethresear.ch post](https://ethresear.ch/t/increase-the-max-effective-balance-a-modest-proposal/15801)
* **Improve node operator usability** — See other items like Verkle trees and SNARKs that make validator clients much more light weight, but also UX improvements are welcome in here too (e.g. make running a node a simple install-and-run experience)
* **Reducing minimum balance** — 32 ETH is a big deterrant for solo staking, reducing it is becoming more and more of a security
    * The [Paths to SSF](https://notes.ethereum.org/@vbuterin/single_slot_finality) document highlights several potential staking designs where the 32 ETH minimum is reduced or outright removed
* **Explore solutions to liquid staking centralization** — Mitigating centralization concerns around big liquid staking pools controlling
    * [Liquid staking maximalism](https://notes.ethereum.org/@dankrad/r1xAbQXm2) design by Dankrad
    * [Musings about enshrining liquid staking or making decentralized liquid staking much safer](https://vitalik.eth.limo/general/2023/09/30/enshrinement.html)

## The Verge

*Goal: **verifying** blocks should be super easy - download N bytes of data, perform a few basic computations, verify a SNARK and you're done*

This section is essentially about filling ["the client gap"](https://www.reddit.com/r/ethereum/comments/ryk3it/my_first_impressions_of_web3/hrrz15r/) by making light clients finally viable: Not everyone wants to or can run a full node. The Verge aims to introduce trustless or trust-minimized alternatives that are easy to run and don't require a lot of storage and bandwidth. The ultimate endgame of The Verge is having these light clients provide security guarantees that are equal to today's full nodes.

Everything relies on zero-knowledge technology such as SNARKs and STARKs, which themselves rely on polynomial commitment schemes. Here are some links about that:

* [An approximate introduction to how zk-SNARKs are possible](https://vitalik.ca/general/2021/01/26/snarks.html)
* [Anatomy of a STARK](https://aszepieniec.github.io/stark-anatomy/)
* [zkSNARKS explained like you're someone who knows some math and some coding](https://www.reddit.com/r/zkTech/comments/tfjvrj/zksnarks_explained_like_youre_someone_who_knows/)
* [On the role of Polynomial Commitment Schemes in scaling Ethereum](https://scroll.io/blog/kzg)

### What's done

* **Most serious EVM DoS issues solved** – Mainly gas pricing issues, [fixed in the Berlin upgrade](https://medium.com/ethereum-cat-herders/the-berlin-upgrade-overview-2f7ad710eb80)
* **Basic light client support (sync committees)** – Thanks to sync committees, it is easy to build light clients that follow the consensus layer
    * See how [Helios client](https://a16zcrypto.com/building-helios-ethereum-light-client/) is leveraging sync committees (with a good write-up on how these committees work)
* **Verkle tree specification and implementation** — The plan for how Verkle trees are going to work is coming along nicely! 

### What's next

* **SNARK-based light clients** – SNARKify the sync committee transition to quickly prove which validators form the current sync committee
    * [Helios](https://a16zcrypto.com/posts/article/an-introduction-to-light-clients/) is working on leveraging the power of SNARKs in their light client implementation
* **Verkle trees** - Replace the data structure used for the global state by a more efficient one, making state proofs much shorter (enabling *stateless clients*!) as well as more zk-friendly
    * [List of links about Verkle Trees](https://notes.ethereum.org/@domothy/verkle_links) 
    * [Verkle.info](https://verkle.info/)
* **Fully SNARKed Ethereum** – The following 3 items put together constitute a major milestone toward [Ethereum's Endgame](https://vitalik.ca/general/2021/12/06/endgame.html) of having extremely efficient and trustless block verification:
 * * **SNARK for Verkle proofs** – By merging Verkle proofs into a single SNARK, blocks will contain a short standalone proof about the parts of the state they modify, so it won't be necessary to verify the whole state of block `N-1` to verify that block `N` modified it correctly.
 * * **SNARK for consensus state transition** – Move away from the merely trust-minimized sync committees onto fully trustless verification of *everything* happening on the consensus layer
 * * **SNARK for L1 EVM** — Leveraging the efforts done by rollup teams on zk-EVM by integrating it in L1 directly
      * See this [post on enshrined rollups](https://www.reddit.com/r/ethereum/comments/vrx9xe/ama_we_are_ef_research_pt_8_07_july_2022/if7auu7/?context=1)
* **Explore EVM verification precompile** — Being able to verify EVM execution inside the EVM itself, inception-style. More detail [here](https://notes.ethereum.org/@vbuterin/enshrined_zk_evm)
* **SNARK / STARK ASICs** – Having hardware specifically designed to be fast at crafting SNARK or STARK proofs
* **Move to quantum-safe SNARKs (e.g. STARKs)** – Part of the long-term effort to make Ethereum safe from quantum computers before it becomes a plausible concern
    * SNARKs are efficient be rely on cryptography known to be broken by quantum computers, while STARKs aren't

## The Purge

*Goal: **simplify** the protocol, **eliminate technical debt** and **limit costs** of participating in the network by clearing old history*

### What's done

* **Most serious EVM Denial-of-Service issues solved** - Mostly solved by all the [gas repricings](https://medium.com/ethereum-cat-herders/the-berlin-upgrade-overview-2f7ad710eb80) done in the Berlin upgrade
* **Beacon chain fast sync** – All the development effort towards syncing from a recent finalized epoch rather than from genesis (known as "checkpoint sync" in most consensus clients)
* **EIP-4444 specification** – See [the EIP specification](https://eips.ethereum.org/EIPS/eip-4444)

### What's next

* **History Expiry** — Reduces storage requirements, sync time and code complexity by letting old history expire
    * See this [twitter thread](https://twitter.com/lightclients/status/1462576116359569411)
    * Relies on **implementation of EIP-4444**, which itself is contingent on **p2p history** retrievial (like [Portal Network](https://www.portal.network/))
    * [Vitalik's AMA on History Expiry](https://www.reddit.com/r/ethereum/comments/qzvsfq/impromptu_technical_ama_on_history_expiry/)
* **State expiry** – Fix the whole "pay once, have your data stored forever by everyone" problem regarding the state
    * The idea is to automatically expire unused portions of the state and only keeping a verkle tree root that users can use to revive expired state should they need it
    * [Vitalik's AMA on State Expiry](https://www.reddit.com/r/ethereum/comments/o9s15i/impromptu_technical_ama_on_statelessness_and/)
    * Relies on:
        * **Address space extension** — [Increase the size of addresses](https://ethereum-magicians.org/t/increasing-address-size-from-20-to-32-bytes/5485) from 20 bytes to 32 bytes to protect against collisions and add data about the state's period
        * **Application analysis** — Figure out how it might break current applications/contracts and how they can adapt
* **LOG reform** — Simplify the way [event logs](https://ethereum.github.io/execution-specs/autoapi/ethereum/frontier/bloom/index.html) work to allow more efficiently searching of historical events
* **Serialization harmonization** — The execution layer uses [RLP](https://ethereum.org/en/developers/docs/data-structures-and-encoding/rlp/) for data serialization, while the consensus layer uses [SSZ](https://ethereum.org/en/developers/docs/data-structures-and-encoding/ssz/) this would get rid of RLP in favor of using SSZ everywhere
* **Remove old transaction types** — Stop supporting old transaction types (see [EIP-2718](https://eips.ethereum.org/EIPS/eip-2718)) to remove code complexity from clients (at the cost of some backwards compatibility)
* **EVM simplification track**
    * **Ban SELFDESTRUCT** — This opcode is the root of many problems
        * [Pragmatic destruction of SELFDESTRUCT](https://hackmd.io/@vbuterin/selfdestruct) explains the why and how of removing this opcode
        * Relevant EIPs: [EIP-4758](https://eips.ethereum.org/EIPS/eip-4758) and [EIP-4760](https://eips.ethereum.org/EIPS/eip-4760) and [discussion](https://ethereum-magicians.org/t/eip-4758-deactivate-selfdestruct/8710)
    * **Simplify gas mechanics** — Involves removing a lot of gas-related EVM features mentioned [here](https://hackmd.io/@vbuterin/evm_feature_removing)
    * **Precompiles -> EVM implementations** — Get rid of [precompiled contracts](https://www.evm.codes/precompiled?fork=merge) in favor of direct EVM implementations (namely big modular arithmetic, see The Splurge)

## The Splurge

*Goal: Fix **everything else***

All the nice-to-have things that aren't required for the higher priority stuff belong in The Splurge. The biggest item is [account abstraction](https://docs.ethhub.io/ethereum-roadmap/ethereum-2.0/account-abstraction/), but also small tweaks to existing things.

### What's done

* **EIP-1559** — This famous [EIP](https://eips.ethereum.org/EIPS/eip-1559) came with [many benefits](https://domothy.com/eip1559/) beyond just burning ETH
* **ERC-4337 specification** — This [ERC](https://eips.ethereum.org/EIPS/eip-4337) aims at introducing Account Abstraction without modifying the core protocol 
    * [Initial explainer on ERC-4337](https://medium.com/infinitism/erc-4337-account-abstraction-without-ethereum-protocol-changes-d75c9d94dc4a)

### What's next

* **Endgame EIP-1559** – Enhance EIP-1559 by making it [multidimensional](https://ethresear.ch/t/multidimensional-eip-1559/11651), [more like an AMM-curve](https://ethresear.ch/t/make-eip-1559-more-like-an-amm-curve/9082) and [time-aware](https://eips.ethereum.org/EIPS/eip-4396)
* **EVM improvement track** along with the simplification track from The Purge leading to the **EVM endgame**
    * **EVM Object Format (EOF)** — A set of multiples EIPs allowing validating and versioning EVM bytecode when it is deployed. Various explainers: [[1]](https://notes.ethereum.org/@ipsilon/evm-object-format-overview), [[2]](https://twitter.com/lightclients/status/1593270266909450241), [[3]](https://www.reddit.com/r/ethereum/comments/ztso6h/a_simple_explanation_of_eof_evm_object_format/)
    * **Big modular arithemetic** – A lot of the roadmap's cryptography relies on modular arithmetic over very large numbers, which could be done more efficiently in the EVM directly
    * **Further EVM improvements** — Anything else that's worth adding to improve the EVM – or [removing](https://hackmd.io/@vbuterin/evm_feature_removing) to get rid of complexity
* **Account abstraction track** leading to the **Endgame account abstraction**. See [Vitalik's descriptions](https://notes.ethereum.org/@vbuterin/account_abstraction_roadmap#Convert-an-EOA-into-a-smart-contract-wallet) on the following items for more detail:
    * **ERC-4337** – Developing compliant smart wallets that actually gain adoption
    * **Voluntary EOA conversion** — With an EIP, allow a normal account to irreversibly add code to convert into it into a contract, namely to become a 4337-compliant smart wallet.
    * **In-protocol enshrining** — Make the above conversion mandatory for all existing accounts
* **Verifiable Delay Functions (VDFs)** — Essentially "non-parallelizable proof of work" which would enhance the [randomness used in PoS](https://github.com/ethereum/annotated-spec/blob/master/phase0/beacon-chain.md#aside-randao-seeds-and-committee-generation) and other things
    * See [this ethresear.ch post](https://ethresear.ch/t/verifiable-delay-functions-and-attacks/2365) about VDFs and their potential use
* **Explore solution for dust accounts** – Rescuing "dust funds" that costs more gas fees to move than they are worth. See a [bunch of ideas here](https://ethereum-magicians.org/t/some-medium-term-dust-cleanup-ideas/6287)
* **Explore deep cryptography**, stay up-to-date with latest cryptographic magic to see how it can be integrated inside net cryptoeconomic gadgets. Things like:
    * [Obfuscation](https://en.wikipedia.org/wiki/Indistinguishability_obfuscation) for privacy
    * [Fully homomorphic encryption](https://vitalik.eth.limo/general/2020/07/20/homomorphic.html) for things like [encrypted mempools](https://www.youtube.com/watch?v=fHDjgFcha0M)
    * [One-shot signatures](https://www.reddit.com/r/ethereum/comments/14vpyb3/ama_we_are_ef_research_pt_10_12_july_2023/jrnyxa8/) for getting rid of slashing, or implement "quantum cash"
* **Explore delay-encrypted mempools** — To enhance mempool privacy, reduce censorship, reduce toxic MEV
    * [Writeup about encrypted mempools](https://joncharbonneau.substack.com/p/encrypted-mempools) 