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

## Stake
1. Stake RAZORs using this command

    `$ ./razor stake --address <address> --amount <amount>`

    Example: `./razor stake --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000`

2. Wait for the staking process to continue. It may take upto 10 minutes.
4. Now you have staked your RAZORs and must start validating queries to avoid inactivity penalties.
5. To start validating, use this command

   `./razor vote --address <address>`

   Example: `./razor vote --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c`

 Your node will start automatically fetching and answering queries. You must keep our computer online to be able to validate without any interruptions.
