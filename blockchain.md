## Install Geth

    sudo apt-get install software-properties-common 
    sudo add-apt-repository -y ppa:ethereum/ethereum 
    sudo apt-get update 
    sudo apt-get install ethereum -y

## Run Geth

    geth -rpc -rpcaddr "0.0.0.0" --rpcport 8545 --rinkebyß