# kafka_flink_demo

1. 安装Apache Maven(apache-maven-3.8.1)
https://maven.apache.org
解压到一个目录，配置环境变量。
export PATH=/[path of extracted folder]/apache-maven-3.8.1/bin:$PATH
2. 创建项目(适用于自己创建)
创建一个目录(以"kafka_flink_demo"为例), 然后在这个目录打开terminal并运行以下命令:
mvn archetype:generate
\
-DarchetypeGroupId=org.apache.flink
\
-DarchetypeArtifactId=flink-quickstart-java
\
-DarchetypeVersion=1.12.0
3. 将项目(包含src和pox文件)导入IDE
4. 下载Apache Kafka(kafka_2.12-2.7.0)
https://kafka.apache.org/downloads
5. 下载Flink(flink-1.12.2)
https://flink.apache.org/downloads.html
6. 运行Apache Kafka
# start zookeeper server
./bin/zookeeper-server-start.sh ./config/zookeeper.properties
# start broker
./bin/kafka-server-start.sh ./config/server.properties 
# create topic “test”
./bin/kafka-topics.sh --create --topic test --zookeeper localhost:2181 --partitions 1 --replication-factor 1
# consume from the topic using the console producer
./bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
# produce something into the topic (write something and hit enter)
./bin/kafka-console-producer.sh --topic test --broker-list localhost:9092
