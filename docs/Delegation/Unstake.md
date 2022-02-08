## Quick start - Unstake

Razor network is a proof of stake network. In order to participate in the network as a delegator, you will need to "Delegate" your RAZORs. RAZORs are the native tokens in the network and they are compatible with the ERC20 tokens standard.

> Warning: Razor network is in alpha state and is deployed on Matic Mumbai testnet. Please don't use assets with value.

## TLDR;

Withdrawing your funds from Razor Network is the two Step process. The first Step is to Unstake and other one is to Withdraw. Any staker of delegator can unstake their funds in 5th State, also known as Confirm State. Once you have reached to confirm State you can follow the steps given in the Guide and perform Unstake. When you Unstake, the funds will be locked in the smart contracts for 48 epochs which is subjected to change based on the governance proposals. So as per current value of Withdraw lock, You can withdraw the tokens after 48 epochs by performing the Withdraw transaction. 

## Metamask Setup

1. Change the Network to “Polygon Mumbai Testnet” 
2. Click on “Import Tokens” 
3. Under “Token Contract Address” input the testnet sRAZOR token contract address.<br>
     Note : *You can get sRAZOR token address from the staker to whom you have delegated.*
4. Now your wallet must be showing the sRAZOR Tokens in your wallet.
5. Make sure to get some test MATIC on Mumbai for gas from the faucet [here](https://faucet.polygon.technology/)

## Unstaking your delegated Amount

### Step 1

 Visit <https://razorscan.io/>

 **Note** : *We recommend all the Delegators to bookmark this specific URL to prevent any phishing Attacks*

![Screenshot](/img/1.png)

### Step 2
 Now, click on “Connect Wallet” from the top right corner and make sure your network is set to “Polygon Mumbai Testnet”.

![Screenshot](/img/2.png)

### Step 3
 Once your wallet is connected, visit [https://razorscan.io/staking](https://razorscan.io/staking) or click on “Participants” from the menu bar on the left and you should see the screen below:

![Screenshot](/img/3.png)

### Step 4

Unstake function works in only Confirm State. To check the current state of an Epoch go to the “Participants” tab from the menu on the left side on RazorScan and you will see the state, like in the picture below: 

![Screenshot](/img/8.png)


### Step 5

Once the Epoch is in the state where the “unstake” function is allowed, navigate to your address by clicking on the Metamask icon on the top right corner of the screen.

![Screenshot](/img/9.png)


### Step 6

Click on the “Delegate” button and choose “unstake”.

![Screenshot](/img/10.png)


### Step 7

Once you click on “Unstake” a dialogue box will appear. Enter the amount that you want to unstake, and click on the “Unstake” button.

![Screenshot](/img/11.png)


### Step 8

Sign the unstake transaction on the Metamask popup to successfully complete unstaking.

To withdraw the unstaked funds into your wallet, you will need to wait for a certain amount of epochs. You can check the current epoch on the participants' page.

![Screenshot](/img/12.png)


### Step 9

Once the Epoch moves to the appropriate one, navigate to your account by clicking on the Metamask icon on the top right corner on RazorScan. Click on the “Delegate” button corresponding to the staker address where you unstaked your funds and then click on “Withdraw.” 

![Screenshot](/img/13.png)


### Step 10

Choose the amount you wish to withdraw from the unstaked amount and sign the transaction. Once completed, you will be able to view the amount in your wallet. 

**Note** : *We have restricted the unstaking functionality to only Confirm State. Once you have unstaked, you need to wait for some epochs, so the withdrawal lock period gets completed and you can withdraw. To get the exact details of Withdraw Lock Period you can visit [https://razorscan.io/governance/values](https://razorscan.io/governance/values)*

