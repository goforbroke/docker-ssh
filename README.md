# docker-ssh
SSH server in docker for ansible sandbox.

## requirement

- Docker: 20.10
- Ansible: 2.10

## build

```
$ docker-compose build --build-arg PASSWD=<Password>
```

## start

```
$ docker-compose up -d
$ ssh -p 2222 root@localhost uptime
12:03:33 up  1:06,  0 users,  load average: 0.03, 0.33, 0.21
```

After setup hosts.yaml, ansible can tests.

```
$ ansible -i hosts.yml observer -m command -a "uptime" -k
SSH password:
xxxx | CHANGED | rc=0 >>
 12:07:41 up  1:10,  1 user,  load average: 0.00, 0.14, 0.15
 ```