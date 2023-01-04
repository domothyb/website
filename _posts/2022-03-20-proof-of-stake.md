---
layout: post
title: "Stuff you should know: Proof of Stake edition"
---

Various questions and misconceptions about Ethereum Proof of Stake

## Wat merge?

A lot more info can be found on [ethmerge.com](https://ethmerge.com/) so I will keep this section light

* When the merge happens, Ethereum will be secured by Proof of Stake instead of Proof of Work.

* The Merge is not "ETH 2.0", there is no ETH 2.0, [it's an obsolete term.](https://blog.ethereum.org/2022/01/24/the-great-eth2-renaming/)

* **If you currently hold ETH, you don't need to do anything.** You will still hold the same amount of ETH after the merge, there is no "ETH2 coin", no need to migrate anything, etc. Everything sames exactly the same, only the consensus mechanism changes under the hood.

* It's called "merge" because it's about *merging* the Beacon Chain (*consensus layer*) with the current chain (*execution layer*) and ditching the proof of work part of the execution layer.

* If you don't know, "consensus" is just a fancy word for the goal of ordering transactions and getting some economic guarantee that this order won't change. Both PoW and PoS achieve consensus by different means:

  * PoW: "It costs too much to mess up with the order of blocks, playing by the rules is more lucrative."

  * PoS: "It costs too much to mess up with the order of blocks, because if I do I'll lose all the money I put up as collateral."

* Since it's only the consensus mechanism changing, **Proof of Stake by itself doesn't lower gas fees significantly**.

## Why merge?

* Lower security costs since there's less energy needed to achieve consensus.

  * For PoW you need miners to be able to *at least* cover all the hardware and energy they use otherwise no one will mine. This requires a big issuance that is quickly sold for fiat to pay the bills.
  
  * For PoS you just need to give some yield to stakers to make people want to deposit capital rather than just invest it elsewhere. No big bills to pay beyond an ordinary computer and an internet connection, so the yield just has to reflect the opportunity costs and risks involved.

* More sustainability:

  * The security of a blockchain is basically proportional to the value of its coin. This is true for both PoW (more valuable coin rewards = more reasons to play by the rules = more miners = harder to mess up the consensus) and PoS (more valuable staked coins = more reasons to play by the rules to avoid losing the staked coins)

  * A newly issued coin is essentially value being taken from all holders of the coin and being redistributed to someone. All else equal, selling that coin for fiat extracts value out of the network.

* It opens the door for many scaling solutions in the future, namely data sharding, statelessness, light clients, and [more](https://twitter.com/VitalikButerin/status/1466411377107558402)

* It helps reduce some complexity of the code going forward, by separating concerns between execution and consensus.

* Appeasing the environment and gamers is certainly a nice side-effect, but not really a major reason behind the switch to PoS, since it's mostly about externalities over which Ethereum as a protocol doesn't have much control (source of energy production, GPU supply chains, etc.)

## Wen merge?

* It happened on September 15th, 2022

## Nope, your a idiot. They will delay it like they always have in the past. They promised it years ago and still haven't delivered.

Believe or not this was a common talking point before the merge

## Those millions of ETH staked will crash the price the very moment they're unlocked LOL

For sure, there will be plenty of stakers who will want to finally take profit, especially those who locked their ETH back when 32 ETH was worth $10k. But there's plenty more to consider on the other side of the equation:

* The merge doesn't unlock any ETH. Withdrawals will come in the first hard fork following the merge, likely 6-8 months after. That's months of no proof of work issuance (~13k ETH/day) being sold off *and* no proof of stake issuance coming into circulation.

* Just like how there's a queue to deposit ETH, there will be [a queue to withdraw it.](https://github.com/ethereum/annotated-spec/blob/master/phase0/beacon-chain.md#how-does-eth2-proof-of-stake-work). Assuming a mass sell-off event, everyone is in that queue, limited at a rate of 1125 valitors per day. So there's no "opening the floodgates" moment. Everyone unstaking would literally take over a year. A year of ~38k ETH/day entering back into circulation (or... roughly 1% of average daily volume)

* After the merge, validators will start receiving fee rewards as well, doubling the yield [by some estimates](https://docs.google.com/spreadsheets/d/1vrK5sY5ooq-F8dcyRhmmAJ5YtgkvWKWP3OfGCZIYxSA/edit#gid=0). There are thousands of people waiting in line to stake *right now*. They're okay with a 5% yield on their ETH, I don't think they're gonna yeet the moment it becomes 10% lol

* The biggest risk involved in staking is *by far* the merge. Something catastrophic could go wrong, yet people have been staking and locking up their ETH for over a year despite this risk and despite the ETH being locked until an unknown floating date. How many people/institutions are waiting on the sidelines for this risk to disappear before jumping in?

* And don't forget stakers exiting means fewer validators which means higher rewards for the stakers who don't exit. It also means more incentives for other people to *start* staking if they weren't before...

* But of course it's crypto, and crypto's gonna crypto. The merge will bring excitement and volatility and possibly a sell-the-news dip, who knows. I don't pretend to know the future, but the way I see it it's much more likely way more ETH will flow *into* staking than out of it.

## If proof of stake is so good, then how come Ethereum didn't go with that from the start?

* Proof of Work is easy to conceptualize and implement, Proof of Stake isn't. Especially when back in 2014 it was mostly a theoretical concept still being researched, with some blockchain implementing some version of it.

* There were several fundamental problems with PoS that needed to be overcome from a research perspective before thinking about implementing it. 

* There is no one-size-fits-all for Proof of Stake. Every PoS blockchain comes with its own PoS specification that has pros and cons on various aspects, so it's not as simple as "but this other blockchain did it, why can't ethereum just do the same thing"

* Starting as a proof of work chain had the benefit of letting anyone mine coins on their own without anyone's permission, which helped the coin distribution become way better than those newer chains that are proof of stake from the start and have to decide how to allocate the initial coins, which can't really be done permissionlessly.

* Related to above: Yes, there was still a premine/presale for Ethereum, but it has now been diluted to half the supply after years of mining and multiple bull/bear cycles making that ETH swap hands, bringing the distribution [closer to Bitcoin's](https://medium.com/@adamscochran/the-10k-audit-42c100dd32bb). So it's not that big of a deal in 2022 when Ether as an asset is extremely liquid and easy to acquire. 

## Nah, this is really just a ploy to screw over the miners one last time after years of hard work

* PoS has been the eventual goal since [day 1](https://blog.ethereum.org/2014/07/22/launching-the-ether-sale/), everyone mining was always aware that it would end one day. There is no rugpull or unfairness going on here.

* Economic factors trump any kind of miner-blockchain loyalty. You can kinda view the blockchain as a business and the miners as employees:

  * Miners/employees have been paid for the service they provide (namely, secure consensus) with the block rewards. The paycheck is an expense for the employer and it comes from diluting the value of existing coins from holders (see above in "why merge?")

  * Miners go to the chain offering the highest rewards, most of them would ditch Ethereum in a heartbeat if another GPU minable coin gave out more rewards. 

  * Similarly, Ethereum will pay less for the service it requires if stakers can do it for way cheaper. 

* It's not entirely exclusive. Miners can also be holders of the coin, and users of the blockchain. Nothing prevents them from holding their rewards and becoming stakers too.

## The coin stops having inherent value if you're not spending real world energy to mine it

I don't really buy this argument. There is nothing magical about computing hashes over and over until you land on one that fits arbitrary requirements. I mean, you could have a proof of work blockchain where the work is done by solving sudoku puzzles and it would work exactly the same: NP-complete problem, hard to compute one way but easy to verify a solution once one has been found. That doesn't mean solving sudoku inherently brings value into the world. Cranking up the mining difficulty of a coin doesn't magically make everyone richer, it just makes mining less profitable – unless of course demand goes up too, which so far hasn't been too much of a problem in the crypto world.

The way I see it, the value of a coin ultimately comes from supply and demand, and the demand comes from how valuable the blockspace is. People need ETH to buy the blockspace, regardless of whether that ETH is generated by a miner or a staker. Sure, the more miners there are the higher the security/decentralization which further increases the value proposition of the blockspace in a positive feedback loop, but [feedback loops exist in Proof of Stake Ethereum too](https://i.imgur.com/3bPV35a.png) and they're super cool too!

## Proof of Stake is a recipe for total centralization

* It's basically the same as Proof of Work but slightly different. "Better" or "worse" really depends on your opinion. The way I see it, PoW is really just PoS with extra steps.

* Ethereum as a community values decentralization highly, any potential centralization vector is addressed by the research team to come up with ways to mitigate it, even if it's at the cost of other important stuff like scaling (e.g. keeping gas limits low so more nodes can participate in decentralization, even if that results in congestion and high fees)

* There **are** shortcomings currently, decentralization is a spectrum and a process and we're not there yet, and for the time being there are many centralization crutches that need to go away on the long term. That said, none of these crutches represent existential risks for the network, and for practically any "it's centralized because X" statement, there is an item on [the roadmap](https://twitter.com/VitalikButerin/status/1466411377107558402) addressing X. I personally find it much more fascinating to come up with a whole bunch of stuff to solve X rather than give up and say "it can't be done because of X". 

* Something interesting about Ethereum's PoS design that is often overlooked: Quadratic penalties. A single validator going down, messing up, or downright attacking the network doesn't get penalized very badly. A thousand validators doing it at the same time get penalized much more heavily. 

  * This means that if you're a megawhale with thousands of validators, it's in your own best interest to spread them out, avoid cloud hosting, use different clients, etc. Sure, the capital is still concentrated, but at least the points of failures are distributed which is good for the health of the network overall.

  * Compared to a big mining operation that relies on a central location to amortize costs, which can be spotted from energy usage and shut down if the authorities don't like it. It's hard to move mining equipment across the world, but staking only relies on private/public keys and not any actual hardware beyond a consumer grade computer.

## PoS is really just "who has money makes more money"

* Yes. Unfortunately we live in a world of high wealth inequality. Blockchains don't fix that. 

* It's also true of proof of work: Whoever has money can buy more mining rigs and make more money. Except with mining, the ROI becomes better with economies of scale: Centralized mining operations have the big bucks to get bulk/discount rates on hardware and move to the places with cheap electricity. The solo miner simply can't realistically compete. With Proof of Stake, everyone earns the same yield proportionally, where they stake $10 or $10M.

* "*They may be centralized, but those big mining operations have no reason to attack the network and weaken it since they dumped millions in infrastructure*"....... so you're saying you're fine with big centralized actors existing, as long as they have some kind of a big *stake* in the network?

## Passive interest on your deposit though? Printing money out of thin air? That's literally central banks and fiat part 2 electric boogaloo

* You have to really stretch it to make this case, but I've seen people do that lol. Those takes usually begin with "proof of stake is nothing new"

* There's still "work" being done by validators: creating blocks and validating other blocks. It's just that the work done is composed entirely of the *actually useful work* that the blockchain needs to reach consensus, instead of computing hashes over and over again until one of them meets an arbitrary requirement. 

* It's not really "free money being printed out of thin air", there are still costs involved in staking capital, they're just more abstract and less direct than energy bills:

  * Opportunity costs – Why stake at all if another investment offers you a better yield?

  * Illiquidity – From the moment you deposit, your capital is locked up, queued up until your validator is active, then when you withdraw there is yet another queue before getting it back.

  * Inherent risks – It's still a fairly new thing, something could go wrong, there could be a critical bug, network could get attacked, your staking hardware could get compromised, etc.

  * Volatility – at the end of the day it's still a volatile asset, if you're the kind of investor who denominates their investments in their country's fiat currency, then a 5% yield on an asset that can drop 30% overnight isn't all that great (the upside of 5% yield on an asset that doubles is pretty great though, turn that 100% gain into 110%)

  * Maintenance – You still have to maintain and secure your validator, ensure 100% uptime, update software, etc. 

* Here's where it gets nifty: The more stakers there are, the lower the individual rewards get. This basically means that all those costs above will get priced by the market itself. It's easy to see why: If the staking yield is too low, then the rewards don't justify the costs and people will pull out and invest elsewhere, bringing the yield back up. Likewise if it's too high, that'll attract more capital and bring it back down. 

* As far as inflation goes: Let's say the market as a whole decides that 5% is the ideal yield, of which 3% comes from issuance. That works out to about 30 million ETH staked printing 900 thousand new ETH per year. At a total supply of 120 million ETH, that's an inflation rate of 0.75%. Which is outpaced by EIP1559 burn as long as gas fees are at least 23 gwei. (I cannot stress this enough: *Ether-the-asset will become a yield-bearing deflationary asset very soon*)

* "*Nice math but there's no supply cap + they change the monetary policy all the time*" 

  * The goal has been "minimum viable issuance to secure the network" for years, priorizing network security over an arbitrary supply cap.
  
  * No update to the monetary policy has ever increased supply inflation. Low inflation rate (specifically *dis*inflation) has been the goal since day 1.

  * There will be an equilibrium acting as an effective supply cap – decided again by market forces valuing Ethereum's blockspace – once the rate of EIP1559 burn matches the rate of issuance. That's super nifty if you ask me.

* So yeah, there's no "central Ethereum bank" adjusting rates arbitrarily and printing money to cronies. The market itself dictates how much inflation/deflation there is, no single entity can control it the way a central bank controls fiat inflation rates.

## Whales have all the money needed to take over and change the rules and slash honest stakers

* No. Ethereum has no on-chain governance of any kind for this reason. Protocol updates are a community effort (*Layer 0*) and you don't need any money staked to call out bad ideas and participate in the process.

* This is exactly the same as Proof of Work: Even if you have 99% of the hashpower, you can't make invalid transactions that steal people's money without their private keys, or change protocol rules, or really do anything beyond reorganizing blocks. The 1% of honest nodes will reject any block that don't follow the rules and you'll be mining on an invalid/useless chain. Now replace hashpower/mining with stake/staking and the same holds true for Proof of Stake (with the difference that someone caught reorganizing blocks will have their entire stake destroyed, whereas the blockchain can't exactly destroy mining rigs)

* And simply put, there is a fuckton of ETH involved. 10 million and counting and that's *before the merge*. At current prices that's roughly 30 billion dollars. Both "amount of ETH staked" and "value of ETH" are projected to go up, so attacks become increasingly unlikely due to the sheer economic cost involved in doing an attack — *once* — and the absurdity of acquiring that much ETH in the first place if the attack comes from an outside actor (where would you buy 10 million ETH to have 51% of the stake? 20M?)

## 32 ETH is way too much, the average person doesn't have that much

* I agree it's a lot. There are some ideas of how it could be lowered ([better signature aggregation](https://www.reddit.com/r/ethereum/comments/rwojtk/ama_we_are_the_efs_research_team_pt_7_07_january/hrmt6o0/) or [a rotating cap of active validators](https://ethresear.ch/t/simplified-active-validator-cap-and-rotation-proposal/9022)) but they don't seem to be very high on the priority list currently, as opposed to making sure the base layer is truly secure.

* The reason for such a high number is it has to fall in a technical sweetspot. In a nutshell, it has to be low enough to be accessible and have enough validators to secure the chain, but high enough to not have too many validators and bloat the chain with overhead. And having a fixed amount for each validator reduces a lot of the complexity by having each validator weighted exactly the same in the distributed randomness process of who gets to produce each block.

* There is a whole bunch of [math involved](https://thomasborgers.medium.com/ethereum-2-0-economic-review-1fc4a9b8c2d9) to arrive at 32 ETH from a technical standpoint, back when 32 ETH was worth about 7000 USD. [Earlier math from 2017](https://medium.com/@VitalikButerin/parametrizing-casper-the-decentralization-finality-time-overhead-tradeoff-3f2011672735) even suggested over 1000 ETH minimum. 

* Thankfully, just like mining pools exist, there are staking pools to allow staking in smaller amounts. It doesn't necessarily fly in the face of the "not your keys not your coins" mantra, thanks to things like [RocketPool](https://rocketpool.net/), [Secret Shared Validators](https://medium.com/coinmonks/secret-shared-validators-on-ethereum-2-0-ea29ab380016) (not yet launched) which use smart contracts to be permissionless, decentralized and non-custodian. And because of the quadratic penalties mentioned above, I believe decentralized staking operations will outperform the centralized ones on the long run. I recommend superphiz's [guide to staking](https://www.reddit.com/r/ethstaker/comments/t1xpr5/how_to_stake_on_ethereum_march_2022_edition/) for more info. And obviously, I admit staking through exchanges is yucky if you value decentralization

* Related to above, stuff like Rocket Pool is better viewed as a higher-level abstraction to base staking, rather than "just a staking pool". I go into more details on this [here](https://www.reddit.com/r/ethereum/comments/tijcq1/stuff_rethereum_should_know_proof_of_stake_edition/i1gd27b/?context=1) for those interested.

## PoS hasn't been proven, while we know PoW works

That's actually totally fair and there is no real rebuttal to this, obviously. Only time will tell. I just think it's irrelevant in the context that Ethereum *is* switching to PoS and was always going to. If you don't believe in it, don't participate/invest in it. I do personally believe in a long term sustainable PoS Ethereum, but even then I'm glad good ol' boring-by-design Bitcoin will be there chugging its proof of work along.

It's all part of the great crypto experiment of our lifetime. Either it's just a fad and will fail into obscurity, which would be a bummer for sure, or we'll have succeeded in creating monster robust networks capable of outlasting humanity. To achieve that, prioritizing decentralization is key. Which is something I mainly just see in Bitcoin and Ethereum, despite the widely different philosophies. It's why I'm glad to have both to truly see what's what on the long term.
