---
title: "How to monitoring all machines ?"
date: 2022-05-19T12:13:32+05:30
description: "Grafana, Influxdb2, Telegraf"
tags: [Grafana, Influxdb2, Telegraf]
---

## Mornitoring

## Grafana - Influxdb2 - Telegraf

**Telegraf** is an agent responsible for gathering and aggregating data, like the current CPU usage for example.

**InfluxDB** will store data, and expose it to Grafana.

**Grafana** is a modern dashboarding solution.

### Context

                       +-----------------------------+ 
                       |                             | 
                       |                             | 
                       |          GRAFANA            | 
                       |                             | 
                       |                             | 
                       +-------------+---------------+ 
                                     | 
                                     | 
                                     | 
                                     | 
      +------------------------------v--------------------------------+ 
      |                                                               | 
      |                                                               | 
      |                          INFLUXDB v2                          | 
      |                                                               | 
      |                                                               | 
      +---------------------------------------------------------------+ 
                ^                        ^                       ^ 
                |                        |                       | 
                |                        |                       | 
                |                        |                       | 
       +--------+---------+    +---------+--------+     +--------+--------+ 
       |                  |    |                  |     |                 | 
       | +--------------+ |    | +--------------+ |     | +-------------+ | 
       | |              | |    | |              | |     | |             | | 
       | |   TELEGRAF   | |    | |   TELEGRAF   | |     | |  TELEGRAF   | | 
       | +--------------+ |    | +--------------+ |     | +-------------+ | 
       |                  |    |                  |     |                 | 
       +------------------+    +------------------+     +-----------------+ 
             LINUX                    WINDOWS                 CENTOS 
created with *[Asciiflow Guide](https://asciiflow.com/)*.

### How to setup

1: Change the value of variables in .evn file.

    DOCKER_INFLUXDB_INIT_USERNAME= 
    DOCKER_INFLUXDB_INIT_PASSWORD= 
    DOCKER_INFLUXDB_INIT_ORG= 
    DOCKER_INFLUXDB_INIT_BUCKET= 
    DOCKER_INFLUXDB_INIT_ADMIN_TOKEN=

2: Change the value of file ./telegraf/telegraf.conf

    # Override default hostname, if empty use os.Hostname(), hostname of machine you want to collect data. 
    - hostname 
    -  [[outputs.influxdb_v2]] 
        # The URLs of the InfluxDB cluster nodes. 
        urls = ['host-name-of-influxdb'] 
        token = DOCKER_INFLUXDB_INIT_ADMIN_TOKEN 
        organization = DOCKER_INFLUXDB_INIT_ORG 
        bucket = DOCKER_INFLUXDB_INIT_BUCKET 

3: Run docker-compose in mornitoring folder. ***If you don't have influxdb server***

    docker-compose up -d 

4: Run docker-compose in mornitoring folder. ***If you already have influxdb server, you just install telegraf server***

    docker-compose up telegraf 

**telegraf** is a service name of docker-compose.

**Special case**: If you want to install telegraf in Windows server (or your windows can not use docker), please refer this document:  
How to install telegraf in windows server [Click me !](https://github.com/influxdata/telegraf/blob/master/docs/WINDOWS_SERVICE.md).

### Docker-compose

    version: "3.5" 
    services: 
        influxdb2: 
            image: influxdb:latest 
            network_mode: "bridge" 
            container_name: influxdb2 
            ports: 
                - "8086:8086" 
            volumes: 
                - ./influxdbv2/data:/var/lib/influxdb2 
                - ./influxdbv2/config:/etc/influxdb2 
            environment: 
                - DOCKER_INFLUXDB_INIT_MODE=setup 
                - DOCKER_INFLUXDB_INIT_USERNAME=${DOCKER_INFLUXDB_INIT_USERNAME}
                - DOCKER_INFLUXDB_INIT_PASSWORD=${DOCKER_INFLUXDB_INIT_PASSWORD}
                - DOCKER_INFLUXDB_INIT_ORG=${DOCKER_INFLUXDB_INIT_ORG}
                - DOCKER_INFLUXDB_INIT_BUCKET=${DOCKER_INFLUXDB_INIT_BUCKET}
                - DOCKER_INFLUXDB_INIT_RETENTION=1w 
                - DOCKER_INFLUXDB_INIT_ADMIN_TOKEN=${DOCKER_INFLUXDB_INIT_ADMIN_TOKEN}
            restart: always 
        telegraf: 
            image: telegraf:latest 
            network_mode: "bridge" 
            pid: "host" 
            container_name: telegraf 
            ports: 
                - "8092:8092" 
                - "8094:8094" 
                - "8125:8125" 
            volumes: 
                - ./telegraf/telegraf.conf:/etc/telegraf/telegraf.conf:ro 
                - /var/run/docker.sock:/var/run/docker.sock:ro 
                - /sys:/host/sys:ro 
                - /proc:/host/proc:ro 
                - /etc:/host/etc:ro 
            environment: 
                - HOST_PROC=/host/proc 
                - HOST_SYS=/host/sys 
                - HOST_ETC=/host/etc 
            restart: always

### Docker-compose for Grafana8

    version: "3.5"
    services:
        grafana8:
            image: grafana/grafana:latest
            container_name: grafana8
            volumes:
            - ./data:/var/lib/grafana
            ports:
            - "3000:3000"
            restart: always

