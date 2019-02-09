## Application Decentralized Star Notary


StarNotary smart contract allows for the ownership and transfer of stars, that is deployed on the Rinkeby public test network. The star notary contract is inherited from <a href = http://erc721.org/>ERC721 </a>, that is a minimum interface smart contract that allows for unique tokens to be managed, owned and traded.

Supporting courses:
* Identity and Smart Contracts

Follow this step below to deployment and test this project.


![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/shutterstock_749922058.jpg)

# Getting started and deploying contract

_My Versions_

``Token address 0x2D98d975e01c55FC9537c1987D9C9d65c3e3D2a1``

``openzeppelin-solidity v2.1.2``

``nodejs v11.9.0``

``npm  v6.5.0``

``Truffle v5.0.3``

``webpack (web3) 4.28.1``

1) Download project

```
$ git clone https://github.com/wleandrooliveira/private_decentralized_star_notary.git
```

2) Install dependencies

```
$ cd private_decentralized_star_notary
$ npm install (if not installed truffle using command to install truffle npm -g install truffle)
$ truffle develop
```
You should see truffle running on http://127.0.0.1:9545/ with a development console
Next compiling the contract, inside the development console, run:
```
$ truffle (develop)>compile
```
Then migrating the contract to the locally running Ethereum network, inside the development console, run:
```
$ truffle (develop)>migrate --reset
```
Testing the StarNotary contract with TestStarNotary.js inside the development console, run:
```
$ truffle (develop)>test
```
__Note__ you will need web3 for the Front End of the DAPP, this should automatically install with truffle. But if you have problems with webpack-dev-server. Find that module in app/node_modules/webpack-dev-server and delete it.
Then run   <br>   ```npm install webpack-dev-server```

Open another terminal window and go inside the project directory, and run:
```
    cd app

    npm run dev
```
3) Run application with Metamask

Make sure you have <a href = "https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn">metaMask </a> chrome extension install

Once installed click on the little fox top left of browser and then on the drop down for different networks. Select Custom RPC, scroll down to new network and paste http://127.0.0.1:9545 then save.

![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/localhost_metamask.PNG)

If successful you should see you are connect to the local network.

![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/network.PNG)

Now we need to import one of are truffle address so we can create some stars.

Go to the truffle development console and copy a private key. This key will be used to import the address into metaMask. Go back to metamask and click on the circle of colors then import account. __Note__ Make sure your still on the local network.  Paste your private key then select import. If done right you should see your new test account with 100 ETH. Make sure you have this account selected.

```
$ truffle develop
```
Copy private key 
![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/develop.PNG)

Paste private key in Metamask to import an account.

![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/paste.PNG)

Open new console or terminal and access folder app in project

```
$ cd app
$ npm run dev
```
To access DAPP, access in your browser to http://127.0.0.1:8080
Accept request to connect a account imported on your matemask.

![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/connect.PNG)

Next create a star with a star name (string) and star ID (integer), then press create star. You should see a metaMask
notification allowing you to confirm a contract interaction.

![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/star.PNG)

Confirm Contract Transaction
![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/confirm.PNG)

Looking up a star by id.
![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/lookup.PNG)

You can see you transaction in Metamask.
![Alt text](https://github.com/wleandrooliveira/private_decentralized_star_notary/blob/master/images/transact.PNG)

### Deploying Contract to the Rinkeby public test network

if not installed truffle-hdwallet-provider and openzeppelin-solidity

you can install using command.

```
$ npm install --save truffle-hdwallet-provider

$ npm install --save openzeppelin-solidity

```
Now follow steps to run DAPP

``` 
$ truffle develop

$ truffle (develop)>compile

$ truffle (develop)>migrate --reset --network rinkeby

```
In other console or terminal

```
$ cd app
$ npm run dev
```
__Note__ <a href = "https://faucet.rinkeby.io/">Rinkeby faucet</a> must be used to get test ether to make transactions.

To view the DAPP point your browser to http://127.0.0.1:8080, make sure you selected a Rinkeby account in metaMask with Ether. Next create a star with a star name (string) and star ID (integer), then press create star. You should see a metaMask notification allowing you to confirm a contract interaction.

Contract will pend for a couple of seconds. Then you should see confirmation. Next look up the star you just created by entering the star ID.

StarNotary smart contract is now deployed on Rinkeby test network.