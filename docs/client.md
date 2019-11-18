# Running a Node
You will need to run a node in order to become a staker and answer to queries in the network.

## Installation

Please check [QuickStart](Quick Start/Stake.md) for installation instructions

## Commands
Run the commands in following way:
    `node index.js <command>`
You can run following commands in CLI:

`-help` See a list of available commands

`create <password>`  Creates a new wallet with given password. The wallets are stored in `keys/` directory.

>WARNING: this is not a secure method of key generation, DO NOT use it for assets on mainnet.
The code will be improved in the future to make key generation more secure.

Fund this account with ether and schells to start participating in the network.

You can use the full commands (stake) or the short form (s) as shown below.

Supported commands:

    stake|s <amount> <address> <password>

Stake some schells

    unstake|u <accountId>

Unstake all schells

    withdraw|w <accountId>

Withdraw all schells. Make sure schells are unstaked and unlocked

    vote|v <account> <password>

Start monitoring contract, commit, vote, propose and dispute automatically

    transfer|t <to> <amount> <from> <password>

transfer schells

    create|c <password>

Create wallet with the given password

    demo|d

sample query URLs

    createJob|j <url> <selector> <name> <repeat> <fee> <account> <password>

Create oracle query job.

Here,

`<address>` is the address of the wallet generated using create command. Check the `keys` directory to see all available keys.


## Example

    node index.js create deadbeef
    node index.js stake 1000 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c deadbeef
    node index.js vote 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c deadbeef
