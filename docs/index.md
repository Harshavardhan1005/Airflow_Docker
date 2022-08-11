# Running Apache Airflow in Docker

## step 1

Docker Engine need to have atleast 4GB memory (ideally 8GB)
check if you have enough memory by running command
```bash
docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'
```


## step 2

Download Docker Compose yaml file to deploy airflow on docker compose
```bash
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.3.3/docker-compose.yaml'
```

## step 3

Create dags, logs and plugins folder inside the project directory
```bash
mkdir ./dags ./logs ./plugins
```

## step 4

Initialize the database
```bash
docker-compose up airflow-init
```

check the running containers
```bash
docker ps
```

## step 5

Launch airflow by docker-compose
```bash
docker-compose up -d
```

## step 6

Open browser and type (http://0.0.0.0:8080) to launch the airflow webserver

