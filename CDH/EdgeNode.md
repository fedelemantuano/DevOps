# EdgeNode

* <PID> is the process PID of the instance and can be found in CM selecting instances -> chose an instance -> processes (in stdout is compleatili defined)
* <HBASE_MASTER_HOST> is the host on which the master runs
* <KERBEROS_DOMAIN> domain of kerberized cloudera
* <SOLR_HOST> a solr server host
  
  
### Client Configuration retrieval
```sh
wget -O <SVC_NAME>.zip --http-user=admin --http-password=admin http://<CM_HOST>:7180/cmf/services/<SVC_NUM>/client-config
```

### HBase

```sh
su - hbase -s /bin/bash
scp root@<HBASE_MASTER_HOST>:/run/cloudera-scm-agent/process/<PID>-hbase-MASTER/hbase.keytab .    # Only first Time
scp root@<HBASE_MASTER_HOST>:/run/cloudera-scm-agent/process/<PID>-hbase-MASTER/hbase-site.xml .  # Only first Time
mv /etc/hbase/conf/hbase-site.xml /etc/hbase/conf/hbase-site.xml.bak                              # Only first Time
mv /var/lib/hbase/hbase-site.xml /etc/hbase/conf/hbase-site.xml                                   # Only first Time
kinit -k -t hbase.keytab hbase/<HBASE_MASTER_HOST>@<KERBEROS_DOMAIN>
hbase shell
```

### Solr

```sh
su - solr -s /bin/bash
scp root@<SOLR_HOST>:/run/cloudera-scm-agent/process/<PID>-solr-SOLR_SERVER/solr.keytab . # Only first Time
kinit -k -t solr.keytab solr/<SOLR_HOST>@<KERBEROS_DOMAIN>
```
