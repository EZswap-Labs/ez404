# EZ404 

EZ404 is a fork of DN404. The main file is `EZDN404.sol`.
When user `publicMint`, it will call `mintNewPosition` , user's eth converts to weth and add liquidity in UniswapV3 pool itself.
And this LP token will deposit in EZDN404 contract.

DN404 is an implementation of a co-joined ERC20 and ERC721 pair.

To learn more about these dual nature token pairs, you can read the full [ERC-7631 spec](https://eips.ethereum.org/EIPS/eip-7631).

- Full compliance with the ERC20 and ERC721 specifications.
- Transfers on one side will be reflected on the other side.
- Pretty optimized.

## Installation

To install with [**Foundry**](https://github.com/gakonst/foundry):

```sh
forge install vectorized/dn404
```

To install with [**Hardhat**](https://github.com/nomiclabs/hardhat):

```sh
npm install dn404
```

## Contracts

The Solidity smart contracts are located in the `src` directory.

```ml
src
├─ DN404 — "ERC20 contract for DN404"
├─ DN404Mirror — "ERC721 contract for DN404"
└─ example
   ├─ SimpleDN404 — "Simple DN404 example as ERC20"
   └─ NFTMintDN404 — "Simple DN404 example as ERC721"
```

## Contributing

Feel free to make a pull request.

Guidelines same as [Solady's](https://github.com/Vectorized/solady/issues/19).

## Safety

This is **experimental software** and is provided on an "as is" and "as available" basis.

We **do not give any warranties** and **will not be liable for any loss** incurred through any use of this codebase.

While DN404 has been heavily tested, there may be parts that exhibit unexpected emergent behavior when used with other code, or break in future Solidity versions.

Please always include your own thorough tests when using DN404 to make sure it works correctly with your code.

## Upgradability

Most contracts in DN404 are compatible with both upgradeable and non-upgradeable (i.e. regular) contracts.

Please call any required internal initialization methods accordingly.

## Acknowledgments

This repository is inspired by various sources:

- [ERC7647 (a.k.a. SJ741)](https://github.com/SJ741/sj741-token)
- [ERC7651 (a.k.a. "ERC"404)](https://github.com/Pandora-Labs-Org/erc404)
- ["ERC"425](https://github.com/paradox425/ERC425)
- [Solady](https://github.com/vectorized/solady)
- [ERC721A](https://github.com/chiru-labs/ERC721A)

[npm-shield]: https://img.shields.io/npm/v/dn404.svg
[npm-url]: https://www.npmjs.com/package/dn404

[ci-shield]: https://img.shields.io/github/actions/workflow/status/vectorized/dn404/ci.yml?branch=main&label=build
[ci-url]: https://github.com/vectorized/dn404/actions/workflows/ci.yml

```
forge script script/DeployEZDN404.s.sol:EZN404Script --rpc-url https://1rpc.io/matic --broadcast --verify -vvvv

forge script script/DeployEZDN404.s.sol:EZN404Script --rpc-url https://rpc.ankr.com/polygon --broadcast --verify -vvvv

forge script script/DeployEZDN404.s.sol:EZN404Script --rpc-url https://1rpc.io/matic --verify --resume     

forge test --fork-url <your_rpc_url> --fork-block-number 1

forge test test/ezdn404/ezdn404.t.sol:EZDN404Test

forge test --match-path test/ezdn404/ezdn404.t.sol --fork-url https://rpc.ankr.com/polygon --fork-block-number 56881747 -vv

forge test --match-path test/ezdn404/ezdn404.t.sol --fork-url https://rpc.ankr.com/eth --fork-block-number 19862397 -vv
```