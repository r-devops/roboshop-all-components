# Payment Service

This service is responsible for payments in RoboShop e-commerce app.

This service is written on `Python 3`, So need it to run this app.

CentOS 7 comes with `Python 2` by default. So we need `Python 3` to be installed.

1. Install Python 3

```
# yum install python36 gcc python3-devel -y
```

2. Create a user for running the application

```
# useradd roboshop
```

3. Download the repo.

```
$ cd /home/roboshop
$ curl -L -s -o /tmp/payment.zip "https://github.com/roboshop-devops-project/payment/archive/main.zip"
$ unzip /tmp/payment.zip
$ mv payment-main payment
$ cd payment
```

4. Install the dependencies

```
# cd /home/roboshop/payment 
# pip3 install -r requirements.txt
```

**Note: Above command may fail with permission denied, So run as root user**

5. Update the roboshop user and group id in `payment.ini` file.

6. Setup the service

```
# mv /home/roboshop/payment/systemd.service /etc/systemd/system/payment.service
# systemctl daemon-reload
# systemctl enable payment 
# systemctl start payment
```
