#Quick start - Stake

Razor network is a proof of stake network. In order to participate in the network as a validator, you will need to "Stake" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

> Warning: Razor network is in alpha state and is deployed on görli testnet. Please don't use assets with value.

##Get tokens

You will need some görli ether to pay for transaction fees.

You can get some here:

1. [https://goerli-faucet.slock.it/](https://goerli-faucet.slock.it/)

2. OR [https://faucet.goerli.mudit.blog/](https://faucet.goerli.mudit.blog/)

In order to get started, you will also need some Görli RAZORs.

1. Use an ethereum compatible browser (e.g. Chrome browser with Metamask plugin)
2. Set the network to "Görli testnet" in Metamask
3. Go to [https://razorscan.io/#/faucet](https://razorscan.io/#/faucet)
4. Paste your ethereum address in the address field.
5. Click "Get RZR"
6. After a few minutes, after your transaction is confirmed, click "Check RZR Balance" to confirm you have received some free testnet RAZORs.

Now you are all set! Let's download the CLI client and start staking!

##Download and Install
You will need a development environment with `git, python and nodejs` to get started. Please check the internet on guides about how to install these.

In future we will provide a docker container to make things easier.

1. Clone the repositoy `https://github.com/razor-network/cli`

    `git clone git@github.com:razor-network/cli.git`

2. Go to the cloned directory

    `cd cli`

3. Install packages

    `npm i`

4. Create a directory called keys

    `mkdir keys`

5. Rename the file config-sample.json to sample.json

    `mv config-sample.json config.json`

6. Edit config.json to add your Ethereum node address (private or infura)

## Create a new wallet
1. Create a new ethereum wallet with a password of your choice.

    `node index.js c <password>`

2. You can check the `keys` directory for available wallets.

    `ls keys`

3. Send your RAZORs and görli ether to this address.

## Stake
1. Stake RAZORs using this command

    `node index.js stake <amount of RAZORs to stake> <your ethereum address> <your password>`


    Example: `node index.js stake 1000 0xdeadbeef password123`

2. Wait for the staking process to continue. It may take upto 10 minutes.
3. Now you have staked your RAZORs and must start validating queries to avoid inactivity penalties.
4. To start validating, use this command

   `node index.js vote <your ethereum address> <your password>`

   Example: `node index.js vote 0xdeadbeef password123`

 Your node will start automatically fetching and answering queries. You must keep our computer online to be able to validate without any interruptions.
