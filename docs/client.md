# Running a Razor Network Node
In this tutorial, we will explain the basic fundamental requirements to run your own validator node. 

## Installation From Source

Please follow Instructions here to run a razor node from source.

## Using Docker

It is higly recommended to run Razor Node using Docker. This is because you dont need a complete development enviroment to run a node. Also we keep on updating and deploying the code from our github repository. 

## Requirements

Docker-CE : Quick instructions for setting up Docker is given below:

### Create a Directory

Once you have setup the Docker, you need to Run a Razor Node.

Create a local directory to add all the configuration parameters in razor.yaml file.

`vi $HOME/.razor/razor.yaml`

Add following configuration parameters in the razor.yaml file

    `buffer: 20
     gaslimit: 2
     gasmultiplier: 1
     gasprice: 0
     provider: <rpc-url>
     wait: 30`

The parameters' value can be setup as per your requirements.

### Setup a Account or Create account

`docker-compose run razor-go/usr/local/bin/razor create`

OR

`docker-compose run razor-go/usr/local/bin/razor import`

After setting up the account, Get some tRAZORs and tMATICs to 
start voting. 


## Commands
Run the commands in following way:
    `docker-compose run razor-go /usr/local/bin/razor <command>`
You can run following commands in CLI:

`-help` See a list of available commands

`create <password>`  Creates a new wallet with given password. The wallets are stored in `keys/` directory.

>WARNING: this is not a secure method of key generation, DO NOT use it for assets on mainnet.
The code will be improved in the future to make key generation more secure.

Fund this account with ether and RAZORs to start participating in the network.

You can use the full commands (stake) or the short form (s) as shown below.

Supported commands:

### Stake some RAZORs

 stake --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --value 56781001 --pow 14
    
### Delegate RAZORs

    delegate --address <address> --value <value> --pow <power> --stakerId <staker_id>

### unstake some RAZORs

    unstake --address <address> --stakerId <staker_id> --value <value> --pow <power> --autoWithdraw

### withdraw RAZORs

    withdraw --address <address> --stakerId <staker_id>
    
### Activate Delegation

    setDelegation --address <address> --status <true_or_false> --commission <commission>

### Start Voting

    vote --address <address>

### transfer RAZORs

    transfer --amount <amount> --to <transfer_to_address> --from <transfer_from_address>

### Create Wallet

    create

Here,

`<address>` is the address of the wallet generated using create command. Check the `keys` directory to see all available keys.


## Example

    ./razor create
    ./razor stake --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000
    ./razor vote --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c
