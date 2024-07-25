# Base requirements

## Docker
TODO: add traefik config in compose file too (or maybe provide one without it)

```
services:
  mosquitto:
    image: eclipse-mosquitto:latest
    container_name: mosquitto
    restart: always
    ports:
      - "1883:1883"
    volumes:
      - mosquitto_data:/mosquitto/data
      - mosquitto_logs:/mosquitto/log
      - ./config:/mosquitto/config
    command: mosquitto -c /mosquitto/config/mosquitto.conf
    networks:
      - iot

  telegraf:
    image: telegraf:latest
    container_name: telegraf
    restart: always
    volumes:
      - ./telegraf.conf:/etc/telegraf/telegraf.conf:ro
    networks:
      - iot
    depends_on:
      - mosquitto
      - influxdb

  influxdb:
    image: influxdb:latest
    restart: always
    container_name: influxdb
    volumes:
      - influxdb_data:/var/lib/influxdb2
      - influxdb_config:/etc/influxdb2
    networks:
      - iot
      - back-tier
    labels:
      - "traefik.enable=true"
      - "traefik.docker.network=traefik"
      - "traefik.frontend.rule=Host:<your.influxdb.host>"
      - "traefik.port=8086"
    environment:
      - DOCKER_INFLUXDB_INIT_MODE=setup
      - DOCKER_INFLUXDB_INIT_USERNAME=admin
      - DOCKER_INFLUXDB_INIT_PASSWORD=<your-password>
      - DOCKER_INFLUXDB_INIT_ORG=ludi
      - DOCKER_INFLUXDB_INIT_BUCKET=mqtt
      - DOCKER_INFLUXDB_INIT_ADMIN_TOKEN=<your-admin-token>

  grafana:
    image: grafana/grafana
    container_name: grafana
    restart: always
    labels:
      - "traefik.enable=true"
      - "traefik.docker.network=traefik"
      - "traefik.frontend.rule=Host:<your.grafana.host>"
      - "traefik.port=3000"
    networks:
      - iot
      - back-tier
    volumes:
      - ./grafana-provisioning:/etc/grafana/provisioning
      - grafana-data:/var/lib/grafana
    environment:
      GF_SECURITY_ADMIN_PASSWORD: <your-admin-password>
    depends_on:
      - influxdb
    
  node-red:
    image: nodered/node-red:latest
    container_name: node-red
    restart: always
    ports:
      - "1880:1880"
    volumes:
      - node_red_data:/data
    networks:
      - iot
      - back-tier
    labels:
      - "traefik.enable=true"
      - "traefik.docker.network=traefik"
      - "traefik.frontend.rule=Host:<your.node-red.host>"
      - "traefik.port=1880"
      - "traefik.frontend.entryPoints=https"
      - "traefik.frontend.redirect.entryPoint=https"
      - "traefik.frontend.redirect.permanent=true"
    environment:
      - TZ=Europe/Vienna

networks:
  iot:
  back-tier:
    external:
      name: traefik

volumes:
  mosquitto_data:
  mosquitto_logs:
  influxdb_data:
  influxdb_config:
  grafana-data:
  node_red_data:
```