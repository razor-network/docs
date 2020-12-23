# Contracts
The contracts can be found in our github repo [here](https://github.com/razor-network/contracts)

The addresses where the contracts are deployed can be found [here](https://github.com/razor-network/contracts/blob/master/ADDRESSES.md)

The different kinds of contracts and their functions:

1. State manager: Manage the state of the network
2. Stake Manager: Staking and unstaking, penalties and rewards
3. Vote Manager: Management of reported votes: commits and reveals
4. Block Manager: Create new blocks on Razor Network
5. Job Manager: This contract manager queue of pending queries and results of processed queries
6. Delegator: Proxy contract provides access to the latest Job Manager contract.


# Access Control List
### Access Types 


| Type            | Access                                                                                                    |
| :-------------- | :-------------------------------------------------------------------------------------------------------- |
| Node            | Anyone, Not differentiated on msg.sender                                                                  |
| Particular Node | Anyone, Differentiated on msg.sender                                                                      |
| Client          | Anyone                                                                                                    |
| Internal        | Only Parent and Inherited contract                                                                        |
| Role Wise       | Specific Role, grantable/revocable by Admin through ACL.sol                                               |
|                 | <ol><li>JobConfirmer</li><li>BlockConfirmer</li><li>StakeModifier</li><li>StakerActivityUpdater</li></ol> |

<br/>

### Functional Overview

#### JobManager.sol

| Function   | Access       | Comments |
| :--------- | :----------- | :------- |
| createJob  | Client       |          |
| fulfillJob | JobConfirmer |          |


#### BlockManager.sol

| Function              | Access          | Comments |
| :-------------------- | :-------------- | :------- |
| propose               | Particular Node |          |
| giveSorted            | Particular Node |          |
| resetDispute          | Particular Node |          |
| confirmBlock          | BlockConfirmer  |          |
| \_insertAppropriately | Internal        |          |


#### VoteManager.sol

| Function | Access          | Comments |
| :------- | :-------------- | :------- |
| commit   | Particular Node |          |
| reveal   | Node            |          |


#### StakeManager.sol


| Function                   | Role                  | Comments |
| :------------------------- | :-------------------- | :------- |
| setStakerEpochLastRevealed | StakerActivityUpdater |          |
| updateCommitmentEpoch      | StakerActivityUpdater |          |
| stake                      | Particular Node       |          |
| unstake                    | Particular Node       |          |
| withdraw                   | Particular Node       |          |
| givePenalties              | StakeModifier         |          |
| giveBlockReward            | StakeModifier         |          |
| giveRewards                | StakeModifier         |          |
| slash                      | StakeModifier         |          |

<br/>

### Roles and their Holders


![ACL](img/ACL.png)

| ***Role***                | ***Accessible Functions***                              | ***Functions of*** | ***Role Holder*** |
| :------------------------ | :------------------------------------------------------ | :----------------- | :---------------- |
| **JobConfirmer**          | fullfillJob()                                           | JobManager         | BlockManager      |
| **BlockConfirmer**        | confirmBlock()                                          | BlockManager       | VoteManager       |
| **StakeModifier**         | slash()<br>giveBlockReward()                            | StakeManager       | BlockManager      |
|                           | giveRewards()<br>givePenalties()                        | StakeManager       | VoteManager       |
| **StakerActivityUpdater** | setStakerEpochLastRevealed()<br>updateCommitmentEpoch() | StakeManager       | VoteManager       |


