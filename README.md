# mystnodes

## mystnodes使用的中文记录

### 前置条件

一台能连接互联网的服务器或本地设备

主流架构不是特殊架构，最好是支持docker

手中有1美元paypal余额或3USD左右的MATIC或者5USD左右的ETH

### Docker版本的安装流程(别的方法自行查看docs)

事先安装好docker

然后运行

- 这里映射的内外网端口一致，如果需要外网端口为别的，假设为```2222```，则将```4449:4449```改为```2222:4449```

```bash
docker pull mysteriumnetwork/myst && docker run --cap-add NET_ADMIN -d -p 4449:4449 --name myst -v myst-data:/var/lib/mysterium-node --restart unless-stopped mysteriumnetwork/myst:latest service --agreed-terms-and-conditions
```

打开```外网IP:4449```按照提示操作

需要设置自己的Key，然后付款设置费，再然后设置提款地址

自己的Key可在```https://mystnodes.com/me```中的```API details```找到

推荐初期第一个节点使用paypal，因为不用考虑各种矿工费，除非这之前持有MATIC，否则使用加密货币支付设置费都很奢侈

设置提现地址推荐使用meta钱包，如浏览器中的```MetaMask```插件中的```polygon```链(只有这个链能在别的节点设置时付款设置费)

其他相关问题可在```https://docs.mysterium.network/```中找到解决办法

#### 注意事项

后续新增别的节点需要迁移节点信息，得琢磨docs中的迁移节点部分

由于使用docker安装，myst命令变成了

```
docker exec -ti myst 命令部分
```

需要在容器内部执行

新增节点还是得付设置费，但此时手上已有一定量的MYST代币了，记得使用polygon链上的货币进行付款即可，成本就比较低廉了

#### 收益

美国数据中心IP一天24小时大概收入0.1~0.2个MYST货币(前提是网络不垃圾，1Gbps带宽)

提款需要收大概20%手续费，可以等节点满5个MYST货币自动提款，也可以访问对应IP的UI面板手动提款
