# logging-layer-registry
this project uses RabbitMQ as input and registers json data on MongoDB or HDFS according to message header named "tag"

## Setup
This setup assumes you already have docker-compose and docker (using docker toolbox) installed.


```
git clone https://github.com/SadeghMahmoudpour/logging-layer-registry.git
cd logging-layer-registry
docker-compose up
```
## Play
first you need to add your message in rabbit.
```
open http://localhost:15672/
```
and use the login

```
username: rabbitmq
password: rabbitmq
```
got to Queues and select "logs" queue http://localhost:15672/\#/queues/%2F/logs(http://localhost:15672/#/queues/%2F/logs)  
here you can publish your message with json payload as data and header named "tag" with this format: "mongo.{collection name}" to register data in mongo or "hdfs.{file name}" for hdfs
