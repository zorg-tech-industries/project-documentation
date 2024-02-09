Server Hardening and Data Protection
Installed Components

    Installed and configured Sysmon (Windows) for system log generation.

Configuration Details

    Deployed a Windows Server 2019 Base as an EC2 instance on AWS.
    Set up a Windows 10 Pro VM for Remote Desktop Protocol (RDP) access to the Windows Server 2019 Base.

Manual Hardening of Windows Server 2019 Base

To enhance security and protect data, we performed manual hardening on the Windows Server 2019 Base by implementing six benchmarks from the CIS (Center for Internet Security) systems hardening documentation.
Implemented Benchmarks:

    1.1.5 (L1) Ensure 'Password must meet complexity requirements' is set to 'Enabled'
        Explanation: This policy ensures that passwords meet basic requirements for strong passwords, reducing the risk of unauthorized access due to weak passwords.

    1.1.6 (L1) Ensure 'Store passwords using reversible encryption' is set to 'Disabled'
        Explanation: Disabling reversible password encryption helps prevent attackers from easily decrypting stored passwords, enhancing overall password security.

    1.2.1 (L1) Ensure 'Audit Credential Validation' is set to 'Success and Failure'
        Explanation: Enabling auditing of credential validation helps track and monitor authentication attempts, aiding in the detection of unauthorized access attempts.

    1.2.2 (L1) Ensure 'Audit Kerberos Authentication Service' is set to 'Success and Failure'
        Explanation: Auditing Kerberos authentication service helps monitor Kerberos authentication events, which are critical for securing Windows authentication mechanisms.

    18.4.3 (L1) Ensure 'Configure SMB v1 client driver' is set to 'Enabled: Disable driver (recommended)'
        Explanation: Disabling the SMB v1 client driver enhances security by mitigating the risk associated with outdated and vulnerable SMB v1 protocol.

    18.4.4 (L1) Ensure 'Configure SMB v1 server' is set to 'Disabled'
        Explanation: Disabling the SMB v1 server configuration further strengthens security by preventing the use of the outdated and insecure SMB v1 protocol.

By implementing these benchmarks, we have fortified the Windows Server 2019 Base against common security threats, ensuring better protection of data and resources hosted on the server.

Additional Actions Taken:

    Setup Sysmon onto the Windows Server 2019 Base instance: Installed Sysmon to generate security-relevant system logs for enhanced monitoring and detection of adversarial activity.

    Admin User Account Setup for Juan: Created an admin user account for Juan on the same instance to facilitate tracking of Sysmon logs.

    AWS EBS Volume Encryption: Since the Windows Server 2019 instance did not have Bitlocker for full disk encryption, we utilized AWS EBS Volume encryption to encrypt all instances' volumes, ensuring data security.

    Disable AWS Accounts to Reduce Noise in Logs: Disabled AWS accounts to reduce noise for certain AWS accounts in the logs, focusing on relevant security events for better monitoring and analysis.

## Revision History:

2/8/2024 - Created by Kevin Hoang 
