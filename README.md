# MYST

## Language

[English Docs](README.md) | [中文文档](README_ZH.md)

## Instructions

### Pre-conditions

Register for the site: 

https://mystnodes.co/?referral_code=qx2oT3x6bxKOXYJ906Ca9m0PKAvk8g3wcEd2o5IJ

A server or local device that can connect to the Internet

Mainstream architectures are not special architectures, preferably docker-enabled (LXC virtualization is a no-no because Docker can't create shims on LXC)

Have around 0.5USD of MATIC tokens on Polygon chain in hand ( if you don't have any, feel free to inquire at https://t.me/spiritlhl_bot )

### Installation process for the Docker version (check the docs on your own for other methods)

Install docker beforehand

```
curl -sSL https://get.docker.com/ | sh
```

then run

(The internal and external ports mapped here are the same, if you need the external port to be something else, assuming ```2222```, change ```4449:4449``` to ```2222:4449```)

```bash
docker pull mysteriumnetwork/myst && docker run --log-opt max-size=10m --cap-add NET_ADMIN -d -p 4449:4449 --name myst -v myst-data:/var/lib/mysterium-node --restart unless-stopped mysteriumnetwork/myst:latest service --agreed-terms-and-conditions
sudo docker stop watchtower; sudo docker rm watchtower; sudo docker rmi containrrr/watchtower; sudo docker run -d --restart=always --name watchtower -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --cleanup --include-stopped --include-restarting --revive-stopped --interval 60 myst
```

Open ```Public_IP:4449``` and follow the prompts

You need to set up your own key, then pay the setup fee, then set up the withdrawal address.

You can find your own key in the ```API details``` in the ```API details``` in the ```API details```.

It is recommended to use paypal for the first node at the beginning, because you don't have to think about all the miner's fees, and unless you have a MATIC before that, you can't afford to use cryptocurrencies to pay the setup fee.

Setting up a withdrawal address is recommended using a meta wallet, such as the ```polygon``` chain in the ```MetaMask``` plugin in your browser (only this chain can pay setup fees when setup on other nodes)

Token Contract Address:

```
0x1379E8886A944d2D9d440b3d88DF536Aea08d9F3
```

Solutions to other related issues can be found in ```https://docs.mysterium.network/```

### 注意事项

Subsequent to this node does not use the need to migrate the node information can not be in the new node to pay a setup fee, have to ponder the docs in the migration node part!

Because of the use of docker installation, myst command becomes

```
docker exec -ti myst your_command
```

It needs to be executed inside the container

You still have to pay the setup fee to add new nodes, but if you already have a certain amount of MYST tokens on hand, remember to use the polygon chain currency to pay for them, which is cheaper (0.01USD per node to activate).

But note that the use of MYST activation requires fuel costs, that is, MATIC you need to hold about 1U or 0.5U can be enough for you to carry out more than a hundred times 0.05 ~ 0.1 MYST currency transfer!

(If you need more than 0.1MYST when you activate, wait for a while for the MYST to fall back to the range).

### Experiences

U.S. data center IP 24 hours a day about 0.01 ~ 0.1 MYST currency income (provided that the IP is a data center IP, home wide or business wide earnings will be higher, 1Gbps bandwidth)

Withdrawals require a fee of about 20%, you can wait until the node is full of 5 MYST currency automatic withdrawals, you can also visit the corresponding IP UI panel to withdraw manually (the more you save the better withdrawals, the handling ratio to see the deduction of the lesser).

It takes about 3 days to get a clear picture of the level of earnings, and the later the earnings become more stable.

Home wide earnings than the data center, now 1 MYST currency is equal to 0.2 U.S. dollars, I feel that in addition to the U.S., other regions only home wide earnings will be high, other earnings will be very low

Turkey and Sweden have no earnings at all, and Poland and France have low earnings.
