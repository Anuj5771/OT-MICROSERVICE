

## Step:1 git clone repository 
```bash
 git clone https://github.com/OT-MICROSERVICES/employee-api.git
 cd employee-api/
```


## Step:2  Install Golang
```bash
 sudo apt update
 sudo apt install golang-go
 go version
```

## Step:3   Install Make
```bash
 sudo apt update
 sudo apt install make

```
## Step:4 . Install jq 
```bash
sudo apt install -y jq

```
 
## step:5  install ScyllaDB
```bash
sudo mkdir -p /etc/apt/keyrings
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys a43e06657bac99e3
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.2.list
sudo apt-get update
sudo apt-get install -y scylla


```


## step:6 To configure ScyllaDB

```bash
 - seeds: <private_ip>
- listen_address: <private_ip>
- rpc_address: <private_ip>
 
```

## step:7 Cassandra login scyllaDB
```bash
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer

```


## step:8  configuration file 

```bash
 vi config.yml <private ip>
```





## step:9 configuring ScyllaDB I/O settings
```bash
sudo /opt/scylladb/scripts/scylla_io_setup
sudo systemctl start scylla-server
cqlsh 172.31.44.148 -u cassandra -p cassandra
```



## step:10 cassandra login 
```bash
 CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
 CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };


```

## step:11 Redis Installation
```bash
sudo apt-get install lsb-release curl gpg
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg
sudo chmod 644 /usr/share/keyrings/redis-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list
sudo apt-get update
sudo apt-get install redis
sudo systemctl enable redis-server
sudo systemctl start redis-server


```
## step:12 Redis cli configure
```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
```


## step:13 Update the Redis configuration file (
```bash
Update the Redis configuration file (/etc/redis/redis.conf) to bind to the private
```
## Step:14 Install migrate Tool
```bash
  curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
  sudo mv migrate /usr/local/bin/migrate
  migrate --version

```

## Step:15 Run Database Migrations
```bash
vi migration.json <private ip>
make run-migrations

```


## Step:16 Test the Application
```bash
 go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```
## Step:17 configuration the main.go files
```bash
 sudo vi nano main.go
```
## Step:18 Test the Application
```bash
go run main.go
```
## Step:19 Test the Application
```bash

 http://public ip:8081/swagger/index.html
```

## Authors


| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
|Anuj yadav |anuj.yadav@mygurukulam.co |  anuj169  | https://github.com/anuj169
