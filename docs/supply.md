# Supply Distribution of ELITE (ftm.guru) token
This document attempts to address how the 1337 ELITEs are distributed.  
_^ implies approximation._
### API Endpoint
[https://ftm.guru/rawdata/supplies.json](https://ftm.guru/rawdata/supplies.json)

## Overview
### Max Supply = 1337 ELITE
- The theoretical maximum number of ELITE that can ever exist together.
- Includes each and every ELITE.

### Total Supply = 1336.9999 ELITE
- The present number of total ELITEs in existence.
- Excludes the ELITE burned directly by the Protocol's burn function.

### Current Supply = 250^
- Includes only the ELITE that can be accessed by general public
- Excludes Protocol Reserve (671 ELITE)
- Excludes ELITEs considered burnt.
- Excludes Team Tokens (13.37 ELITE)
- Excludes E..L.I.T.E. D.A.O. Treasury (12 ELITE)

### Burned Supply
- Includes ELITE burned directly by the Protocol's burn function. (<0.1 ELITE)
- Includes ELITE burned directly to "Zero-addresses" (>17 ELITE)
  - Burns by Voting
  - Burns by Taxation
  - Other burns to
    - "Zero-address" : `0x0000000000000000000000000000000000000000`
    - "Dead-address" : `0x000000000000000000000000000000000000DEAD`
    - "Dead-Elite address" : `0x00000000000000000000000000000000DEAD1337`

## Special Addresses
### Protocol Reserve & Genesis Address
`0xbab9645d1B78425A7e4e9e78E8DD32aAbd800a16`  
#### Purupose:
- Create ELITE
- Set-up the "KingMaker"
- Manage the Protocol Reserve
- Special transactions to smart contracts
  - To exceed holding limit (8.9 ELITE)
  - To seed farms with Rewards tax-free

### Official Dev-Team Address
`0x5C146cd18fa53914580573C9b9604588529406Ca`
#### Purpose:
- Deploy all Offical Smart Contracts for Guru Network
- Queue timelocked transactions

### E.L.I.T.E. D.A.O. Treasury
`0x167D87A906dA361A10061fe42bbe89451c2EE584`
#### Purpose:
- Collect all Protocol Taxes
- Collect all Protocol Fees
- Hold & Manage the treasury
- Manage all DAO-owned Smart Contracts
- Queue timelocked transactions for all DAO-owned Smart Contracts

### Publicly-Extensible Infinite Timelock
`0x74BFb7E94bEf5767F5F6Ace2D0df73a224ADB689`
#### Purpose:
- Special timelocking concept invented by ftm.guru.
- A contract that can lock the ELITE tokens held by it for an infinite duration of time.
- Anyone can freely call the "`relock`" function on it to extend the timelock further.
- These ELITE were originally supposed to be added as liquidity to 3 more DEXes (133.7 ELITE each), but the community voiced its opinion against it.
Ever since, they have been staying timelocked.
- Will be upgraded in future to incentivise public `relock`ing

## Calculations
- Following notation implies adding ("plus") or subtracting ("minus") the ELITE balances at the specific addresses.  
i.e.  `CALL:balanceOf(<specific-address-here>)`
- `CALL:f()` format notation implies calling the ELITE Smart Contract's specified view-function.  
Call `0xf43Cc235E686d7BC513F53Fbffb61F760c3a1882` on Chain-ID `0xFA` (250:Fantom Opera).

### Max Supply
1337
### Total Supply
`CALL:totalSupply()`
### Circulating Supply
`CALL:totalSupply()`  
minus `0x5c146cd18fa53914580573c9b9604588529406ca`  
minus `0x74BFb7E94bEf5767F5F6Ace2D0df73a224ADB689`  
minus `0xbab9645d1B78425A7e4e9e78E8DD32aAbd800a16`  
minus `0x167D87A906dA361A10061fe42bbe89451c2EE584`  
minus `0x0000000000000000000000000000000000000000`  
minus `0x000000000000000000000000000000000000dEaD`  
minus `0x000000000000000000000000000000001337dEaD`  
minus `0x5c146cd18fa53914580573c9b9604588529406ca`  
minus `0x5c146cd18fa53914580573c9b9604588529406ca`
### Unreserved Supply
`CALL:circulatingSupply()`
### Burned Supply
1337  
minus `CALL:totalSupply()`  
plus `0x0000000000000000000000000000000000000000`  
plus `0x000000000000000000000000000000000000dEaD`  
plus `0x000000000000000000000000000000001337dEaD` 

## Further Reading
### XELITE
`0x1BE23c78038B6057172848534AcD62667fA2620d`  
- Interest Bearing ELITE
- Earn a small yet stable passive income for holding ELITE
- https://ftm.guru/xelite





### Known DEX Smart Contracts
#### SpookySwap : WFTM + ELITE
`0xea035a13b64cb49d85e2f0a2736c9604cb21599c`
#### Sushi : WFTM + ELITE
`0x50576ed9d94cf934bc32abf76e08ec6ddcd54bf0`
#### SpiritSwap : WFTM + ELITE
`0x7c8f47d2d151cedfdb847ab3c5b67d05daf3539b`
#### ZooDEX : WFTM + ELITE
`0xad28B6C529714954AE2B6d390c8eaD874ddc4970`
#### ZooDEX : ZOO + ELITE
`0x7618793c51e0dc954ba1dd2eeeb3dfa08f777d0a`
#### Sushi : USDC + ELITE
`0x1dfcddf675038ead27f1d75b435b5b05ba825e9a`
#### SpookySwap : USDC + ELITE
`0x20DD18EcA4Bd91B4d23534603D836174Fd5123c9`
#### Elk DEX : WFTM + ELITE
`0xf25417182FbfdEbf1a92142b31A1B32135f1Fd60`
#### Elk DEX : USDC + ELITE
`0xDeC1a7eF080B22fEe247aCD033a8Aca8666bDdcb`
#### ShibaSwap : WFTM + ELITE
`0x0652Dec650566439CFFEB4BEb201F062fc13243F`
#### ShibaSwap : USDC + ELITE
`0xe2121F534316CD3fc91E70a39AAa25785e1c20C1`
#### NipdEX : WFTM + ELITE
`0x736c1462feEc9D936dF0B99F4BE5eD019118534a`
#### HyperJump : WFTM + ELITE
`0xdc79C700EeDc83bE8d19Ad2d245717c7539DFA1c`
#### CyberSwap : WFTM + ELITE
`0x2668141243eCbFEb1b7556D5F08c11Bd94d9b6db`
#### PaintSwap : WFTM + ELITE
`0xF33c436E3C1f0AD9EcB400aA28183910585eFe21`
#### 
`0x6511D0222D90A1135A755c9AC643b862824c79F6`
#### 
`0xE03a36ceC8E6A5cdE1Dae1dd10A5131683F53C3A`
#### 
`0x5817Edb6378B58Bcc9405C864191EB869F7CEc66`
#### 
`0xf91c58d3b908831461b462D341271959e0Aec34D`
#### 
`0x0Ec3f086C8be2efc1bE8C1480C6d48E9b42b816a`
#### EmpireDEX : USDC + ELITE
`0x1218a2F1CE880c01D174C6b1AEb7f2115A152Fa1`
#### 
`0x2221b4ed9d5f2a706f6bf4fcd40ee36da88d2476`
#### 
`0x7808640c1127B31764d549c7Cf0d0bCbA599f7B4`
#### 
`0xba293BeBB30CB8Aa144CB6246ed0cDC1232e12fF`
#### 
`0x2AFb5E33Dd34C6dA03d64444721251B7D17D15BE`
#### 
`0x8E6f0C6c4D3Ad3606001b1C918e8C45Ffbb8678D`
#### 
`0x0068ecb52df9ca8D9e25f38A7370F54B9F413a48`
#### 
`0x6B3AF21Cb0aED1C9C91b48a5afb60D412468811a`
#### 
`0xB70c24D275caC060f357C0AEf163B99B6dee24F5`
#### 
`0x6906976bf20102611D723379d4E83e2b985fb823`
#### SpiritSwap : SPIRIT + ELITE
`0xad70c7cbc8f856681b4ebdd37aeac58cf7100736`

### Known Yield-bearing Smart Contracts containing ELITE
Farm|Uses|From|Gives|Smart Contract Address|
|----|----|----|----|----|
|[↗ ftm.guru YieldState 1](https://ftm.guru/YS/1)|ELITE-FTM LP|Sushi|ELITE|`0xeF66A11788a3B3180be4Aa31A5743c6a6e87a555`|
|[↗ ftm.guru YieldState 2](https://ftm.guru/YS/2)|ELITE-FTM LP|SpookySwap|ELITE|`0xAD70c7cBC8f856681b4ebdD37AEAc58cF7100736`|
|[↗ ftm.guru XELITE](https://ftm.guru/xelite)|ELITE| ftm.guru/xelite |ELITE|`0x1BE23c78038B6057172848534AcD62667fA2620d`|

### Top-25 Addresses

