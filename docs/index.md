# Running Apache Airflow in Docker

# Prerequisites

* Python version > 3.6
* Install Docker and Docker-Compose

## Step 1

* Docker Engine need to have atleast 4GB memory (ideally 8GB)
* check if you have enough memory by running command
```bash
docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'
```

## Step 2

Download Docker Compose yaml file to deploy airflow on docker compose
```bash
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.3.3/docker-compose.yaml'
```

## Step 3

Create dags, logs and plugins folder inside the project directory
```bash
mkdir ./dags ./logs ./plugins
```

Only for Linux Users
```bash
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

## Step 4

Initialize the database
```bash
docker-compose up airflow-init
```

check the running containers
```bash
docker ps
```

## Step 5

Launch airflow by docker-compose
```bash
docker-compose up -d
```

## Step 6

Open browser and type [http://0.0.0.0:8080](http://0.0.0.0:8080) to launch the airflow webserver
[](https://github.com/Harshavardhan1005/Airflow_Docker/blob/main/img/airflow.png)


To Stop all the running containers
```bash
docker-compose down -v
```

