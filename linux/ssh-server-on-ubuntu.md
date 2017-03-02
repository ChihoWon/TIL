# ssh server on ubuntu

I write this note because i need to run ssh server on ubuntu.  
Well, running ssh server on laptop might be dangerous.    
anyway, let's find out how to run ssh on ubuntu!  

First, you need to check your local system with `dkpg` command.  

```sh
$ dpkg -l | grep ssh
ii  libssh-4:amd64   0.6.3-4.3   amd64   tiny C SSH library (OpenSSL flavor)
ii  libssh-gcrypt-4:amd64   0.6.3-4.3   amd64   tiny C SSH library (gcrypt flavor)
ii  openssh-client   1:7.2p2-4ubuntu2.1   amd64   secure shell (SSH) client
$
```

No ssh server found on this system. so you should install ssh server with `apt-get`.

```sh
$ sudo apt-get install -y openssh-server
```  

Fine. Make sure port 22 is open and check what services are running on this system.

```sh
$ netstat -ntl | grep 22
tcp        0      0 0.0.0.0:22    0.0.0.0:*               LISTEN     
tcp6      0      0 :::22             :::*                        LISTEN
$
```

check ssh service.

```sh
$ sudo service --status-all | grep ssh
[ + ]  ssh
$
```

Cool. it's done.   
if you want to make sure, restart your service.  

```sh
$ sudo service ssh restart
$ sudo service ssh status
● ssh.service - OpenBSD Secure Shell server
   Loaded: loaded (/lib/systemd/system/ssh.service; enabled; vendor preset: enabled)
   Active: active (running) since 수 2016-08-24 13:42:01 KST; 5s ago
 Main PID: 9579 (sshd)
    Tasks: 1
   Memory: 732.0K
      CPU: 34ms
   CGroup: /system.slice/ssh.service
           └─9579 /usr/sbin/sshd -D

 8월 24 13:42:01 naglfar systemd[1]: Starting OpenBSD Secure Shell server...
 8월 24 13:42:01 naglfar sshd[9579]: Server listening on 0.0.0.0 port 22.
 8월 24 13:42:01 naglfar sshd[9579]: Server listening on :: port 22.
 8월 24 13:42:01 naglfar systemd[1]: Started OpenBSD Secure Shell server.
```
