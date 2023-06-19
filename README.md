# Lookup destination IP reputation.
translate {
  dictionary_path => "${SYNLITE_SURICATA_DICT_PATH:/etc/logstash/synlite_suricata/dictionaries}/ip_rep_basic.json"
  field => "[dest_ip]"
  destination => "[@metadata][dest_rep_label]"
}

# Parse the IP reputation label into tags.
if [@metadata][dest_rep_label] {
  ruby {
    init => "
      require 'json'
    "
    code => "
      event.set('[dest_rep_tags]', JSON.parse(event.get('[@metadata][dest_rep_label]')))
    "
  }
}
