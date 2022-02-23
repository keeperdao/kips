# KIP-16: Sunset the Hiding Vaults product

```
kip: 16
title: Sunset the Hiding Vaults product
author: tommy <tommy@keeperdao.com>, WhatsTheDeetz <kd@keeperdao.com>
status: last-call
tags: none
created: 2022-02-14
replaced-by: none
replaces: none
```

## Proposal

Discontinue support for the Hiding Vaults product.

## Background

The Hiding Vaults product is technically impressive, and can be a valuable springboard for future features in our first-party trading product. But when considered as a whole, it no longer makes sense for us to dedicate resources to its development and maintenance.

- The intention behind the Hiding Vaults was to give our Keepers access to MEV opportunities from liquidations and generate revenue for the treasury from it. But we’ve since realized that by focusing on a B2B (or perhaps better: DAO-to-protocol) strategy - such as the recently announced partnership with B. Protocol - we’re able to give our Keepers access to these MEV opportunities much more efficiently, with minimal capital requirements or need for additional automation.
- The things our team has the deepest expertise in, the best growth case for, and can be the best in the world at, are arbitrage, order execution, and coordination. By not focusing on them exclusively, we are losing ground and eroding these competitive advantages.
- Because the Hiding Vault is such a different product from our core focus, it splits the focus of several of our teams - e.g. Engineering, Product and Marketing - and as such is a detriment to us functioning most efficiently towards fulfilling the DAOs purpose. Great startups often do one thing well. It’s time for us to become singularly focused one that one thing again.
- There is no product-market fit: The amount of total and regular users are low, and less than 10 new vaults have been minted in the last 60 days. Our Vaults TVL has been consistently shrinking, with withdrawals from the vault outpacing new loans.
- The Hiding Vault, as a completely separate product from trading, makes defining what KeeperDAO does much more confusing.
- The opportunity cost is high: should we continue to focus on something that *could* make the DAO money in the future, while we could be working on something that *already* makes us money today and has a much higher TAM? Liquidation profits only account for about 5% of all MEV, to focus on it at the expense of arbitrage or other opportunities would be a disservice to tokenholders.
- The Hiding Vaults’ economics are driven by inflationary ROOK rewards and as such is a hindrance to our near-term goal of making ROOK deflationary through Coordinomics.
- The economics behind the Hiding Vault aren’t working. To put it bluntly, we are basically paying customers to use a service that stops us from making money.

Innovation means dealing with uncertainty. You’re trying to build something no one has build before. Sometimes this works, sometimes it doesn’t. And when it doesn’t, it’s best to cut your losses quickly and move on. This is the natural process of entrepreneurship. In our case, this means sunsetting the Hiding Vaults and making sure our entire team is once again singularly focused on building the Coordination Protocol of DeFi.

As a first step in this process, this KIP proposes to immediately end the Hiding Vault emissions. This will stop giving away 282.975 ROOK per week. Ending rewards and notifying users that the product will be deprecated is the first step in a scheduled phase-out of Hiding Vaults. We will, just as we have with legacy LPs, keep a minimal interface running to all users to repay loans, and withdraw funds from the vaults.

## Specification
1. Mint exactly enough ROOK to cover the period between the end of Act V and the block that this KIP is ratified on (if it is ratified).
2. Stop ROOK emissions to Hiding Vault users after the block that this KIP is ratified on (if it is ratified).
3. Notify all Hiding Vault users of a scheduled phase-out of the Hiding Vault functionality.
4. Shut down the bot handling Hiding Vault liquidations. Any remaining Hiding Vault positions will still function, but liquidations will be handled by external keepers in the wild.
5. Maintain, for a reasonable amount of time, a UI that will allow users to withdraw their capital from the Hiding Vaults. After that, provide instructions for users to call the Hiding Vault smart contracts directly (Warning: this will be complex).
