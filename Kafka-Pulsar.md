#### Good Kafka doc.
https://jaceklaskowski.gitbooks.io/apache-kafka/kafka-docker.html  
https://medium.com/@manuzhang/a-whirlwind-tour-of-kafka-summit-sf-2018-fec98752804c  
http://cloudurable.com/blog/kafka-tutorial-kafka-producer-advanced-java-examples/index.html  
https://gerardnico.com/dit/kafka/kafka  
https://www.javaworld.com/article/3060078/big-data-messaging-with-kafka-part-1.html  
https://www.javaworld.com/article/3066873/big-data-messaging-with-kafka-part-2.html   
https://medium.com/@psinghal04/replaying-kafka-messages-an-implementation-in-golang-e5c6867cf084   



#### Kafka Best Practices
https://medium.com/real-time-streaming/apache-kafka-best-practices-d9fac5c483c0   
https://dzone.com/articles/kafka-consumer-and-multi-threading   
https://data-flair.training/blogs/kafka-performance-tuning/   
https://www.infoq.com/articles/apache-kafka-best-practices-to-optimize-your-deployment/  
https://dzone.com/articles/kafka-internals-topic-partitions  

#### KSQL and UDF
https://gist.github.com/kaiwaehner/850217a8071851dd2332571f90049b21  
https://medium.com/bakdata/queryable-kafka-topics-with-kafka-streams-8d2cca9de33f  

#### Kafka Security
https://opencredo.com/blogs/securing-kafka-using-vault-pki/  
https://speakerdeck.com/salyh/transparent-end-to-end-security-for-apache-kafka-dh?slide=13  

#### Kafka Time Consumer
https://mapr.com/docs/61/MapR_Streams/example-TimeBasedConsumer.html  

#### Best Practices and Pitfalls
https://codeburst.io/kafka-gotchas-c627d4186aa0   


#### Kafka in a Docker Container
https://rmoff.net/2018/08/02/kafka-listeners-explained/   


#### Avro Schema Evolution
##### Backward-Compatible
New schema reads old data
- If field does not exist use a default value
- Query over old and new data using a new schema
##### Forward-Compatible
Old schema reads new data
- Ignores new fields
- Deleting fields without defaults is not forward compatible
- Data stream evolve without changing our downstream consumers
##### Full-Compatible
Both forward and backward
- Only add fields with defaults
- Only remove fields that have defaults
###### Breaking Change
Not Backward nor Forward
- Adding/Remove elements from an Enum
- Changing the type of a field (string -> int for example)
- Rename a required field (field without default)
##### Rules
- Make your primary key required
- Give default values to all the fields that could be removed in the future (null is allowed)
- Be careful when using Enums as they can't evolve over time
- Don't rename fields. You can add aliases instead (other names)
- When evolving a schema, ALWAYS give default values
- When evolving a schema, NEVER delete a required field

