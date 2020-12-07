# Sybil Interface

[![Styled With Prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://prettier.io/)

- Interface: [https://sybil.org](https://sybil.org)

Governance interface that incorporates Sybil, a tool for linking Ethereum addresses to social identities. Only Ethereum mainnet is supported. 

## Social Verification

Sybil is a tool that connects wallet addresses to digital identities. Users sign messages with their Ethereum keys, and post signatures on their social profiles. Verifiers can then check these signatures and verify truthful address -> profile mappings. 

This interface allows users to connect their Ethereum addresses to social profiles using the Sybil verification flow. For more detailed documentation on the Sybil verification process, see here: [https://github.com/Uniswap/sybil-list](https://github.com/Uniswap/sybil-list)

#### Supported Social Platforms

This interface supports social verification through Twitter only. However, more platforms can be added in the future (Github, etc). 

## Governance 

The interface allows users to view data about delegates and proposals for multiple Ethereum goverance. Users can also delegate votes and vote on active proposals. 

#### Supported protocols 

Currenlty Uniswap and Compound governance are supported in the interface. 

#### Adding protocol support 

Forks of Compound or Uniswap governance can easily be integrated into the interface. There are two data sources the interface uses: data directly pulled from Governance contracts and data from governance subgraphs. 

Steps to add new protocol support: 

1. Add relevant information to list of supported protocols here: [https://github.com/Uniswap/sybil-interface/blob/master/src/state/governance/reducer.ts](https://github.com/Uniswap/sybil-interface/blob/master/src/state/governance/reducer.ts)
  - 

2. Make sure to have a [subgraph]() that can return data that matches the stuctures in [queries.js](./src/apollo/queries.js)
* To fork 

## Development

### Install Dependencies

```bash
yarn
```

### Run

```bash
yarn start
```

### Configuring the environment (optional)

To have the interface default to a different network when a wallet is not connected:

1. Make a copy of `.env` named `.env.local`
2. Change `REACT_APP_NETWORK_ID` to `"{YOUR_NETWORK_ID}"`
3. Change `REACT_APP_NETWORK_URL` to e.g. `"https://{YOUR_NETWORK_ID}.infura.io/v3/{YOUR_INFURA_KEY}"` 

Note that the interface only works on mainnet to limit the amount of required data soures for goverance systems. 

## Contributions

**Please open all pull requests against the `master` branch.** 
CI checks will run against all PRs.

