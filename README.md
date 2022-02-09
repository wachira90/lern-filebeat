# lern-filebeat
lerning filebeat

## download
````
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-oss-7.15.1-x86_64.rpm

chmod 755 filebeat-oss-7.15.1-x86_64.rpm
rpm -vi filebeat-oss-7.15.1-x86_64.rpm
rpm --import https://packages.elastic.co/GPG-KEY-elasticsearch
rpm -vi filebeat-oss-7.15.1-x86_64.rpm
wget https://packages.elastic.co/GPG-KEY-elasticsearch
````

## check enable module

````

filebeat modules list

[root@server1 ~]#   filebeat modules list
Enabled:
nginx

Disabled:
apache
auditd
elasticsearch
haproxy
icinga
iis
kafka
kibana
logstash
mongodb
mysql
nats
osquery
pensando
postgresql
redis
santa
system
traefik
[root@server1 ~]#
````

## enable module

````
filebeat modules enable system nginx

filebeat modules disable system system
````

## test
````
filebeat test config
````

## file init config `filebeat.yml`

````
filebeat.inputs:
- type: log
  paths:
    - /path/to/file/logstash-tutorial.log 
output.logstash:
  hosts: ["localhost:5044"]
````

## run

````
filebeat -e -c /etc/filebeat/filebeat.yml
````
## get log from
````
tail -f /var/log/nginx/access.log
````

## odbc
````
https://artifacts.elastic.co/downloads/elasticsearch/esodbc-7.17.0-windows-x86_64.msi

https://artifacts.elastic.co/downloads/elasticsearch/esodbc-7.10.1-windows-x86_64.msi
````
