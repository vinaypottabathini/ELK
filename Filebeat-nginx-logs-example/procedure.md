


Purposes :

	* change elasticsearch configuration

	* install nginx

	* check the elasticsearch index in kibana

------------------------------------------------------------------




* filebeat - beats family (metricbeat, heartbeat...)

* filebeat - send logs directly in elasticsearch

* without log transformation

* better in this case > lighter than logstash

------------------------------------------------------------------


* installation of filebeat

```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.8.2-linux-x86_64.tar.gz
tar xzvf filebeat-8.8.2-linux-x86_64.tar.gz
sudo apt-get update
sudo apt-get install filebeat
```

------------------------------------------------------------------



* change listen IP and seed_discovery on elasticsearch

```
network.host: 0.0.0.0
discovery.seed_hosts: ["127.0.0.1"]
sudo systemctl restart elasticsearch
```

* set the elasticsearch IP in /etc/filebeat/filebeat.yml

------------------------------------------------------------------


* install nginx

```
sudo apt install nginx
```



* activate the nginx module

```
sudo filebeat modules list
ls /etc/filebeat/modules.d/
sudo filebeat modules enable nginx
sudo systemctl restart filebeat
```

* Test it in KIbana  -- filebeat-* datastream should be there
