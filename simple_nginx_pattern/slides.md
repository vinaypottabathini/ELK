



<br>

Purposes :

		* install nginx

		* add grok pattern

		* set logstash configuration

		* check in elasticsearch in kibana

-------------------------------------------------------------



<br>

* install a local nginx (just an example)

```
sudo apt install nginx
sudo usermod -aG adm logstash
```

-------------------------------------------------------------



<br>

* add a grok pattern (help to parse logs)

```
mkdir /etc/logstash/pattern
chmod 755 -R /etc/logstash/pattern
cat /etc/logstash/pattern/nginx
NGUSERNAME [a-zA-Z\.\@\-\+_%]+
NGUSER %{NGUSERNAME}
```

-------------------------------------------------------------

<br>


