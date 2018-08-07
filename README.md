# flume-kafka-source

> flume kafka source fixed kafka rebalance offset to 0 maybe repeat bug.

> copy from apache-flume-1.8.0

> kafka version up to 1.1.0

# use

```

# complise
mvn clean -e -U install -DskipTests=true

# use it with flume plugin, copy $SOURCE/target/flume-kafka-source-1.0.0.jar to
$FLUME_HOME/plugins.d/kafka-source/lib/flume-kafka-source-1.0.0.jar

# kafka source conf, detail see http://flume.apache.org/FlumeUserGuide.html#kafka-source
a1.sources.r1.type = cn.fireapp.flume.source.kafka.KafkaSource # only changed
a1.sources.r1.batchSize = 500
a1.sources.r1.batchDurationMillis = 10000
a1.sources.r1.kafka.bootstrap.servers = localhost:9200
a1.sources.r1.kafka.topics.regex = ^topic_[0-9]{8}$
a1.sources.r1.kafka.consumer.group.id = flume-id-test
a1.sources.r1.kafka.consumer.auto.offset.reset = earliest
a1.sources.r1.kafka.consumer.session.timeout.ms = 30000
a1.sources.r1.kafka.consumer.request.timeout.ms = 40000
a1.sources.r1.kafka.consumer.max.poll.records = 500

```

