# Kuma token network

This network configuration makes use of the [Hyperledger Fabric network setup](https://github.com/Kunstmaan/hyperledger-fabric-network-setup) to generate all the needed artifacts. To 

The configuration creates two organisations `AuthOrg` and `KunstmaanOrg`, both will get a certificate which is signed by a ROOT certificate. AuthOrg is the organisation that has all the users and KunstmaanOrg is the organisation responsible for hosting the peer and the orderer. 

This configuration is just for testing purposes and isn't a very good blockchain configuration. It's possible to change the configuration in [crypto_config-kuma.yaml](./configuration/crypto_config-kuma.yaml) and regenerate all the artifacts using `kuma-hf-network generate ./configuration/crypto_config-kuma.yaml`. 

Right now only the [devmode configuration](./generated/devmode) is being used by [Hyperledger Fabric chaincode dev setup](https://github.com/Kunstmaan/hyperledger-fabric-chaincode-dev-setup) and that one only needs one orderer and one peer.


There is also a production network setup in this, you can start it using `helpers/blockchain_manager.sh start`. You can see help about that script, which contains different features by running `helpers/blockchain_manager.sh -h`. Note that since the production network is using TLS authentication, you need to resolve the names of the peers/orderers into an ip (probably your localhost if you're running this on your machine). This can be done using `generated/scripts/set_hosts_private.sh` which will modify your `/etc/hosts` file.
