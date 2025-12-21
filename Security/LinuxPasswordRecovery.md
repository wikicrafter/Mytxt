# Linux Password Recovery Guide

A comprehensive, beginner-friendly guide for recovering/resetting passwords on various Linux distributions.

> [!CAUTION]
> These procedures require physical access to the machine. Always ensure you have proper authorization before attempting password recovery on any system.

---

## Table of Contents
- [Ubuntu/Debian-based Systems](#ubuntudebian-based-systems)
- [Fedora/RHEL/CentOS](#fedorарhelcentos)
- [Arch Linux](#arch-linux)
- [openSUSE](#opensuse)
- [Gentoo](#gentoo)
- [Alpine Linux](#alpine-linux)
- [General Methods](#general-methods)
- [Troubleshooting](#troubleshooting)

---

## Ubuntu/Debian-based Systems

### Method 1: Recovery Mode (Easiest for Beginners)

This is the simplest method for Ubuntu and Debian-based systems.

#### Step 1: Access the GRUB Menu

1. **Restart your computer**

2. **Immediately after the BIOS/manufacturer logo disappears**, hold down the `Shift` key (for BIOS systems) or repeatedly tap the `Esc` key (for UEFI systems)

3. You should see a **black screen with white text** showing boot options - this is the GRUB menu

4. **Use the arrow keys** to select "Advanced options for Ubuntu" (or your distribution name)

5. Press `Enter`

#### Step 2: Enter Recovery Mode

1. You'll see a list of kernel versions with "(recovery mode)" next to some entries

2. **Select the top entry** that says "(recovery mode)" using the arrow keys

3. Press `Enter`

4. Wait for the system to load - you'll see text scrolling on the screen

#### Step 3: Access Root Shell

1. You'll see a **Recovery Menu** with several options

2. **Use the arrow keys** to select "root - Drop to root shell prompt"

3. Press `Enter`

4. You might be asked to press `Enter` again to continue - do so

5. You should now see a command prompt that looks like: `root@hostname:~#`

#### Step 4: Make the Filesystem Writable

The filesystem is currently read-only, so we need to make it writable:

1. **Type this command exactly** and press Enter:
   ```bash
   mount -o remount,rw /
   ```

2. You won't see any output if it worked - that's normal!

#### Step 5: Reset Your Password

1. **Type the following command** and press Enter:
   ```bash
   passwd your_username
   ```
   Replace `your_username` with your actual Ubuntu username (the name you use to log in)

2. **For the root password**, just type:
   ```bash
   passwd
   ```

3. **Enter your new password** when prompted

   > [!NOTE]
   > You won't see any characters (not even dots or stars) while typing your password. This is a security feature - just type carefully and press Enter!

4. **Type the same password again** to confirm

5. You should see: "password updated successfully"

#### Step 6: Reboot

1. **Type this command** to restart:
   ```bash
   reboot -f
   ```

2. Your computer will restart, and you can now log in with your new password!

---

### Method 2: GRUB Edit Mode (Alternative Method)

This method gives you more control but requires editing boot parameters.

#### Step 1: Access GRUB Menu

1. **Restart your computer**

2. **Hold `Shift`** (BIOS) or tap `Esc` repeatedly (UEFI) to see the GRUB menu

3. **Highlight the Ubuntu entry** (usually the first one) but **don't press Enter yet**

#### Step 2: Edit the Boot Entry

1. **Press the `e` key** (for "edit")

2. You'll see several lines of code - don't panic! We only need to change one line

3. **Use the arrow keys** to find the line that starts with `linux` or `linuxefi`
   - It's usually near the middle of the screen
   - It will have words like `quiet splash` at the end

4. **Move your cursor to the end of that line** (use the `End` key or arrow keys)

5. **Add a space, then type:**
   ```
   init=/bin/bash
   ```
   The end of the line should now look like: `quiet splash init=/bin/bash`

   > [!TIP]
   > If you make a mistake, press `Esc` to cancel and start over

#### Step 3: Boot with Modified Settings

1. **Press `Ctrl+X`** or **`F10`** to boot with these temporary changes

2. Wait a few seconds - you'll see a command prompt appear

#### Step 4: Make Filesystem Writable

1. **Type this command** and press Enter:
   ```bash
   mount -o remount,rw /
   ```

#### Step 5: Change Your Password

1. **Type:**
   ```bash
   passwd your_username
   ```
   (Replace `your_username` with your actual username)

2. **Enter your new password twice**

#### Step 6: Reboot Properly

1. **Type:**
   ```bash
   sync
   exec /sbin/init
   ```

2. The system will continue booting normally

3. Log in with your new password!

---

## Fedora/RHEL/CentOS

### Method 1: Beginner-Friendly Fedora Guide (Recommended)

This method works for Fedora 20+ and is explained in detail for beginners.

#### Step 1: Access the GRUB Menu

1. **Restart your computer**

2. **As soon as the manufacturer logo disappears** (Lenovo, Dell, HP, etc.), **tap the `Esc` key repeatedly** or **hold `Shift`**

3. You should see a **black screen with a list of Fedora versions** - this is the GRUB menu

4. **Make sure the top (default) Fedora entry is highlighted**

5. **Press `e`** to edit it

#### Step 2: Edit the Boot Parameters

1. You'll see several lines of code on the screen

2. **Use the arrow keys** to find the line starting with `linux`, `linux16`, or `linuxefi`
   - This line is usually in the middle of the screen
   - It's often the longest line

3. **Move your cursor to the end of that line** (use the `End` key)

4. **Look for the words `rhgb quiet`** near the end

5. **Delete `rhgb quiet`** (use Backspace) and **type:**
   ```
   rw init=/bin/bash
   ```

   > [!TIP]
   > If you can't find `rhgb quiet`, just add `rw init=/bin/bash` to the very end of the line

6. **Press `Ctrl+X`** or **`F10`** to boot

#### Step 3: Reset the Password

1. Your computer will boot into a **command prompt** (white text on black background)

2. **Type this command** and press Enter:
   ```bash
   passwd your_username
   ```
   - Replace `your_username` with your actual Fedora username
   - For root password, just type `passwd`

3. **Enter your new password twice**

   > [!NOTE]
   > You won't see any characters while typing - this is normal and secure!

#### Step 4: Fix SELinux (Very Important!)

Fedora uses SELinux security. If you skip this step, your new password might not work!

1. **Type this command exactly:**
   ```bash
   touch /.autorelabel
   ```

2. **Reboot by typing:**
   ```bash
   /sbin/reboot -f
   ```

#### What Happens Next

1. **Your computer will restart**

2. **You'll see "SELinux is relabeling"** - this is normal!
   - This process takes **2-5 minutes**
   - Your computer might restart again automatically
   - Don't turn off your computer during this process

3. **Once finished**, you'll see the normal login screen

4. **Log in with your new password** - you're done!

> [!WARNING]
> **Encrypted Disk?** If you enter a password immediately when you turn on your computer (before seeing the Fedora logo), your disk is encrypted. You'll still need that encryption password - this guide only resets your user login password.

---

### Method 2: Advanced Fedora Method (rd.break)

This is the official Fedora method for advanced users.

#### Step 1: Access GRUB and Edit

1. **Reboot** and **interrupt GRUB** (tap any key during countdown)

2. **Press `e`** to edit the boot entry

3. **Find the line starting with `linux`**

4. **Add to the end:**
   ```
   rd.break
   ```

5. **Press `Ctrl+X`** to boot

#### Step 2: Remount and Access System

1. You'll see a `switch_root:/#` prompt

2. **Type:**
   ```bash
   mount -o remount,rw /sysroot
   ```

3. **Then type:**
   ```bash
   chroot /sysroot
   ```

#### Step 3: Reset Password and Fix SELinux

1. **Reset password:**
   ```bash
   passwd username
   ```

2. **Relabel for SELinux:**
   ```bash
   touch /.autorelabel
   ```

3. **Exit and reboot:**
   ```bash
   exit
   reboot
   ```

4. **Wait for SELinux relabeling** (2-5 minutes)

---

### Method 3: Older RHEL/CentOS 7

For older Red Hat Enterprise Linux and CentOS systems.

#### Step 1: Edit GRUB

1. **Access GRUB menu** and press `e`

2. **Find the line starting with `linux16`**

3. **Replace `ro` with:**
   ```
   rw init=/sysroot/bin/sh
   ```

4. **Press `Ctrl+X`** to boot

#### Step 2: Reset Password

1. **Access the system:**
   ```bash
   chroot /sysroot
   ```

2. **Change password:**
   ```bash
   passwd username
   ```

3. **Fix SELinux:**
   ```bash
   touch /.autorelabel
   ```

4. **Reboot:**
   ```bash
   exit
   reboot -f
   ```

---

## Arch Linux

### Method 1: GRUB Edit (Quick Method)

Perfect for Arch Linux users who need quick password recovery.

#### Step 1: Access GRUB Menu

1. **Restart your computer**

2. **When you see the GRUB menu**, highlight the Arch Linux entry

3. **Press `e`** to edit

#### Step 2: Modify Boot Parameters

1. **Find the line starting with `linux`**
   - It usually contains `/vmlinuz-linux`

2. **Go to the end of that line** (press `End`)

3. **Add:**
   ```
   init=/bin/bash
   ```

4. **Press `Ctrl+X`** to boot

#### Step 3: Make Filesystem Writable

1. You'll see a command prompt: `bash-5.x#`

2. **Type:**
   ```bash
   mount -n -o remount,rw /
   ```

   > [!NOTE]
   > The `-n` flag is important for Arch - it prevents writing to `/etc/mtab`

#### Step 4: Change Password

1. **Type:**
   ```bash
   passwd your_username
   ```

2. **Enter your new password twice**

#### Step 5: Reboot

1. **Type:**
   ```bash
   exec /sbin/init
   ```

2. The system will continue booting normally

3. **Log in with your new password!**

---

### Method 2: Live USB (More Reliable)

Use this if the GRUB method doesn't work.

#### Step 1: Boot from Arch Live USB

1. **Insert your Arch Linux USB** (or create one from another computer)

2. **Restart** and **boot from USB**
   - Usually press `F12`, `F2`, or `Del` during startup to access boot menu

3. **Wait for the Arch Linux prompt** to appear

#### Step 2: Find Your Root Partition

1. **Type:**
   ```bash
   lsblk
   ```

2. **Look for your root partition** - it's usually the largest partition
   - Example: `/dev/sda2` or `/dev/nvme0n1p2`
   - Note the device name

#### Step 3: Mount and Access Your System

1. **Mount your root partition** (replace `sdXY` with your partition):
   ```bash
   mount /dev/sdXY /mnt
   ```
   Example: `mount /dev/sda2 /mnt`

2. **Enter your system:**
   ```bash
   arch-chroot /mnt
   ```

#### Step 4: Reset Password

1. **Type:**
   ```bash
   passwd your_username
   ```

2. **Enter new password twice**

#### Step 5: Exit and Reboot

1. **Type:**
   ```bash
   exit
   ```

2. **Unmount:**
   ```bash
   umount /mnt
   ```

3. **Reboot:**
   ```bash
   reboot
   ```

4. **Remove the USB** when the computer restarts

5. **Log in with your new password!**

---

## openSUSE

### Method 1: YaST Rescue System (Easiest)

openSUSE has a built-in rescue system that makes password recovery easy.

#### Step 1: Access Rescue System

1. **Restart your computer**

2. **Access the GRUB menu** (tap `Esc` or hold `Shift`)

3. **Select "Advanced Options"**

4. **Choose "Start Rescue System"**

5. Press `Enter` and wait for the rescue system to load

#### Step 2: Mount Your System

1. **Find your root partition:**
   ```bash
   lsblk
   ```

2. **Mount it** (replace `sdXY`):
   ```bash
   mount /dev/sdXY /mnt
   ```

#### Step 3: Access Your System

1. **Type:**
   ```bash
   chroot /mnt
   ```

2. You're now inside your installed system!

#### Step 4: Reset Password

1. **Type:**
   ```bash
   passwd your_username
   ```

2. **Enter new password twice**

#### Step 5: Exit and Reboot

1. **Type:**
   ```bash
   exit
   reboot
   ```

2. **Log in with your new password!**

---

### Method 2: GRUB Edit

Quick alternative for openSUSE.

#### Step 1: Edit GRUB

1. **Access GRUB menu** and press `e`

2. **Find the `linux` line**

3. **Add to the end:**
   ```
   init=/bin/bash
   ```

4. **Press `Ctrl+X`**

#### Step 2: Reset Password

1. **Make filesystem writable:**
   ```bash
   mount -o remount,rw /
   ```

2. **Change password:**
   ```bash
   passwd your_username
   ```

3. **Reboot:**
   ```bash
   reboot -f
   ```

---

## Gentoo

Gentoo password recovery requires a Live CD/USB.

### Step 1: Boot from Gentoo Live Media

1. **Insert Gentoo Live CD/USB**

2. **Boot from it** (press `F12` or `Del` during startup)

3. **Wait for the Gentoo prompt**

### Step 2: Mount Your System

1. **Find your root partition:**
   ```bash
   lsblk
   ```

2. **Mount it:**
   ```bash
   mount /dev/sdXY /mnt/gentoo
   ```
   Replace `sdXY` with your root partition

### Step 3: Mount Boot (If Separate)

If you have a separate `/boot` partition:

```bash
mount /dev/sdXZ /mnt/gentoo/boot
```

### Step 4: Enter Your System

1. **Chroot into your system:**
   ```bash
   chroot /mnt/gentoo /bin/bash
   source /etc/profile
   ```

2. You're now inside your installed Gentoo system

### Step 5: Reset Password

1. **Type:**
   ```bash
   passwd your_username
   ```

2. **Enter new password twice**

### Step 6: Exit and Reboot

1. **Exit chroot:**
   ```bash
   exit
   ```

2. **Unmount partitions:**
   ```bash
   umount -l /mnt/gentoo/boot
   umount -l /mnt/gentoo
   ```

3. **Reboot:**
   ```bash
   reboot
   ```

4. **Remove the Live media**

5. **Log in with your new password!**

---

## Alpine Linux

Alpine is a lightweight distribution often used in containers and embedded systems.

### Step 1: Access GRUB

1. **Restart** and **press `e`** at the boot menu

### Step 2: Edit Boot Parameters

1. **Find the kernel line** (starts with `linux`)

2. **Add to the end:**
   ```
   init=/bin/sh
   ```

3. **Press `Ctrl+X`** to boot

### Step 3: Make Filesystem Writable

1. **Type:**
   ```bash
   mount -o remount,rw /
   ```

### Step 4: Change Password

1. **Type:**
   ```bash
   passwd your_username
   ```

2. **Enter new password twice**

### Step 5: Reboot

1. **Type:**
   ```bash
   sync
   reboot -f
   ```

2. **Log in with your new password!**

---

## General Methods

### Universal Method: Live USB/CD

This method works for **ANY Linux distribution** - it's your universal backup plan!

#### Step 1: Get a Live USB

1. **Download a Linux ISO** (Ubuntu, Fedora, etc.) on another computer

2. **Create a bootable USB** using:
   - **Rufus** (Windows)
   - **Etcher** (Windows/Mac/Linux)
   - **dd** command (Linux)

#### Step 2: Boot from Live USB

1. **Insert the USB** into your computer

2. **Restart** and **access boot menu**:
   - Common keys: `F12`, `F2`, `F9`, `Del`, `Esc`
   - Look for "Boot Menu" or "Boot Options"

3. **Select your USB drive** from the list

4. **Choose "Try Ubuntu"** (or equivalent) - don't install!

5. **Wait for the desktop** to appear

#### Step 3: Find Your Root Partition

1. **Open a terminal** (usually `Ctrl+Alt+T`)

2. **Type:**
   ```bash
   lsblk
   ```

3. **Identify your root partition:**
   - Look for the largest partition (usually 20GB+)
   - Common names: `/dev/sda1`, `/dev/sda2`, `/dev/nvme0n1p2`
   - Note the name!

   > [!TIP]
   > If you see `[SWAP]`, that's not it - keep looking!

#### Step 4: Mount Your System

1. **Create a mount point:**
   ```bash
   sudo mkdir -p /mnt
   ```

2. **Mount your root partition** (replace `sdXY`):
   ```bash
   sudo mount /dev/sdXY /mnt
   ```
   Example: `sudo mount /dev/sda2 /mnt`

3. **If you have a separate `/boot` partition**, mount it too:
   ```bash
   sudo mount /dev/sdXZ /mnt/boot
   ```

#### Step 5: Mount System Directories

These commands connect important system directories:

```bash
sudo mount --bind /dev /mnt/dev
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys
```

> [!NOTE]
> Copy and paste these commands one by one - they're important!

#### Step 6: Enter Your System

1. **Type:**
   ```bash
   sudo chroot /mnt
   ```

2. You're now inside your installed system!

#### Step 7: Reset Password

1. **Type:**
   ```bash
   passwd your_username
   ```
   Replace `your_username` with your actual username

2. **Enter new password twice**

3. You should see: "password updated successfully"

#### Step 8: Clean Up and Reboot

1. **Exit chroot:**
   ```bash
   exit
   ```

2. **Unmount everything:**
   ```bash
   sudo umount /mnt/sys
   sudo umount /mnt/proc
   sudo umount /mnt/dev
   sudo umount /mnt/boot
   sudo umount /mnt
   ```

3. **Reboot:**
   ```bash
   sudo reboot
   ```

4. **Remove the USB** when the computer restarts

5. **Log in with your new password!**

---

### Single User Mode (If Available)

Some distributions support single user mode.

#### Step 1: Edit GRUB

1. **Access GRUB menu** and press `e`

2. **Find the `linux` line**

3. **Add to the end:**
   ```
   single
   ```
   Or:
   ```
   systemd.unit=rescue.target
   ```

4. **Press `Ctrl+X`**

#### Step 2: Reset Password

1. You'll boot into a minimal system

2. **Type:**
   ```bash
   passwd your_username
   ```

3. **Reboot:**
   ```bash
   reboot
   ```

---

## Troubleshooting

### Problem: "Authentication token manipulation error"

**What it means:** The filesystem is read-only

**Solution:**
```bash
mount -o remount,rw /
```

Then try changing the password again.

---

### Problem: SELinux prevents login after password reset

**What it means:** SELinux security labels are incorrect

**Solution 1 - Relabel (Recommended):**
```bash
touch /.autorelabel
reboot
```

Wait 2-5 minutes for relabeling to complete.

**Solution 2 - Temporary Disable:**
```bash
setenforce 0
```

> [!WARNING]
> This temporarily disables SELinux security - use Solution 1 instead!

---

### Problem: GRUB is password protected

**What it means:** Someone secured GRUB with a password

**Solution:** Use the Live USB/CD method instead - it bypasses GRUB entirely.

---

### Problem: Encrypted /home directory

**What it means:** Your home folder is encrypted with your old password

**Important:** Changing your password will make your encrypted files inaccessible!

**Solution:**

**If you remember the old password:**
1. Boot normally with old password
2. Decrypt home directory
3. Change password
4. Re-encrypt with new password

**If you forgot the old password:**
1. Boot from Live USB
2. Use `ecryptfs-recover-private` tool
3. You'll need the encryption passphrase (different from login password)

---

### Problem: Full disk encryption (LUKS)

**What it means:** Your entire disk is encrypted

**Signs:**
- You enter a password immediately when turning on the computer
- Before you see any logos or boot screens

**Important:** You **MUST** know the encryption password to access the system.

**Solution:** If you forgot the encryption password, password recovery is **impossible** without the encryption key. This is by design for security.

---

### Problem: Can't find root partition

**What it means:** You're not sure which partition contains your Linux installation

**Solution:**

1. **List all partitions:**
   ```bash
   lsblk -f
   ```

2. **Look for:**
   - Filesystem types: `ext4`, `xfs`, `btrfs`
   - Large sizes (20GB+)
   - Labels with your distribution name

3. **Example output:**
   ```
   NAME   FSTYPE SIZE MOUNTPOINT
   sda2   ext4   50G  /
   ```
   In this case, `/dev/sda2` is your root partition

---

### Problem: System won't boot after password reset

**What it means:** File permissions might be wrong

**Solution:**

1. **Boot from Live USB**

2. **Mount your system** (see Live USB method above)

3. **Fix `/etc/shadow` permissions:**
   ```bash
   sudo chroot /mnt
   chmod 640 /etc/shadow
   chown root:shadow /etc/shadow
   ```

4. **Exit and reboot:**
   ```bash
   exit
   sudo reboot
   ```

---

### Problem: "No such file or directory" when running passwd

**What it means:** You might not have mounted the filesystem correctly

**Solution:**

1. **Make sure filesystem is writable:**
   ```bash
   mount -o remount,rw /
   ```

2. **If using chroot, make sure you're in the chroot:**
   ```bash
   chroot /mnt  # or /sysroot for Fedora
   ```

3. **Try again:**
   ```bash
   passwd username
   ```

---

## Security Notes

> [!IMPORTANT]
> **Physical Access = Root Access**
> 
> These methods show that anyone with physical access to your computer can reset passwords. This is why physical security is crucial!

### How to Protect Your System

#### 1. Set a GRUB Password

Prevent unauthorized GRUB editing:

```bash
# Generate password hash
grub-mkpasswd-pbkdf2
```

Enter a password and copy the hash.

**For Ubuntu/Debian:**
```bash
sudo nano /etc/grub.d/40_custom
```

Add:
```
set superusers="admin"
password_pbkdf2 admin <paste_hash_here>
```

Update GRUB:
```bash
sudo update-grub
```

**For Fedora/RHEL:**
```bash
sudo nano /etc/grub.d/40_custom
```

Add the same lines, then:
```bash
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```

#### 2. Enable Full Disk Encryption

When installing Linux, choose the encryption option. This protects against:
- Physical theft
- Unauthorized access
- Data recovery attempts

> [!NOTE]
> With full disk encryption, password recovery is impossible without the encryption key!

#### 3. Secure Your BIOS/UEFI

1. Enter BIOS/UEFI settings (usually `Del`, `F2`, or `F12` during boot)
2. Set a supervisor/admin password
3. Disable booting from USB/CD
4. Enable Secure Boot (if supported)

#### 4. Physical Security

- Lock your computer in a secure location
- Use a cable lock for laptops
- Don't leave your computer unattended in public

---

## Quick Reference Table

| Distribution | Easiest Method | Difficulty | Time Needed |
|--------------|----------------|------------|-------------|
| Ubuntu/Debian | Recovery Mode | ⭐ Easy | 2-3 minutes |
| Fedora/RHEL 8+ | rw init=/bin/bash | ⭐⭐ Medium | 5-7 minutes |
| CentOS 7 | init=/sysroot/bin/sh | ⭐⭐ Medium | 5-7 minutes |
| Arch Linux | init=/bin/bash | ⭐⭐ Medium | 3-5 minutes |
| openSUSE | Rescue System | ⭐ Easy | 3-5 minutes |
| Gentoo | Live CD chroot | ⭐⭐⭐ Hard | 10-15 minutes |
| Alpine | init=/bin/sh | ⭐⭐ Medium | 3-5 minutes |
| **Any Linux** | **Live USB chroot** | ⭐⭐ Medium | 10-15 minutes |

**Legend:**
- ⭐ Easy - Beginner friendly
- ⭐⭐ Medium - Some Linux knowledge needed
- ⭐⭐⭐ Hard - Advanced users

---

## Additional Resources

### Official Documentation

- **Ubuntu:** [Lost Password Recovery](https://help.ubuntu.com/community/LostPassword)
- **Fedora:** [Reset Root Password](https://docs.fedoraproject.org/en-US/quick-docs/reset-root-password/)
- **Arch Linux:** [Reset Lost Root Password](https://wiki.archlinux.org/title/Reset_lost_root_password)
- **RHEL:** [Red Hat Documentation](https://access.redhat.com/documentation/)

### Video Tutorials

Search YouTube for:
- "Ubuntu password recovery"
- "Fedora reset password"
- "Linux password reset tutorial"

### Community Support

- **Ubuntu Forums:** https://ubuntuforums.org/
- **Fedora Forums:** https://ask.fedoraproject.org/
- **Arch Forums:** https://bbs.archlinux.org/
- **Reddit:** r/linux4noobs, r/linuxquestions

---

## Final Tips

> [!TIP]
> **Prevention is Better Than Recovery!**
> 
> - Write down your password in a secure location
> - Use a password manager (KeePassXC, Bitwarden)
> - Create a password reset disk when you first install Linux
> - Keep a Live USB handy for emergencies

> [!CAUTION]
> **Always Have Authorization!**
> 
> Only use these methods on:
> - Your own personal computer
> - Systems you have explicit permission to access
> - Work computers with IT department approval
> 
> Unauthorized access is illegal and unethical!

---

**Remember:** This guide is for educational purposes and legitimate system recovery only. Always ensure you have proper authorization before attempting password recovery on any system.

**Good luck, and welcome back to your Linux system! 🐧**
