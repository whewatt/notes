## Install Geth

    sudo apt-get install software-properties-common 
    sudo add-apt-repository -y ppa:ethereum/ethereum 
    sudo apt-get update 
    sudo apt-get install ethereum -y

## Run Geth

    geth -rpc -rpcaddr "0.0.0.0" --rpcport 8545 --rinkebyß

## Dev tools

Chrome plugin Metamask
Testrpc
    sudo npm install -g ethereumjs-testrpc
    testrpc
Truffle
    sudo npm install -g truffle
    truffle

## Starting a new project
1.  Create a folder
2.  In the folder, run truffle
    truffle unbox webpack
    <img src="images/truffle.png">

## Deploy an app
1.  testrpc
2.  Save the mnemonic
    <img src ="images/testrpc.png">