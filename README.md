# Prometheus Monitoring Setup

This repository contains an automated script written in Bash to install and configure Prometheus, Node Exporter, Alert Manager, cAdvisor, and Grafana for monitoring a GCP VM and its containers. The setup utilizes service discovery, Prometheus rules, alerts, and Grafana dashboards to provide a comprehensive monitoring solution.

## Prerequisites

Before proceeding with the installation, ensure that you have the following prerequisites:

- A GCP VM running a compatible Linux distribution.
- Access to the GCP VM with administrative privileges.
- A Slack workspace with an incoming webhook URL to receive notifications.

## Installation Steps

Follow the steps below to install and configure the monitoring stack:

1. Clone this repository to your GCP VM:

   ```bash
   git clone https://github.com/Ahmadshata/Prometheus.git
   ```
   
   ```bash
   cd <repository-directory>
   ```
   Set the Slack webhook URL in the SLACK_WEBHOOK_URL variable.
   Modify any other configuration variables as per your requirements.
   
   ```bash
   bash ./Prometheus.sh
   bash ./Node-Exporter.sh
   ```
   The script will automate the installation and configuration of Prometheus and Node Exporter.
   
## Accessing the Monitoring Stack:

- Prometheus: Access the Prometheus web interface using the following URL: http://<vm-ip>:9090. Ensure that Prometheus is up and running.
- Node Exporter: Check the Node Exporter metrics by visiting: http://<vm-ip>:9100/metrics.
- c-Advisor: Access the cAdvisor web interface using: http://<vm-ip>:8080. Verify that container metrics are being collected.
- Grafana: Access the Grafana dashboard using the following URL: http://<vm-ip>:3000. Log in with the default credentials (admin/admin) and configure your own username and password.
  
## Configuration and Customization:

- Prometheus Configuration: The Prometheus configuration file prometheus.yml can be modified to add additional scrape targets, configure service discovery, and define alerting rules.
- Alert Manager Configuration: Customize the alertmanager.yml file to define alert receivers, notification configurations, and routes.
- Prometheus Rules and Alerts: Modify the rules.yml file to add or modify alerting rules as per your monitoring requirements.
- Grafana Dashboards: Import custom Grafana dashboards to visualize the metrics and create your own custom dashboards.
  
  Monitoring and Alerting:

The monitoring stack is now set up to monitor your GCP VM and containers. Prometheus will collect metrics from the configured targets, and you can use the Prometheus web interface to create custom queries and visualizations.

The defined alerting rules will trigger alerts whenever a rule condition is violated. These alerts will be sent to the configured Slack channel via the defined webhook URL. Monitor the Slack channel for any important notifications and take appropriate actions as required.

Use Grafana to explore pre-built dashboards or create your own custom dashboards to visualize the collected metrics and gain insights into your system's performance.

## Conclusion
This project provides an automated script to install and configure Prometheus, Node Exporter, thourough steps to deploy Cadvisor container, and Grafana for monitoring a GCP VM and its containers. 
The use of service discovery, Prometheus rules, alerts, and Grafana dashboards ensures comprehensive monitoring.
