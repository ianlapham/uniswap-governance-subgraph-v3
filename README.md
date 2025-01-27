## Uniswap Governance Subgraph v3 (Both alpha governances)

This subgraph tracks Governance data on Uniswap governance contracts. It is aware of both versions of GovernorAlpha and also GovernorBravo.

This Subgraph provides a proposal id schema as follows: Alpha v1 proposals have a "0." prefix (ex: proposal 4 is 0.4) and Alpha v2 proposals have a "1." prefix (ex: the first proposal on alpha v2 is 1.1).
Bravo proposals have a "2." prefix).

While this naming schema is more complex than a linear version (which is used for [Uniswap Governance Subgraph v2](https://thegraph.com/explorer/subgraph/arr00/uniswap-governance-v2)), it uses the actual proposal id as part of the id which will corrolate to the transactions that users are signing to vote. This will hopefully minimize confusion.

This subgraph indexes and exposes in GraphQL all the event data related to the GovernorAlpha v1 and v2 and Uniswap token contracts from Uniswap, providing an easy access to Token holder and Delegates information, Proposals and votes casted, and all the relationships between those entities.

A live version of this subgraph can be found [here](https://thegraph.com/explorer/subgraph/arr00/uniswap-governance-v3), along with useful queries and examples already available on the playground.

### Historical data

We don't keep track of historical data via entities, since as of the v0.17 GraphNode update they implemented "time-travel" queries, which allow to access the subgraph state for any block number, which allows to get any historical data that you might need from subgraphs, and also calculate with any granularity the data changes that happen on the subgraph.

We recommend [this article](https://blocklytics.org/blog/ethereum-blocks-subgraph-made-for-time-travel/) from the Blocklytics team, which explains how to take advantage of "time-travel" queries and also how to translate timestamps to block numbers, which might be better suited for some use cases!
