# Cart Service

This service is responsible for Cart Service in  RobotShop e-commerce portal.

This service is written in NodeJS, Hence need to install NodeJS in the system.

```
# yum install nodejs make gcc-c++ -y 
```

Let's now set up the cart application.

As part of operating system standards, we run all the applications and databases as a normal user but not with root user.

So to run the cart service we choose to run as a normal user and that user name should be more relevant to the project. Hence we will use `roboshop` as the username to run the service.

```
# useradd roboshop
```

So let's switch to the `roboshop` user and run the following commands.

```
$ curl -s -L -o /tmp/cart.zip "https://github.com/roboshop-devops-project/cart/archive/main.zip"
$ cd /home/roboshop
$ unzip /tmp/cart.zip
$ mv cart-main cart
$ cd cart
$ npm install 
```

Now, lets set up the service with systemctl.

```
# mv /home/roboshop/cart/systemd.service /etc/systemd/system/cart.service
# systemctl daemon-reload
# systemctl start cart
# systemctl enable cart
```


