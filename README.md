# Monitoring.
# Index

1. [What is Monitoring?](#What-is-Monitoring)
2. [Why is Monitoring Important?](#Why-is-Monitoring)
3. [Various Monitoring Aspects](#various-monitoring-aspects)
4. [What is Prometheus?](#what-is-prometheus)
5. [Where and Why is Prometheus Used?](#where-and-why-is-prometheus-used)
6. [Specific Use Cases for Using Prometheus Monitoring](#specific-use-cases-for-using-prometheus-monitoring)
7. [How does Prometheus Work?](#how-does-prometheus-work)
8. [Prometheus Architecture Explained](#prometheus-architecture-explained)
9. [Prometheus Server](#prometheus-server)
10. [What are Targets and Metrics?](#what-are-targets-and-metrics)
11. [How does Prometheus Collect Metrics from Targets?](#how-does-prometheus-collect-metrics-from-targets)
12. [What are Target Endpoints and Exporters?](#what-are-target-endpoints-and-exporters)
13. [How to Monitor Your Own Application?](#how-to-monitor-your-own-application)
14. [Pull Mechanism - Unique Advantage of Prometheus](#pull-mechanism---unique-advantage-of-prometheus)
15. [Pushgateway for Short-lived Jobs](#pushgateway-for-short-lived-jobs)
16. [Configuring Prometheus - Example YAML Configuration](#configuring-prometheus---example-yaml-configuration)
17. [Alert Manager - Triggering Alerts](#alert-manager---triggering-alerts)
18. [Prometheus Data Storage - Where Does Prometheus Store the Data?](#prometheus-data-storage---where-does-prometheus-store-the-data)
19. [PromQL Query Language](#promql-query-language)
20. [Key Characteristics - Advantages and Disadvantages of Prometheus](#key-characteristics---advantages-and-disadvantages-of-prometheus)
21. [Prometheus Monitoring with Docker and Kubernetes](#prometheus-monitoring-with-docker-and-kubernetes)
22. [Grafana ](#Grafana)

# What-is-Monitoring

Monitoring is the process of **collecting** and **analyzing** data about a system in order to identify and troubleshoot problems. It is an essential part of IT operations, as it allows organizations to ensure that their systems are running **smoothly** and **efficiently**.


# Why is Monitoring.

**Identifying and troubleshooting problems:** Monitoring can help organizations to identify and troubleshoot problems quickly. This can help to prevent outages and to improve the overall performance of the system.

**Ensuring system availability:** Monitoring can help organizations to ensure that their systems are available when they are needed. This is important for businesses that rely on their systems to operate.

**Protecting system security:** Monitoring can help organizations to protect their systems from unauthorized access. This is important for businesses that handle sensitive data.

**Make informed decisions:** Monitoring can provide organizations with data that can be used to make informed decisions about their systems. For example, monitoring can be used to identify trends in system performance, which can help organizations to make decisions about how to improve the performance of their systems.

Overall, monitoring is an essential part of IT operations. It allows organizations to ensure that their systems are running smoothly and efficiently, and it helps to identify and troubleshoot problems quickly.

##  **Here are some of the benefits of monitoring:**

**Prevention:** Monitoring can help to prevent problems from occurring by identifying potential issues before they cause an outage or other disruption.

**Resolution:** Monitoring can help to resolve problems quickly by providing information about the source of the issue and how to fix it.

**Improvement:** Monitoring can help to improve the performance of systems by identifying areas where they can be optimized.

**Cost savings:** Monitoring can help to save money by preventing outages and other disruptions that can lead to lost revenue.

## The challenges of monitoring include:

**Data collection:** Collecting data can be a challenge, especially for large systems.

**Data analysis:** Analyzing data can be a challenge, especially for complex systems.

**Alerting:** Alerting users of problems can be a challenge, especially if the problems are not obvious.

**Cost:** Monitoring can be expensive, especially for large systems.

Overall, monitoring is an essential part of IT operations. It allows organizations to ensure that their systems are running smoothly and efficiently, and it helps to identify and troubleshoot problems quickly.

## Various Monitoring Aspects

1. **Infrastructure Monitoring:**
   - Servers (CPU, memory, disk usage, etc.)
   - Network devices (routers, switches, firewalls)
   - Storage systems (SAN/NAS)
   Infrastructure Monitoring:
   - Nagios
   - Zabbix
   - Prometheus
   - Grafana
   - SolarWinds Server & Application Monitor (SAM)

2. **Application Monitoring:**
   - Application response times
   - Error rates and exceptions
   - Throughput and request rates
   **Application Monitoring:**
   - New Relic
   - Datadog
   - AppDynamics
   - Dynatrace
   - Stackify Retrace

3. **End-User Monitoring (EUM):**
   - End-user experience and satisfaction
   - Page load times
   - Transaction success rates
   **End-User Monitoring (EUM):**
   - Google Analytics
   - Pingdom
   - Dynatrace Real User Monitoring (RUM)
   - New Relic Browser

4. **Log Monitoring:**
   - System logs (syslog, Windows Event Logs)
   - Application logs (web server, database, application-specific)
   **Log Monitoring:**
   - ELK Stack (Elasticsearch, Logstash, Kibana)
   - Splunk
   - Graylog
   - Sumo Logic

5. **Performance Monitoring:**
   - Application performance metrics
   - Server performance metrics
   - Network performance metrics
   **Performance Monitoring:**
   - Apache JMeter
   - Gatling
   - LoadRunner
   - Locust

6. **Security Monitoring:**
   - Security events and alerts
   - Intrusion detection
   - Logins and access attempts
   **Security Monitoring:**
   - ArcSight
   - Splunk Enterprise Security
   - LogRhythm
   - IBM QRadar

7. **Network Monitoring:**
   - Network bandwidth utilization
   - Latency and packet loss
   - Network device health (status, availability)
   **Network Monitoring:**
   - PRTG Network Monitor
   - SolarWinds Network Performance Monitor (NPM)
   - Nagios Network Analyzer
   - ManageEngine OpManager

8. **Cloud Monitoring:**
   - Cloud resource utilization (compute, storage, networking)
   - Auto-scaling events
   - Cloud service availability
   **Cloud Monitoring:**
   - Amazon CloudWatch
   - Google Cloud Monitoring (formerly Stackdriver)
   - Azure Monitor
   - Datadog Cloud Monitoring

9. **Database Monitoring:**
   - Database query performance
   - Connection pool usage
   - Database locks and deadlocks
   **Database Monitoring:**
   - Oracle Enterprise Manager (OEM)
   - SQL Server Management Studio (SSMS)
   - Prometheus with database exporters (e.g., mysqld_exporter)

10. **Synthetic Monitoring:**
    - Simulated user interactions and transactions
    - Global performance variations
    - Regional performance monitoring
    **Synthetic Monitoring:**
    - Pingdom
    - Uptrends
    - Site24x7
    - Dynatrace Synthetic Monitoring

11. **Container Monitoring:**
    - Resource utilization in containerized environments (e.g., Docker, Kubernetes)
    - Container health and status
    **Container Monitoring:**
    - Docker Monitoring with cAdvisor
    - Kubernetes Monitoring with Prometheus Operator
    - Sysdig Monitor
    - Datadog Container Monitoring

12. **Virtualization Monitoring:**
    - Virtual machine performance metrics
    - Hypervisor performance and resource usage
    **Virtualization Monitoring:**
    - VMware vRealize Operations
    - SolarWinds Virtualization Manager
    - Microsoft System Center Virtual Machine Manager (SCVMM)

13. **Service-Level Agreement (SLA) Monitoring:**
    - Monitoring adherence to SLAs and uptime guarantees
    - Service availability and response times
    **Service-Level Agreement (SLA) Monitoring:**
    - Freshping
    - UptimeRobot
    - Pingdom
    - StatusCake

14. **Alerting and Notification:**
    - Setting up and managing alert thresholds
    - Notifying relevant teams or stakeholders of critical events
    **Alerting and Notification:**
    - PagerDuty
    - OpsGenie
    - VictorOps
    - Slack (integration with monitoring tools for alerting)

15. **Dashboarding and Visualization:**
    - Creating and customizing real-time dashboards
    - Data visualization for easier analysis and reporting
    **Dashboarding and Visualization:**
    - Grafana
    - Kibana (part of ELK Stack)
    - Datadog Dashboard
    - New Relic Insights

Each of these monitoring aspects provides unique insights into the health and performance of different components of the IT infrastructure and applications. By monitoring these aspects, organizations can ensure optimal performance, detect and resolve issues proactively, and provide a seamless experience to end-users.

# **Prometheus: Overview and Architecture**

## What is Prometheus?

Prometheus is an open-source **monitoring** and **alerting** system that is widely used in the DevOps and cloud-native ecosystem. It was developed by **SoundCloud** and later donated to the **Cloud Native Computing Foundation (CNCF)**.

Prometheus was created to **monitor highly dynamic container environments** like Kubernetes, Docker Swarm, etc. However, 
it can also be used in a traditional non-container infrastructure where you have just bare servers with applications deployed 
directly on it. 
So over the past years, Prometheus has become the mainstream monitoring tool of choice in the container and 
microservice world.

**Key Features of Prometheus:**
1. **Multi-Dimensional Data Model:** Prometheus follows a multi-dimensional data model, where each data point is identified by a combination of key-value pairs. This allows for flexible and efficient querying and aggregation of metrics.

2. **Time-Series Database:** Prometheus stores time-series data natively, making it well-suited for monitoring time-based data such as metrics.

3. **PromQL:** Prometheus Query Language (PromQL) allows users to query and manipulate metrics data easily. It supports functions for aggregation, filtering, and mathematical operations.

4. **Pull-Based Architecture:** Prometheus follows a pull-based approach, where it periodically scrapes (pulls) metrics data from target applications and services. This enables it to work effectively in dynamic environments like Kubernetes.

5. **Service Discovery:** Prometheus integrates with various service discovery mechanisms like Kubernetes service discovery, Consul, and others to automatically discover and monitor new targets as they appear or disappear.

6. **Alerting:** Prometheus comes with a built-in alerting mechanism that allows users to define alerting rules based on metrics thresholds or other conditions. When an alert rule is violated, Prometheus can send alerts to various alerting channels like email, Slack, or PagerDuty.

# **Prometheus Architecture:**

Prometheus consists of several key components that work together to provide efficient monitoring capabilities:

![image](https://github.com/RavikiranSavai/Monitoring_With_Prometheus-Grafana/assets/76962621/2a58bc67-78be-4f8e-88b2-1f0e23d454ea)

1. **Prometheus Server:** The core component responsible for data collection and storage. It scrapes metrics data from configured targets using HTTP-based pull mechanism and stores the time-series data in its local **time-series database**. like CPU Uses, No of exceptions.

**Second**, it has a **data retrieval worker** that is responsible for getting or pulling those metrics from applications, services, servers, 
and other target resources and storing them or pushing them into that database.

And **third**, it has a web server or server API that accepts
 queries for that stored data, and that web server component or the server API is used to display the data in a dashboard or UI, either 
 through Prometheus dashboard or some other data visualization tool like Grafana.

2. **Pushgateway:** A service that allows ephemeral or batch jobs to push their metrics to Prometheus. This is useful for jobs that do not have long lifetimes or those that cannot be scraped directly by Prometheus.

3. **Exporters:** Prometheus exporters are small agents that run alongside the applications or services and expose their metrics in a format that Prometheus can scrape. There are various exporters available for popular applications like Node Exporter (for system-level metrics), MySQL Exporter, Apache Exporter, etc.

4. **Alertmanager:** This component handles alerts generated by Prometheus. It takes care of deduplicating, grouping, and sending alerts to various alert notification channels.

5. **Prometheus Web UI:** A graphical user interface that allows users to explore metrics, execute queries, and visualize data using graphs and charts.

Service discovery in Prometheus is a crucial feature that allows the monitoring system to automatically discover and monitor new instances of targets (e.g., applications, services, or servers) as they are added or removed from the infrastructure. Prometheus uses service discovery to dynamically collect metrics from these targets without requiring manual configuration.

There are various methods of service discovery supported by Prometheus:

1. **Static Configurations**: In this method, you define the targets directly in the Prometheus configuration file. This approach is useful for monitoring a small, fixed set of targets that do not change frequently. However, it lacks the flexibility to scale automatically with dynamic environments.

   Example static configuration:
   ```yaml
   scrape_configs:
     - job_name: 'my_application'
       static_configs:
         - targets: ['localhost:9090', 'example.com:8080']
   ```

2. **File-Based Service Discovery**: Prometheus can also be configured to read target configurations from a file. This file can be updated dynamically, and Prometheus will automatically pick up changes.

   Example file-based configuration (targets.json):
   ```json
   [
     {
       "targets": ["localhost:9090"]
     },
     {
       "targets": ["example.com:8080"]
     }
   ]
   ```
   In Prometheus configuration:
   ```yaml
   scrape_configs:
     - job_name: 'my_application'
       file_sd_configs:
         - files:
           - 'targets.json'
   ```

3. **DNS Service Discovery**: Prometheus can discover targets using DNS records. This is particularly useful for dynamically scaling environments where DNS records are updated as new instances are added or removed.

   Example DNS service discovery configuration:
   ```yaml
   scrape_configs:
     - job_name: 'my_application'
       dns_sd_configs:
         - names: ['my_application.service.consul']
           type: 'A'
           port: 8080
   ```

4. **Kubernetes Service Discovery**: Prometheus provides native support for discovering and monitoring targets in Kubernetes clusters. It leverages Kubernetes' API to discover services, pods, and endpoints.

   Example Kubernetes service discovery configuration:
   ```yaml
   scrape_configs:
     - job_name: 'my_application'
       kubernetes_sd_configs:
         - role: endpoints
           namespaces:
             names: ['my-namespace']
   ```

Service discovery ensures that Prometheus can automatically detect changes in your infrastructure and start monitoring new instances or remove monitoring for instances that are no longer available. It simplifies the monitoring setup and helps maintain an up-to-date view of the targets being monitored.


**Conclusion:**

Prometheus is a powerful monitoring solution with a flexible data model, scalable architecture, and a rich ecosystem of exporters and integrations. Its pull-based approach and service discovery capabilities make it well-suited for modern containerized environments like Kubernetes. With its effective alerting and visualization features, Prometheus empowers DevOps teams to gain valuable insights into their systems and applications, enabling them to detect and resolve issues proactively and ensure the smooth operation of their infrastructure.


# **Grafana: Overview and Features**

Grafana is an open-source data visualization and monitoring platform that is widely used in conjunction with various data sources, including Prometheus, to create insightful and interactive dashboards. It was originally designed for graphing time-series data but has evolved into a versatile tool that supports various data sources and allows users to build rich visualizations.

**Key Features of Grafana:**

1. **Data Source Agnostic:** Grafana supports a wide range of data sources, making it easy to integrate with various monitoring and analytics platforms. Some popular data sources include Prometheus, Graphite, Elasticsearch, InfluxDB, MySQL, and many others.

2. **Rich Visualization Options:** Grafana offers a wide variety of visualization options, including graphs, charts, tables, heatmaps, and single-stat panels. Users can choose from various visualization types to represent their data effectively.

3. **Dashboard Templating:** Grafana allows users to create dynamic dashboards by utilizing templating variables. These variables can be used in queries and panel titles, making it easy to create reusable and flexible dashboards.

4. **Alerting:** Grafana provides a built-in alerting system that allows users to set up alert rules based on specific metrics conditions. When the conditions are met, Grafana can trigger notifications through various channels such as email, Slack, PagerDuty, and more.

5. **Annotations:** Grafana allows users to add annotations to charts and graphs to mark important events or incidents. Annotations help provide additional context to the data being visualized.

6. **Dashboard Sharing and Permissions:** Grafana allows users to share dashboards with others and control their access permissions. Users can share public links or restrict access to specific user groups or roles.

7. **Plugins and Extensions:** Grafana has a vibrant community that contributes various plugins and extensions, expanding its functionality and providing additional integrations with different services.

**Grafana Architecture:**

Grafana is primarily a front-end application that interacts with data sources and visualization backends. The key components of Grafana architecture are:

1. **Grafana Server:** The core component that handles user authentication, dashboard creation, and interaction with data sources. It provides the Grafana web interface and APIs for data retrieval and manipulation.

2. **Data Sources:** Grafana communicates with various data sources to retrieve metric data and other relevant information. These data sources can be time-series databases like Prometheus or InfluxDB, as well as other databases and services.

3. **Dashboards:** Grafana allows users to create and customize dashboards that display visualizations of data from the selected data sources. Dashboards are created using the Grafana web interface or JSON-based configuration files.

4. **Plugins:** Grafana supports plugins that extend its capabilities. Plugins can provide additional data sources, panels, alerting notification channels, and other functionalities.

**Conclusion:**

Grafana is a powerful and user-friendly data visualization platform that empowers users to create compelling dashboards and gain valuable insights from their data. Its ability to connect to various data sources, coupled with its rich visualization options and alerting capabilities, makes it a valuable tool for monitoring and analyzing data from different systems and applications. Grafana's extensibility through plugins and its active community ensure that it remains a popular choice for data visualization and monitoring needs across various domains.
