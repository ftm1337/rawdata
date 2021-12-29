# FTM.guru : TVL Contract
## On-Chain Total Value Locked Adapter

### Introduction
We have deployed  a Smart Contract that calculates instantaneous TVL (via on-chain calls) & per-block TVL (via web3 calls) of any Decentralized Finance platform.
The ftm.guru platform, taking in consideration its huge collection of on-chain Stores of Value, uses this Smart Contract across its products.
#### Index
Universal usage:
- Smart Contract Details
- Summary of Modules
- On-chain Usage (`ITVL`)
- Off-chain Usage (A.B.I.)
- Accounts & DataBanks

ftm.guru's Databanks & Adapters:
- Banks (Account Details)
- Finding TVL via adapter

----

## Universal Usage
### General
- The Universal TVL Finder can work with any Protocol, Project or EVM-like blockchain. 
- `coin` refers to the native unit of the blockchain. On Fantom Opera, it refers to the FTM.

### Smart Contract Details
#### v5 Address
`0x3f0458FfB6D106d2F5CdeC9CEdc9054A69275489`
- [Read on ftmscan](https://ftmscan.com/address/0x3f0458FfB6D106d2F5CdeC9CEdc9054A69275489#readContract)
#### v4 Address
`0x41b9231e528a417341382b2c995c6dde21cea93d`
- [Read on ftmscan](https://ftmscan.com/address/0x41b9231e528a417341382b2c995c6dde21cea93d#readContract)

### Summary of Modules


### On-chain Usage (`ITVL`)


### Off-chain Usage (A.B.I.)


### Accounts & DataBanks


----

# ftm.guru's Databanks & Adapters:
## ftm.guru's Banks : Account Details
Below are detailed all Banks, by chronology.  
Beneath it, are detailed all Banks, grouped acccording to modules.

## Banks : By Chronology

|  №  |    Asset Locked Up    | Pool Contract locker              | ITVL Interface Module |
| --- |           ---         |          ---                      |           ---         |
| 1   | ELITE-WFTM Sushi LPT  | YieldState                        | `lpt_coin_usd`        |
| 2   | ELITE-WFTM Spooky LPT | YieldState 2                      | `lpt_coin_usd`        |
| 3   | ELITE                 | XELITE                            | `t_coin_usd`          |
| 4   | FTM                   | BO#1 FTMUSD 3-day Call/Put Option | `coin_usd`            |



## Banks : By Module
### `coin_usd`
For native FTM locked in a contract, with price sourced from an FTM-USDC Spookyswap pool.

**1. BO#1 FTMUSD 3-day Call/Put Option**
Current FTM Locked in the 3-day Binary Options Contract.

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0x92679257ecA3c3Dba25b777185EB82cD81991e72` | BO#1 [FTMUSD 3-day](https://ftm.guru/bo/1)

**2. Degam - Micro JackPot**
Current FTM Locked in the Micro Jackpot.

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0x21eE31ea0e5B4628aC3c1b2Ec6602aeB60d8D124` | Degam [Micro Jackpot](https://ftm.guru/degam)

**2. Degam - Micro JackPot**
Current FTM Locked in the Mini Jackpot.

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0x9A6eb015aebC6466d407d40D278894bc773bd009` | Degam [Mini Jackpot](https://ftm.guru/degam)

**3. FTM Coin-Flip**
Current FTM Locked in the FTM Coin-Flip contract.

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0x9A6eb015aebC6466d407d40D278894bc773bd009` | Casino [FTM Coin-Flip](https://ftm.guru/cointoss_1)
  

### `t_coin_usd`
For simple tokens locked in a contract, with price sourced from an FTM pool.

**1. XELITE Pool**
ELITE staked in XELITE.

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0xf43cc235e686d7bc513f53fbffb61f760c3a1882` | ELITE Token |
| `dec` | 18 | Decimals in Asset |
| `pool` | `0x1BE23c78038B6057172848534AcD62667fA2620d` | XELITE Contract - [ftm.guru/xelite](https://ftm.guru/xelite) |
| `lp` | `0xea035a13b64cb49d85e2f0a2736c9604cb21599c` |  ELITE-WFTM SpLP : Spookyswap Liquidity Token |

### `lpt_coin_usd`
For Liquidity tokens locked in a contract, with price sourced from valuation of an FTM-base pool.

**1. Sushi YieldState**

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0x50576ed9d94cf934bc32abf76e08ec6ddcd54bf0` | ELITE-WFTM SLP : Sushiswap Liquidity Token |
| `dec` | 18 | Decimals in Asset |
| `pool` | `0xef66a11788a3b3180be4aa31a5743c6a6e87a555` | Farm : YieldState#1 - [ftm.guru/YS/1](https://ftm.guru/YS/1) |
| `lp` | `0x50576ed9d94cf934bc32abf76e08ec6ddcd54bf0` |  ELITE-WFTM SLP : Sushiswap Liquidity Token |

### 2. Spooky YieldState

| Key | Value | Description |
| --- | --- | --- |
| `asset` | `0xea035a13b64cb49d85e2f0a2736c9604cb21599c` | ELITE-WFTM SpLP : Spookyswap Liquidity Token |
| `dec` | 18 | Decimals in Asset |
| `pool` | `0xad70c7cbc8f856681b4ebdd37aeac58cf7100736` | Farm : YieldState#2 - [ftm.guru/YS/2](https://ftm.guru/YS/2) |
| `lp` | `0xea035a13b64cb49d85e2f0a2736c9604cb21599c` |  ELITE-WFTM SpLP : Spookyswap Liquidity Token |



### Finding ftm.guru's TVL via adapter
 - Self-Reporting with on-chain verfied Source
 - Returns T.V.L. denominated in USD.
 - Value is extended with 18 digits such that:
 - tvl=1000000000000000000 implies $1 in TVL. 
  
#### Inheritable Solidity Interface
```
//All tvlGuru Compliant contracts must implement the ITVL interface
interface ITVL{
	function tvl() external view returns(uint256);
}
```

## Contact Us:
https://discord.com/invite/QpyfMarNrV
