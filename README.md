# elasticsearch cluster

make elasticsearch cluster in local machine

##  Vagrant
```
$vagrant up
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
- make snapshotの
- sotp allocation
- stop node
- deploy new elasticsearch 
- start new version.
