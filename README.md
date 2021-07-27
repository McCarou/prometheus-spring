# prometheus-spring
Prometheus (running in Docker) collects metrics from Spring Application

Required:
- Installed Docker;
- Intellij IDEA / Eclipse
- Some free time :)

Bulded for MacOS - the string "host.docker.internal:8080" in prometheus.yaml must be replaced on other OS
https://prometheus.io/docs/guides/multi-target-exporter/

To run Prometheus:

0. Clone the project
1. Pull Prometheus Image
```
docker pull prom/prometheus
```
2. Pull Node explorer Image
```
docker pull prom/node-exporter
```
3. Start Prometheus container by cd to the project directory and run
```
docker run \                                      
    -p 9090:9090 \
    -v ./prometheus.yml:/etc/prometheus/prometheus.yml \
    --name prom-prometheus \
    prom/prometheus
```
4. (Optional) Start Node Explorer container by cd to the project directory and run
```
docker run \                                      
    -p 9100:9100 \
    --name prom-node-exporter \
    prom/node-exporter
```
5. Run the project in IDE (TODO: build an image)
6. Run http://localhost:9090 in your browser