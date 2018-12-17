# Log management in CDH

# CM Firehose

Host Monitor Storage Directory  firehose.storage.base.directory /var/lib/cloudera-host-monitor (./ts)
Time-Series Storage firehose_time_series_storage_bytes  10 GB

```bash
systemctl stop cloudera-scm-server.service
cd /var/lib/cloudera-service-monitor/ts
rm -rf ts_stream_rollup_*
rm -rf ts_type_rollup_*
systemctl start cloudera-scm-server.service
```
