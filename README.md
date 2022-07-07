## First Airflow DAG: Data ingestion pipeline



https://airflow.apache.org/docs/apache-airflow/stable/start/index.html

https://airflow.apache.org/docs/apache-airflow/stable/security/access-control.html



1. Prepare the database first `docker-compose up airflow-init`

This is going to created db/airflow.db sqlite database

2. Add raw data for current execution date and hour to be ingested

3. - Launch Airflow `docker-compose up`

Wait for scheduler and webserver to get healthy, then go to `localhost:8081` 

```python
username: admin
password: airflow
```

4. Enable the DAG and watch it ingest data.

Other commands
If you want to run airflow sub-commands, you can do so like this:

sudo docker-compose run --rm airflow-webserver airflow dags list  - List dags

sudo docker-compose run --rm airflow-webserver  airflow test [DAG_ID] [TASK_ID] [EXECUTION_DATE] - Test specific task

If you want to run/test python script, you can do so like this:

sudo docker-compose run --rm airflow-webserver  python /usr/local/airflow/dags/[PYTHON-FILE].py - Test python script
