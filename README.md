# aladdin-executor

"Your wish is my command". A distributed executor service.

> [!WARNING]  
> This is still under development. Please do not use it with sensitive data for now, please wait for a
stable release.  
> It's mostly ideal for experimental and learning projects.**

This wants to be a distributed filesystem in k8s an orchestrated with Apache Airflow. It can be deployed on any cloud provider or on-prem.

# Features

- Retries, failure tolerance, recovery, resilience, suspendable jobs
- Sequential and parallel execution
- Job groups
- Replicated jobs
- Inter-process communication with `zbus` and `gRPC` and `Apache Arrow Flight`
- Persistent job states
- Cancel concurrent execution
- Exclusive job execution
- Remote scheduling, manual, automatic, cron

# Stack

- Kuberetes
- [Apache Airflow](https://airflow.apache.org/)
- Kafka for inter services communication and cron jobs
- [Kafka Connect](https://docs.confluent.io/platform/current/connect/index.html) for stream processing
- [Apache Flink](https://flink.apache.org/) for real-time event processing
- Observability with Grafana and Prometheus
