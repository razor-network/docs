#Quick start - Delegate

Razor network is a proof of stake network. In order to participate in the network as a delegator, you will need to "Delegate" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

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

##Download and Install
One of the quickest ways to get `razor-go` up and running on your machine is by using Docker

```
docker run -d \
-it \
--name razor-go \
-v "$(echo $HOME)"/.razor:/root/.razor \ 
razornetwork/razor-go
```
Note that we are leveraging docker bind-mounts to mount `.razor` directory so that we have a shared mount of `.razor` directory between the host and the container. The `.razor `directory holds keys to the addresses that we use in `razor-go`, along with logs and config. We do this to persist data in the host machine, otherwise you would lose your keys once you delete the container.

You need to set a provider before you can use the razor-go cli on docker

`docker exec -it razor-go setconfig -p <provider_url>`

You can now execute razor-go cli commands by running:

`docker exec -it razor-go <command>

### Building the source

1. Clone the repositoy `https://github.com/razor-network/razor-go`

    `git clone git@github.com:razor-network/razor-go.git`

2. Go to the cloned directory

    `cd razor-go`

3. Install packages

    `npm install`

4. If you want to build it from scratch i.e./ by fetching the smart contract bindings as well, run `npm run build-all`.
 
    (Note : To build from scratch, `geth` and `abigen` must be installed in your system)
                       
5. If you already have the `pkg/bindings` you can run `npm run build` instead of `npm run build-all` to directly build the binary.

6. While building the binary, supply the provider RPC url and the gas multiplier.

7. The binary will be generated at `build/bin`.

8. Go to the `build/bin` directory where the razor binary is generated.

`cd build/bin`

## Create a Account
1. Create an account using `create` command. You will be asked to enter the password that'll be used to encrypt the keystore file.

    `$ ./razor create`

For Docker:

    `docker exec -it razor-go razor create`

If you already have account and private key. You can easily import that to `razor-go` client. To do that you can use `import` command. You will be asked to enter the private key and then the password.

    `$ ./razor import`
    
For Docker:
    
    `$ docker exec --it razor-go razor import`

2. Send your RAZORs and MATICs to this address.

## Delegate
1. Delegate RAZORs using this command

    `$ ./razor delegate --address <address> --value <value> --stakerId <staker_id>`

    Example: `$ ./razor delegate --address 0x5a0b54d5dc17e0aadc383d2db43b0a0d3e029c4c --amount 1000 --stakerId 1`

For Docker:

    `$ docker exec -it razor-go razor delegate --address <address> --amount <amount> --stakerId <staker_id>`

2. You need to wait for sometime till the delegation transaction gets confirmed. Once you have delegated funds, you will recieve the sRZRs from the corressponding staker.

