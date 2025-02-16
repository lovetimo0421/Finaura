### Overview

This repository contains smart contracts for a decentralized NFT marketplace and a platform for renting out smart contract wallets.

#### Key Features:


- Smart Contract Wallet Ownership Transfer:
- Owners of smart contract wallets can list their wallets for sole or rent.
- Flexible rental periods and pricing.
- NFT Marketplace:
- Users can mint, list, buy, rent, and sell NFTs.
- Supports ERC-721 and ERC-1155 NFT standards.
- EOA and Smart Contract Wallet Integration:
- Seamless integration between the NFT marketplace and the wallet rental platform.
- Built with Solidity:
- Developed using the Solidity programming language for Ethereum.
- Secure and efficient smart contract implementation.

### VSCode Integration

This project is IDE agnostic, but for the best user experience, you may want to use it in VSCode alongside Nomic
Foundation's [Solidity extension](https://marketplace.visualstudio.com/items?itemName=NomicFoundation.hardhat-solidity).

### GitHub Actions

This project comes with GitHub Actions pre-configured. Your contracts will be linted and tested on every push and pull
request made to the `main` branch.

Note though that to make this work, you must use your `INFURA_API_KEY` and your `MNEMONIC` as GitHub secrets.

For more information on how to set up GitHub secrets, check out the
[docs](https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions).

You can edit the CI script in [.github/workflows/ci.yml](./.github/workflows/ci.yml).

## Usage

### Pre Requisites

First, you need to install the dependencies:

```sh
npm install
```

Then, you need to set up all the required
[Hardhat Configuration Variables](https://hardhat.org/hardhat-runner/docs/guides/configuration-variables). You might
also want to install some that are optional.

To assist with the setup process, run `bunx hardhat vars setup`. To set a particular value, such as a BIP-39 mnemonic
variable, execute this:

```sh
bunx hardhat vars set MNEMONIC
? Enter value: ‣ here is where your twelve words mnemonic should be put my friend
```

If you do not already have a mnemonic, you can generate one using this [website](https://iancoleman.io/bip39/).

### Compile

Compile the smart contracts with Hardhat:

```sh
npm run compile
```

### TypeChain

Compile the smart contracts and generate TypeChain bindings:

```sh
npm run typechain
```

### Test

Run the tests with Hardhat:

```sh
npm run test
```

### Lint Solidity

Lint the Solidity code:

```sh
npm run lint:sol
```

### Lint TypeScript

Lint the TypeScript code:

```sh
npm run lint:ts
```

### Coverage

Generate the code coverage report:

```sh
npm run coverage
```

### Report Gas

See the gas usage per unit test and average gas per method call:

```sh
REPORT_GAS=true npm run test
```

### Clean

Delete the smart contract artifacts, the coverage reports and the Hardhat cache:

```sh
npm run clean
```

### Deploy

Deploy the contracts to Hardhat Network:

```sh
npm run deploy:contracts
```

### Tasks

#### Deploy Lock

Deploy a new instance of the Lock contract via a task:

```sh
npm run task:deployLock --unlock 100 --value 0.1
```

### Syntax Highlighting

If you use VSCode, you can get Solidity syntax highlighting with the
[hardhat-solidity](https://marketplace.visualstudio.com/items?itemName=NomicFoundation.hardhat-solidity) extension.

## Using GitPod

[GitPod](https://www.gitpod.io/) is an open-source developer platform for remote development.

To view the coverage report generated by `npm run coverage`, just click `Go Live` from the status bar to turn the server
on/off.

## Local development with Ganache

### Install Ganache

```sh
npm i -g ganache
```

### Run a Development Blockchain

```sh
ganache -s test
```

> The `-s test` passes a seed to the local chain and makes it deterministic

Make sure to set the mnemonic in your `.env` file to that of the instance running with Ganache.
