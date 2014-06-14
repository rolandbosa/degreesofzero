This tutorial assumes you've already [built bitcoind from source](https://degreesofzero.com/article/building-bitcoind-from-source-on-ubuntu). If you haven't done that, go ahead and do that now.

It's important to note that the `bitcoind` package available in the universal Ubuntu repositories is a very old version. This is why you want to build your own binary from the latest source.


## Dependencies

To get `add-apt-repository`:
```
sudo apt-get install python-software-properties
```

Add the bitcoin PPA:
```
add-apt-repository ppa:bitcoin/bitcoin
apt-get update
```

Install dependencies:
```
apt-get install libboost-all-dev libdb4.8-dev libdb4.8++-dev
```


## The Binary

Put the bitcoind binary in the `/usr/local/bin` directory. Then add a symlink in `/usr/bin`:
```
ln -s /usr/local/bin/bitcoind /usr/bin/bitcoind
```


## Configuration

Before starting bitcoind, you'll want to create the `bitcoin.conf` configuration file:
```
cd ~/
mkdir .bitcoin
cd .bitcoin
vim bitcoin.conf
```

Add the following to `bitcoin.conf`:
```
server=1
daemon=1
testnet=1
rpcuser=UNIQUE_RPC_USERNAME
rpcpassword=UNIQUE_RPC_PASSWORD
```

## Starting bitcoind

Now you're ready to start bitcoind:
```
bitcoind
```

If all is well you should see the following in your console:
```
Bitcoin server starting
```

To view info about your bitcoind instance:
```
bitcoind getinfo
```

And to view a list of all available commands:
```
bitcoind help
```

It's important to note that you may wish to take additional steps to secure your bitcoin installation. These steps may vary based upon the purpose of the installation. I will cover this topic in future articles.

Happy bitcoining!