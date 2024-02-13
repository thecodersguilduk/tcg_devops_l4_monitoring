# The Coders Guild
## DevOps L4 Monitoring Prometheus Demo

A small demo using containers to demonstrate Prometheus and Grafana basics.


## Usage
Ensure you have Docker/Rancher/Podman or something similar and Docker Compose installed.
  - `docker-compose up` will launch the lab after downloading the three containers.
  - Look at the 'Exploring' steps below
  - 'docker-compose down' will then shut everything down *(you may need to CTRL+C to exit the running state first)*


## Exploring
You have just launched 4 containers!

1) 2x Node Exporter
    These Node Exporter containers expose lots of system metrics for us to experiment with, you can read more about them here: https://hub.docker.com/r/prom/node-exporter.
    In the real world these would be our servers, containers or functions running our production code and apps.

2) Prometheus (http://localhost:9090/)
    - Click 'Service'
        - Click 'Service Discovery' and have a look at the discovered details for the Node Exporter containers
    - Click 'Graph' 
        - Click the little icon that looks like a globe, next to the 'Execute' button.
        - Select one of the exposed metrics, like 'node_load1' 
        - Click 'Execute'. 
    - Have a look at the other metrics our Node Exporters are exporting.

3) Grafana (http://localhost:3000) 
    We will use Grafana to explore our collected metrics from the Prometheus datasourve
    - log in with username 'admin' & password 'admin', set a new password or click 'skip'
    - By default we've already configured the datasource to use our Prometheus service
    - Under 'Dashboards',
    - Select 'Node Exporter Full'
        - Grafana user 'rfmoz' kindly created this dashhboard for demonstrating the Grafana with the Node_Exporter containers and Prometheus, more information can be found here https://grafana.com/grafana/dashboards/1860-node-exporter-full/
