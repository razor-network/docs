## Quick start - Delegate

Razor network is a proof of stake network. In order to participate in the network as a delegator, you will need to "Delegate" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

> Warning: Razor network is in alpha state and is deployed on Matic Mumbai testnet. Please don't use assets with value.

## Get tokens

You will need some tMATIC Tokens to pay for transaction fees.

You can get some here:

1. [https://faucet.matic.network/](https://faucet.matic.network/)

In order to get started, you will also need some MATIC RAZORs.

1. Use an ethereum compatible browser (e.g. Chrome browser with Metamask plugin)
2. Set the network to "Matic Mumbai Testnet" in Metamask
3. If you want to get some testnet RAZOR tokens, contact us on Discord.

Now you are all set! Let's download the CLI client and start staking!

## Installing a Razor Node

if you are looking to install a Razor node through docker. You can checkout this link.

## Create a Account
1. Create an account using `create` command. You will be asked to enter the password that'll be used to encrypt the keystore file.

    `$ docker-compose run razor-go/usr/bin/razor create`


2. Send your RAZORs and MATICs to this address.

## Delegate
1. Delegate RAZORs using this command

    `$ razor-go/usr/bin/razorrazor delegate --address <address> --value <value> --stakerId <staker_id>`

    Example: `$ razor-go/usr/bin/razorrazor delegate --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000 --stakerId 1`

2. You need to wait for sometime till the delegation transaction gets confirmed. Once you have delegated funds, you will recieve the sRZRs from the corressponding staker.

