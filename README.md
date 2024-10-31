# genie-do

"Your wish is my command". A distributed executor service.

> [!WARNING]  
> **This is still under development. Please do not use it with sensitive data for now, please wait for a
stable release.  
> It's mostly ideal for experimental and learning projects.**

**If you can represent your code as a Docker image we will run it. You develop it, we run it.**

# Motivation

This wants to be a `distributed executor` in `k8s` an `orchestrated` with `Apache Airflow`. It can be deployed on any `cloud` provider or `on-prem`.  
If you can represent your `job` as a `Docker` image we will `run` it, `retry` it, `distribute` it, and `much more`. You'll have access to `Kafka`, `S3`, `Aapache Spark` & `Flink`, `PostgreSQL`, `NoSQL`...  
There will be `libs` in `several languages`, `gRPC service` and `REST API` to `manage` the jobs. Everything will be easy for you to run your code.

The idea is to take the burdens of managing the cluster from the devs and offer a REST API to interact instead of Python like with Airflow.  
Also in future it will offer libs in various languages.  
And will be able to perform custom local actions similar to GitHub actions and community could build their actions.

It will be similar to GitHub actions + AWS lambda + spark functionality.

# Features

- Retries, failure tolerance, recovery, resilience, suspendable jobs
- Sequential and parallel execution
- Job groups
- Replicated jobs
- Inter-process communication with `dbus`, `zbus`, `gRPC`, `Apache Arrow Flight`. `Spark`, `Flink`
- Persistent job states in `PostgreSQL` and `NoSQL` solutions
- Access file storage like `S3`
- Cancel concurrent execution and exclusive job execution
- Remote scheduling, manual, automatic, cron
- Can execute any code which can be represented as a Docker image

# Stack

- Kuberetes
- [Apache Airflow](https://airflow.apache.org/)
- Kafka for inter services communication and cron jobs
- [Kafka Connect](https://docs.confluent.io/platform/current/connect/index.html) for stream processing
- [Apache Flink](https://flink.apache.org/) for real-time event processing
- S3
- Observability with Grafana and Prometheus
