# ubuntu-vm

A repo for holding ubuntu configs and scripts to setup a development and data science machine

## Contents

- VM Settings
- Installing SSH
- Installing golang
- Installing conda
- Installing spyder
- Installing PostgreSQL
- Installing MySQL
- Installing and configuring git
- Installing DBeaver
- Installing Flask
- Installing ElasticSearch
- Migrating databases and code to VM

## VM Settings

Hardware:

- 1CPU
- 8 Gb RAM
- 100 Gb HD

Software:

OS: Ubuntu 18.04

Network:

- NAT
- Port forwarding rules:

Rule name | Protocol | Host Port | Host IP | Guest Port | Guest IP
----------|----------|-----------|---------|------------|---------
HTTP      | TCP      | 8080      | 127.0.0.1 | 80       | 10.0.2.15
Flask     | TCP      | 5050      | 127.0.0.1 | 5000     | 10.0.2.15
Postgres  | TCP      | 5433      | 127.0.0.1 | 5432     | 10.0.2.15    
MySQL     | TCP      | 3307      | 127.0.0.1 | 3306     | 10.0.2.15
Elastic   | TCP      | 9292      | 127.0.0.1 | 9200     | 10.0.2.15

## Installing SSH

```
sudo apt install openssh-server
```

## Installing golang

## Installing conda

## Installing spyder

## Installing PostgreSQL

## Installing MySQL

## Installing and configuring git

## Installing DBeaver

## Installing Flask

## Installing ElasticSearch

## Migrating databases and code to VM

## Author

Otto Hahn Herrera
