# Jenkins-Labs

## Lab#2

1. configure jenkins image to run docker commands on your hos docker daemon

```
touch Dockerfil
vi Dockerfile
```

```
docker image build . -t jenkins-docker
```

```
docker run -it -d -p 8083:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock -v jenkins_home:/var/jenkins_home jenkins-docker

```

```
docker ps -a
```
OUTPUT
```
CONTAINER ID   IMAGE            COMMAND                  CREATED          STATUS          PORTS                                                                                      NAMES
f62d2bdc236f   jenkins-docker   "/usr/bin/tini -- /u…"   28 seconds ago   Up 21 seconds   0.0.0.0:50000->50000/tcp, :::50000->50000/tcp, 0.0.0.0:8083->8080/tcp, :::8083->8080/tcp   priceless_cori

```

```bash
# docker exec -it f62d2bdc236f bash 
docker exec -it [containerID] bash
docker ps -a

```



---------------------------------------------------------------------------------------------------

2. create CI/CD for this repo https://github.com/mahmoud254/jenkins_nodejs_example.git









----------------------------------------------------------------------------------

3. create docker file to build image for jenkins slave and create container from this image and configure ssh

```
touch Dockerfile
vi Dockerfile
```

```
toush docker-compose.yml
vi docker-compose.yml
```

```
docker-compose up
```
```
docker-compose ps
```
OUTPUT
```

    Name         Command    State    Ports
------------------------------------------
slave-jenkins   /bin/bash   Exit 0        

```

```bash

# docker exec -it bf83f9cd9c70 bash
docker exec -it [containerID] bash
ssh-keygen
cd ./.ssh
cp id_rsa.pub authorized-keys

```
4. from jenkins master create new node with the slave container



5. integrate slack with jenkins



6. send slack message when stage in your pipeline is successful



7. install audit logs plugin and test it




8. fork the following repo https://github.com/mahmoud254/Booster_CI_CD_Project and add dockerfile to run this django app and use github actions to build the docker image and push it to your dockerhub



9. Create infrastructure pipeline to run terraform with jenkins task
