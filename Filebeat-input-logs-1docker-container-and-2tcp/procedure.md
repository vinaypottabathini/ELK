
Purposes :

		* discover another inputs

------------------------------------------------------------------

* list of inputs

```
    Azure eventhub
    Cloud Foundry
    Container
    Docker
    Google Pub/Sub
    HTTP JSON
    Kafka
    Log
    MQTT
    NetFlow
    Office 365 Management Activity API
    Redis
    s3
    Stdin
    Syslog
    TCP
    UDP
```

------------------------------------------------------------------


* docker example

```
  curl -fsSL https://get.docker.com -o get-docker.sh 2>&1 >/dev/null
  sudo sh get-docker.sh 2>&1 >/dev/null
  sudo usermod -aG docker vagrant
```

```
- type: container
  enabled: true
  paths:
    - '/var/lib/docker/containers/*/*.log'
```

Documentation :
https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-input-container.html

------------------------------------------------------------------


* TCP input

```
filebeat.inputs:
- type: tcp
  max_message_size: 10MiB
  host: "localhost:9000"
```


sudo netstat -ntaup
nc
echo "message text writing or field1 field2 field3" | nc ip_address 9000


Documentation :
https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-input-tcp.html

* send data

```
 echo "vinay pottabathini elk developer" |nc 192.168.16.42 9000
```
