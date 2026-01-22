# Architecture Overview

## 1. Project Scope
Raspberry-Pi-Server is designed as an edge / small-scale production-like environment
focused on automation, observability, and defensive security. Its goal is to
provide a stable and auditable infrastructure while supporting containerized
workloads.

## 2. System Components
- **Base OS:** Debian GNU/Linux 13 (Trixie), x64 architecture
- **Container runtime:** Podman (rootless) integrated with systemd
- **Security layers:** UFW firewall, Fail2Ban, SSH hardening
- **Monitoring:** Centralized logs, metrics collection, alerting
- **Access channels:** Secure, authenticated only via keys or internal networks

## 3. Containerized Services
All services run in isolated, rootless containers to enforce principle of least
privilege. Key workloads include:

- Media and test services (e.g., Jellyfin, Grafana, Loki, Promtail)
- Future internal applications to be deployed as additional containers
- Containers orchestrated via systemd Quadlets for automatic start and recovery

> Implementation details such as ports, credentials, or internal IPs are omitted
> to avoid exposing attack surface.

## 4. Networking & Access Control
- Restricted external access; no services are publicly exposed
- Access controlled through secure VPN (WireGuard) or key-based SSH
- Firewall enforces allowlist-only policies for known services
- Logging and alerts ensure visibility on any unauthorized access attempts

## 5. Observability Integration
- Centralized log aggregation and metric collection
- Security-oriented dashboards with alerting on anomalies
- Logs and metrics collected for both host and container workloads
- Integration designed for proactive incident detection

## 6. Security Considerations
- Rootless containers reduce risk in case of compromise
- Principle of least privilege applied to both system users and containers
- Audit-ready logging for authentication, container events, and system changes
- Intrusion prevention and alerting via Fail2Ban hooks and monitoring scripts

## 7. Design Principles
- Security-first mindset (blue team orientation)
- Automation for repeatability and consistency
- Observability embedded into every service
- Separation of concerns: containers isolated, scripts reusable, documentation
  complete
