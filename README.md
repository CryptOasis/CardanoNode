# CardanoNode
Custom cardano-node builds 

- Latest v1.19.0


Apply

```bash
[[ -z "$NODE_HOME" ]] && {
  echo "NODE_HOME env variable is not set. Exiting..."
  exit 127
}

curl -L -s  https://github.com/CryptOasis/CardanoNode/raw/master/builds/$(curl -L  -s  https://github.com/CryptOasis/CardanoNode/raw/master/builds/cardano-node-bin-latest.tgz) |\
tar -C "$NODE_HOME/bin" -zxvf -

```
