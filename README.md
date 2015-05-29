# elasticsearch cluster

make elasticsearch cluster in local machine

## clone and make ssh.config

```
git clone git@github.com:tky/elasticsearch-vagrant.git  
cd elasticsearch-vagrant
vi ssh.config  

Host web1
  HostName 127.0.0.1
  User vagrant
  Port 2003
  UserKnownHostsFile /dev/null
  StrictHostKeyChecking no
  PasswordAuthentication no
  # IdentityFile /Users/tky/.vagrant.d/insecure_private_key
  IdentityFile {{ YOUR VAGRANT KEY }}
  IdentitiesOnly yes
  LogLevel FATAL

Host web2
  HostName 127.0.0.1
  User vagrant
  Port 2004
  UserKnownHostsFile /dev/null
  StrictHostKeyChecking no
  PasswordAuthentication no
  # IdentityFile /Users/tky/.vagrant.d/insecure_private_key
  IdentityFile {{ YOUR VAGRANT KEY }}
  IdentitiesOnly yes
  LogLevel FATAL
```

##  Vagrant
```
vagrant up
```
## execute ansible
```
ansible-playbook es.yml
```

## see head plugin
http://192.168.33.11:9200/_plugin/head/

## MIGRATE
```
ansible-playbook migrate.yml
```
detail

- make snapshot
- sotp allocation
- stop node
- deploy new elasticsearch 
- start new version.
