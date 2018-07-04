T口令功能是将钱包内的资产通过生成T口令和兑换T口令的方式将资产转移，整个过程都是去中心化服务。每一次生成T口令和兑换T口令的过程就是转账的过程，所以会消耗一点TTT作为燃料。
 
T口令就是16个字符的密码，只是生成的每一个T口令（T口令1、T口令2…T口令100）需要和一个固定的助记词继续生成对应的根私钥（根私钥1、密码2…根私钥100），根私钥又派生出对应地址（地址1、地址2…地址100），当用户兑换T口令的时候，会将派生地址的资产转移到自己的钱包地址（地址a、地址b…地址100）里。

原理图如下图所示：

![](https://github.com/TrustNoteDevelopers/wiki/raw/master/samples/images/t-code.png)

当前钱包在github位置：https://github.com/trustnote/trustnote-wallet
 
更多例子，源码都在：https://github.com/TrustNoteDevelopers/samples
