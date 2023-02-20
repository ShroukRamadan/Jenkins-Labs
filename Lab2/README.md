# Jenkins-Labs

#### jenkinsfiles and dockerfiles are used in this lab will be found in this repo

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

![Screenshot from 2023-02-08 18-45-18](https://user-images.githubusercontent.com/57557314/217702115-811c44b8-ac24-4638-8a85-19f11c5e6476.png)


---------------------------------------------------------------------------------------------------

2. create CI/CD for this repo https://github.com/mahmoud254/jenkins_nodejs_example.git


![Screenshot from 2023-02-09 04-30-05](https://user-images.githubusercontent.com/57557314/217702434-a9d96db6-67ff-496d-9073-fb167efd0044.png)


![Screenshot from 2023-02-08 19-48-56](https://user-images.githubusercontent.com/57557314/217702746-cb9dc1ff-5059-4147-b476-2416e47759ff.png)

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

![Screenshot from 2023-02-08 23-45-34](https://user-images.githubusercontent.com/57557314/217702873-76958633-bcba-4ea7-9c89-324a9c5b9021.png)


![Screenshot from 2023-02-08 23-46-01](https://user-images.githubusercontent.com/57557314/217702881-e70fc352-d0ca-44b0-aba8-f65b947f85f5.png)


5. integrate slack with jenkins


![Screenshot from 2023-02-09 01-06-33](https://user-images.githubusercontent.com/57557314/217703251-885aff91-d389-4086-9592-9238a553425c.png)


6. send slack message when stage in your pipeline is successful

![Screenshot from 2023-02-09 04-52-02](https://user-images.githubusercontent.com/57557314/217705589-39262f9c-55fd-4a58-9b0e-a677b2835309.png)


7. install audit logs plugin and test it

![Screenshot from 2023-02-09 04-53-50](https://user-images.githubusercontent.com/57557314/217705816-cf9d3677-1f52-4135-9199-ec0cc6de8fb3.png)



8. fork the following repo https://github.com/mahmoud254/Booster_CI_CD_Project and add dockerfile to run this django app and use github actions to build the docker image and push it to your dockerhub


![Screenshot from 2023-02-09 04-54-27](https://user-images.githubusercontent.com/57557314/217705922-6c384775-1655-45cb-b1c8-8030f8fdfb22.png)

9. Create infrastructure pipeline to run terraform with jenkins task

![Screenshot from 2023-02-09 04-55-03](https://user-images.githubusercontent.com/57557314/217705996-7373496e-fbf7-4a9b-907a-8a46db5bb0cc.png)
