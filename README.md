paccoin a project based on blehcoin, a SHA256D based coin with Proof of Stake.

It is the official currency of the future nation called Pacifica. Although many libertarian (freedom) minded 
individuals have spoken about forming a new nation that is based on libertarian principles, no one has succeeded 
in doing so until now. Pacifica is a nation based on the Kingdom of God, which will one day rule the world under 
the returning King Jesus. We believe that the only true freedom for people on earth will be based on a theocracy 
where Jesus is King.

Official Website for Paccoin is www.pacifica-nation.com/paccoin

Currently only supporting linux machines.

<h1>Installation Instructions: Linux/Unix</h1>

* Install the following dependencies using your terminal program:

sudo apt-get install build-essential libssl-dev libdb4.8-dev libboost-all-dev libminiupnpc-dev<br>
sudo apt-get install libdb++-dev libqrencode-dev qt3-dev-tools qt4-qmake libqt4-dev

* Download the paccoin repository

cd ~<br>
git clone https://github.com/wmcorless/paccoin.git paccoin

This will create a directory called "paccoin" and copy the files into it. 

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
addnode=72.234.46.224

Save this file. 

* Now you're ready to compile and run your wallet.

cd ~/paccoin<br>
qmake paccoin-qt.pro<br>
make

You should see the file paccoin-qt which you can execute by double clicking on it in file manager. This is your wallet 
gui.

It is also recommended that you change the passphrase to something you can remember. If you lose your passphrase 
there is no way to get it back and you will lose any money in your wallet, so be careful.
