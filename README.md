version 0.1.4.0 Updated 4/29/14
Added support to disable POS mining in paccoin.conf
staking=0

paccoin a project based on blehcoin, a SHA256D based coin with Proof of Stake.

Paccoin is a digital currency that users can send or receive paccoins to one another on the internet without the need for banks. It is the official currency of the future nation called Pacifica. 

Official Website for Paccoin is www.pacifica-nation.com/paccoin

<h1>Installation Instructions: Ubuntu</h1>

* Install the following dependencies using your terminal program:

sudo apt-get install build-essential libssl-dev libboost-all-dev libminiupnpc-dev<br>
sudo apt-get install libdb4.8++-dev libqrencode-dev qt4-dev-tools qt4-qmake libqt4-dev<br>

(Some versions of Ubuntu do not have libminiupnpc-dev available. You can download miniupnpc libraries here: http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.8.tar.gz) Use the instructions to install in doc section.

* Download the paccoin repository

cd ~<br>
git clone https://github.com/wmcorless/paccoin.git paccoin-0.1.4.0

This will create a directory called "paccoin-0.1.4.0" and copy the files into it. 

* Next we're going to compile the programs.

cd paccoin/src<br>
make -f makefile.unix

If all goes well you will have a file called paccoind. 

* Run this by using the following command.

./paccoind

The file should end and state that an rpcuser and rpcpassword needs to be added. By running this you have now created 
a hidden directory located at ~/.paccoin. 

* Enter that directory.

cd ~/.paccoin

* Using a text editor create your file paccoin.conf and change the rpcuser and rpcpassword for security 
reasons. 

nano paccoin.conf

rpcuser=yourname<br>
rpcpassword=yourpassword<br>
addnode=72.234.204.139

if you intend to solo mine use the following as an example:

rpcallowip=192.168.1.* (for lan, or use a direct IP)<br>
server=1<br>
gen=0 (use 1 to generate coins (this will cause your computer to run at 100% cpu))<br>

Save this file. 

* Now you're ready to compile and run your wallet.

cd ~/paccoin<br>
qmake paccoin-qt.pro<br>
make

You should see the file paccoin-qt which you can execute by double clicking on it in file manager. This is your wallet 
gui.

It is also recommended that you change the passphrase to something you can remember. If you lose your passphrase 
there is no way to get it back and you will lose any money in your wallet, so be careful.
