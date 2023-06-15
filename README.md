https://redmine.openinfosecfoundation.org/projects/suricata/wiki/_Logstash_Kibana_and_Suricata_JSON_output
 sudo service logstash stop
sudo rm -rf /etc/logstash/
sudo apt-get remove logstash

  {
    "_id": "c5fee8a0-82cb-11e9-8c3c-4925ccb1fc48",
    "_type": "visualization",
    "_source": {
      "title": "Suricata: NFS - Status (records) - donut",
      "visState": "{\"title\":\"Suricata: NFS - Status (records) - donut\",\"type\":\"pie\",\"params\":{\"addLegend\":true,\"addTooltip\":true,\"isDonut\":true,\"labels\":{\"last_level\":true,\"show\":false,\"truncate\":100,\"values\":true},\"legendPosition\":\"right\",\"type\":\"pie\"},\"aggs\":[{\"id\":\"1\",\"enabled\":true,\"type\":\"count\",\"schema\":\"metric\",\"params\":{\"customLabel\":\"Records\"}},{\"id\":\"2\",\"enabled\":true,\"type\":\"terms\",\"schema\":\"segment\",\"params\":{\"field\":\"nfs.status\",\"size\":35,\"order\":\"desc\",\"orderBy\":\"1\",\"otherBucket\":true,\"otherBucketLabel\":\"other\",\"missingBucket\":false,\"missingBucketLabel\":\"Missing\",\"customLabel\":\"Status\"}}]}",
      "uiStateJSON": "{}",
      "description": "",
      "version": 1,
      "kibanaSavedObjectMeta": {
        "searchSourceJSON": "{\"filter\":[{\"meta\":{\"alias\":\"NFS\",\"negate\":false,\"type\":\"phrase\",\"key\":\"event.subtype\",\"value\":\"nfs\",\"params\":{\"query\":\"nfs\"},\"disabled\":false,\"indexRefName\":\"kibanaSavedObjectMeta.searchSourceJSON.filter[0].meta.index\"},\"query\":{\"match\":{\"event.subtype\":{\"query\":\"nfs\",\"type\":\"phrase\"}}},\"$state\":{\"store\":\"appState\"}}],\"query\":{\"language\":\"lucene\",\"query\":\"\"},\"indexRefName\":\"kibanaSavedObjectMeta.searchSourceJSON.index\"}"
      }
    },
    "_meta": {
      "savedObjectVersion": 2
    },
    "_migrationVersion": {
      "visualization": "7.17.0"
    },
    "_references": [
      {
        "name": "kibanaSavedObjectMeta.searchSourceJSON.index",
        "type": "index-pattern",
        "id": "filebeat-*"
      },
      {
        "name": "kibanaSavedObjectMeta.searchSourceJSON.filter[0].meta.index",
        "type": "index-pattern",
        "id": "filebeat-*"
      }
    ]
  },



{
  "_index": "filebeat-7.17.10-2023.06.05-000002",
  "_type": "_doc",
  "_id": "wga0vIgBEc4EjkCgPn6-",
  "_version": 1,
  "_score": 1,
  "_source": {
    "agent": {
      "hostname": "bmc1",
      "name": "bmc1",
      "id": "743f8739-8d42-4ad6-ae41-a2926736131a",
      "type": "filebeat",
      "ephemeral_id": "cb99545d-e449-4a6b-ad32-ba63ce1d717a",
      "version": "7.17.10"
    },
    "log": {
      "file": {
        "path": "/var/log/suricata/eve.json"
      },
      "offset": 1912256515
    },
    "destination": {
      "address": "224.0.0.251",
      "port": 5353,
      "bytes": 0,
      "ip": "224.0.0.251",
      "packets": 0
    },
    "source": {
      "address": "192.168.2.64",
      "port": 5353,
      "bytes": 87,
      "ip": "192.168.2.64",
      "packets": 1
    },
    "fileset": {
      "name": "eve"
    },
    "network": {
      "community_id": "1:9nCTo/snivlqmPGcsc09qzHF0zs=",
      "bytes": 87,
      "transport": "udp",
      "packets": 1,
      "direction": "outbound"
    },
    "tags": [
      "suricata",
      "_geoip_expired_database"
    ],
    "input": {
      "type": "log"
    },
    "@timestamp": "2023-06-15T01:38:27.514Z",
    "ecs": {
      "version": "1.12.0"
    },
    "related": {
      "ip": [
        "192.168.2.64",
        "224.0.0.251"
      ]
    },
    "service": {
      "type": "suricata"
    },
    "host": {
      "hostname": "bmc1",
      "os": {
        "kernel": "5.15.0-73-generic",
        "codename": "focal",
        "name": "Ubuntu",
        "type": "linux",
        "family": "debian",
        "version": "20.04.6 LTS (Focal Fossa)",
        "platform": "ubuntu"
      },
      "containerized": false,
      "ip": [
        "192.168.2.64",
        "fe80::70a:fb96:1f48:f6f7"
      ],
      "name": "bmc1",
      "id": "e8a97754b0c14c17a3bc0b9e1b8adbcd",
      "mac": [
        "7c:10:c9:1f:f5:c9"
      ],
      "architecture": "x86_64"
    },
    "suricata": {
      "eve": {
        "in_iface": "eno1",
        "event_type": "flow",
        "flow_id": "172541367872332",
        "flow": {
          "reason": "timeout",
          "alerted": false,
          "state": "new",
          "age": 0
        }
      }
    },
    "event": {
      "duration": 0,
      "ingested": "2023-06-15T01:38:29.180929395Z",
      "original": "{\"timestamp\":\"2023-06-15T08:38:27.514167+0700\",\"flow_id\":172541367872332,\"in_iface\":\"eno1\",\"event_type\":\"flow\",\"src_ip\":\"192.168.2.64\",\"src_port\":5353,\"dest_ip\":\"224.0.0.251\",\"dest_port\":5353,\"proto\":\"UDP\",\"app_proto\":\"failed\",\"flow\":{\"pkts_toserver\":1,\"pkts_toclient\":0,\"bytes_toserver\":87,\"bytes_toclient\":0,\"start\":\"2023-06-15T08:35:44.060236+0700\",\"end\":\"2023-06-15T08:35:44.060236+0700\",\"age\":0,\"state\":\"new\",\"reason\":\"timeout\",\"alerted\":false}}",
      "created": "2023-06-15T01:38:28.185Z",
      "kind": "event",
      "module": "suricata",
      "start": "2023-06-15T01:35:44.060Z",
      "end": "2023-06-15T01:35:44.060Z",
      "category": [
        "network"
      ],
      "type": [
        "connection",
        "start"
      ],
      "dataset": "suricata.eve"
    }
  },
  "fields": {
    "event.category": [
      "network"
    ],
    "host.os.name.text": [
      "Ubuntu"
    ],
    "host.hostname": [
      "bmc1"
    ],
    "host.mac": [
      "7c:10:c9:1f:f5:c9"
    ],
    "service.type": [
      "suricata"
    ],
    "host.os.version": [
      "20.04.6 LTS (Focal Fossa)"
    ],
    "host.os.name": [
      "Ubuntu"
    ],
    "source.ip": [
      "192.168.2.64"
    ],
    "suricata.eve.event_type": [
      "flow"
    ],
    "suricata.eve.flow.reason": [
      "timeout"
    ],
    "destination.address": [
      "224.0.0.251"
    ],
    "agent.name": [
      "bmc1"
    ],
    "host.name": [
      "bmc1"
    ],
    "network.community_id": [
      "1:9nCTo/snivlqmPGcsc09qzHF0zs="
    ],
    "event.kind": [
      "event"
    ],
    "suricata.eve.flow_id": [
      "172541367872332"
    ],
    "source.packets": [
      1
    ],
    "event.original": [
      "{\"timestamp\":\"2023-06-15T08:38:27.514167+0700\",\"flow_id\":172541367872332,\"in_iface\":\"eno1\",\"event_type\":\"flow\",\"src_ip\":\"192.168.2.64\",\"src_port\":5353,\"dest_ip\":\"224.0.0.251\",\"dest_port\":5353,\"proto\":\"UDP\",\"app_proto\":\"failed\",\"flow\":{\"pkts_toserver\":1,\"pkts_toclient\":0,\"bytes_toserver\":87,\"bytes_toclient\":0,\"start\":\"2023-06-15T08:35:44.060236+0700\",\"end\":\"2023-06-15T08:35:44.060236+0700\",\"age\":0,\"state\":\"new\",\"reason\":\"timeout\",\"alerted\":false}}"
    ],
    "host.os.type": [
      "linux"
    ],
    "network.packets": [
      1
    ],
    "fileset.name": [
      "eve"
    ],
    "input.type": [
      "log"
    ],
    "log.offset": [
      1912256515
    ],
    "suricata.eve.in_iface": [
      "eno1"
    ],
    "agent.hostname": [
      "bmc1"
    ],
    "tags": [
      "suricata",
      "_geoip_expired_database"
    ],
    "host.architecture": [
      "x86_64"
    ],
    "agent.id": [
      "743f8739-8d42-4ad6-ae41-a2926736131a"
    ],
    "source.port": [
      5353
    ],
    "ecs.version": [
      "1.12.0"
    ],
    "host.containerized": [
      false
    ],
    "event.created": [
      "2023-06-15T01:38:28.185Z"
    ],
    "agent.version": [
      "7.17.10"
    ],
    "host.os.family": [
      "debian"
    ],
    "event.start": [
      "2023-06-15T01:35:44.060Z"
    ],
    "destination.bytes": [
      0
    ],
    "destination.port": [
      5353
    ],
    "event.end": [
      "2023-06-15T01:35:44.060Z"
    ],
    "source.address": [
      "192.168.2.64"
    ],
    "destination.packets": [
      0
    ],
    "host.ip": [
      "192.168.2.64",
      "fe80::70a:fb96:1f48:f6f7"
    ],
    "agent.type": [
      "filebeat"
    ],
    "event.module": [
      "suricata"
    ],
    "suricata.eve.flow.state": [
      "new"
    ],
    "related.ip": [
      "192.168.2.64",
      "224.0.0.251"
    ],
    "host.os.kernel": [
      "5.15.0-73-generic"
    ],
    "network.bytes": [
      87
    ],
    "network.direction": [
      "outbound"
    ],
    "host.id": [
      "e8a97754b0c14c17a3bc0b9e1b8adbcd"
    ],
    "source.bytes": [
      87
    ],
    "suricata.eve.flow.alerted": [
      false
    ],
    "suricata.eve.flow.age": [
      0
    ],
    "host.os.codename": [
      "focal"
    ],
    "destination.ip": [
      "224.0.0.251"
    ],
    "network.transport": [
      "udp"
    ],
    "event.duration": [
      0
    ],
    "event.ingested": [
      "2023-06-15T01:38:29.180Z"
    ],
    "@timestamp": [
      "2023-06-15T01:38:27.514Z"
    ],
    "host.os.platform": [
      "ubuntu"
    ],
    "event.type": [
      "connection",
      "start"
    ],
    "log.file.path": [
      "/var/log/suricata/eve.json"
    ],
    "agent.ephemeral_id": [
      "cb99545d-e449-4a6b-ad32-ba63ce1d717a"
    ],
    "event.dataset": [
      "suricata.eve"
    ]
  }
}
