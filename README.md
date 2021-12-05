# Web3-Inbox
First of many Blockchain projects to practice stuff I learned and test them together with good programming pricinciples.

This project contains but the simplest Smart Contract that does nothing more than save a save and display a message. The point was to be able to generate the 
Ethereum side of an aplication from start to finish. 

Few questions to ask yourself..

Is this the right way to do things in a professional/produciton enviroment? 
  -> Absolutely NOT. There are much better ways of doing things which I will focus on in my next side projects!

Then what is the point of this project?
  -> As mentioned above, we all need to start from somehwere. This projects aim to help me and whoever is interested in learning about Web3 
     what a very basic setup for a defi up can look like. This space is changing rapidly and together with it we have new versions for crucial 
     libraries like web3.js or traditional faucets that you would use to get some test Ether not working or permanently offline. 
     
How do I then test this?
  -> Below you will find a basic setup guide. I will not go through everything, like how to set up Metamask, or how to make an Infura account cause there are 
     many great content creators out there with step by step guides. I will though provide some things to look out for to save you some trouble!


---------------------------------------------------------------------------------------------------------------------------------------------------------------

After cloning the repository and directing yourself to it you will need to do a few things!

<code>npm init</code>

npm install solc web3 mocha ganache-cli @truffle/hdwallet-provider

Update your test script in the package.json file to be 
  "test": "mocha"

In deploy.js you need to update the provider with your own Metamask Mnemonic and Infura URL

provider = new HDWalletProvider(
  'YOUR_MNEMONIC',
  'YOUR_INFURA_URL'
);

NOTE*** 
  At the point of writting this. If you lost your metamask Mnemonic the only thing you can do is remove the extension all together and start again and 
  for the love of God and all that is holy please make sure you are not on the Mainnet and instead you are on a testnet like Rinkeby! VERY IMPORTANT!!!
  ![](images/Metamask.png)

  When creating your infura account make sure you switch away from the Mainnet and into the Rinkeby Network
  ![](images/InfuraNetworkSelect.jpg)


Then you need to run the compile script using the javascript file called 'compile'
node compile.js

The deploy script using.. you guessed it the js file called 'deploy' (which is where you updated your infura link to Rinkbey and Metamask Mnemonic also switched to Rinkeby)
node deploy.js

That should generate the following:
  Attempting to deploy from account 0x438...
  
Followed by a
  Contract deployed to 0x8643...

You can then go to:
  -> https://rinkeby.etherscan.io/
  
  enter the address you just got and search for the contract
  ![](images/EtehrScan.jpg)

If you want to then test the Contract then what you have to do is go to
  -> http://remix.ethereum.org
  -> Create a new file and call it "Inbox.sol"
  -> Go to "Deploy & run transactions"
  -> Make sure you select "Injected Web3" (then a metamask verification will appear just accept to connect)
  -> Your Metamask account should appear under "Account"
  -> Almost there hang on.. at "At Address" you will paste there the address of the contract and click the "At address" button

If everything went smoothly you should be able to see the deployed contract under "Deployed Contracts"
  ![](images/Remix.jpg)

You can click message which will give you the currently set message or you can enter a new one yourself (a metamask modal will pop up).
After doing that you can go back to Etherscan and see your transaction and/or retrieve your new message!

Oh forgot to mention that if you want some FAKE ether for your testing cause setting a new message will cost you gas you need to do the following:

Go to:
  -> https://faucets.chain.link/rinkeby

    Enter your wallet address (testnet account address) - Metamask
    Check 0.1 test ETH
    Uncheck 10 test LINK
    Check the Im Not a Robot verification
    Click Send Request

Do this a couple of times to get some FAKE ether sent to your Metamask


  



  
  

  
