# macOS Password Recovery Guide

A comprehensive, beginner-friendly guide for recovering/resetting passwords on macOS.

> [!CAUTION]
> These procedures require physical access to the Mac. Always ensure you have proper authorization before attempting password recovery on any system. Some methods may require your Apple ID credentials.

---

## Table of Contents
- [Quick Start - Which Method Should I Use?](#quick-start---which-method-should-i-use)
- [Method 1: Apple ID Reset (Easiest)](#method-1-apple-id-reset-easiest)
- [Method 2: Recovery Mode (Recommended)](#method-2-recovery-mode-recommended)
- [Method 3: Another Admin Account](#method-3-another-admin-account)
- [Method 4: Terminal in Recovery Mode](#method-4-terminal-in-recovery-mode)
- [Method 5: Reset Using Installation Media](#method-5-reset-using-installation-media)
- [FileVault Encrypted Macs](#filevault-encrypted-macs)
- [Troubleshooting](#troubleshooting)
- [Security Notes](#security-notes)

---

## Quick Start - Which Method Should I Use?

Choose based on your situation:

| Your Situation | Best Method | Difficulty |
|----------------|-------------|------------|
| **Linked Apple ID to Mac** | Apple ID Reset | ⭐ Very Easy |
| **macOS Catalina or newer** | Recovery Mode | ⭐ Easy |
| **Have another admin account** | Another Admin | ⭐ Very Easy |
| **Older macOS (Mojave or earlier)** | Terminal in Recovery | ⭐⭐ Medium |
| **FileVault encrypted** | Apple ID or Recovery Key | ⭐⭐ Medium |
| **Forgot everything** | Installation Media | ⭐⭐⭐ Hard |

---

## Method 1: Apple ID Reset (Easiest)

If you linked your Apple ID to your Mac account, this is the fastest method!

### What You Need
- Your Apple ID email
- Your Apple ID password
- Internet connection

### Step 1: Trigger the Reset Option

1. **Turn on your Mac** (or restart if it's already on)

2. **At the login screen**, enter any password **three times incorrectly**

3. After the third wrong attempt, you'll see a message:
   > "If you forgot your password, you can reset it using your Apple ID"

4. **Click the arrow button** (→) next to this message

> [!NOTE]
> If you don't see this message, your Apple ID isn't linked to this account. Try Method 2 instead.

### Step 2: Enter Your Apple ID

1. You'll see a window asking for your **Apple ID**

2. **Enter your Apple ID email** (example: yourname@icloud.com)

3. **Enter your Apple ID password**

4. **Click "Reset Password"**

### Step 3: Create New Password

1. You'll see fields to create a new password

2. **Enter your new password** in the first field

3. **Re-enter the same password** in the second field (to confirm)

4. **Optional:** Add a password hint (recommended!)

5. **Click "Reset Password"**

### Step 4: Log In

1. Your Mac will return to the login screen

2. **Enter your new password**

3. **You're in!** 🎉

> [!TIP]
> Write down your new password in a secure place or use a password manager like iCloud Keychain!

---

## Method 2: Recovery Mode (Recommended)

This is the official Apple method for password recovery. Works on macOS Catalina (10.15) and newer.

### For Apple Silicon Macs (M1, M2, M3, etc.)

#### Step 1: Enter Recovery Mode

1. **Shut down your Mac completely**
   - Click Apple menu → Shut Down
   - Wait until the screen is completely black

2. **Press and hold the Power button**
   - Keep holding it!
   - You'll see "Loading startup options..."
   - Keep holding until you see a gear icon labeled "Options"

3. **Release the Power button**

4. **Click "Options"**

5. **Click "Continue"**

#### Step 2: Access Password Reset Utility

1. You'll see the **Recovery Mode menu bar** at the top

2. **Click "Utilities"** in the menu bar

3. **Select "Terminal"** from the dropdown

4. **Type this command** and press Enter:
   ```bash
   resetpassword
   ```

5. The **Reset Password** window will appear

#### Step 3: Reset Your Password

1. **Select your startup disk** (usually "Macintosh HD")

2. **Select your user account** from the dropdown menu

3. **Enter your new password** in the "New Password" field

4. **Re-enter the password** in the "Verify" field

5. **Add a password hint** (optional but recommended)

6. **Click "Next"**

7. **Click "Restart"**

#### Step 4: Log In

1. Your Mac will restart

2. **Enter your new password** at the login screen

3. **You're back in!** 🎉

---

### For Intel Macs

#### Step 1: Enter Recovery Mode

1. **Restart your Mac**

2. **Immediately press and hold** `Command (⌘) + R`
   - Keep holding both keys!
   - Don't let go until you see the Apple logo or a spinning globe

3. You'll see the **macOS Utilities** window

#### Step 2: Access Password Reset Utility

1. **Click "Utilities"** in the menu bar at the top

2. **Select "Terminal"**

3. **Type this command** and press Enter:
   ```bash
   resetpassword
   ```

4. The **Reset Password** window will open

#### Step 3: Reset Your Password

1. **Select your startup disk** (usually "Macintosh HD")

2. **Select your user account** from the list

3. **Enter your new password**

4. **Verify your new password** (type it again)

5. **Add a password hint** (optional)

6. **Click "Save"** or "Next"

7. **Click "Restart"**

#### Step 4: Log In

1. Your Mac will restart normally

2. **Enter your new password**

3. **Success!** 🎉

> [!WARNING]
> If you see a message about "System volume is encrypted," your Mac uses FileVault. See the [FileVault section](#filevault-encrypted-macs) below.

---

## Method 3: Another Admin Account

If you have another administrator account on the Mac, this is the quickest method!

### Step 1: Log In with Another Admin Account

1. **At the login screen**, select the other admin account

2. **Enter that account's password**

3. **Log in**

### Step 2: Open Users & Groups

1. **Click the Apple menu** (  ) in the top-left corner

2. **Select "System Settings"** (macOS Ventura+) or **"System Preferences"** (older versions)

3. **Click "Users & Groups"**

> [!NOTE]
> On older macOS versions, you might need to click the lock icon and enter the admin password to make changes.

### Step 3: Reset the Password

**For macOS Ventura (13.0) and newer:**

1. **Find the user account** you want to reset in the list

2. **Click the (i) info button** next to the username

3. **Click "Reset Password"**

4. **Enter a new password** twice

5. **Add a password hint** (optional)

6. **Click "Change Password"**

**For macOS Monterey (12.0) and older:**

1. **Select the user account** from the left sidebar

2. **Click "Reset Password"**

3. **Enter a new password** twice

4. **Add a password hint**

5. **Click "Change Password"**

### Step 4: Log Out and Test

1. **Click the Apple menu** → **Log Out**

2. **Select the account** you just reset

3. **Enter the new password**

4. **You're in!** 🎉

---

## Method 4: Terminal in Recovery Mode

This is an advanced method for older macOS versions or when other methods don't work.

### Step 1: Boot into Recovery Mode

**Apple Silicon Macs:**
- Hold the Power button until you see "Options"

**Intel Macs:**
- Restart and hold `Command (⌘) + R`

### Step 2: Open Terminal

1. **Click "Utilities"** in the menu bar

2. **Select "Terminal"**

### Step 3: List All Users

1. **Type this command** to see all user accounts:
   ```bash
   dscl . list /Users
   ```

2. **Press Enter**

3. **Find your username** in the list (ignore system accounts like _mbsetupuser, daemon, etc.)

### Step 4: Reset the Password

1. **Type this command** (replace `username` with your actual username):
   ```bash
   resetpassword
   ```

2. **Press Enter**

3. The Reset Password utility will open

4. **Follow the on-screen instructions** to reset your password

### Step 5: Restart

1. **Click "Restart"** when done

2. **Log in with your new password**

---

## Method 5: Reset Using Installation Media

Use this method if nothing else works. You'll need a USB drive with macOS installer.

### Step 1: Create macOS Installation Media

**On another Mac:**

1. **Download macOS** from the App Store

2. **Insert a USB drive** (16GB or larger)

3. **Open Terminal** (Applications → Utilities → Terminal)

4. **Run the appropriate command** for your macOS version:

   **For macOS Ventura:**
   ```bash
   sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
   ```

   **For macOS Monterey:**
   ```bash
   sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
   ```

   Replace `MyVolume` with your USB drive name

5. **Enter your password** and wait (takes 20-30 minutes)

### Step 2: Boot from USB

**Apple Silicon Macs:**
1. Shut down your Mac
2. Insert the USB drive
3. Hold the Power button
4. Select the USB installer when it appears

**Intel Macs:**
1. Insert the USB drive
2. Restart your Mac
3. Hold `Option (⌥)` key
4. Select the USB installer

### Step 3: Access Terminal

1. **Don't click "Install macOS"**

2. **Click "Utilities"** in the menu bar

3. **Select "Terminal"**

4. **Type:**
   ```bash
   resetpassword
   ```

5. **Follow the reset process** as described in Method 2

---

## FileVault Encrypted Macs

FileVault is Apple's full-disk encryption. If enabled, password recovery is more complex.

### How to Know If You Have FileVault

- You enter a password **before** seeing the Apple logo when booting
- System Settings → Privacy & Security → FileVault shows "On"

### Recovery Options for FileVault

#### Option 1: Use Your Recovery Key

When you enabled FileVault, you were given a recovery key (a long string of letters and numbers).

1. **Boot into Recovery Mode** (see Method 2)

2. **Click "Utilities"** → **"Terminal"**

3. **Type:**
   ```bash
   resetpassword
   ```

4. **Select your user account**

5. **Click "Reset using Recovery Key"**

6. **Enter your FileVault recovery key**

7. **Create a new password**

8. **Restart**

> [!IMPORTANT]
> The recovery key looks like: `XXXX-XXXX-XXXX-XXXX-XXXX-XXXX`

#### Option 2: Use iCloud Recovery

If you chose to store your recovery key with Apple:

1. **Boot into Recovery Mode**

2. **Use the resetpassword utility**

3. **Sign in with your Apple ID**

4. **Follow the prompts** to reset your password

#### Option 3: Contact Apple Support

If you lost both your password and recovery key:

1. **Contact Apple Support**: 1-800-MY-APPLE (1-800-692-7753)

2. **Provide proof of ownership** (receipt, serial number)

3. Apple may be able to help, but **data recovery is not guaranteed**

> [!WARNING]
> Without the password or recovery key, your data may be permanently inaccessible. This is by design for security.

---

## Troubleshooting

### Problem: "The recovery server could not be contacted"

**What it means:** Your Mac can't connect to Apple's servers in Recovery Mode

**Solution:**

1. **Check your internet connection**
   - Click the Wi-Fi icon in the menu bar
   - Connect to a network

2. **Try again** after connecting

3. **If still failing**, use a wired Ethernet connection if possible

---

### Problem: "Firmware password is set"

**What it means:** Someone enabled a firmware password (extra security layer)

**Signs:**
- You see a lock icon when booting
- Can't access Recovery Mode

**Solution:**

1. **If you know the firmware password**, enter it

2. **If you don't know it:**
   - **For Intel Macs**: Visit an Apple Store or Authorized Service Provider with proof of purchase
   - **For Apple Silicon Macs**: Contact Apple Support

> [!NOTE]
> Firmware passwords cannot be bypassed without Apple's help. This is a security feature.

---

### Problem: "Your disk is encrypted with FileVault"

**What it means:** Full-disk encryption is enabled

**Solution:** See the [FileVault section](#filevault-encrypted-macs) above

---

### Problem: Can't see my user account in the reset list

**What it means:** The account might be hidden or corrupted

**Solution:**

1. **In Terminal (Recovery Mode), type:**
   ```bash
   ls /Users
   ```

2. **Look for your username** in the output

3. **If you see it**, use the Terminal method (Method 4)

4. **If you don't see it**, the account may be corrupted - contact Apple Support

---

### Problem: "Password reset successful" but still can't log in

**What it means:** Keychain or FileVault issues

**Solution:**

1. **Try resetting again** - sometimes it takes two attempts

2. **Reset NVRAM/PRAM:**
   - **Intel Macs**: Restart and hold `Command + Option + P + R` for 20 seconds
   - **Apple Silicon**: This happens automatically

3. **Boot into Safe Mode:**
   - **Intel**: Restart and hold `Shift`
   - **Apple Silicon**: Hold Power button, select disk, hold `Shift`, click "Continue in Safe Mode"

4. **Try logging in** from Safe Mode

---

### Problem: "Your login keychain password is different"

**What it means:** Your keychain still uses the old password

**Solution:**

1. **Click "Create New Keychain"** (you'll lose saved passwords)

   **OR**

2. **Click "Keep Using"** and enter the old password when prompted for keychain access

3. **To update keychain password:**
   - Open **Keychain Access** (Applications → Utilities)
   - Click **Keychain Access** menu → **Preferences**
   - Click **Reset My Default Keychain**

---

## Security Notes

> [!IMPORTANT]
> **Physical Access = Admin Access**
> 
> These methods show that physical access to a Mac allows password resets. Protect your Mac with these measures:

### How to Protect Your Mac

#### 1. Enable FileVault

Full-disk encryption protects your data even if someone resets your password.

1. **Open System Settings/Preferences**

2. **Go to Privacy & Security** → **FileVault**

3. **Click "Turn On FileVault"**

4. **Save your recovery key** in a secure location!

> [!WARNING]
> Without the recovery key, data recovery is impossible if you forget your password!

#### 2. Set a Firmware Password

Prevents booting from external drives or Recovery Mode.

**Intel Macs:**
1. Boot into Recovery Mode (`Command + R`)
2. Click **Utilities** → **Startup Security Utility** (or **Firmware Password Utility**)
3. Click **Turn On Firmware Password**
4. Create a strong password
5. **Write it down** and store securely!

**Apple Silicon Macs:**
- Firmware passwords work differently
- Use **System Settings** → **Touch ID & Password** → **Require password**
- Enable **Secure Boot** in Recovery Mode

#### 3. Use a Strong Password

- At least 12 characters
- Mix of uppercase, lowercase, numbers, symbols
- Not a dictionary word
- Not personal information (birthdate, name, etc.)

#### 4. Enable Find My Mac

Allows remote locking and wiping:

1. **System Settings** → **Apple ID** → **iCloud**

2. **Enable "Find My Mac"**

3. If stolen, you can lock or erase remotely from iCloud.com

#### 5. Use Two-Factor Authentication

Protect your Apple ID:

1. **System Settings** → **Apple ID**

2. **Password & Security**

3. **Turn on Two-Factor Authentication**

#### 6. Physical Security

- Don't leave your Mac unattended in public
- Use a cable lock (Kensington lock slot on some models)
- Enable automatic screen lock:
  - **System Settings** → **Lock Screen**
  - Set to lock after 5 minutes or less

---

## macOS Version Quick Reference

| macOS Version | Release Year | Recovery Mode Method |
|---------------|--------------|----------------------|
| Sonoma (14.0) | 2023 | Power button (Apple Silicon) / ⌘+R (Intel) |
| Ventura (13.0) | 2022 | Power button (Apple Silicon) / ⌘+R (Intel) |
| Monterey (12.0) | 2021 | Power button (Apple Silicon) / ⌘+R (Intel) |
| Big Sur (11.0) | 2020 | Power button (Apple Silicon) / ⌘+R (Intel) |
| Catalina (10.15) | 2019 | ⌘+R |
| Mojave (10.14) | 2018 | ⌘+R |
| High Sierra (10.13) | 2017 | ⌘+R |
| Sierra (10.12) | 2016 | ⌘+R |

---

## Additional Resources

### Official Apple Support

- **Password Reset Guide**: https://support.apple.com/en-us/HT202860
- **FileVault Recovery**: https://support.apple.com/en-us/HT204837
- **Apple Support**: 1-800-MY-APPLE (1-800-692-7753)
- **Apple Support Website**: https://support.apple.com/

### Community Resources

- **Apple Support Communities**: https://discussions.apple.com/
- **Reddit**: r/mac, r/applehelp
- **MacRumors Forums**: https://forums.macrumors.com/

### Video Tutorials

Search YouTube for:
- "macOS password reset [your macOS version]"
- "Reset Mac password without Apple ID"
- "FileVault password recovery"

---

## Final Tips

> [!TIP]
> **Prevention is Better Than Recovery!**
> 
> - Link your Apple ID to your Mac account
> - Store your FileVault recovery key securely
> - Use iCloud Keychain or a password manager
> - Write down important passwords in a secure physical location
> - Enable Find My Mac for remote access

> [!CAUTION]
> **Always Have Authorization!**
> 
> Only use these methods on:
> - Your own personal Mac
> - Macs you have explicit permission to access
> - Company Macs with IT department approval
> 
> Unauthorized access is illegal and unethical!

---

---

**Remember:** This guide is for educational purposes and legitimate system recovery only. Always ensure you have proper authorization before attempting password recovery on any system.

**Good luck, and welcome back to your Mac! 🍎**

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

