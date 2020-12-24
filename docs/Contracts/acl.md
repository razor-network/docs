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