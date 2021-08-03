#Quick start - Delegate

Razor Network in beta state allows community members to delegate their Razor tokens. You can delegate your Razor tokens to any of the validators who have enabled delegation.Razor tokens are the native tokens of Razor Network, compatible with all the ERC20 tokens.

> Warning: Razor network is in alpha state and is deployed on Matic Mumbai testnet. Please don't use assets with value.

##Get tokens

You will need some MATIC Tokens to pay for transaction fees.

You can get some here:

1. [https://faucet.matic.network/](https://faucet.matic.network/)

In order to get started, you will also need some MATIC RAZORs.

1. Use an ethereum compatible browser (e.g. Chrome browser with Metamask plugin)
2. Set the network to "Matic Mumbai Testnet" in Metamask
3. Go to [https://razorscan.io/#/faucet](https://razorscan.io/#/faucet)
4. Paste your ethereum address in the address field.
5. Click "Get RAZOR"
6. After a few minutes, after your transaction is confirmed, click "Check RAZOR Balance" to confirm you have received some free testnet RAZORs.

Now you are all set! Let's download the CLI client and start staking!

##Download and Install
You will need a development environment with `git, python, go, go-ethereum, abigen and nodejs` to get started. Please check the internet on guides about how to install these.

In future we will provide a docker container to make things easier.

1. Clone the repositoy `https://github.com/razor-network/razor-go`

    `git clone git@github.com:razor-network/razor-go.git`

2. Go to the cloned directory

    `cd razor-go`

3. Install packages

    `npm install`

4. Want to build your own smart contracts binding (Note : You must have go-ethreum and abigen installed)

    `npm run build-all`
 
    (Note : You can run `npm run build` if you already have bindings)
                       
5. While building the binary, supply the provider RPC url and the gas multiplier 

6. The binary will be generated at build/bin

## Create a new wallet
1. Create a new ethereum wallet with a password of your choice.

    `./razor create`

2. Send your RAZORs and MATICs to this address.

## Delegate
1. Delegate RAZORs using this command

    `./razor delegate --address <address> --amount <amount> --stakerId <staker_id>`
     
     Example: `./razor delegate --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000 --stakerId 1`

2. Your wallet will be credited with sRZRs tokens of staker to which you delegate Razor tokens. sRZRs would help you to withdraw rewards or delegated funds. Hence you need to ensure that all your sRZRs are safe.

