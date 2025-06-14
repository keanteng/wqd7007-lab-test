# WQD7007 Lab Test

![Apache Hive](https://img.shields.io/badge/Apache%20Hive-FDEE21?style=for-the-badge&logo=apachehive&logoColor=black)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Bash Script](https://img.shields.io/badge/bash_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)

The lab test is designed to assess your understanding of data cleaning and transformation using Hive. You will be working with a dataset where you are performing various data cleaning operations, and generating insights from the data.

## Setup Hive on Docker

```bash
# pull the latest Hive image
docker pull apache/hive:4.0.1

# run the Hive container
docker run -d -p 10000:10000 -p 10002:10002 `
  --env SERVICE_NAME=hiveserver2 `
  --name hive-server `
  -v "${PWD}:/keanteng" `
  apache/hive:4.0.1
```

After the container is running, you can access the Hive CLI or Beeline to interact with Hive.

```bash
# find your data, you will be put at opt/hive, to go to root
cd ..
cd ..

# view your directory
ls keanteng

# start hive CLI
hive

# set the connection
!connect jdbc:hive2://localhost:10000
```

## Docker Extra

```bash
# start the container
docker start hive-server

# stop the container
docker stop hive-server

# enter the cli
docker exec -it hive-server bash

# list all running containers
docker ps
```
## Further Usage
```bash
# remove a container
docker rm hive-server

# prune all stopped containers
docker container prune
# remove all unused images
docker image prune -a
# remove all unused volumes
docker volume prune
# remove build cache
docker builder prune
```