# CardanoNode
Custom cardano-node builds 

- Latest v1.19.0


Apply

```bash
# Default
NODE_VER=1.19.0

[[ -z "$NODE_HOME"  ]] && {
  echo "NODE_HOME env variable is not set. Exiting..."
  exit 127
}

# cardano-node-bin-1.19.0.tgz
NODE_FILE=$(curl -L  -s  https://github.com/CryptOasis/CardanoNode/raw/master/builds/cardano-node-bin-latest.tgz)
NODE_VER=$( echo $NODE_FILE | sed -e 's@^.*-\(.*\).tgz@\1@' )
curl -L -s  "https://github.com/CryptOasis/CardanoNode/raw/master/builds/$NODE_FILE" |\
tar -C "$NODE_HOME/bin" -zxvf -

pushd "$NODE_HOME/bin/"
ln -sf "cardano-node-$NODE_VER" "cardano-node" 
ln -sf "cardano-cli-$NODE_VER" "cardano-cli"
popd 

```
