# Threat Model

## 1. Scope & Assumptions
This threat model covers the Raspberry-Pi-Server platform as an edge / small-scale
production-like Linux environment. The focus is on infrastructure, access
channels, containerized services, and observability components.

Assumptions:
- No public service exposure by default
- Security controls are active at host, network, and container levels
- This model intentionally abstracts implementation details

## 2. Assets
Critical assets identified within the platform include:

- Host operating system and kernel
- Authentication mechanisms (SSH keys, VPN access)
- Containerized workloads and configurations
- Logs and monitoring data
- Automation scripts and operational tooling

## 3. Threat Actors
Potential threat actors considered:

- Opportunistic external attackers performing automated scans
- Unauthorized internal users or compromised credentials
- Malicious actors targeting misconfigured services
- Accidental misconfiguration by administrators

## 4. Threat Categories
Threats are grouped using a simplified STRIDE-based approach:

- **Spoofing:** Unauthorized access via stolen or weak credentials
- **Tampering:** Modification of system files, scripts, or container images
- **Repudiation:** Lack of traceability for actions performed on the system
- **Information Disclosure:** Exposure of logs, credentials, or configurations
- **Denial of Service:** Resource exhaustion or service disruption
- **Privilege Escalation:** Abuse of misconfigurations or excessive privileges

## 5. Identified Risks
High-level risks identified include:

- Brute-force or credential-based attacks against remote access services
- Misconfigured firewall or container networking rules
- Compromised container images or dependencies
- Insufficient log monitoring leading to delayed detection
- Human error during maintenance or updates

## 6. Mitigation Strategies
Mitigations implemented or planned include:

- Key-based authentication and hardened access policies
- Host firewall with allowlist rules and VPN-based access
- Rootless containers and least privilege execution
- Centralized logging and security-oriented dashboards
- Automated alerts for suspicious activity
- Infrastructure documentation and change tracking

## 7. Residual Risk & Continuous Improvement
Residual risk is acknowledged and continuously evaluated. The threat model is
considered a living document and is updated as the platform evolves.

Future improvements include:
- Enhanced log correlation and anomaly detection
- Regular review of security controls and access policies
- Expansion of monitoring to cover additional threat scenarios
