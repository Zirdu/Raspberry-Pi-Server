# Security Overview

## 1. Security Objectives
Raspberry-Pi-Server is designed with a security-first approach to minimize attack surface,
ensure auditability, and provide resilience against unauthorized access. The
objectives include:

- Protect system and container workloads from compromise
- Enforce least privilege across users and services
- Maintain visibility on critical events
- Ensure reproducibility and consistency through automation

## 2. Host Hardening
- Base system regularly updated with security patches
- Minimal software installed to reduce potential vulnerabilities
- Unnecessary services disabled
- Secure permissions on critical directories and files
- User accounts follow principle of least privilege

## 3. SSH Access & Authentication
- SSH access allowed only via key-based authentication
- Root login disabled
- Port obfuscation or custom port recommended for additional obscurity
- Monitoring of login attempts through log analysis

## 4. Firewall & Network Policies
- Host-based firewall (UFW) active with allowlist rules only
- No direct exposure of services to the Internet
- VPN (WireGuard) provides secure external access when required
- Network segmentation for container workloads to reduce lateral movement

## 5. Intrusion Detection & Prevention
- Fail2Ban configured to block repeated failed login attempts
- Hooks trigger alerts via scripts to notify administrator of suspicious events
- Log analysis scripts detect unusual authentication patterns
- Proactive measures in place to mitigate brute-force or automated attacks

## 6. Container Security
- Containers run rootless to minimize privilege escalation risk
- Each workload isolated to prevent cross-container compromise
- Immutable container images where possible
- Security principles applied to Quadlets and systemd integration

## 7. Logging & Alerting
- Centralized logging for system, SSH, and container events
- Alerts delivered through automated scripts (e.g., Telegram)
- Logs structured to support both operational monitoring and security review
- Retention policies ensure relevant events are kept for incident analysis

## 8. Security Best Practices
- Apply defense-in-depth principles at host, container, and network level
- Regularly review and update scripts, firewall rules, and container policies
- Avoid exposing sensitive configuration or credentials in repositories
- Maintain documentation for reproducibility and auditability
