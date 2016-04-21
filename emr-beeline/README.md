#Beeline
YMMV

We were having issues connecting to EMR outside of the cluster on just a regular EC2 instance.

Plop this container on your machine and you can connect to the emr cluster ip address/hostname

1. Create an alias for beeline:
  1. `alias beeline="docker run -ti --rm -v $PWD:$PWD kcmerrill/emr-beeline /opt/mapr/hive/hive-0.13/bin/beeline"`
2. Query your EMR cluster:
  2. ./beeline -u jdbc:hive2://<EMR_IP>:10000/default -e "select * from schema.table_name LIMIT 1000" --outputformat=tsv

