# Running a Node
End user javascript client implmentation  for Razor network.
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
Supported commands:

    stake <amount> <address> <password>
    vote <address> <password>
    unstake <address> <password>
    withdraw <address> <password>
    transfer <toAddress> <fromAddress> <password>
Here,

`<address>` is the address of the wallet generated using create command. Check the `keys` directory to see all available keys.


## Example

    node index.js create deadbeef
    node index.js stake 1000 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c deadbeef
    node index.js vote 1 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c deadbeef

    // apiid 0 = CMC
    // apiid 1 = Kraken
    // apiid 2 = Gemini
