# Observability Overview

## 1. Objectives
The observability stack in Raspberry-Pi-Server provides visibility into both system
operations and security events. The main objectives are:

- Monitor system health and container workloads
- Detect anomalies in authentication, network, and service activity
- Provide actionable alerts for operational and security issues
- Maintain auditable dashboards and metrics for ongoing analysis

## 2. Stack Components
- **Grafana:** Dashboard visualization and alerting
- **Prometheus:** Metrics collection from system and container workloads
- **Loki:** Centralized log aggregation
- **Promtail:** Log shipping from host and containers
- **Custom scripts:** Parse logs, generate alerts via Telegram

## 3. Metrics Collection
- System metrics: CPU, memory, disk usage, uptime
- Container metrics: resource usage, service status, restart events
- Network metrics: VPN connections, internal traffic, firewall logs

## 4. Log Aggregation
- Centralized collection of host, SSH, and container logs
- Logs structured for easy filtering and correlation
- Historical retention to support incident analysis and auditing

## 5. Dashboards & Visualization
- Predefined dashboards for system health and container workloads
- Security-oriented dashboards highlighting suspicious access or errors
- Visualizations designed to support proactive response

## 6. Alerting & Notification
- Alerts triggered by log patterns or metric thresholds
- Delivery through secure channels (e.g., Telegram notifications)
- Alert scripts include contextual information for quick investigation
- Reduces alert fatigue by focusing on actionable events

## 7. Automation & Provisioning
- Dashboards, datasources, and alerts are provisioned via code
- Container deployment is automated through rootless Podman Quadlets
- Log parsing and alert scripts integrated with CI/CD or system timers

## 8. Security Considerations
- Logs and metrics are collected securely without exposing sensitive data
- Alerting focuses on incidents relevant to security posture
- Container isolation ensures observability stack cannot compromise system
- Principle of least privilege applied across monitoring and alerting components
