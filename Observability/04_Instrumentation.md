## 🎛️ Instrumentation
- Instrumentation refers to the process of adding monitoring capabilities to your applications, systems, or services.
- This involves embedding/Writting code or using tools to collect metrics, logs, or traces that provide insights into how the system is performing.

## 🎯 Purpose of Instrumentation:
- **Visibility**: It helps you gain visibility into the internal state of your applications and infrastructure.
- **Metrics Collection**: By collecting key metrics like CPU usage, memory consumption, request rates, error rates, etc., you can understand the health and performance of your system.
- **Troubleshooting**: When something goes wrong, instrumentation allows you to diagnose the issue quickly by providing detailed insights.

## ⚙️ How it Works:
- **Code-Level Instrumentation**: You can add instrumentation directly in your application code to expose metrics. For example, in a `Node.js` application, you might use a library like prom-client to expose custom metrics.

## 📈 Instrumentation in Prometheus:
- 📤 **Exporters**: Prometheus uses exporters to collect metrics from different systems. These exporters expose metrics in a format that Prometheus can scrape and store.
    - **Node Exporter**: Collects system-level metrics from Linux/Unix systems.
    - **MySQL Exporter (For MySQL Database)**:  Collects metrics from a MySQL database.
    - **PostgreSQL Exporter (For PostgreSQL Database)**: Collects metrics from a PostgreSQL database.
- 📊 **Custom Metrics**: You can instrument your application to expose custom metrics that are relevant to your specific use case. For example, you might track the number of user logins per minute.

## 📈 Types of Metrics in Prometheus
- 🔄️ **Counter**:
    - A Counter is a cumulative metric that represents a single numerical value that only ever goes up. It is used for counting events like the number of HTTP requests, errors, or tasks completed.
    - **Example**: Counting the number of times a container restarts in your Kubernetes cluster
    - **Metric Example**: `kube_pod_container_status_restarts_total`

- 📏 **Gauge**:
    - A Gauge is a metric that represents a single numerical value that can go up and down. It is typically used for things like memory usage, CPU usage, or the current number of active users.
    - **Example**: Monitoring the memory usage of a container in your Kubernetes cluster.
    - **Metric Example**: `container_memory_usage_bytes`

- 📊 **Histogram**:
    - A Histogram samples observations (usually things like request durations or response sizes) and counts them in configurable buckets.
    - It also provides a sum of all observed values and a count of observations.
    - **Example**: Measuring the response time of Kubernetes API requests in various time buckets.
    - **Metric Example**: `apiserver_request_duration_seconds_bucket`

- 📝 Summary:
    - Similar to a Histogram, a Summary samples observations and provides a total count of observations, their sum, and configurable quantiles (percentiles).
    - **Example**: Monitoring the 95th percentile of request durations to understand high latency in your Kubernetes API.
    - **Metric Example**: `apiserver_request_duration_seconds_sum`
