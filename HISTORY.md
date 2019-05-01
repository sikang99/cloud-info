


## Operation


### History

* 2019/09/05 (Tue):
    - docker-ce failed to start after installation

```
# clean the existing installation at first
$ sudo apt purge docker-ce docker-ce-cli containerd.io
$ sudo rm -rf /var/lib/docker /etc/docker/*
$ sudo rm -f /etc/apt/source.list.d/docker*
# install a new docker
$ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```


