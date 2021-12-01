# RabbitMQ Installation

RabbitMQ is a messaging Queue which is used by some components of the applications.

## Manual Installation

1. Erlang is a dependency which is needed for RabbitMQ.

```
# yum install https://github.com/rabbitmq/erlan g-rpm/releases/download/v23.2.6/erlang-23.2.6-1.el7.x86_64.rpm -y 
```

2. Setup YUM repositories for RabbitMQ.

```
# curl -s https://packagecloud.io/install/repositories/rabbitmq/rabbitmq-server/script.rpm.sh | sudo bash
```

3. Install RabbitMQ

```
# yum install rabbitmq-server -y 
```

4. Start RabbitMQ

```
# systemctl enable rabbitmq-server 
# systemctl start rabbitmq-server 
```

RabbitMQ comes with a default username / password as `guest`/`guest`. But this user cannot be used to connect. Hence we need to create one user for the application.

5. Create application user

```
# rabbitmqctl add_user roboshop roboshop123
# rabbitmqctl set_user_tags roboshop administrator
# rabbitmqctl set_permissions -p / roboshop ".*" ".*" ".*"
```

Ref link : https://www.rabbitmq.com/rabbitmqctl.8.html#User_Management

