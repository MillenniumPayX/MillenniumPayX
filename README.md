MillenniumPayX Core (fork of PIVX) integration/staging repository
======================================


It is recommended [use the shell script](https://github.com/lgsproject/MPX-install) to install a MillenniumPayX Masternode on a Linux server running Ubuntu 14.04, 16.04, 18.04

***

Quick installation of the MillenniumPayX daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):

    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/lgsproject/MillenniumPayX.git
    cd MillenniumPayX
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip logiscoind
    sudo strip MillenniumPayX-cli
    sudo strip MillenniumPayX-tx
    cd ..

Running the daemon:

    logiscoind 

Stopping the daemon:

    MillenniumPayX-cli stop

Demon status:

    MillenniumPayX-cli getinfo
    MillenniumPayX-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/lgsproject/MillenniumPayX/releases

P2P port: 48484, RPC port: 48483
-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
