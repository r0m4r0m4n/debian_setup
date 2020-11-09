# Setup VM for Docker via VMBox and Vagrant
```
mkdir VirtualMachine
cd VirtualMachine
```
via Vagrant:
```
vagrant init debian/buster64
vagrant up
```
Login into virtual OS:
```
sudo apt-get update | sudo apt-get upgrade -y
adduser docker
usermod -aG sudo docker
su docker
sudo apt-get install -y fish vim git curl wget unzip zip
```
## Configure SSH-connection:
Enable login from remote hosts to upload ssh-key:

`sudo vim /etc/ssh/sshd_config` \
`PasswordAuthentication yes`
    
Complete follow commands `ssh-keygen => ssh-copy-id` from remote host.\
For closing root and password access in file `sshd_config` type:
```
AllowUsers docker
PermitRootLogin no
PasswordAuthentication no
```
and then restart: \
`sudo service ssh restart`
