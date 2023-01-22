# mystnodes

## mystnodes使用的中文记录

### 前置条件

一台能连接互联网的服务器或本地设备

主流架构不是特殊架构，最好是支持docker

手中有1美元paypal余额或1USD左右的MATIC (没有的欢迎咨询 https://t.me/spiritlhl_bot )

### Docker版本的安装流程(别的方法自行查看docs)

事先安装好docker

然后运行

- 这里映射的内外网端口一致，如果需要外网端口为别的，假设为```2222```，则将```4449:4449```改为```2222:4449```

```bash
docker pull mysteriumnetwork/myst && docker run --cap-add NET_ADMIN -d -p 4449:4449 --name myst -v myst-data:/var/lib/mysterium-node --restart unless-stopped mysteriumnetwork/myst:latest service --agreed-terms-and-conditions
[[ ! $(docker ps -a) =~ watchtower ]] && docker run -d --name watchtower --restart always -p 2095:8080 -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --cleanup
```

打开```外网IP:4449```按照提示操作

需要设置自己的Key，然后付款设置费，再然后设置提款地址

自己的Key可在```https://mystnodes.com/me```中的```API details```找到

推荐初期第一个节点使用paypal，因为不用考虑各种矿工费，除非这之前持有MATIC，否则使用加密货币支付设置费都很奢侈

设置提现地址推荐使用meta钱包，如浏览器中的```MetaMask```插件中的```polygon```链(只有这个链能在别的节点设置时付款设置费)

其他相关问题可在```https://docs.mysterium.network/```中找到解决办法

### 注意事项

后续这个节点不用的需要迁移节点信息可以不用在新节点上再交一笔设置费，得琢磨docs中的迁移节点部分

由于使用docker安装，myst命令变成了

```
docker exec -ti myst 命令部分
```

需要在容器内部执行

新增节点还是得付设置费，但此时手上已有一定量的MYST代币了，记得使用polygon链上的货币进行付款即可，成本就比较低廉了(每个节点0.01USD即可激活)

但注意使用MYST进行激活需要燃料费，也就是MATIC你需要持有大概1U或者0.5U即可，足够你进行一百次以上的0.05~0.1MYST货币转账了

(激活时显示需要的MYST超过0.1MYST的，等待一段时间自然回落到区间内的)

### 收益

美国数据中心IP一天24小时大概收入0.01~0.1个MYST货币(前提是该IP是数据中心IP，家宽或商宽收益会更高点，1Gbps带宽)

提款需要收大概20%手续费，可以等节点满5个MYST货币自动提款，也可以访问对应IP的UI面板手动提款(攒的越多提现越好，手续费比例来看扣的少点)

大概需要3天才能看清楚收益水平，越往后收益就越稳定

家宽收益比数据中心的高，现在1个MYST货币大概等于0.2美元，感觉除了美国，别的地区只有家宽收益会高，别的收益会非常低

土耳其地区似乎完全没有收益
