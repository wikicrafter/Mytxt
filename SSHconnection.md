# SSH connection 

* Get-Service sshd - sshd is openSSH service

* Start-Service sshd - starts the sshd service

* Get-Service sshd - verifie if sshd service is running 

 > As I wanted the SSH service to start every time the system booted up, I entered:

* Set-Service -Name sshd -StartupType 'Automati

> To check and make sure that the port for the SSH server was open, I entered:

* Get-NetFirewallRule -Name *ssh*

# scp fenton@10.0.0.167:/TestFile CopyOfFil
---
# generate keygen: ssh-keygen -t rsa 

# to copy publick key into server side you can use command: 
## scp .ssh/id_rsa.pub  fenton@10.0.0.167: (publick jey must be on server)

### let's make a shortcat for instance: nano .ssh/config /there write next commands <br>
Host Name
    User UserName
    HostName example.dev
    IdentityFile (Then path to private key like:) ~/.ssh/id_rsa

### (Now you give some name and it will be shortcut)
### ssh example 




## scp alternative for windows is pscp - it's available from putty.com


