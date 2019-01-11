![alt text](diagram.png "Diagram")


## Install JAVA

```bash
 yum install java-1.8.0-openjdk
```

## Install ElasticSearch

```bash
 rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
 rpm -i https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.2.3.rpm
```

### Enable elasticSearch

```bash
 systemctl daemon-reload
 systemctl enable elasticsearch
 systemctl start elasticsearch
```

## Install Kibana

```bash
 rpm -i https://artifacts.elastic.co/downloads/kibana/kibana-6.2.3-x86_64.rpm
```

### Enable Kibana

```bash
 systemctl enable kibana
 systemctl start kibana
```



## Install FileBeat

```bash
 rpm -i https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-6.2.3-x86_64.rpm
 vim /etc/filebeat/modules.d/system.yml.disabled 
 filebeat modules enable system
 /usr/share/elasticsearch/bin/elasticsearch-plugin install ingest-geoip
```

```bash
 systemctl restart elasticsearch
```

### Enable Kibana
```bash
filebeat setup
systemctl enable filebeat
systemctl start filebeat
```
