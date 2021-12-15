# About swarmpit   
[![Publish levell swarmpit docker image](https://github.com/jimmylevell/swarmpit/actions/workflows/action.yml/badge.svg)](https://github.com/jimmylevell/swarmpit/actions/workflows/action.yml)  

Swarmpit container of levell.  
Provides web interface for managing the docker swarm.  

## Frameworks used
- Swarmpit 

# Docker image details 
## Swarm pit
Base image: swarmpit/swarmpit:latest

## DB
Base image: couchdb:2.3.0     # this version is required by swarmpit   
Exposed ports: 5984  

## Influx DB
Base image: influxdb:1.7  
Exposed ports: 8086  

## Swarm agent
Base image: swarmpit/agent:latest  

# Deployment
## General
Service: swarmpit  
Data Path: /home/docker/levell/swarmpit/  
Access URL: swarmpit.app.levell.nl  

## Attached Networks
- traefik-public - access to reverse proxy
- levell - access to levell services

## Attached volumes
swarmpit-db-data: database data  
swarmpit-influx-data: influx data  

## Environment variables 
SWARMPIT_DB: URL for database access  
SWARMPIT_INFLUXDB: URL for influx DB access  
DOCKER_API_VERSION: Docker API version (docker version)  

# Authentication
Local  
- admin@levell.nl
