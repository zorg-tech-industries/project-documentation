# Server Hardening and Data Protection
Installed

    Installed and configured Sysmon (Windows) for system log generation.

Configuration

    Deployed a Windows Server 2019 Base as an EC2 instance on AWS.
    Set up a Windows 10 Pro VM for Remote Desktop Protocol (RDP) access to the Windows Server 2019 Base.

Manual Hardening of Windows Server 2019 Base

To enhance security and protect data, I manually hardened the Windows Server 2019 Base by implementing six benchmarks from the CIS (Center for Internet Security) systems hardening documentation.
Benchmarks Implemented:

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
