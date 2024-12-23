# Basic operation 

## Description 

In this task we have install and configured redis and see how we can use it for caching.

## Install Redis

```bash
sudo apt update
sudo apt install redis-server
```

## Configure Redis

```bash
sudo nano /etc/redis/redis.conf
```

In this file change add this and restart redis service
```bash
supervised systemd
sudo systemctl restart redis
sudo systemctl status redis
```
## store and test 

```bash
redis-cli
set test "It's working!"
get test
exit
sudo systemctl restart redis
redis-cli
get test
```


