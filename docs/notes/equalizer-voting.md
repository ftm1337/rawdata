# Voting Rules at Equalizer.Exchange
If you lock your EQUAL tokens at <https://Equalizer.exchange>, you will receive a VE-NFT (ve means "vote-escrow"). This is a Financial NFT, which represents the absolute ownership rights to the EQUAL locked inside such an NFT. It can be utilized to Vote for your favorite Liquidity Pools and the proportion of votes that a pool gets determines how much share of EQUAL emissions it gets incentivized with in the upcoming week!

## Moving your veNFT between wallets
To trade your NFTs, you might need to move them to a different address like an NFT marketplace. Or to participate in an NFT DEX like the VeNAMM, you will be required to move your veNFTs into its Liquidity pools. Some people have multiple NFTs and might want to Merge them into a Single NFT (in this case, the 'from' NFT is burned & its contents get transferred to the 'to' NFT. Or you might want to simply change your address and use a new one for personal reason. In all such cases, you would want to Transfer your NFTs to a different address.
Here are some things that you should keep in mind:

### Without Voting
If you have not Voted using a NFT, then that NFT can be freely moved between wallets like a regular NFT.
- You can use Metamask, Rainbow, Frame, Mathwallet or any other wallet to transfer NFTs.
- NFTs can also be transferred using the **transferFrom** function via ftmscan:
<https://ftmscan.com/address/0x8313f3551c4d3984ffbadfb42f780d0c8763ce94#writeProxyContract>

### After Voting
But if you have voted using a NFT, it gets blocked from movement for upto 1 week, until the upcoming Thursday.
- To move such an NFT, you first have to call the **reset** function#21 by entering the TokenID of your NFT. It can be done via ftmscan:
<https://ftmscan.com/address/0x4bebeb8188aef8287f9a7d1e4f01d76cbe060d5b#writeProxyContract>

- After doing the Reset of Votes, your NFT is free to be moved.

#### Note that
- You can NOT reset a NFT in the same week that it has voted.
- NFTs that have Voted in the current week can be resetted only in the next Week that starts after the upcoming Thursday.
- Each NFT can only Vote Once in a single Week. It might vote multiple pools, but can only vote once.
- The NFTs Resetted in the Current Week can NOT Vote in the Same Week
- Resetting a NFT will waste 1 Full Week of yields.
- You will NOT be able to earn Bribes from such an NFT during the week it was Resetted (since it will not be able to vote).
- You will NOT be able to earn Trade-Fees from such an NFT during the week it was Resetted (since it will not be able to vote).

---

## Merging 2 NFTs
To merge 2 NFTs, one of them will be burned and the other will inherit its Voting power and its underlying EQUAL amount will be transferred to the other NFT. The NFT which you want to burn is called a **"From-NFT"** and the NFT which will inherit the rights of the "from-NFT" is called a **"To-NFT"**.
- Merging 2 NFTs burns the "from" NFT, which moves it to Zero address (0x00..00)
- The TokenId of the Resultant NFT after a merge will be the same as the "To-NFT"

###  "From-NFT" has voted
If the "From-NFT" has already Voted in the current week, it cannot be merged. To merge a NFT that has already voted, it will have to be "Reset" first.
- As described in the above section, as Merging counts as moving the "From-NFT". Follow the above procedure, same rules apply here.
- To merge your NFT into a different NFT, you must be Approved/Owner of Both NFTs.
- The "To-NFT" does not have to be Reset. It can continue to Vote & earn its bribes without a break.
 
### After Merging veNFTs
Once you have merged 2 NFTs, you will have to call the **Poke** function and enter the TokenID of your new NFT to scale up your Votes to include the votes of the old "From-NFT" into the new "To-NFT". It can be done via ftmscan function #19
<https://ftmscan.com/address/0x4bebeb8188aef8287f9a7d1e4f01d76cbe060d5b#writeProxyContract>

- After a merge, you still cannot change the votes. But the number of votes can be increased to the new combined amount of "From-NFT" & "To-NFT".
- If you do not poke the merged NFT, your Votes will not increase in the current week.
- Voting again in a subsequent week will automatically poke your NFT.

---

## Earning Bribe & Trade Fees
Voting will give you the Trade-fee generated by the pool you have voted for in proportion to your votes. Additionally, you will also earn any extra Bribes that someone else might have added for *bribing* voters to vote for a specific pool.

### Trade Fee
Trade Fees starts accumulating automatically and has to be claimed by Liquidity token holders. In most cases, the holder of LPs is a gauge contract (a.k.a. the LP-Farm) and it needs to claim its share of Trade-fees frequently. The Gauges give these Trade-fees as Rewards to the Voters of it's pool.
To earn this reward:
- Vote for a pool that generates a good trading volume: 0.2% of Volume is trade-fee (0.02% in case of stablepools)
- These Rewards will be streamed starting from the time you vote.
- **Vote as early as possible** to accrue the maximum trade fees over the whole week.
- Trade-fee earning start accruing from start of Thursday till end of Wednesday.

### Bribe rewards
Some people/teams/DAOs/users might post additonal rewards for the voters of a specific Pool to lure Voters into voting for thier pool. Such rewards are commonly known as Bribes.
- It is recommended to **Vote after a Bribe has been added** to earn that bribe.
- These Rewards will be paid in a lump-sum on upcoming Thursday.

[comment]: <> (-Vote after a Bribe has been added to earn that bribe. Voting for a pool before Bribes are added will notThis is a comment, it will not be included)

---

#### Written by Sam (543)
Guru Network ( 🦾 , 🚀 )
