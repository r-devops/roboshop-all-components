# User Service

This service is responsible for User Logins and Registrations Service in RobotShop e-commerce portal.

This service is written in NodeJS, Hence need to install NodeJS in the system.


```
# yum install nodejs make gcc-c++ -y 
```

Let's now set up the User application.

As part of operating system standards, we run all the applications and databases as a normal user but not with root user.

So to run the User service we choose to run as a normal user and that user name should be more relevant to the project. Hence we will use `roboshop` as the username to run the service.

```
# useradd roboshop
```

So let's switch to the `roboshop` user and run the following commands.

```
$ curl -s -L -o /tmp/user.zip "https://github.com/roboshop-devops-project/user/archive/main.zip"
$ cd /home/roboshop
$ unzip /tmp/user.zip
$ mv user-main user
$ cd /home/roboshop/user
$ npm install 
```


Now, lets set up the service with systemctl.

```
# mv /home/roboshop/user/systemd.service /etc/systemd/system/user.service
# systemctl daemon-reload
# systemctl start user
# systemctl enable user
```


