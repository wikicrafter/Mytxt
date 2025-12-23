import subprocess

def change_mac(interface, new_mac):
    print(f"Changing MAC address of {interface} to {new_mac}")

    # Disable the Wi-Fi interface
    subprocess.call(["sudo", "ifconfig", interface, "down"])

    # Change the MAC address
    subprocess.call(["sudo", "ifconfig", interface, "hw", "ether", new_mac])

    # Enable the Wi-Fi interface
    subprocess.call(["sudo", "ifconfig", interface, "up"])

# Example usage
interface = "wlan0"  # Replace with your Wi-Fi interface name
new_mac = "00:11:22:33:44:55"  # Replace with the desired MAC address

change_mac(interface, new_mac)

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

