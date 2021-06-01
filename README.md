Update your system: 

```
apt-get update -y
```

Install additional packages

```
apt-get install curl gnupg2 apt-transport-https unzip -y
```

Import the GPG key,

```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add -
```

Add Elasticsearch,

```
sh -c 'echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" > /etc/apt/sources.list.d/elastic-7.x.list'
```

Update the repository cache and install Elasticsearch

```
apt-get update -y
apt-get install elasticsearch -y
```

Start and enable Elasticsearch after installation is complete,

```
systemctl start elasticsearch
systemctl enable elasticsearch
```

Verify it is installed
```
systemctl status elasticsearch
```

Check if port 9200 is open,
```
ss -antpl | grep 9200
```
Or, request to the Elasticsearch server,

```
curl -X GET "localhost:9200/"
```
