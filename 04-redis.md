# REDIS

Redis is used for in-memory data storage and allows users to access the data over API.

## Manual Installation of Redis.

1. Install Redis.

```
# yum install epel-release yum-utils -y
# yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y
# yum-config-manager --enable remi
# yum install redis -y
```

2. Update the BindIP from `127.0.0.1` to `0.0.0.0` in config file `/etc/redis.conf` & `/etc/redis/redis.conf`


3. Start Redis Database

```
# systemctl enable redis
# systemctl start redis
```

