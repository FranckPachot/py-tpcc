ycqlsh> create keyspace tpcc;


```

/usr/local/bin/python -m pip install --upgrade pip
pip install pycassa
python tpcc.py --print-config cassandra


cat > cassandra.config <<'CONFIG'
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


python tpcc.py --config=cassandra.config cassandra

```
