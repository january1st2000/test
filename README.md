Thg 6 12 16:17:16 bmc1 filebeat[1059]: 2023-06-12T16:17:16.318+0700        ERROR        [publisher_pipeline_output]        pipeline/output.go:154        Failed to connect to backoff(async(tcp://192.168.2.65:5044)): dial tcp 192.168.2.65:5044: connect: connection refused
root@bmc1:~# filebeat test output
logstash: 192.168.2.65:5044...
  connection...
    parse host... OK
    dns lookup... OK
    addresses: 192.168.2.65
    dial up... ERROR dial tcp 192.168.2.65:5044: connect: connection refused
