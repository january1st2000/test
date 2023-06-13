Thg 6 12 16:17:16 bmc1 filebeat[1059]: 2023-06-12T16:17:16.318+0700        ERROR        [publisher_pipeline_output]        pipeline/output.go:154        Failed to connect to backoff(async(tcp://192.168.2.65:5044)): dial tcp 192.168.2.65:5044: connect: connection refused
root@bmc1:~# filebeat test output
logstash: 192.168.2.65:5044...
  connection...
    parse host... OK
    dns lookup... OK
    addresses: 192.168.2.65
    dial up... ERROR dial tcp 192.168.2.65:5044: connect: connection refused


appender.plain_rolling.type = RollingFile
appender.plain_rolling.name = plain_rolling
appender.plain_rolling.fileName = ${sys:ls.logs}/logstash-plain.log
appender.plain_rolling.filePattern = ${sys:ls.logs}/logstash-plain-%d{yyyy-MM-dd}-%i.log.gz
appender.plain_rolling.policies.type = Policies
appender.plain_rolling.policies.time.type = TimeBasedTriggeringPolicy
appender.plain_rolling.policies.time.interval = 1
appender.plain_rolling.policies.time.modulate = true
appender.plain_rolling.layout.type = PatternLayout
appender.plain_rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c]%notEmpty{[%X{pipeline.id}]}%notEmpty{[%X{plugin.id}]} %m%n
appender.plain_rolling.policies.size.type = SizeBasedTriggeringPolicy
appender.plain_rolling.policies.size.size = 100MB
appender.plain_rolling.strategy.type = DefaultRolloverStrategy
appender.plain_rolling.strategy.max = 30

appender.plain_rolling_slowlog.type = RollingFile
appender.plain_rolling_slowlog.name = plain_rolling_slowlog
appender.plain_rolling_slowlog.fileName = ${sys:ls.logs}/logstash-slowlog-plain.log
appender.plain_rolling_slowlog.filePattern = ${sys:ls.logs}/logstash-slowlog-plain-%d{yyyy-MM-dd}-%i.log.gz
appender.plain_rolling_slowlog.policies.type = Policies
appender.plain_rolling_slowlog.policies.time.type = TimeBasedTriggeringPolicy
appender.plain_rolling_slowlog.policies.time.interval = 1
appender.plain_rolling_slowlog.policies.time.modulate = true
appender.plain_rolling_slowlog.layout.type = PatternLayout
appender.plain_rolling_slowlog.layout.pattern = [%d{ISO8601}][%-5p][%-25c] %m%n
appender.plain_rolling_slowlog.policies.size.type = SizeBasedTriggeringPolicy
appender.plain_rolling_slowlog.policies.size.size = 100MB
appender.plain_rolling_slowlog.strategy.type = DefaultRolloverStrategy
appender.plain_rolling_slowlog.strategy.max = 30

appender.deprecation_plain_rolling.type = RollingFile
appender.deprecation_plain_rolling.name = deprecation_plain_rolling
appender.deprecation_plain_rolling.fileName = ${sys:ls.logs}/logstash-deprecation.log
appender.deprecation_plain_rolling.filePattern = ${sys:ls.logs}/logstash-deprecation-%d{yyyy-MM-dd}-%i.log.gz
appender.deprecation_plain_rolling.policies.type = Policies
appender.deprecation_plain_rolling.policies.time.type = TimeBasedTriggeringPolicy
appender.deprecation_plain_rolling.policies.time.interval = 1
appender.deprecation_plain_rolling.policies.time.modulate = true
appender.deprecation_plain_rolling.layout.type = PatternLayout
appender.deprecation_plain_rolling.layout.pattern = [%d{ISO8601}][%-5p][%-25c]%notEmpty{[%X{pipeline.id}]}%notEmpty{[%X{plugin.id}]} %m%n
appender.deprecation_plain_rolling.policies.size.type = SizeBasedTriggeringPolicy
appender.deprecation_plain_rolling.policies.size.size = 100MB
appender.deprecation_plain_rolling.strategy.type = DefaultRolloverStrategy
appender.deprecation_plain_rolling.strategy.max = 30

logger.slowlog.appenderRef.plain_rolling_slowlog.ref = plain_rolling_slowlog
logger.deprecation.appenderRef.deprecation_plain_rolling.ref = deprecation_plain_rolling
