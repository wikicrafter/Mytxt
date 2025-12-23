# Fedora Linux Command Reference Guide

A comprehensive guide to essential Fedora Linux commands for system administration and daily use.

---

## Table of Contents
- [Package Management (DNF)](#package-management-dnf)
- [System Management (systemctl)](#system-management-systemctl)
- [System Information](#system-information)
- [Hostname Management (hostnamectl)](#hostname-management-hostnamectl)
- [User & Group Management](#user--group-management)
- [File & Directory Operations](#file--directory-operations)
- [Network Management](#network-management)
- [Firewall Management (firewalld)](#firewall-management-firewalld)
- [SELinux Management](#selinux-management)
- [Disk & Storage Management](#disk--storage-management)
- [Process Management](#process-management)
- [Log Management (journalctl)](#log-management-journalctl)
- [Time & Date Management (timedatectl)](#time--date-management-timedatectl)
- [Performance Monitoring](#performance-monitoring)
- [Archive & Compression](#archive--compression)

---

## Package Management (DNF)

DNF (Dandified YUM) is the default package manager for Fedora.

### Basic Package Operations

```bash
# Update package cache
sudo dnf check-update

# Update all packages
sudo dnf update
sudo dnf upgrade  # Same as update

# Install a package
sudo dnf install package_name

# Install multiple packages
sudo dnf install package1 package2 package3

# Remove a package
sudo dnf remove package_name

# Remove package and dependencies
sudo dnf autoremove package_name

# Reinstall a package
sudo dnf reinstall package_name
```

### Search & Information

```bash
# Search for packages
dnf search keyword

# Get package information
dnf info package_name

# List all installed packages
dnf list installed

# List available packages
dnf list available

# Show package dependencies
dnf repoquery --requires package_name

# Show what package provides a file
dnf provides /path/to/file
```

### Repository Management

```bash
# List enabled repositories
dnf repolist

# List all repositories (enabled and disabled)
dnf repolist --all

# Enable a repository
sudo dnf config-manager --set-enabled repo_name

# Disable a repository
sudo dnf config-manager --set-disabled repo_name

# Add a new repository
sudo dnf config-manager --add-repo repository_url
```

### Package Groups

```bash
# List available groups
dnf group list

# Install a group
sudo dnf group install "Group Name"

# Remove a group
sudo dnf group remove "Group Name"

# Show group information
dnf group info "Group Name"
```

### Advanced DNF Commands

```bash
# Clean cached data
sudo dnf clean all

# Download package without installing
dnf download package_name

# Show command history
dnf history

# Undo last transaction
sudo dnf history undo last

# Redo a transaction
sudo dnf history redo last

# Check for broken dependencies
sudo dnf check

# Mark package as installed by user
sudo dnf mark install package_name
```

---

## System Management (systemctl)

Systemctl is used to manage systemd services and the system state.

### Service Management

```bash
# Start a service
sudo systemctl start service_name

# Stop a service
sudo systemctl stop service_name

# Restart a service
sudo systemctl restart service_name

# Reload service configuration
sudo systemctl reload service_name

# Check service status
systemctl status service_name

# Enable service at boot
sudo systemctl enable service_name

# Disable service at boot
sudo systemctl disable service_name

# Enable and start service
sudo systemctl enable --now service_name

# Disable and stop service
sudo systemctl disable --now service_name

# Check if service is enabled
systemctl is-enabled service_name

# Check if service is active
systemctl is-active service_name
```

### System State Management

```bash
# Reboot the system
sudo systemctl reboot

# Power off the system
sudo systemctl poweroff

# Suspend the system
sudo systemctl suspend

# Hibernate the system
sudo systemctl hibernate

# Rescue mode (single-user mode)
sudo systemctl rescue

# Emergency mode
sudo systemctl emergency
```

### Service Information

```bash
# List all services
systemctl list-units --type=service

# List all active services
systemctl list-units --type=service --state=active

# List all failed services
systemctl list-units --type=service --state=failed

# Show service dependencies
systemctl list-dependencies service_name

# Show service properties
systemctl show service_name

# View service configuration file
systemctl cat service_name
```

### Systemd Targets (Runlevels)

```bash
# Get current target
systemctl get-default

# Set default target
sudo systemctl set-default multi-user.target

# List all targets
systemctl list-units --type=target

# Switch to graphical target
sudo systemctl isolate graphical.target

# Switch to multi-user target (no GUI)
sudo systemctl isolate multi-user.target
```

---

## System Information

### Hardware Information

```bash
# Display system information
hostnamectl

# Show CPU information
lscpu

# Show memory information
free -h

# Show detailed memory info
cat /proc/meminfo

# Display PCI devices
lspci

# Display USB devices
lsusb

# Show block devices
lsblk

# Display hardware information
sudo dmidecode

# Show BIOS information
sudo dmidecode -t bios

# Show system manufacturer
sudo dmidecode -s system-manufacturer
```

### System Details

```bash
# Kernel version
uname -r

# All system information
uname -a

# OS release information
cat /etc/os-release

# Fedora version
cat /etc/fedora-release

# System uptime
uptime

# Current date and time
date

# Show system architecture
arch
```

---

## Hostname Management (hostnamectl)

Manage system hostname and related settings.

### Basic Hostname Operations

```bash
# Show current hostname and system info
hostnamectl

# Show only hostname
hostnamectl hostname

# Set hostname (all types)
sudo hostnamectl set-hostname new-hostname

# Set pretty hostname (with spaces/special chars)
sudo hostnamectl set-hostname "My Fedora Server" --pretty

# Set static hostname
sudo hostnamectl set-hostname fedora-server --static

# Set transient hostname (temporary)
sudo hostnamectl set-hostname temp-name --transient
```

### System Information via hostnamectl

```bash
# Show chassis type
hostnamectl chassis

# Set chassis type
sudo hostnamectl set-chassis laptop
# Options: desktop, laptop, server, tablet, handset, vm, container

# Show deployment environment
hostnamectl deployment

# Set deployment
sudo hostnamectl set-deployment production

# Show location
hostnamectl location

# Set location
sudo hostnamectl set-location "Data Center A"
```

### Icon and Machine ID

```bash
# Set icon name
sudo hostnamectl set-icon-name computer-laptop

# Show machine ID
hostnamectl machine-id

# Show boot ID
hostnamectl boot-id
```

---

## User & Group Management

### User Operations

```bash
# Add a new user
sudo useradd username

# Add user with home directory
sudo useradd -m username

# Add user with specific shell
sudo useradd -m -s /bin/bash username

# Set user password
sudo passwd username

# Change your own password
passwd

# Delete a user
sudo userdel username

# Delete user and home directory
sudo userdel -r username

# Modify user properties
sudo usermod -c "Full Name" username

# Lock a user account
sudo usermod -L username

# Unlock a user account
sudo usermod -U username

# Change user's shell
sudo usermod -s /bin/zsh username

# Set account expiration date
sudo usermod -e 2024-12-31 username
```

### Group Operations

```bash
# Create a new group
sudo groupadd groupname

# Delete a group
sudo groupdel groupname

# Add user to group
sudo usermod -aG groupname username

# Add user to multiple groups
sudo usermod -aG group1,group2,group3 username

# Remove user from group
sudo gpasswd -d username groupname

# List all groups
cat /etc/group

# Show user's groups
groups username

# Show current user's groups
groups
```

### User Information

```bash
# Show current user
whoami

# Show logged in users
who

# Show what users are doing
w

# Show last logged in users
last

# Show failed login attempts
sudo lastb

# Display user ID and group ID
id username

# Show user information
finger username
```

---

## File & Directory Operations

### Basic Operations

```bash
# List files
ls
ls -l      # Long format
ls -lh     # Human-readable sizes
ls -la     # Include hidden files
ls -ltr    # Sort by time, reverse

# Change directory
cd /path/to/directory
cd ~       # Home directory
cd -       # Previous directory
cd ..      # Parent directory

# Print working directory
pwd

# Create directory
mkdir dirname

# Create nested directories
mkdir -p parent/child/grandchild

# Remove empty directory
rmdir dirname

# Remove directory and contents
rm -r dirname

# Remove forcefully
rm -rf dirname
```

### File Operations

```bash
# Create empty file
touch filename

# Copy file
cp source destination

# Copy directory recursively
cp -r source_dir destination_dir

# Copy preserving attributes
cp -p source destination

# Move/rename file
mv source destination

# Remove file
rm filename

# Remove multiple files
rm file1 file2 file3

# Find files
find /path -name "filename"

# Find files by type
find /path -type f  # Files only
find /path -type d  # Directories only
```

### File Viewing & Editing

```bash
# View file contents
cat filename

# View file with pagination
less filename
more filename

# View first 10 lines
head filename

# View last 10 lines
tail filename

# Follow file updates (logs)
tail -f filename

# Edit with nano
nano filename

# Edit with vim
vim filename

# Edit with vi
vi filename
```

### File Permissions

```bash
# Change permissions (numeric)
chmod 755 filename
chmod 644 filename

# Change permissions (symbolic)
chmod u+x filename      # Add execute for user
chmod g-w filename      # Remove write for group
chmod o+r filename      # Add read for others
chmod a+x filename      # Add execute for all

# Change ownership
sudo chown user:group filename

# Change ownership recursively
sudo chown -R user:group directory

# Change group only
sudo chgrp groupname filename
```

### File Information

```bash
# Show file type
file filename

# Show file statistics
stat filename

# Calculate file checksum
md5sum filename
sha256sum filename

# Show disk usage
du -sh directory

# Show disk usage of all items
du -h --max-depth=1

# Show file system disk space
df -h
```

---

## Network Management

### Network Configuration (nmcli)

```bash
# Show network status
nmcli general status

# Show all connections
nmcli connection show

# Show active connections
nmcli connection show --active

# Show device status
nmcli device status

# Connect to WiFi
nmcli device wifi connect SSID password PASSWORD

# List available WiFi networks
nmcli device wifi list

# Disconnect interface
nmcli device disconnect interface_name

# Bring interface up
sudo nmcli connection up connection_name

# Bring interface down
sudo nmcli connection down connection_name
```

### IP Configuration

```bash
# Show IP addresses
ip addr show
ip a

# Show specific interface
ip addr show eth0

# Show routing table
ip route show

# Add IP address
sudo ip addr add 192.168.1.100/24 dev eth0

# Delete IP address
sudo ip addr del 192.168.1.100/24 dev eth0

# Show network interfaces
ip link show

# Bring interface up
sudo ip link set eth0 up

# Bring interface down
sudo ip link set eth0 down
```

### Network Testing

```bash
# Ping a host
ping google.com
ping -c 4 google.com  # Send 4 packets

# Trace route to host
traceroute google.com

# Show network statistics
netstat -tuln

# Show listening ports
ss -tuln

# Show established connections
ss -tun

# DNS lookup
nslookup google.com
dig google.com

# Show hostname
hostname

# Show hostname IP
hostname -I
```

### Network Tools

```bash
# Download file
wget https://example.com/file

# Download with curl
curl -O https://example.com/file

# Test network speed
speedtest-cli

# Scan network
sudo nmap 192.168.1.0/24

# Show ARP table
arp -a
ip neigh show

# Flush DNS cache
sudo systemd-resolve --flush-caches
```

---

## Firewall Management (firewalld)

### Basic Firewall Operations

```bash
# Check firewall status
sudo firewall-cmd --state

# Start firewall
sudo systemctl start firewalld

# Stop firewall
sudo systemctl stop firewalld

# Enable firewall at boot
sudo systemctl enable firewalld

# Reload firewall
sudo firewall-cmd --reload

# Get default zone
sudo firewall-cmd --get-default-zone

# Set default zone
sudo firewall-cmd --set-default-zone=public
```

### Zone Management

```bash
# List all zones
sudo firewall-cmd --get-zones

# List active zones
sudo firewall-cmd --get-active-zones

# Show zone information
sudo firewall-cmd --zone=public --list-all

# Add interface to zone
sudo firewall-cmd --zone=public --add-interface=eth0

# Change interface zone
sudo firewall-cmd --zone=home --change-interface=eth0
```

### Service & Port Management

```bash
# List allowed services
sudo firewall-cmd --list-services

# Add service
sudo firewall-cmd --add-service=http
sudo firewall-cmd --add-service=https

# Add service permanently
sudo firewall-cmd --permanent --add-service=http

# Remove service
sudo firewall-cmd --remove-service=http

# Add port
sudo firewall-cmd --add-port=8080/tcp

# Add port permanently
sudo firewall-cmd --permanent --add-port=8080/tcp

# Remove port
sudo firewall-cmd --remove-port=8080/tcp

# List open ports
sudo firewall-cmd --list-ports
```

### Advanced Firewall Rules

```bash
# Add rich rule
sudo firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.168.1.0/24" accept'

# Block IP address
sudo firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.168.1.100" reject'

# Allow specific IP to specific port
sudo firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.168.1.50" port port="22" protocol="tcp" accept'

# List rich rules
sudo firewall-cmd --list-rich-rules

# Enable masquerading (NAT)
sudo firewall-cmd --add-masquerade

# Port forwarding
sudo firewall-cmd --add-forward-port=port=80:proto=tcp:toport=8080
```

---

## SELinux Management

### SELinux Status

```bash
# Check SELinux status
sestatus

# Get SELinux mode
getenforce

# Set SELinux to permissive (temporary)
sudo setenforce 0

# Set SELinux to enforcing (temporary)
sudo setenforce 1

# Set SELinux mode permanently
sudo nano /etc/selinux/config
# Change SELINUX=enforcing or SELINUX=permissive or SELINUX=disabled
```

### SELinux Contexts

```bash
# Show file SELinux context
ls -Z filename

# Show process SELinux context
ps -eZ

# Restore default context
sudo restorecon -v filename

# Restore context recursively
sudo restorecon -Rv /path/to/directory

# Change file context
sudo chcon -t httpd_sys_content_t /var/www/html/index.html

# Set context permanently
sudo semanage fcontext -a -t httpd_sys_content_t "/var/www/html(/.*)?"
```

### SELinux Booleans

```bash
# List all booleans
getsebool -a

# Get specific boolean
getsebool httpd_can_network_connect

# Set boolean temporarily
sudo setsebool httpd_can_network_connect on

# Set boolean permanently
sudo setsebool -P httpd_can_network_connect on
```

### SELinux Troubleshooting

```bash
# View SELinux denials
sudo ausearch -m avc -ts recent

# Generate SELinux policy
sudo audit2allow -a

# Create and install policy module
sudo audit2allow -a -M mypolicy
sudo semodule -i mypolicy.pp

# List loaded modules
sudo semodule -l
```

---

## Disk & Storage Management

### Disk Information

```bash
# Show disk usage
df -h

# Show disk usage by filesystem type
df -hT

# Show inode usage
df -i

# Show disk partitions
sudo fdisk -l

# Show partition table
sudo parted -l

# Show block devices
lsblk

# Show block devices with filesystem
lsblk -f
```

### Partition Management

```bash
# Interactive partition tool
sudo fdisk /dev/sda

# GPT partition tool
sudo gdisk /dev/sda

# Partition editor
sudo parted /dev/sda

# Create partition
sudo parted /dev/sda mkpart primary ext4 0% 100%

# Delete partition
sudo parted /dev/sda rm 1
```

### Filesystem Operations

```bash
# Create ext4 filesystem
sudo mkfs.ext4 /dev/sda1

# Create XFS filesystem
sudo mkfs.xfs /dev/sda1

# Create Btrfs filesystem
sudo mkfs.btrfs /dev/sda1

# Check filesystem
sudo fsck /dev/sda1

# Check ext4 filesystem
sudo e2fsck /dev/sda1

# Label filesystem
sudo e2label /dev/sda1 MyLabel

# Show filesystem UUID
sudo blkid /dev/sda1
```

### Mount Operations

```bash
# Mount filesystem
sudo mount /dev/sda1 /mnt

# Mount with options
sudo mount -o ro /dev/sda1 /mnt

# Unmount filesystem
sudo umount /mnt

# Show mounted filesystems
mount

# Remount read-write
sudo mount -o remount,rw /mnt

# Edit fstab for permanent mounts
sudo nano /etc/fstab
```

### LVM Management

```bash
# Show physical volumes
sudo pvdisplay

# Show volume groups
sudo vgdisplay

# Show logical volumes
sudo lvdisplay

# Create physical volume
sudo pvcreate /dev/sda1

# Create volume group
sudo vgcreate vg_name /dev/sda1

# Create logical volume
sudo lvcreate -L 10G -n lv_name vg_name

# Extend logical volume
sudo lvextend -L +5G /dev/vg_name/lv_name

# Resize filesystem
sudo resize2fs /dev/vg_name/lv_name
```

---

## Process Management

### Process Viewing

```bash
# Show all processes
ps aux

# Show process tree
ps auxf
pstree

# Show processes for current user
ps ux

# Interactive process viewer
top

# Better top alternative
htop

# Show processes by CPU usage
ps aux --sort=-%cpu | head

# Show processes by memory usage
ps aux --sort=-%mem | head
```

### Process Control

```bash
# Kill process by PID
kill PID

# Force kill process
kill -9 PID

# Kill process by name
killall process_name

# Kill all processes by user
sudo killall -u username

# Send signal to process
kill -SIGNAL PID

# Show process by name
pgrep process_name

# Kill process by name (better)
pkill process_name
```

### Background & Foreground

```bash
# Run command in background
command &

# List background jobs
jobs

# Bring job to foreground
fg %1

# Send job to background
bg %1

# Disown job (keep running after logout)
disown %1

# Run command immune to hangups
nohup command &
```

### Process Priority

```bash
# Run with lower priority
nice -n 10 command

# Change priority of running process
renice -n 5 -p PID

# Show process priority
ps -eo pid,ni,comm
```

---

## Log Management (journalctl)

### Basic Log Viewing

```bash
# View all logs
sudo journalctl

# View logs from current boot
sudo journalctl -b

# View logs from previous boot
sudo journalctl -b -1

# Follow logs in real-time
sudo journalctl -f

# Show last 100 lines
sudo journalctl -n 100

# Show logs with priority
sudo journalctl -p err
```

### Filter by Service/Unit

```bash
# Show logs for specific service
sudo journalctl -u service_name

# Show logs for multiple services
sudo journalctl -u service1 -u service2

# Follow service logs
sudo journalctl -u service_name -f

# Show kernel messages
sudo journalctl -k
```

### Time-based Filtering

```bash
# Show logs since specific time
sudo journalctl --since "2024-01-01 00:00:00"

# Show logs until specific time
sudo journalctl --until "2024-01-01 23:59:59"

# Show logs from last hour
sudo journalctl --since "1 hour ago"

# Show logs from today
sudo journalctl --since today

# Show logs from yesterday
sudo journalctl --since yesterday --until today
```

### Advanced Journalctl

```bash
# Show disk usage
sudo journalctl --disk-usage

# Vacuum logs older than 2 weeks
sudo journalctl --vacuum-time=2weeks

# Vacuum logs to 500MB
sudo journalctl --vacuum-size=500M

# Verify log integrity
sudo journalctl --verify

# Export logs to JSON
sudo journalctl -o json

# Show logs in verbose mode
sudo journalctl -o verbose
```

---

## Time & Date Management (timedatectl)

### Time & Date Operations

```bash
# Show current time and date
timedatectl

# Show time status
timedatectl status

# Set date and time
sudo timedatectl set-time "2024-01-01 12:00:00"

# Set date only
sudo timedatectl set-time "2024-01-01"

# Set time only
sudo timedatectl set-time "12:00:00"
```

### Timezone Management

```bash
# List available timezones
timedatectl list-timezones

# Set timezone
sudo timedatectl set-timezone America/New_York

# Set timezone to UTC
sudo timedatectl set-timezone UTC

# Show current timezone
timedatectl | grep "Time zone"
```

### NTP Configuration

```bash
# Enable NTP synchronization
sudo timedatectl set-ntp true

# Disable NTP synchronization
sudo timedatectl set-ntp false

# Check NTP status
timedatectl show-timesync --all

# Show NTP servers
timedatectl timesync-status
```

### Hardware Clock

```bash
# Set hardware clock to UTC
sudo timedatectl set-local-rtc 0

# Set hardware clock to local time
sudo timedatectl set-local-rtc 1

# Show hardware clock setting
timedatectl | grep "RTC"
```

---

## Performance Monitoring

### System Monitoring

```bash
# System resource usage
top
htop

# I/O statistics
iostat

# Virtual memory statistics
vmstat

# Network statistics
netstat -s

# Disk I/O statistics
sudo iotop

# Process I/O usage
sudo pidstat

# System activity report
sar
```

### Memory Monitoring

```bash
# Show memory usage
free -h

# Detailed memory info
cat /proc/meminfo

# Show swap usage
swapon --show

# Clear cache (safe)
sudo sync; echo 3 | sudo tee /proc/sys/vm/drop_caches
```

### CPU Monitoring

```bash
# Show CPU info
lscpu

# CPU usage per core
mpstat -P ALL

# Show load average
uptime

# Detailed CPU stats
cat /proc/cpuinfo
```

---

## Archive & Compression

### Tar Archives

```bash
# Create tar archive
tar -cvf archive.tar directory/

# Create compressed tar.gz
tar -czvf archive.tar.gz directory/

# Create compressed tar.bz2
tar -cjvf archive.tar.bz2 directory/

# Extract tar archive
tar -xvf archive.tar

# Extract tar.gz
tar -xzvf archive.tar.gz

# Extract tar.bz2
tar -xjvf archive.tar.bz2

# List archive contents
tar -tvf archive.tar

# Extract to specific directory
tar -xzvf archive.tar.gz -C /path/to/directory
```

### Compression Tools

```bash
# Compress with gzip
gzip filename

# Decompress gzip
gunzip filename.gz

# Compress with bzip2
bzip2 filename

# Decompress bzip2
bunzip2 filename.bz2

# Compress with xz
xz filename

# Decompress xz
unxz filename.xz

# Create zip archive
zip -r archive.zip directory/

# Extract zip archive
unzip archive.zip
```

---

## Quick Reference

### Most Used Commands

```bash
# System update
sudo dnf update -y

# Install package
sudo dnf install package_name

# Restart service
sudo systemctl restart service_name

# Check service status
systemctl status service_name

# View logs
sudo journalctl -u service_name -f

# Check disk space
df -h

# Check memory
free -h

# Check processes
top

# Network status
ip a

# Firewall status
sudo firewall-cmd --list-all
```

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨
