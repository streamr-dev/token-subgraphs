## Subgraphs for indexing the DATA token on different chains.

Based on the [OpenZeppelin subgraph framework](https://docs.openzeppelin.com/subgraphs/0.1.x/)

## Prerequisites

Install The Graph's CLI tool:

```
npm install -g @graphprotocol/graph-cli
```

## Config

There are `.json` config files in `configs` directory to describe the DATA token on each chain, for example `data-mainnet.json`:

```
{
  "output": "data-mainnet/data-mainnet.",
  "chain": "mainnet",
  "datasources": [
    { "address": "0x8f693ca8d21b157107184d29d398a8d082b38b76", "startBlock": 12819337, "module": [ "erc20", "accesscontrol" ] }
  ]
}
```

## Building

The Graph resources can be generated from those config files, for example:

```
npm run build-mainnet
```

This will generate `.graphql` and `.yaml` files to the `data-mainnet` directory.

## Deploying

You'll need to authenticate with

```
graph auth --product hosted-service <ACCESS_TOKEN>
```

Then:

```
npm run deploy-mainnet
```

Will deploy the mainnet subgraph to the hosted version of The Graph under the `streamr-dev` account.
