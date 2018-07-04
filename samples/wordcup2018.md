The essence of the World Cup guessing game is a Token distribution system triggered by conditions. In the process of payment collection and transfer, the headlessRPC service is used. Its download address is:

https://github.com/TrustNoteDevelopers/RPC

Developers need to deploy a headless server on their own and build a business system that interacts with headless with RPC commands to implement the query and distribution of digital assets (Token).

From a technical point of view, it is through the two interfaces of getnewaddress and getaddressbalance to build the order system based on the TrustNote chain. Through the sendtoaddress interface, payment can be made to the winning user.

![](https://raw.githubusercontent.com/TrustNoteDevelopers/wiki/master/samples/images/worldcup2018_01.jpg)

To build such a guessing game, you only need to use these three interfaces. The technical principles and implementation methods are described in detail below.

![](https://raw.githubusercontent.com/TrustNoteDevelopers/wiki/master/samples/images/worldcup2018_02.jpg)

1) generate the collection address

When a user makes a bet, the system generates a new TTT wallet address, which is displayed to the user by a qr code plug-in. The user pays the bet amount to this address by scanning the TTT wallet.

The ability to generate new addresses USES the getnewaddress method in headless. As shown in the figure below, getnewaddress returns a newly produced wallet address in the headless server.

$curl -- data '{" jsonrpc ":" 2.0 ", "id" : 1, "method" : "getnewaddress", "params" : {}}' http://127.0.0.1:6332 {" jsonrpc ":" 2.0 ", "result" : "QZEM3UWTG5MPKYZYRMUZLNLX5AL437O3", "id" : 1}


2) check the payment status

The newly generated address balance is 0, and every time the user makes a comment, a new address is generated, so the address is one-time. A one-time address can be used to determine whether a user's payment is valid.

Using the getaddressbalance interface in headless, you can query the balance of the specified address. In the World Cup guessing game, after users scan the code to pay, the system will regularly check the balance of the address just generated. If the balance is greater than 0, the order will be considered effective. The usage of getaddressbalance is as follows:

Curl -- data '{" jsonrpc ":" 2.0 ", "id" : 1, "method" : "getaddressbalance", "params" : [" AC32OSLNT64L2B2GARP7SNFDPR3WDNZZ "]}' http://127.0.0.1:6332
{" jsonrpc ":" 2.0 ", "result" : {" address ":" AC32OSLNT64L2B2GARP7SNFDPR3WDNZZ ", "objBalance" : {" bytes ": 0," QXZVREFQWR0pM0qrZ + d + HIeJTEyMkd rgB7 / Syp6Ufk = ": 10000}}," id ": 1}


3) transfer

For the winning user, you need to transfer it using the sendtoaddress interface. Developers only need this interface and don't care which address to transfer to the user from (because headless generates an infinite number of addresses). Headless is essentially a wallet, so no matter how many addresses Headless generates, developers only need to use the sendtoaddress interface to complete the transfer from Headless to the user's address.


Headless developer documentation can be in here to view in detail: https://github.com/TrustNoteDevelopers/RPC
