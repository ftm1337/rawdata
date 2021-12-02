# Supply Distribution of ELITE (ftm.guru) token
This document attempts to address how the 1337 ELITEs are distributed.  
^ implies approximation.  
**API Endpoint: https://ftm.guru/rawdata/supplies.json**

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
### Top-20 Addresses
### Known DEX Smart Contracts
### Known Farming Smart Contracts
### Known Staking Smart Contracts
### XELITE
`0x1BE23c78038B6057172848534AcD62667fA2620d`  
- Interest Bearing ELITE
- https://ftm.guru/xelite
