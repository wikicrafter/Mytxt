# SSH connection 

* Get-Service sshd - sshd is openSSH service

* Start-Service sshd - starts the sshd service

* Get-Service sshd - verifie if sshd service is running 

 > As I wanted the SSH service to start every time the system booted up, I entered:

* Set-Service -Name sshd -StartupType 'Automati

> To check and make sure that the port for the SSH server was open, I entered:

* Get-NetFirewallRule -Name *ssh*

# scp fenton@10.0.0.167:/TestFile CopyOfFil
