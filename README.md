# agile-cryptdb-backend
A MySQL v5.5 backend for CryptDB

Forked from https://github.com/docker-library/mysql/

For integration with CryptDB in AGILE see https://github.com/Agile-IoT/Practical-Cryptdb_Docker

## How to setup:

##### 1. Make sure to have Docker installed

http://docs.docker.com/v1.8/installation/

##### 2. Create a folder, clone project and navigate to folder containing the Dockerfile

    git clone https://github.com/Agile-IoT/agile-cryptdb-backend.git

##### 3. Build docker image

    sudo docker build -t agile-cryptdb-backend .

##### 4. Run docker container based built image

    sudo docker run -d --name agile-cryptdb-backend -p 3306:3306 agile-cryptdb-backend

### To use the image in a stack, add the following to docker-compose.yml

    agile-cryptdb-backend:
      container_name: agile-cryptdb-backend
      hostname: agile-cryptdb-backend
      image: agile-cryptdb-backend
      restart: always
      ports:
        - 3306:3306/tcp
      environment:
        MYSQL_ROOT_PASSWORD: root
      volumes:
        - $DATA/agile-cryptdb-backend:/var/lib/mysql
