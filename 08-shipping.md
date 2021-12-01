# Shipping Service.

Shipping service is responsible for finding the distance of the package to be shipped and calculate the price based on that.

Shipping service is written in Java, Hence we need to install Java.

1. Install Maven, This will install Java too

```
# yum install maven -y
```

2. As per the standard process, we always run the applications as a normal user.

Create a user

```
# useradd roboshop
```

3. Download the repo

```
$ cd /home/roboshop
$ curl -s -L -o /tmp/shipping.zip "https://github.com/roboshop-devops-project/shipping/archive/main.zip"
$ unzip /tmp/shipping.zip
$ mv shipping-main shipping
$ cd shipping
$ mvn clean package 
$ mv target/shipping-1.0.jar shipping.jar 
```

4. Update Servers IP address in `/home/roboshop/shipping/systemd.service`

5. Copy the service file and start the service.

```
# mv /home/roboshop/shipping/systemd.service /etc/systemd/system/shipping.service
# systemctl daemon-reload
# systemctl start shipping 
# systemctl enable shipping
```

