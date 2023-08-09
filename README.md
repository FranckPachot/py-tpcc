ycqlsh> create keyspace tpcc;


```

bash

curl -sSL https://downloads.yugabyte.com/get_clients.sh | bash
ln -s "/py-tpcc/pytpcc/yugabyte-client-2.16.0.1/bin/ycqlsh" /usr/local/bin/ycqlsh
ycqlsh yb 9042 -e 'create keyspace tpcc'

/usr/local/bin/python -m pip install --upgrade pip
pip install pycassa cqlsh
pip install yb-cassandra-driver --install-option="--no-cython"
cd /py-tpcc/pytpcc/

cat > ycql.config <<'CONFIG'
[cassandra]
# Keyspace
keyspace             = tpcc
# ReplicationFactor
replicationfactor    = 1
# The host address to the Cassandra database
hostname             = yb
# Port number
port                 = 9042
# Name
name                 = tpcc
CONFIG


python tpcc.py --config=ycql.config cassandra

```
