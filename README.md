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
