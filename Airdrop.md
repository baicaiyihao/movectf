1、

curl --location --request POST 'https://faucet.devnet.sui.io/gas' --header 'Content-Type: application/json' --data-raw '{ "FixedAmountRequest": { "recipient": "0x8cb825ebf41660e8b5053f255625762b0e35474127e948c39410744989c4c04e" } }'

获取测试币

{"transferredGasObjects":[{"amount":10000000000,"id":"0xc7e4cf6cf4023133774cbc1ae2277e3c2967e059e30f9991426ec0d6243a47fa","transferTxDigest":"8fzRNWgoBxX8y13Tob9SwvuqVLX3rRgfBZ7ZFSGU8mGu"}],"error":null}(base)

 

 

2、获取drop

Vault在https://suiexplorer.com/上获取

![image-20231229170647991](https://github.com/baicaiyihao/movectf/blob/main/1703841398798.jpg)

获取后用下列命令获取drop

(base) root@DESKTOP-FL11GC3:~/sui# sui client call --package 0x29ca6794c9cb174ca25909efac513d45633555b6919ca6ef78dc3c5c002eec71 --module drop --function airdrop --args 0x6e87e406bd8595ef9f4c4cb0cc8b2336c69285beceaa5344b09e91f3072d7c54 --gas-budget 10000000

3、

创建新账户继续获取drop

sui client call --package 0x29ca6794c9cb174ca25909efac513d45633555b6919ca6ef78dc3c5c002eec71 --module drop --function airdrop --args 0x6e87e406bd8595ef9f4c4cb0cc8b2336c69285beceaa5344b09e91f3072d7c54 --gas-budget 10000000

获取后转移给0x7d4bdbdfd8ce930af7dd18b56d918811d8e5e20e309132130d238631e828984d

sui client transfer --to 0x7d4bdbdfd8ce930af7dd18b56d918811d8e5e20e309132130d238631e828984d --object-id 0x1e2ef3baf55c5d752a6793b89b1ed09cbda435d787462d8e4b700c9b1d9741e9 --gas-budget 10000000

查询目前有2个drop

![image-20231229170722811](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20231229170722811.png)

重复上述转移操作

创建地址

sui client new-address ed25519 movectf2

切换地址

sui client switch --address 0x69628aa28cd1ad91a97f5bb5f569fd01f581e40f608e7f8fa572e11dc40ea145

获取测试币

curl --location --request POST 'https://faucet.devnet.sui.io/gas' --header 'Content-Type: application/json' --data-raw '{ "FixedAmountRequest": { "recipient": "0x69628aa28cd1ad91a97f5bb5f569fd01f581e40f608e7f8fa572e11dc40ea145" } }'

领取空投

sui client call --package 0x29ca6794c9cb174ca25909efac513d45633555b6919ca6ef78dc3c5c002eec71 --module drop --function airdrop --args 0x6e87e406bd8595ef9f4c4cb0cc8b2336c69285beceaa5344b09e91f3072d7c54 --gas-budget 10000000

转移drop

sui client transfer --to 0x7d4bdbdfd8ce930af7dd18b56d918811d8e5e20e309132130d238631e828984d --object-id 0x2e749139b2d8a6c817463590bb01c5730fd70d2d57315defd3cbb66c2ffe8699  --gas-budget 1000000

 

4、

切换地址回去

sui client switch --address 0x7d4bdbdfd8ce930af7dd18b56d918811d8e5e20e309132130d238631e82898

4d

 

5、

然后重复合并drop

sui client merge-coin --primary-coin 0x1e2ef3baf55c5d752a6793b89b1ed09cbda435d787462d8e4b700c9b1d9741e9 --coin-to-merge 0x47e939684a2142eaa611c7f888ebcf63dc97e669b754df8972b367c32820668c --gas-budget 10000000

 

6、

获取flag

sui client call --package 0x29ca6794c9cb174ca25909efac513d45633555b6919ca6ef78dc3c5c002eec71 --module drop --function get_flag --args 0xcf9ada18e37021a146d1edc3eb0f4f38f5bfadb1bacbcb4bf012d4ef88d183d3 0x1e2ef3baf55c5d752a6793b89b1ed09cbda435d787462d8e4b700c9b1d9741e9 --gas-budget 10000000

 

提交Transaction Digest: 7e9eaz4JWvHkFptzyx99du89vP5s8en29GrbJN8mxnZp

![image-20231229170814231](https://github.com/baicaiyihao/movectf/blob/main/1703841380475.jpg)

 



