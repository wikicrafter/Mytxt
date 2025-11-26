# Cybersecurity Essentials

This document outlines crucial security practices to protect personal and organizational assets.

## 1. Identity and Access Management

### Strong Passwords
- **Length & Complexity**: Use at least 12-16 characters, mixing uppercase, lowercase, numbers, and symbols.
- **Uniqueness**: Never reuse passwords across different services.
- **Manager**: Use a reputable Password Manager (e.g., Bitwarden, 1Password, KeePass) to generate and store credentials.

### Multi-Factor Authentication (MFA)
- **Enable Everywhere**: Turn on MFA/2FA for all accounts that support it (Email, Banking, Social Media).
- **Method Preference**:
    1.  Hardware Keys (YubiKey) - *Most Secure*
    2.  Authenticator Apps (Google/Microsoft Authenticator, Authy)
    3.  SMS/Email - *Least Secure (but better than nothing)*

## 2. Threat Awareness

### Phishing
- **Verify Senders**: Check the actual email address, not just the display name.
- **Hover Links**: Hover over links to see the actual URL before clicking.
- **Urgency**: Be skeptical of emails demanding immediate action or sensitive information.
- **Attachments**: Do not open unexpected attachments, even from known contacts.

### Social Engineering
- Be cautious of unsolicited phone calls or messages asking for remote access or credentials.
- Verify the identity of the requester through a secondary channel.

## 3. System and Software Security

### Updates
- **OS & Apps**: Enable automatic updates for your Operating System, Web Browser, and critical applications.
- **Patches**: Security patches fix known vulnerabilities; apply them immediately.

### Antivirus & Anti-malware
- Use a reputable antivirus solution (Windows Defender is sufficient for most Windows users if kept updated).
- Perform periodic full system scans.

## 4. Data Protection

### Backups
- **3-2-1 Rule**:
    - **3** copies of your data.
    - **2** different media types (e.g., local drive + cloud).
    - **1** copy offsite.
- **Encryption**: Encrypt sensitive backups.

### Device Encryption
- Enable Full Disk Encryption (BitLocker on Windows, FileVault on macOS, LUKS on Linux) to protect data if the device is stolen.

## 5. Network Security

### Wi-Fi
- **Home**: Change default router passwords and use WPA3 (or WPA2-AES).
- **Public**: Avoid accessing sensitive data (banking) on public Wi-Fi. Use a VPN if necessary.

### Firewall
- Ensure your system firewall is enabled.

## 6. Physical Security
- Lock your computer when walking away (Win + L).
- Do not leave sensitive documents on your desk.
