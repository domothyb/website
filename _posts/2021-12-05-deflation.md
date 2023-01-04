---
layout: post
title: Deflationary Ether
---

## "No one is going to spend Ether if it's deflationary"

*Does a deflating supply of Ether the asset help or hurt Ethereum the network?*

### Is it actually deflationary?

First, the important nitpick: Ether's supply is not inherently deflationary. It self-adjusts based on the following variables: number of stakers and demand for blockspace. Right now, the first variable doesn't come into play as the consensus is still achieved by proof-of-work, with 2 new ETH being issued roughly every 13 seconds.

During times of high blockchain activity, the rate of burning outpaces the rate of issuance. But in general, the supply still inflates, just at a lower rate than before EIP-1559 was implemented. In other words, Ether only becomes deflationary when it's actively being used. If deflation is bad for spending, then overall spending will reduce and it will go back to being inflationary.

After the network switches to proof-of-stake, the issuance will drop drastically (around 90%) and Ether should become deflationary for many years – possibly decades – until there comes a point where the rate of burning equals the rate of issuance. The [best math available](https://ethresear.ch/t/circulating-supply-equilibrium-for-ethereum-and-minimum-viable-issuance-during-the-proof-of-stake-era/10954) shows this will happen anywhere between 40 and 60 million Ether.

### Why burning fees makes sense

Let's address the next question that often follows: *Why have fees if they're just getting burned anyway?*

High gas fees are a result of limited supply vs. a lot of demand for blockspace. The cost of gas fees at any given time reflects the actual *value* of Ethereum's blockspace at that moment, as far as things can have value due to supply and demand. Anyone who is not in a rush to use the network can wait for the demand to go down and pay lower fees.

Reducing gas fees artificially would lead to ["blockspace shortages"](https://www.investopedia.com/terms/p/price-controls.asp) and make [DoS attacks](https://en.wikipedia.org/wiki/Denial-of-service_attack) against the network cheaper. The mechanism behind EIP-1559 automatically adjusts the base fee that is burned depending on how full or empty the blocks are.

So why burn the fees? There are a lot of reasons to do so, but the easiest one to grasp in my opinion is this one: Since whoever creates blocks decides which transactions to include, the base fee cannot go to them as they could simply create dummy transactions to fill the blocks to artificially increase the fees everyone else has to pay. Burning the fees is a market-efficient way to avoid overpaying for blockspace, as was often the case under the first-price auction model before EIP-1559.

So, the higher the demand, the higher the fees. In that regards, you're essentially paying the network itself for using the product it offers: secure, credibly-neutral blockspace. (Side-note: there *is* a small premium you can pay to block creators to prioritize the inclusion of your transaction, but in general, around 80-90% of the fees you pay will be burned)

By virtue of holding Ether as an asset, the value created by people using the network flows in part back to you via this burning mechanism.

### "Pure" use-cases for Ether

Next, let's address the core of the question: *why would you spend Ether today if it's gonna be worth more later*? Simply put: it's not meant to be a currency for day-to-day usage. I would argue that the existence of Ether-the-asset only serves to achieve the following two goals:

* Paying for gas fees to use the network

* Securing the network

Any other use-cases you may imagine – collateral in DeFi, speculation/trading, store of value, even using it as money — are direct results of the open and permissionless nature of Ethereum coupled with Ether's inherent scarcity and value. But as a rule of thumb, the eventual "Ethereum utopia" **does not** entail buying a loaf of bread for 0.000784 ETH and paying five times the amount in gas fees. Anyone who argues otherwise is either misinformed or willfully spreading misinformation themselves.

### Blockspace as a product

Ethereum-the-blockchain provides a product and a service, and you have to pay for it with Ether-the-asset.

As a concrete example, if VISA wants to [use Ethereum as a secure layer for settling transactions](https://www.forbes.com/sites/ninabambysheva/2021/03/29/visa-to-start-settling-transactions-with-bitcoin-partners-in-usdc/), and blockspace currently costs $X per byte in USD, then VISA will buy $X's worth of Ether for every byte they want to commit to the chain. Settling their transactions will burn that amount of Ether immediately. It doesn't matter that this $X's worth of Ether might double in the next year, they need to use Ethereum's blockspace *today* so they buy it. And they burn it. Increased buying pressure *and* downward pressure on supply!

### Buying Ether to burn it

Sooner or later a lot of people/institutions will be buying-and-burning Ether to settle any arbitrary data/computation on Ethereum. They don't have to care about it as an asset, it's just a medium to pay for blockspace. The existence of Ether-the-asset is basically nothing more than a necessary tool derived from a self-sustaining and self-adjusting network that doesn't depend on any one central entity deciding the price of blockspace nor even any one government that controls and issues the currency in which the blockspace is paid! 

With that in mind, Ether is a utility coin first and foremost, and its value is tied to the value of the blockspace it offers. The fact that it's gonna increase in value over time as it becomes scarcer and captures value through burning only helps Ethereum's interests:

1. A higher price for Ether represents a higher value of the collateral staked which incentivizes validators to play by the rule to avoid losing their capital, and it's harder for an attacker to acquire the capital necessary to attack the network in any meaningful way.

2. Since VISA knows Ether is gonna increase in price, and they know they need to settle a lot of transactions over the coming years, the best move for them is to buy a lot of Ether today for a lower cost basis instead of buying it at a higher price when the time comes to actually spend it on blockspace.

If Ethereum's blockspace becomes valuable – and I believe it will – it's inevitable that Ether will become a part of every major institution's balance sheets at some point because that's the most cost-efficient way to use it.

In fact, that's not true. There *is* a more cost efficient way to use it: Buy a lot of Ether, stake it and get 5-8% return a year, *denominated in Ether*. This is good for VISA as they're essentially getting Ether for "free" – after the initial capital investment and taxes –  and it's good for Ethereum because more stakers means more network security. VISA using Ethereum as a settlement layer means their interests are aligned with Ethereum's well-being, and the same goes for all the other institutions that do the same.

I personally think it's extremely bullish for Ether as an asset to picture people paying for things in fiat or stablecoins using a VISA credit card, without even knowing that Ethereum is being used indirectly under the hood to settle that transaction, which burns Ether. But of course, this VISA example is just an easy one. There are many other use-cases for Ethereum's blockspace, such as DeFi, NFTs, gaming, or [blockchains leveraging Ethereum's security](https://twitter.com/domothy/status/1465905887541972996) in the coming "Layer 2" ecosystem.

### Summary

* Ether's supply is not inherently deflationary, it self-adjusts depending on blockchain usage and stakers

* That said, it *will* be deflationary for many years after the switch to proof-of-stake

* Ether is not meant to be used as a day-to-day currency to buy goods and services directly

* Ethereum offers a valuable product: secure, credibly-neutral, permissionless blockspace

* Whoever wants to use this product has to spend Ether, a majority of which is burned

* The most cost-efficient way (in dollar terms) to use Ethereum is to buy Ether at today's price and stake it to have more Ether to spend later

* A higher value of Ether represents more network security by virtue of the proof-of-stake collateral value being higher as well

* Ether captures value created by the people using Ethereum through the fee burning mechanism

* **Conclusion**: Supply deflation and price appreciation are good for Ethereum as a whole

### Some more links

* [Concise graph](https://twitter.com/domothy/status/1462988092848156677) representing the long-term model with the moving parts involved, including the burn

* [Justin Drake's tweet](https://twitter.com/drakefjustin/status/1431735094587404292) representing the relationship between Ether's value and Ethereum's utility

* [ultrasound.money](https://ultrasound.money/) to see stats on EIP-1559 burn, what dapps are burning the most, and projections regarding annualized deflation and long-term supply with parameters you can tweak