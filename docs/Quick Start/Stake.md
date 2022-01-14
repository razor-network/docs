#Quick start - Stake

Razor network is a proof of stake network. In order to participate in the network as a validator, you will need to "Stake" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

> Warning: Razor network is in alpha state and is deployed on Matic Mumbai testnet. Please don't use assets with value.

##Get tokens

You will need some MATIC Tokens to pay for transaction fees.

You can get some here:

1. [https://faucet.matic.network/](https://faucet.matic.network/)

In order to get started, you will also need some MATIC RAZORs.

1. Use an ethereum compatible browser (e.g. Chrome browser with Metamask plugin)
2. Set the network to "Matic Mumbai Testnet" in Metamask
3. If you want to get some testnet RAZOR tokens, contact us on Discord.

Now you are all set! Let's download the CLI client and start staking!

## Installing a Razor node

If you are looking to Install it from docker, you can checkout following link.

## Stake
1. Stake RAZORs using this command

    `$ $ docker-compose run razor-go/usr/bin/razor stake --address <address> --value <value>`

    Example: `$ docker-compose run razor-go/usr/bin/razor stake --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --value 1000`

For Docker:

    `$ docker exec -it razor-go razor stake --address <address> --value <value>`

2. Wait for the staking process to continue. It may take upto 10 minutes.
4. Now you have staked your RAZORs and must start validating queries to avoid inactivity penalties.
5. To start validating, use this command

   `$ docker-compose run razor-go/usr/bin/razor vote --address <address>`

   Example: `.$ docker-compose run razor-go/usr/bin/razor vote --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c`

6. If you want to enable delegation for your node, you can run following command.

    `$ docker-compose run razor-go/usr/bin/razor setDelegation --address <address> --status <true_or_false> --commission <commission>`

    It will enable the delegation, and people can delegate funds to your staker's account.

 Your node will start automatically fetching and answering queries. You must keep our computer online to be able to validate without any interruptions.
