
# AWS GuardDuty

- Provides intelligent threat detection and continuous monitoring for your AWS accounts and workloads.
- GuardDuty is a managed service
- Utilizes machine learning, anomaly detection, and integrated threat intelligence to identify and prioritize potential threats.
- GuardDuty analyzes billions of events across multiple AWS data sources, such as:
  - VPC Flow Logs
  - AWS CloudTrail event logs
  - DNS logs
- It automatically detects a wide range of threats, including:
  - Unauthorized and malicious activity
  - Account compromise
  - Instance compromise
  - Reconnaissance by attackers
- Detected threats are rated by severity, and findings are delivered as detailed alerts in the GuardDuty console.
- Alerts can include actionable information to help mitigate threats, such as:
  - The type of threat detected
  - The affected resource
  - The action that triggered the detection
- GuardDuty findings can be exported to Amazon CloudWatch Events or Amazon EventBridge for further analysis or to trigger automated responses.
- Offers integration with AWS Security Hub for consolidated security incident management.
- Provides customizable threat detection lists and trust lists that tailor its response to the specific security needs of your business environment.
- Unlike CloudTrail, which requires log storage and analysis setup, GuardDuty is fully managed and provides immediate out-of-the-box security monitoring with no need for user-managed rules or policies.

