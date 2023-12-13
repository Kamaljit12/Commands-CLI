# Kafka CLI Commands: Spin Up a Kafka Environment

## Run the ZooKeeper service:
    $ bin/zookeeper-server-start.sh config/zookeeper.properties

## start the Kafka broker service:
    $ bin/kafka-server-start.sh config/server.properties

# Kafka CLI Commands: Create a Topic

## create kafka topics with partition and replication factor
    $ bin/kafka-topics.sh --create --topic my-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1

# Kafka CLI Commands: View Details About a Topic

##  view metadata about the topics in your Kafka cluster. The following Kafka CLI command provides information on the number of partitions and replicas, among other topic details:
    $ bin/kafka-topics.sh --bootstrap-server=localhost:9092 --describe --topic my-topic

## view the information of the zookeeper
    $ kafka-topics.sh --describe --zookeeper localhost:2181 --topic my-topic

# Kafka CLI Commands: List Topics

## display a list of all the topics in the Kafka cluster.
    $ bin/kafka-topics.sh --list --zookeeper localhost:2181
    
  - You can also pass the Kafka cluster URL to list all topics.
    
         $ bin/kafka-topics.sh --bootstrap-server=localhost:9092 --list

# Kafka CLI Commands: Publish Events to a Topic
- Kafka clYou can use Kafka CLI’s console producer client to emit new events to your Kafka topic. Run the following command, to perform this:
- ients normally communicate via the Kafka broker to read and write events. The broker is responsible for persisting these events in a distributed, partitioned, commit log (topic).

      $ bin/kafka-console-producer.sh --topic my-topic --bootstrap-server localhost:9092

# Kafka CLI Commands: View Events

- To view the events stored in the Kafka topic, you will use Kafka CLI’s consumer client. So, open a new terminal session. Then you can run the command shown below:

      $ bin/kafka-console-consumer.sh --topic my-topic --from-beginning --bootstrap-server localhost:9092

# Kafka CLI Commands: Change Message Retention Period
- When the producer client sends an event to the Kafka broker, that event is appended to the end of one of the commit logs. By default, the event is retained for 168 hours or 7 days after which it’s deleted to free up disk space.
- Based on your application’s requirements, you might want to bypass this behavior. For example, consider the following command:

      $ bin/kafka-topics.sh --zookeeper=localhost:2181 --alter --topic my-topic --config retention.ms=300000*

# Kafka CLI Commands: Add Partitions to a Topic
- In a multi-node cluster, you might consider splitting your topics into multiple partitions to achieve higher throughput. This is because if you simply constrain a topic to a single node, it limits the ability to scale out.
- Instead of limiting yourself to a single node, you should take advantage of the extra CPU and RAM by distributing your topics across multiple machines. To add partitions to your Kafka topic, use the following command:

      $ bin/kafka-topics.sh --zookeeper=localhost:2181 --alter --topic my-topic --partitions 10

# Kafka CLI Commands: Delete a Topic
You can delete a topic from the Kafka broker using the following Kafka CLI command:

      $ bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic my-topic

However, if you have set a custom retention policy for your topic as we did earlier, you first need to delete it before executing that command. To delete the retention policy, use the following command:

      $ bin/kafka-topics.sh --zookeeper localhost:2181 --alter --topic mytopic --delete-config retention.ms





      

  

