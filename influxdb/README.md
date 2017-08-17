# gatling-docker

docker build -t ngammoudi/influxdb:1.0 .
sudo docker run -d -p 8083:8083 -p 8086:8086 -e PRE_CREATE_DB="gatling;jmxTrans"  ngammoudi/influxdb:1.0