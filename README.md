Copyright (c) 2009-2019 Bitcoin Developers
Copyright (c) 2013 Darkcoin Developers
Copyright (c) 2019 Ozcoin Developers

What is Ozcoin?
----------------
http://www.ozcoin.com

Ozcoin (OzC) is a peer-to-peer and business-to-business cryptocurrency designed 
with a long-term vision in mind. We are determined to create a resilient digital 
currency that will play a pivotal role in the digital finance macrocosm of the 
future due to being built upon solid programming design and advanced financial 
technology with genuine usability and merchant integration.

Ozcoin is based on darkcoin and bitcoin and uses X11 as proof-of-work algorithm.

 - 1 minute block target
 - 90 millon total coins
 - 20000.007 coins per block (till 1000th Block) == 20.0000072% ~~ 20% 
 - 9 coins per block (till 8888888th Block) == 79.9999928% ~~ 80% 
 - Reward Maturity: 21 blocks
 - 2 Hours to retarget difficulty
 - P2P Port: 5207
 - RPC Port: 5208


License
-------

Ozcoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of Ozcoin depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to Ozcoin folder. For that, go to the directory where Ozcoin folder is located and then do:

sudo chmod -R 777 Ozcoin/


 1.3 Compilation

After sucessfully giving all permissions, go to Ozcoin folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running Ozcoin CLI

Once compilation successfully ends, you can run Ozcoin daemon with following steps:

a) Make sure you are in src folder of Ozcoin ( your_directory/Ozcoin/src )
b) Run: ./Ozcoin -daemon
c) The above comamnd will create "data directory for Ozcoin"(.Ozcoin folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.Ozcoin/Ozcoin.conf
It is recommended you use the following random password:
rpcuser=Ozcoinrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.Ozcoin/Ozcoin.conf
e) Run: nano /home/your_linux_username/.Ozcoin/Ozcoin.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to Ozcoin.conf file and save.
g) Run: ./Ozcoin -daemon ( This time there won't be any error message )
h) Run: ./Ozcoin getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running Ozcoin-qt (Linux GUI Wallet)

After successfully comiling Ozcoin CLI, you can proceed for Ozcoin-qt Wallet

a) Make sure you are in Ozcoin's root directory ( your_directory/Ozcoin)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./Ozcoin-qt
e) You will see an Ozcoin-qt icon in your Ozcoin's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install Ozcoin GUI Wallet

2.2 Default Location of Ozcoin's root Directory in Windows is:
    
    32-bit: Program Files/Ozcoin
    64-bit: Program Files (x86)/Ozcoin

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/Ozcoin


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of Ozcoin ( your_directory/Ozcoin/src )

3.2 Run daemon: ./Ozcoin -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./Ozcoin getinfo

b) Check your Wallet's Balance: ./Ozcoin getbalance

c) Check number of Nodes you are connected to: ./Ozcoin getconnectioncount

d) Display Detailed information of Connedted Nodes: ./Ozcoin getpeerinfo

e) Generate New Address for Wallet: ./Ozcoin getnewaddress

f) Send some OzC amount to an OzC address: ./Ozcoin sendtoaddress <OzC Address> <Amount>
   example: ./Ozcoin sendtoaddress iVFWg6saZ4L6yvaJso14y2YpRD5hGPNVEL 0.999

g) View all transactions in your wallet: ./Ozcoin listtransactions

h) Encrypt CLI and GUI Wallet: ./Ozcoin encryptwallet <passphrase>
   example: ./Ozcoin encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./Ozcoin walletpassphrase <passphrase> <timeout>
   example: ./Ozcoin walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./Ozcoin walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./Ozcoin walletpassphrase thehard*&password!! thenew%^password

