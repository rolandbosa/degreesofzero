First, you'll need to download the source code for the latest release of bitcoin; you can view a list of releases [here](https://github.com/bitcoin/bitcoin/releases). You'll usually want to get the most recent stable release (which will just have numbers, no suffix).

An example of downloading the latest release at the time of writing this post:
```
wget https://github.com/bitcoin/bitcoin/archive/v0.9.2.tar.gz /usr/local/src/
```

Extract the archive:
```
cd /usr/local/src
tar -zxvf v0.9.2.tar.gz
```


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


## Build

It's time to build.

```
cd /usr/local/src/bitcoin-0.9.2
./autogen.sh
./configure --with-cli=no --with-gui=no
make
```
This will take a little while.

After the build process has completed with no errors, you should end up with a bitcoind binary located at `/usr/local/src/bitcoin-0.9.2/src/bitcoind`. Now it's time to move on to [installing bitcoind on Ubuntu](https://degreesofzero.com/article/intalling-bitcoind-on-ubuntu).