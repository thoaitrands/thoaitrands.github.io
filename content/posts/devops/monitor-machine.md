---
title: "How to monitoring all machines ?"
date: 2022-05-19T12:13:32+05:30
description: "Grafana, Influxdb2, Telegraf"
tags: [Grafana, Influxdb2, Telegraf]
---

## Mornitoring

## Grafana - Influxdb2 - Telegraf

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

4: Run docker-compose inmornitoring folder. ***If you already have influxdb server, you just install telegraf server***

    docker-compose up telegraf 

telegraf is a service name of docker-compose.
