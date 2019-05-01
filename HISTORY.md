## Operation


### History

* 2019/09/05 (Tue):
```
$ docker version
Client:
 Version:           18.09.5
 API version:       1.39
 Go version:        go1.10.8
 Git commit:        e8ff056
 Built:             Thu Apr 11 04:43:57 2019
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.5
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.8
  Git commit:       e8ff056
  Built:            Thu Apr 11 04:10:53 2019
  OS/Arch:          linux/amd64
  Experimental:     false

$ systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Wed 2019-05-01 12:34:00 KST; 1h 18min ago
     Docs: https://docs.docker.com
 Main PID: 14737 (dockerd)
    Tasks: 14
   CGroup: /system.slice/docker.service
           └─14737 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```
    - clean the old docker and reinstall a new one
```
# clean the existing installation at first
$ sudo rm -rf /var/lib/docker /etc/docker
$ sudo rm -f /etc/apt/source.list.d/docker*
$ sudo apt purge docker-ce docker-ce-cli containerd.io

# re-install the docker
$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
$ sudo usermod -aG docker <your-user>
$ apt-cache madison docker-ce
$ sudo docker run hello-world
```
    - docker-ce failed to start after update


