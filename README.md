# learning-prometheus
This example for how to use Prometheus and Grafana . It first step for learn

#Start Grafana
First step start service Grafana with docker run

```sh
docker run -d \
  -p 3000:3000 \
  --name=grafana \
  -e "GF_SERVER_ROOT_URL=http://grafana.server.name" \
  -e "GF_SECURITY_ADMIN_PASSWORD=secret" \
  grafana/grafana
```

#Start Prometheus
Second step start service Prometheus with docker run and use prometheus.yml

```sh
docker run -d \
    -p 9090:9090 \
    -v /tmp/prometheus.yml:/etc/prometheus/prometheus.yml \
    prom/prometheus

```

#Setup Node exporter
must install 
1. Go compiler
2. RHEL/CentOS: glibc-static package

if you install you can build node exporter  by
```sh
go get github.com/prometheus/node_exporter
cd ${GOPATH-$HOME/go}/src/github.com/prometheus/node_exporter
make
```
