# Jenkins-Labs


## Lab#1

1. install jenkins with docker image

```
docker run -p 8083:8080 -d jenkins/jenkins:lts

```

2. install role based authorization plugin

![Screenshot from 2023-02-03 17-44-50](https://user-images.githubusercontent.com/57557314/216739545-eae13b3c-989d-4eb9-b65a-a3809176b079.png)

3. create new user

![Screenshot from 2023-02-03 17-47-10](https://user-images.githubusercontent.com/57557314/216739555-d869cd39-b30f-4dd7-9f2d-1fd95a3c7dd2.png)

4. create read role and assign it to the new user

![Screenshot from 2023-02-04 03-49-13](https://user-images.githubusercontent.com/57557314/216740105-f8bf8228-11a5-417b-83af-014112d9a213.png)

![Screenshot from 2023-02-04 03-49-32](https://user-images.githubusercontent.com/57557314/216740110-204383ba-4450-49b3-93c1-b1bff8fa173e.png)


5. create free style pipeline and link it to private git repo(inside it create directory and create file with "hello world")


![Screenshot from 2023-02-03 23-42-46](https://user-images.githubusercontent.com/57557314/216739635-77fef602-129f-4799-8b78-74a28638a876.png)


![Screenshot from 2023-02-03 23-43-03](https://user-images.githubusercontent.com/57557314/216739639-b3e11ebe-ff0f-4de6-89b2-e1ba115dc9ed.png)


#################


1. create declarative in jenkins GUI pipeline for your own repo to do "ls"


![Screenshot from 2023-02-03 23-55-48](https://user-images.githubusercontent.com/57557314/216739691-9cdd35a0-7c31-48a7-9358-dff29bcef83e.png)


![Screenshot from 2023-02-03 23-56-27](https://user-images.githubusercontent.com/57557314/216739716-a54ce37e-c10e-4e37-b907-c94582b9696a.png)


2. create scripted in jenkins GUI pipeline for your own repo to do "ls"

![Screenshot from 2023-02-04 00-03-05](https://user-images.githubusercontent.com/57557314/216739746-71a4bc49-ef99-4475-adc2-5077394f4c4f.png)


![Screenshot from 2023-02-04 00-03-42](https://user-images.githubusercontent.com/57557314/216739761-aa350a8c-d755-494f-b83b-435a0b97d4f9.png)

3. create the same with jenkinsfile in your branches as multibranch pipeline

![Screenshot from 2023-02-04 00-14-08](https://user-images.githubusercontent.com/57557314/216739831-0be404df-2580-49c6-9556-93943e174b74.png)


![Screenshot from 2023-02-04 03-51-08](https://user-images.githubusercontent.com/57557314/216740214-08226644-2e74-46b9-9a23-df353bc175a7.png)


![Screenshot from 2023-02-04 03-44-59](https://user-images.githubusercontent.com/57557314/216739906-a3a2f987-1121-45da-b693-249b11203a11.png)
