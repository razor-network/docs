# Running a Node
You will need to run a node in order to become a staker and answer to queries in the network.

## Installation

Please check [Quick Start](Quick Start/Stake.md) for installation instructions

## Commands
Run the commands in following way:
    `./razor <command>`
You can run following commands in CLI:

`-help` See a list of available commands

`create <password>`  Creates a new wallet with given password. The wallets are stored in `keys/` directory.

>WARNING: this is not a secure method of key generation, DO NOT use it for assets on mainnet.
The code will be improved in the future to make key generation more secure.

Fund this account with ether and RAZORs to start participating in the network.

You can use the full commands (stake) or the short form (s) as shown below.

Supported commands:

    stake --address <address> --amount <amount>

Stake some RAZORs

    delegate --address <address> --amount <amount> --stakerId <staker_id>

unstake some RAZORs

    unstake --address <address> --stakerId <staker_id> --amount <amount> --autoWithdraw

withdraw RAZORs

    withdraw --address <address> --stakerId <staker_id>
    
Delegate some RAZORs

    setDelegation --address <address> --status <true_or_false> --commission <commission>

Activate Delegation

    vote --address <address>

Start monitoring contract, commit, vote, propose and dispute automatically

    transfer --amount <amount> --to <transfer_to_address> --from <transfer_from_address>

transfer RAZORs

    create

Create wallet with the given password

Here,

`<address>` is the address of the wallet generated using create command. Check the `keys` directory to see all available keys.


## Example

    ./razor create
    ./razor stake --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000
    ./razor vote --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c
