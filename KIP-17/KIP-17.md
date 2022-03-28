# KIP-17: Provide a coordination facility for GMX

```
kip: 17
title: Provide a coordination facility for GMX
author: hazard <hazard@keeperdao.com>, exeggcute <exeggcute@keeperdao.com>
status: last-call
tags: none
created: 2022-02-04
replaced-by: none
replaces: none
```

## Proposal

Collaborate with GMX to coordinate OEV by relaying price oracle updates through the KeeperDAO Coordination protocol, internalizing the value for the GMX protocol on both Arbitrum and Avalanche. 

## Background

### GMX

GMX (https://gmx.io) is a leading decentralized spot and perpetual futures exchange, currently processing approximately $30 million in daily volume on Arbitrum (https://arbitrum.io), and $10 million in daily volume on Avalanche (https://www.avax.network). 

The GMX protocol supports low swap fees and zero price impact trades, with liquidity sourced from a unique multi-asset pool that earns liquidity providers fees from a combination of market making, swap fees, and leverage trading.

### Dynamic price updates

On-chain derivatives markets use a combination of sources to determine the current spot price of an underlying asset. On GMX, dynamic pricing is supported by (1) Chainlink Oracles (https://chain.link), which source price updates from a number of venues, and (2) TWAP pricing from DEXes with high traded volume in the asset.

Because price updates occur per-block, significant changes in the price between updates can create opportunities for arbitrage when the update occurs. The value of this arbitrage, along with related opportunities such as liquidation resulting from the same phenomenon, has been termed Oracle Extractable Value, or OEV.

### GMX and KeeperDAO

GMX will use KeeperDAO’s Coordination protocol to relay oracle updates and internalize OEV/MEV for the protocol and its liquidity pool, which will enhance returns for liquidity providers while preventing negative externalities.

KeeperDAO keepers will source liquidity and conduct atomic backrun arbitrage to ensure that the vast majority of the OEV in each price update is being captured and retained by GMX. All operations are completely transparent and verifiable on-chain, allowing GMX to validate that the service arrangement is sound at all times. The Coordination protocol’s unique design allows KeeperDAO keepers to execute these transactions without contention, further enhancing profitability for GMX.

The two teams will continue to research improvements in design and delivery of fast price oracle updates that allow OEV/MEV to be internalized while eliminating negative effects for the settlement network at the same time.

The integration has been designed to fall back to the *status quo* in the event of failure, so that GMX is not service-dependent on KeeperDAO in any way.

### Arbitrum and Avalanche

This integration will represent the first application of the KeeperDAO Coordination protocol on both an Ethereum Layer-2 (Arbitrum), and a non-Ethereum blockchain (Avalanche).

This should underscore the fact that the Coordination protocol has been designed from the start to operate in a blockchain- and layer-agnostic way, allowing discovery and settlement to occur in many different places at once, all interacting through the same protocol.

## Specification

1. All GMX oracle updates on Arbitrum and Avalanche will be relayed through the KeeperDAO Coordination protocol.
2. The Coordination protocol will discover OEV and (when profitable) settle the price update and any associated arbitrage for the best available profit.
3. The GMX protocol will receive 80% of the discovered per-transaction OEV.
4. No hard service dependency will be created between GMX and KeeperDAO.
