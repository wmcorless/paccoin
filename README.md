paccoin: a SHA256D version of 'foocoin'


Minimal Changes Needed: 

Search/replace "paccoin" with your coin's name.

Rename /src/paccoin* files to your coins name (i.e.: paccoinrpc.cpp to yourcoinrpc.cpp)

Rename /src/qt/paccoin* files to your coins name (i.e.: paccoingui.cpp to yourcoingui.cpp)

Replace/Rename /src/qt/res/icons/paccoin* files to your coins name (i.e.: paccoin.png to yourcoin.png)

Rename files in /src/qt/res/locale/paccoin* files to your coins name

Replace /src/qt/res/images/* with your own images.

Change RPC/P2P Ports in /src/protocol.h LINES 18-21

Change /src/main.cpp following lines:

LINE20: const bool IsCalculatingGenesisBlockHash = true; //(leave/set to true, set back to false afterward)

LINE48: const int64 nChainStartTime = 1376215269; //set to today's epoch

LINE949: int64 nSubsidy = 1 * COIN; //set your block rewards

LINE2547: const char* pszTimestamp = "paccoin - yea he did."; //set to your catchphrase

---------------------------------------------------------------------------------------------------------

Now, compile it like foocoin and run it. Debug.log will spit out a Merkel/GB/nNonce for you. 

Plug those values in here:

/src/main.cpp LINE20: const bool IsCalculatingGenesisBlockHash = false;

/src/main.cpp LINE 2565 block.nNonce   = 0;

/src/main.cpp LINE 2597 assert(block.hashMerkleRoot == uint256("0x"));

/src/main.h LINE 50 static const uint256 hashGenesisBlockOfficial("0x");

Now recompile with the new .cpp and .h and your SHA256D coin is ready to go!
