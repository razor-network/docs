#Quick start - Stake

Razor network is a proof of stake network. In order to participate in the network as a validator, you will need to "Stake" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

> Warning: Razor network is in alpha state and is deployed on Matic Mumbai testnet. Please don't use assets with value.

##Get tokens

You will need some MATIC Tokens to pay for transaction fees.

You can get some here:

1. [https://faucet.polygon.technology/](https://faucet.polygon.technology/)

In order to get started, you will also need some MATIC RAZORs.

1. Use an ethereum compatible browser (e.g. Chrome browser with Metamask plugin)
2. Set the network to "Matic Mumbai Testnet" in Metamask

Now you are all set! Let's download the client and start staking!

## Using Docker

It is highly recommended to run Razor Node using Docker. This is because you dont need a complete development enviroment to run a node. Also we keep on updating and deploying the code from our github repository. 

## Hardware Requirements

4gb RAM

4 Core (arm64 or amd64 architecture)


## Software dependencies

Docker: You can find more information about installing docker [here](https://docs.docker.com/engine/install/)

Razor-Go(github): You can download the Razor-go:v0.2.0-incentnet-prod-patch.1 from [here](https://github.com/razor-network/razor-go/releases/tag/v0.2.0-incentnet-prod-patch.1)

You can download the Razor-go:v0.2.0-incentnet-prod-patch.1 from [here](https://hub.docker.com/layers/razornetwork/razor-go/v0.2.0-incentnet-prod-patch.1/images/sha256-d6e9d10ecc0b18ebc1e2f01c31988f6aff41b7636990c35e1002c2da925014cc?context=repo)


## Setup

Create a local config file to add all the 

    mkdir $HOME/.razor
    vi $HOME/.razor/razor.yaml

Add the following configuration parameters in the razor.yaml file

     buffer: 20           # Buffer size determines, out of all blocks in a state, in how many blocks the voting or any other operation can be performed.
     gaslimit: 2          # The value with which the gas limit will be multiplied while sending every transaction.
     gasmultiplier: 1     # The value with which the gas price will be multiplied while sending every transaction.
     gasprice: 0          # The value of gas price if you want to set manually. For automatic calculation, set 0.
     provider: <rpc-url>  # The RPC URL of the provider you are using to connect to the blockchain.
     wait: 30            # This is the number of blocks the system will wait while voting.


### Run the Razor Network Docker Node

    docker run -d \
    -it \
    --name razor-go \
    -v "$(echo $HOME)"/.razor:/root/.razor \
    razornetwork/razor-go:v0.2.0-incentnet-prod-patch.1

This spins up a razor-go docker image. You can find all the images on the [Razor Network dockerhub](https://hub.docker.com/u/razornetwork).

## Commands

Run the commands in following way:

    docker exec -it razor-go razor <command>


Create an account using the following command:

    docker exec -it razor-go razor create


Fund this account with MATIC testnet tokens and RAZOR testnet tokens to start participating in the network.

You can use the full commands (stake) or the short form (s) as shown below.


Start staking using the `stake` command

    docker exec -it razor-go razor addStake --address <account> --value <value> 

where `address` is the address that contains RAZOR testnet tokens and `value` is the amount of RAZOR that you want to stake.

An example of this command would be:

    docker exec -it razor-go razor addStake --address 0x4561aE6Bd8aF4E6E8668C55496cF73F882CfcbFa --value 10000 --autoVote true
    
To start accepting delegation, use the delegation command in a new terminal:

    docker exec -it razor-go razor setDelegation --address <address> --status <bool> --commission <commission>

where `address` is the address that contains RAZOR testnet tokens, `status` is true or false to turn on or off delegation, and `commission` is the percentage of commission that you can set.

An example of this command would be:

    docker exec -it razor-go razor setDelegation --address 0x4561aE6Bd8aF4E6E8668C55496cF73F882CfcbFa --status true --commission 1

It will enable delegation, and participants can delegate RAZOR tokens to your staker's account.

Start voting using the `vote` command

    docker exec -it razor-go razor vote --address <account>

An example of this command would be: 

    docker exec -it razor-go razor vote --address 0x4561aE6Bd8aF4E6E8668C55496cF73F882CfcbFa


View Logs 

    tail -f ~/.razor/razor.log

That's it! You should have a staker up and running. Your node will start automatically fetching and answering queries. You must keep our computer online to be able to validate without any interruptions. You can monitor the logs, and use [RazorScan](https://razorscan.io) to monitor your staker. 

For more details around all the commands of `razor-go`, please check out the `razor-go` [Readme](https://github.com/razor-network/razor-go#readme).


## Installation From Source

If you would rather install from source, please follow Instructions here to [run a Razor Network node from source](https://github.com/razor-network/razor-go#building-the-source).
