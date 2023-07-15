


Purposes :

		* classic way : filebeat -> logstash -> elasticsearch

		* change the logstash configuration 

		* change the filebeat configuration

		* create logs

		* check the elasticsearch index in kibana

------------------------------------------------------------------


* change the filebeat configuration

```
input {
  beats {
    port => 5044
  }
}
```

Note : name the output index as elk_fb-logstash-%{+YYYY.MM.dd}

------------------------------------------------------------------

* change the logstash configuration

```
output.logstash:
  hosts: ["localhost:5044"]
```

# localhost or local ip address both are same
Note : keep the nginx module enabled

------------------------------------------------------------------


* disable the nginx module

```
sudo filebeat modules disable nginx
```

* and add a path where filebeat finds logs

```
filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/nginx/access.log
```

