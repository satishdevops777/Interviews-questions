# 1. Prometheus
1. What is Prometheus, and how does it work?
```
Answer:
Prometheus is an open-source monitoring system that collects and stores time-series data using a pull-based model. It uses PromQL for querying metrics and works well with Kubernetes.
```
2. How does Prometheus collect metrics?
```
Answer:
Prometheus scrapes metrics from instrumented targets via HTTP endpoints (e.g., /metrics).
```
3. What is a Prometheus exporter?
```
Answer:
An exporter is a component that collects and exposes metrics from non-instrumented services (e.g., node_exporter for system metrics).
```
4. What is PromQL?
```
Answer:
PromQL (Prometheus Query Language) is used to query, filter, and aggregate time-series data. Example:

rate(http_requests_total[5m])
```
5. What is the role of Alertmanager in Prometheus?
```
Answer:
Alertmanager manages and sends alerts (email, Slack, PagerDuty) based on Prometheus-defined conditions.
```
# 2. Grafana

1. What is Grafana, and how is it used?
```
Answer:
Grafana is an open-source visualization tool used for monitoring data from multiple sources (Prometheus, InfluxDB, Elasticsearch).
```
2. How do you integrate Prometheus with Grafana?
```
Answer:
Add Prometheus as a data source in Grafana.
Use PromQL queries to create dashboards.
```
3. What are Grafana dashboards?
```
Answer:
A Grafana dashboard is a customized view displaying multiple metric visualizations.
```
4. How do you set up alerts in Grafana?
```
Answer:
Go to Alerting > Alert Rules
Define conditions and actions (email, Slack, webhook).
```
5. What is the difference between Grafana and Kibana?
```
Answer:
Feature	Grafana	Kibana
Data Source	Prometheus, MySQL, InfluxDB	Elasticsearch
Use Case	Metrics visualization	Log analytics
```
# 3. ELK Stack (Elasticsearch, Logstash, Kibana)

1. What is the ELK Stack?
```
Answer:
The ELK Stack (Elasticsearch, Logstash, Kibana) is used for log aggregation, searching, and visualization.
```
2. What is the role of Elasticsearch in ELK?
```
Answer:
Elasticsearch is a search engine that stores and indexes logs for fast querying.
```
3. How does Logstash process logs?
```
Answer:
Logstash collects, processes, and transforms logs before sending them to Elasticsearch.
```
4. What is Kibana used for?
```
Answer:
Kibana provides a dashboard and visualization layer for Elasticsearch logs.
```
5. How do you filter logs in Logstash?
```
Answer:
Using Grok filters:
filter {
  grok {
    match => { "message" => "%{TIMESTAMP_ISO8601:timestamp} %{LOGLEVEL:level} %{GREEDYDATA:msg}" }
  }
}
```
## 4. AWS CloudWatch
1. What is AWS CloudWatch?
```
Answer:
CloudWatch is a monitoring and observability service for AWS resources and applications.
```
2. What types of metrics does CloudWatch collect?
```
Answer:
Infrastructure metrics (CPU, memory, disk usage).
Application logs (Lambda, ECS, EC2 logs).
```
3. How do you set up CloudWatch Alarms?
```
Answer:
Define a metric threshold.
Set an alarm action (SNS, Lambda, Auto Scaling).
```
4. How do you monitor logs in CloudWatch?
```
Answer:
Using CloudWatch Logs Insights to query logs:
fields @timestamp, @message
| sort @timestamp desc
| limit 10
```
5. What is CloudWatch Logs Agent?
```
Answer:
It is an agent installed on EC2 to send logs to CloudWatch.
```
## 5. Fluentd & Log Forwarding
1. What is Fluentd?
```
Answer:
Fluentd is an open-source log forwarder used for collecting and transporting logs to storage systems.
```
2. How does Fluentd work?
```
Answer:
Fluentd collects logs from multiple sources, processes them, and routes them to destinations (Elasticsearch, S3, Kafka).
```
3. What are Fluentd plugins?
```
Answer:
Fluentd has over 500+ plugins for different sources (file, syslog, Docker) and outputs (S3, Elasticsearch).
```
4. How do you configure Fluentd for log forwarding?
```
Answer:
Example Fluentd configuration:
<source>
  @type tail
  path /var/log/app.log
  pos_file /var/log/td-agent/app.pos
  tag app.logs
</source>

<match app.logs>
  @type elasticsearch
  host elasticsearch.local
  logstash_format true
</match>
```
5. What is the difference between Fluentd and Logstash?
```
Feature                	Fluentd	                        Logstash
Written In	             C, Ruby	                         Java
Performance	      Lightweight, faster      	        Heavier, more features
Use Case	        Log collection & forwarding	        Log processing
```

## 6. Splunk
1. What is Splunk, and why is it used?
```
Answer:
Splunk is a log analysis and monitoring tool that collects, indexes, and visualizes machine-generated data. It is used for log management, security analytics, and real-time monitoring.
```
2. What are the main components of Splunk?
```
Answer:
Indexer: Stores and indexes incoming log data.
Search Head: Provides a web interface for searching and analyzing logs.
Forwarder: Collects and sends logs to the Indexer.
Deployment Server: Manages configurations for forwarders.
```
3. How does Splunk forward data from a remote system?
```
Answer:
Using Splunk Universal Forwarder (UF), which collects logs and sends them to the Splunk Indexer.
```
4. What are Splunk sourcetypes?
```
Answer:
Sourcetypes define how Splunk parses incoming data, helping categorize logs (e.g., syslog, apache_access).
```
5. How do you search logs in Splunk?
```
Answer:
Using Splunk Search Processing Language (SPL):
index=web_logs sourcetype=apache_access | stats count by status
```
6. What is a Splunk Index?
```
Answer:
A Splunk Index is a database-like structure where Splunk stores and retrieves data efficiently.
```
7. How do you create a Splunk alert?
```
Answer:
Go to Search & Reporting → Run a query.
Click Save As → Alert.
Define a trigger condition (e.g., more than 100 errors in 5 minutes).
```
8. What is a Splunk dashboard?
```
Answer:
A Splunk dashboard is a collection of visualizations (charts, tables) created using SPL queries.
```
9. How does Splunk integrate with third-party tools?
```
Answer:
Using Splunk Apps & Add-ons (e.g., Splunk for AWS, Splunk for Kubernetes).
REST API to send and retrieve log data.
```
10. What is Splunk Cluster and its types?
```
Answer:
Indexer Cluster: Replicates indexed data for high availability.
Search Head Cluster: Distributes searches across multiple nodes.
```
