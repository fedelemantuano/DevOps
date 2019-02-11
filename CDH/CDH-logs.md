# Log management in CDH

# CM Firehose

Host Monitor Storage Directory  firehose.storage.base.directory /var/lib/cloudera-host-monitor (./ts)  
Time-Series Storage firehose_time_series_storage_bytes  10 GB

## Fast n Dirty:
```bash
systemctl stop cloudera-scm-server.service
cd /var/lib/cloudera-service-monitor/ts
rm -rf ts_stream_rollup_*
rm -rf ts_type_rollup_*
systemctl start cloudera-scm-server.service
```

## Safety Valve in CM for cmon.conf

* Host Monitor Advanced Configuration Snippet (Safety Valve) for cmon.conf  
* Service Monitor Advanced Configuration Snippet (Safety Valve) for cmon.conf  
* Activity Monitor Advanced Configuration Snippet (Safety Valve) for cmon.conf  

```properties
firehose_time_series_storage_bytes  
3221225472  
```

10 GiB 	10737418240 B  (DEFAULT)  
 5 GiB 	 5368709120 B  
 4 GiB 	 4294967296 B  
 3 GiB 	 3221225472 B  
 2 GiB 	 2147483648 B  
 
