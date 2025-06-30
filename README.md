# Apache Flink containers using Docker Compose

![Static Badge](https://img.shields.io/badge/Flink-suntectec-green?logo=apacheflink&logoColor=%23E6526F)

Running Apache Flink containers using Docker Compose is a convenient way to get up and running to try out some Flink workloads.

There is a post to go along with this project here [https://gordonmurray.com/data/2023/11/02/deploying-flink-cdc-jobs-with-docker-compose.html](https://gordonmurray.com/data/2023/11/02/deploying-flink-cdc-jobs-with-docker-compose.html)

Assuming docker compose is installed you can start the containers using the following command in the same folder as the docker compose file:

```
docker compose up -d
```

This will start the containers in the background and you can check that the containers are running using

```
docker ps
```

You should see something like the following showing a jobmanager and 2 task managers.

```
CONTAINER ID   IMAGE                        COMMAND                  CREATED        STATUS                  PORTS                                                      NAMES
8f178a106918   flink:1.20                   "/docker-entrypoint.…"   16 hours ago   Up 16 hours             6123/tcp, 8081/tcp                                         apache_flink_and_docker_compose-taskmanager-1
1cb1aeae0261   flink:1.20                   "/docker-entrypoint.…"   16 hours ago   Up 16 hours             6123/tcp, 8081/tcp                                         apache_flink_and_docker_compose-taskmanager-2
8ddbb18bef28   flink:1.20                   "/docker-entrypoint.…"   16 hours ago   Up 16 hours             6123/tcp, 0.0.0.0:8081->8081/tcp                           jobmanager
```

To start adding some work to Flink you can access the Flink console using the following command and from there you can try out various jobs like creating tables.

```bash
docker exec -it jobmanager /opt/flink/bin/sql-client.sh
```

To run a Flink job to CDC from a Mariadb container and sink some data in to Redis, use the following:

```bash
docker exec -it jobmanager /opt/flink/bin/sql-client.sh embedded -f job.sql
```
