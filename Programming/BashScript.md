### Clean Temp Files


#!/bin/bash

# Clean temporary files
echo "Cleaning temporary files..."

# Clean the system-wide temporary directory
sudo rm -rf /tmp/*

# Clean the user's temporary directory
rm -rf ~/tmp/*

echo "Temporary files cleaned."


<br>


<hr>

# Performance Optimization 

#!/bin/bash

# Fedora Performance Optimization Script

# Disable unnecessary services
echo "Disabling unnecessary services..."
sudo systemctl disable bluetooth
sudo systemctl disable cups
sudo systemctl disable avahi-daemon
echo "Unnecessary services disabled."

# Optimize systemd for faster boot
echo "Optimizing systemd..."
sudo systemctl mask systemd-rfkill.service
sudo systemctl mask systemd-rfkill.socket
echo "Systemd optimized."

# Adjust swappiness
echo "Adjusting swappiness..."
echo "vm.swappiness = 10" | sudo tee /etc/sysctl.d/99-swappiness.conf
echo "Swappiness adjusted."

# Enable TRIM for SSDs
echo "Enabling TRIM for SSDs..."
sudo systemctl enable fstrim.timer
echo "TRIM enabled."

# Increase the inotify watches limit
echo "Increasing inotify watches limit..."
echo "fs.inotify.max_user_watches=524288" | sudo tee /etc/sysctl.d/99-inotify-watches.conf
sudo sysctl --system
echo "Inotify watches limit increased."

# Disable unnecessary graphical effects
echo "Disabling unnecessary graphical effects..."
gsettings set org.gnome.desktop.interface enable-animations false
gsettings set org.gnome.desktop.interface enable-hot-corners false
echo "Graphical effects disabled."

echo "Performance optimizations complete."

<hr>

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

