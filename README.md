docker-elk
=============

Run Kibana, ElasticSearch, Logstash, and Ngnix in Docker.

This fork is customized to parse non-gziped opush logs

1) Clone this repository
2) Build the image: docker build -t elk-opush:1.4.2 .
3) Put your opush logs into a folder, for exemple /tmp/opush_logs_prod
4) Run the container

docker run --rm -ti --name opush-elk-instance -p 80:80 -p 9200:9200 -v /tmp/opush_logs_prod:/opush elk-opush:1.4.2

Warn: logstash can be long to parse each log file, you can see how it the progress at http://localhost:9200/_plugin/head/

5) You can now get on Kibana at http://localhost/index.html#/dashboard/file/logstash.json 
