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
- Installing Flask
- Installing ElasticSearch
- Install DBeaver 6.1.0

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

```
wget https://dl.google.com/go/go1.13.4.linux-amd64.tar.gz
sudo tar -xvf go1.13.4.linux-amd64.tar.gz
sudo mv go /usr/local
```
Configure golang environment

```
~/.profile

export GOROOT=/usr/local/go
export GOPATH=$HOME/Projects/Golang # Por ejemplo
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```


## Installing conda

Download installer from www.anaconda.com/distribution

```
bash Anaconda3-2019.03-Linux-x86_64.sh
```

## Installing spyder

Spyder comes with Anaconda, launch conda and then `anaconda-navigator` in terminal

## Installing PostgreSQL

```
sudo apt install postgresql postgresql-contrib postgresql-10-postgis-2.4
```
We need to edit `pg_hba.conf` and `postgres.conf`

```
# Database administrative login by Unix domain socket
local   all             postgres                                peer

# TYPE  DATABASE        USER            ADDRESS                 METHOD

# "local" is for Unix domain socket connections only
local   all             all                                     peer
# IPv4 local connections:
host    all             all             0.0.0.0/0               md5
# IPv6 local connections:
host    all             all             ::1/128                 md5
# Allow replication connections from localhost, by a user with the
# replication privilege.
local   replication     all                                     peer
host    replication     all             127.0.0.1/32            md5
host    replication     all             ::1/128                 md5
```

## Installing MySQL

```
sudo apt install mysql-server
sudo mysql_secure_installation
```

## Installing and configuring git

```
sudo apt install git
git config --global user.name "myname"
git config --global user.email "myemail"
```

## Installing Flask

## Installing ElasticSearch

```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update && sudo apt-get install elasticsearch
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service
```

Configuration

Check the following file and put the same names in the bootstrap options

```
/etc/elasticsearch/elasticsearch.yml

network.host: 0.0.0.0
cluster.name: myCluster1
node.name: "myNode1"
```

## Install DBeaver 6.1.0

We use this version as it is the last to support dummy data generation

download deb file from: https://github.com/dbeaver/dbeaver/releases/tag/6.1.0
Install with software installer

## Author

Otto Hahn Herrera
