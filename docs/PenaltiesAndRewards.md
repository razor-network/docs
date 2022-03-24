# Penalties and Reward Structure.

Razor network has carefully designed ensuring that all the honest stakers get rewarded and malicious nodes get penalised. In order to prevent 51% takeover attack, the stakers with 51% of influence are desincetivised heavily.

## Influence, Reputation And Maturity.

Razor network measures the reputation of every staker based on different factors like Stake. Whenever any staker performs stake action, it gets its reputation increased and vice versa. 

        Reputation = Minimum(Log(m+s),Rc);

        Here, m is the maturity and s is the smoothing factor(to prevent high rate of growth) And Rc is the upper limit of Reputation.


With Reputation and staker's stake, Influence of Staker is calculated.

        Influence = Reputation * Stake

## Penalties

### Penalty for Wrong Block Proposed 

If staker tries to propose an invalid block, then any staker can dispute on that by calculating the correct values. We assume that each staker uses the same client and data without any modifications. hence if there is any malicious activity done, staker's stake will be slashed. The part of staker's stake will be burnt and remaining will be sent to disputer.

### Voting Penalites

If any staker, does not participate in epoch and do not provide the commit, then she will get its influence reduced by 1%. And if she commits and do not reveal then there will be significant amount of penalty on influence.

### Inactivity Penalty

Considering technical issues, we have kept a Grace Period for inactivity. If by any chance staker is not able to participate in the network for epochs less then Grace Period, we do not give any Inactivity Penalties.

## Rewards

For every participation in each epoch, staker will be incentivised with increase in the influence of its on network. It is also known as Voting Rewards

If there is malicious block being created, the disputer will get some percentage of the slashed stake of the staker as a reward.

### Block Reward

A block Reward will be awarded to stakers if all the given conditions satisfy.

1. Staker proposes a valid block in Propose state
2. Staker has highest priority for becoming the block producer for epoch.
3. No one has proven block as malicious block.
4. Staker confirms the block and submits to client.

The block Reward will be given in the 5th State , Confirm State.





