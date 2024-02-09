# Security Operations Plan (SOP) for Client Cloud Infrastructure

This document outlines the security operations plan (SOP) for the client's cloud infrastructure hosted on Amazon Web Services (AWS). This plan encompasses security controls, monitoring solutions, incident response procedures, and compliance documentation.

## Security Controls

### Identity and Access Management (IAM) Procedures:

#### Root Account Security:
- **Strong Credentials Required:**
  - Generate a complex and unique password for the root account, exceeding at least 16 characters and using a combination of upper/lowercase letters, numbers, and symbols.
  - Never share passwords with anyone.
- **Disable Direct Login:**
  - Disable all methods of direct login to the root account, including console access, programmatic access, and API calls.

#### IAM User Accounts:
- Utilize IAM user accounts with appropriate permissions for all administrative tasks, eliminating the need for root access in day-to-day operations.

#### Team Member Access Management:
- **Least Privilege Principle:**
  - Implement the principle of least privilege for all team members, granting them only the minimum permissions necessary to perform their specific roles and responsibilities.
  - Regularly review and adjust user permissions based on changes in roles or responsibilities.
- **Individual IAM Users:**
  - Create individual IAM users for each team member.
  - Avoiding shared accounts that pose security risks.
  - Assign permissions to each user based on their specific needs, utilizing IAM policies and roles for efficient management.
- **Multi-Factor Authentication (MFA):**
  - Enforce mandatory MFA for all user accounts, including a combination of something you know (password) and something you have (security token, app authenticator).
  - Educate team members on the importance of MFA and enforce its use for all access attempts.

### Server Hardening and Data Protection:

#### Windows Server Domain Controller:
- The Domain Controller will be displayed through a secure VPN.
- Will restrict inbound traffic to authorized ports and protocols necessary for DC functionality.
- Will utilize firewall rules to further restrict access and prevent unauthorized connection.
- Implement CIS recommendations such as strong passwords, secure group policies, and regular security updates.
- Focus on secure configurations for user accounts and privileges, local security policies, firewalls and network security, and logging and auditing.

#### Linux Data Server Deployment with PII and GDPR Data:
- Is a server designed to store and manage data installed with Install a supported Linux distribution certified for GDPR compliance.
- CIS benchmarks are applied for system hardening.
- Implement full disk encryption at rest using industry-standard algorithms.
- Securely manage encryption keys using a dedicated key management solution.
- Encrypt data in transit using strong protocols like SSH with public-key authentication and TLS/SSL for network traffic.

#### AWS Network Infrastructure with pfSense VPN:
- Will enhance security with a centralized firewall.
- Will establish a VPN for an extra layer of protection.

## Security Information and Event Management (SIEM):

### Log Aggregation:
- Implement a SIEM solution to centralize and analyze event logs from key assets like EC2 instances.

### Implementation:
- Deploy the chosen SIEM solution onto a centralized server, including integrating CloudTrail, CloudWatch, Sysmon (for Windows logs), and Linux logging for comprehensive log acquisition.
- Verify Log Ingestion: After provisioning and configurations, the verification of log ingestion will ensure seamless log flow from CloudTrail and CloudWatch into the SIEM for reliable data analysis.

### Integration:
- **SIEM with AWS CloudWatch, Sysmon (for Windows logs), and Linux Logging:**
  - Integrate with CloudWatch.
  - Set up CloudWatch Log Retrieval by establishing connections and configure parsers for efficient log collection from CloudWatch.
  - Map Events and Validate Integration: Integrate CloudWatch logs with pre-defined security rules and confirm proper parsing and alert activation.
  - Integrate with Sysmon (Windows):
    - Collect and Parse Sysmon Logs: Configure agents to capture desired events and create parsers for conversion to SIEM-compatible format.
    - Analyze and Trigger Alerts: Map parsed Sysmon logs to pre-defined security rules and validate accurate parsing and timely alerts.
  - **Integration with Linux:**
    - Choose and Implement Logging Agent: Select an appropriate agent based on your needs and configure it to capture relevant Linux logs.
    - Ensure Log Ingestion and Alerting: Verify that logs are collected, parsed successfully, and trigger appropriate alerts according to predefined SIEM rules.

## Incident Response Plan

### Detection and Analysis:
- Leverage monitoring tools and SIEM alerts to identify potential security incidents.

### Containment:
- Isolate affected systems and restrict access to minimize further damage.

### Eradication:
- Identify and remove the root cause of the incident.

### Recovery:
- Restore affected systems and data to a known good state.

### Reporting:
- Document the incident, analyze root cause, and implement corrective actions to prevent future occurrences.

## Compliance Documentation

- This plan adheres to the General Data Protection Regulation (GDPR) framework.
- Documentation will showcase compliance through measures like data encryption at rest and in transit, access control mechanisms within IAM, logging and monitoring practices for data access and modification, and incident response procedures aligned with GDPR guidelines.

## Standard Operating Procedure (SOP) for Cloud Security and Compliance with GDPR

### Compliance Framework:
- This SOP is updated to adhere to the General Data Protection Regulation (GDPR) in addition to PCI DSS v4.0.

### Personal Data Identification and Inventory:
- Document all personal data collected, stored, or processed in the cloud environment.
- Identify the legal basis for processing each data type (e.g., consent, contract fulfillment).
- Categorize data based on sensitivity levels (e.g., financial, health, biometrics).

### Data Subject Rights and Privacy Notices:
- Develop and publish a comprehensive privacy notice that explains data collection practices, data use purposes, and individual rights under GDPR.
- Implement procedures to handle data subject requests efficiently and within GDPR timeframes.

### Data Security and Breaches:
- Maintain appropriate technical and organizational measures to protect personal data from unauthorized access, disclosure, alteration, or destruction.
- Implement data breach notification procedures to inform impacted individuals and supervisory authorities within required timeframes.

### Data Retention and Deletion:
- Define clear data retention policies based on legal requirements, business needs, and data minimization principles.
- Implement procedures for secure and timely deletion of personal data when no longer needed.

### Compliance Documentation:
- Update documentation to include:
  - Personal data inventory and legal basis for processing.
  - Privacy notice and data subject rights procedures.
  - Data security and breach notification procedures.
  - Data retention and deletion policies.
- Conduct regular data protection impact assessments (DPIAs) to identify and mitigate risks to personal data.
- Maintain records of all compliance activities and audits.

## Additional Resources:

- [GDPR official website](https://gdpr-info.eu/)
