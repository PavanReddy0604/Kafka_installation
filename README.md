# Kafka installation on docker


1. Create a folder
2. Open that folder in any one of the IDE's
3. create `docker-compose.yml` file
4. open terminal
5. Navigate to the folder which was created in step 1
6. Do `ls`
   
     you should see the `docker-compose.yml` file
8. Run `docker compose -f docker-compose.yml up -d`
   
 - this will read the configuration from the `docker-compose.yml` file,pull the images from registry, start the services defined in it, and run them in detached mode.
       
8.check docker images using `docker images`

9.check running docker containers using `docker ps`
- you should see kafka and zookeeper containers running  

10.Run `docker exec -it kafka /bin/sh`
   
-  this allows you to run commands interactively as if you were directly logged into the container
 - syntax is `docker exec -it <container_id_or_name> sh`  

11.Navigate to bin using `cd opt/bitnami/kafka/bin`  

12.Do `ls`  
- you should all `.sh` files (for linux and Mac OS) or or `.bash` files (for windows OS) related to kafka and zookeeper.
13. **Create Topic**  

        `kafka-topics.sh --create --topic <topic_name> --bootstrap-server localhost:9092`
14. **List Topics**  

        `kafka-topics.sh --bootstrap-server=localhost:9092 --list`
15. **Publish messages to topic**  

        `kafka-console-producer.sh --topic <topic_name> --bootstrap-server=localhost:9092`
16. **Consuming messages from topic**  

        `kafka-console-consumer.sh --topic <topic-name> --bootstrap-server=localhost:9092`

