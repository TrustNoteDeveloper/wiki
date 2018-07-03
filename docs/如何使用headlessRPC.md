# 如何使用 headlessRPC ?

如何使用RPC ？

一、安装 && 运行

1、克隆源码

git clone https://github.com/TrustNoteDevelopers/RPC.git
2、进入RPC目录

cd RPC
3、安装cnpm

npm install cnpm -g
4、使用cnpm安装

cnpm install
5、初始化

npm run init
6、调试运行

npm run rpc
7、服务器运行

sudo npm install -g pm2
pm2 start rpc_server.js
二、调试 & 开发

1、切换到测试网

npm run totest
2、切换到主网

npm run totest
3、生成地址：

curl --data '{"jsonrpc":"2.0", "id":1, "method":"getnewaddress", "params":{} }' http://127.0.0.1:6332
得到地址：

{"jsonrpc":"2.0","result":"QZEM3UWTG5MPKYZYRMUZLNLX5AL437O3","id":1}
4、转账:sendtoaddress

curl --data '{"jsonrpc":"2.0", "id":1, "method":"sendtoaddress", "params":["BVVJ2K7ENPZZ3VYZFWQWK7ISPCATFIW3", 1000] }' http://127.0.0.1:6332
得到如下信息：

{"jsonrpc":"2.0","result":"vuudtbL5ASwr0LJZ9tuV4S0j/lIsotJCKifphvGATmU=","id":1}
祝你好运!

我们的例子在 https://github.com/TrustNoteDevelopers/examples ，欢迎下载使用。

开发者如何交流？

就在知识星球：https://t.zsxq.com/Yf2rN3b

备注：

有些ubuntu没有node，需要如下安装：

sudo apt install npm
sudo npm install -g n
sudo n latest
