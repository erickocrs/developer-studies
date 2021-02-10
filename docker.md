## Docker

- Standards Commands

  ```bash
  docker
  docker version
  docker info
  ```

  ```bash
  docker container --help
  docker container logs container_name
  ```

  Create and Run Containers

  ```bash
  docker container run 80:80 wordpress
  ```

  List containers

  ```bash
  docker container ps
  docker container ps -a
  ```
  Stop Container (ID only enough to be unique)

  ```bash
  docker container stop 6945
  ```

  Remove Containers

  ```bash
  # standard remove
  docker container rm 5665 
  
  # forced remove
  docker container rm -f 5665 446 456
  ```

- Exploring Docker container's file system

  ```
  docker exec -t -i mycontainer /bin/bash
  ```

- Exploring using Snapshotting

  ```bash
  # find ID of your running container:
  docker ps
  
  # create image (snapshot) from container filesystem
  docker commit 12345678904b5 mysnapshot
  
  # explore this filesystem using bash (for example)
  docker run -t -i mysnapshot /bin/bash
  ```

- Docker Inspect

  ```
  docker inspect container-name
  docker inspect container-name | grep IPAddress
  ```

  