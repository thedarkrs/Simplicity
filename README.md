# Simplicity

DO NOT BUILD WITH autogen.sh IT IS NOT FULLY IMPLEMENTED YET
==============================================================

Build Daemon and GUI Wallets with Below Information until this area states otherwise.


UNIX BUILD NOTES
====================
Some notes on how to build Simplicity in Unix.

Copyright (c) 2018 The Simplicity Developers
Distributed under the MIT/X11 software license, see the accompanying
file license.txt or http://www.opensource.org/licenses/mit-license.php.
This product includes software developed by the OpenSSL Project for use in
the OpenSSL Toolkit (http://www.openssl.org/).  This product includes
cryptographic software written by Eric Young (eay@cryptsoft.com) and UPnP
software written by Thomas Bernard.


To Build Headless
-----------------

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev

git clone https://github.com/SimplicityDev2018/Simplicity.git

cd Simplicity/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd

cd Simplicity/src/leveldb

sudo sh build_detect_platform build_config.mk .

cd

cd Simplicity/src

sudo make -f makefile.unix

strip simplicityd

LD_LIBRARY_PATH=/usr/local/lib

export LD_LIBRARY_PATH


To Build Qt Wallet
------------------

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev

git clone https://github.com/SimplicityDev2018/Simplicity.git

cd Simplicity/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd

cd Simplicity/src/leveldb

sudo sh build_detect_platform build_config.mk .

cd

cd Simplicity

sudo qmake SPL-Qt.pro

sudo make -jnumofcoreshere