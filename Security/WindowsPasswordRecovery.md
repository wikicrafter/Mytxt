# Windows Password Recovery Guide

A comprehensive, beginner-friendly guide for recovering/resetting passwords on Windows 10 and Windows 11.

> [!CAUTION]
> These procedures require physical access to the computer. Always ensure you have proper authorization before attempting password recovery on any system.

---

## Table of Contents
- [Quick Start - Which Method Should I Use?](#quick-start---which-method-should-i-use)
- [Method 1: Microsoft Account Password Reset (Easiest)](#method-1-microsoft-account-password-reset-easiest)
- [Method 2: Security Questions (Windows 10)](#method-2-security-questions-windows-10)
- [Method 3: Another Admin Account](#method-3-another-admin-account)
- [Method 4: Password Reset Disk](#method-4-password-reset-disk)
- [Method 5: Safe Mode with Command Prompt](#method-5-safe-mode-with-command-prompt)
- [Method 6: Windows Installation Media](#method-6-windows-installation-media)
- [Method 7: Third-Party Tools](#method-7-third-party-tools)
- [BitLocker Encrypted Drives](#bitlocker-encrypted-drives)
- [Troubleshooting](#troubleshooting)
- [Security Notes](#security-notes)

---

## Quick Start - Which Method Should I Use?

Choose based on your situation:

| Your Situation | Best Method | Difficulty | Time |
|----------------|-------------|------------|------|
| **Microsoft account (email login)** | Online Password Reset | ⭐ Very Easy | 5 min |
| **Local account + security questions** | Security Questions | ⭐ Easy | 2 min |
| **Have another admin account** | Another Admin | ⭐ Very Easy | 3 min |
| **Created password reset disk** | Password Reset Disk | ⭐ Easy | 5 min |
| **Local account, no questions** | Installation Media | ⭐⭐ Medium | 15 min |
| **BitLocker encrypted** | Recovery Key Required | ⭐⭐⭐ Hard | Varies |

---

## Method 1: Microsoft Account Password Reset (Easiest)

If you sign in with a Microsoft account (email address), this is the simplest method!

### What You Need
- Another device (phone, tablet, or another computer)
- Internet connection
- Access to your email or phone for verification

### Step 1: Identify If You Use a Microsoft Account

**At the login screen, look at your username:**
- **Microsoft Account**: Shows an email address (example@outlook.com, example@gmail.com)
- **Local Account**: Shows just a name (like "John" or "Admin")

> [!NOTE]
> If you see just a name (not an email), skip to Method 2 or Method 3.

### Step 2: Go to Microsoft's Password Reset Page

**On another device:**

1. **Open a web browser** (Chrome, Safari, Edge, etc.)

2. **Go to:** https://account.live.com/password/reset

3. You'll see the **"Recover your account"** page

### Step 3: Reset Your Password

1. **Enter your Microsoft account email** (the one you use to sign in to Windows)

2. **Click "Next"**

3. **Choose how to receive a security code:**
   - Email (to your recovery email)
   - Text message (to your phone)
   - Authenticator app

4. **Click "Get code"**

5. **Check your email or phone** for the security code

6. **Enter the code** on the website

7. **Click "Next"**

### Step 4: Create New Password

1. **Enter your new password** in the first field

2. **Re-enter the same password** in the second field

3. **Click "Next"**

4. You'll see: **"Your password has been changed"**

### Step 5: Log In to Windows

1. **Go back to your Windows computer**

2. **At the login screen, enter your NEW password**

3. **Press Enter**

4. **You're in!** 🎉

> [!TIP]
> Your new password works across all Microsoft services (Xbox, Outlook, OneDrive, etc.)

---

## Method 2: Security Questions (Windows 10)

If you have a local account on Windows 10 version 1803 or later, you can use security questions.

### Step 1: Trigger Security Questions

1. **At the login screen**, enter any wrong password

2. **Click "OK"**

3. **Look below the password field** - you should see **"Reset password"**

4. **Click "Reset password"**

> [!NOTE]
> If you don't see "Reset password," you didn't set up security questions. Try Method 3 or Method 6 instead.

### Step 2: Answer Security Questions

1. You'll see your **three security questions**

2. **Answer each question** exactly as you set them up
   - Answers are case-sensitive!
   - Example: If you typed "Fluffy" originally, "fluffy" won't work

3. **Click "Submit"** or press Enter

### Step 3: Create New Password

1. **Enter your new password** in the first field

2. **Re-enter the same password** in the second field

3. **Press Enter**

### Step 4: Log In

1. You'll return to the login screen

2. **Enter your new password**

3. **You're in!** 🎉

> [!WARNING]
> If you answer the security questions incorrectly too many times, you'll need to restart your computer and try again.

---

## Method 3: Another Admin Account

If you have another administrator account on the computer, this is quick and easy!

### Step 1: Log In with Another Admin Account

1. **At the login screen**, click on the other admin account

2. **Enter that account's password**

3. **Press Enter** to log in

### Step 2: Open Computer Management

**Method A - Right-click Start Menu:**

1. **Right-click the Start button** (Windows logo in bottom-left)

2. **Select "Computer Management"**

**Method B - Search:**

1. **Click the Start button**

2. **Type:** `Computer Management`

3. **Click the app** when it appears

### Step 3: Navigate to Users

1. In the left sidebar, **expand "Local Users and Groups"**
   - Click the arrow (▶) next to it

2. **Click "Users"**

3. You'll see a list of all user accounts on the right

### Step 4: Reset the Password

1. **Right-click the user account** you want to reset

2. **Select "Set Password"**

3. **Read the warning** and **click "Proceed"**

   > [!WARNING]
   > This will cause the user to lose access to encrypted files, stored passwords, and email. Only proceed if necessary!

4. **Enter the new password** in the first field

5. **Re-enter the password** in the second field

6. **Click "OK"**

7. You'll see: **"The password has been set"**

8. **Click "OK"**

### Step 5: Log Out and Test

1. **Click Start** → **Your account icon** → **Sign out**

2. **Select the account** you just reset

3. **Enter the new password**

4. **You're in!** 🎉

---

## Method 4: Password Reset Disk

If you created a password reset disk before forgetting your password, you're in luck!

### What You Need
- The USB drive or disk you created as a password reset disk

### Step 1: Insert the Reset Disk

1. **Insert the USB drive** into your computer

2. **At the login screen**, enter any wrong password

3. **Click "OK"**

### Step 2: Use the Reset Disk

1. **Look below the password field** - you'll see **"Reset password"**

2. **Click "Reset password"**

3. The **Password Reset Wizard** will open

4. **Click "Next"**

### Step 3: Select Your Reset Disk

1. **Select your USB drive** from the dropdown menu

2. **Click "Next"**

### Step 4: Create New Password

1. **Enter your new password** in the first field

2. **Re-enter the password** in the second field

3. **Type a password hint** (optional but recommended)

4. **Click "Next"**

5. **Click "Finish"**

### Step 5: Log In

1. **Enter your new password** at the login screen

2. **Press Enter**

3. **You're in!** 🎉

> [!TIP]
> Your password reset disk still works! You can use it again if you forget your password in the future.

---

## Method 5: Safe Mode with Command Prompt

This method works for Windows 10 and 11 when you can access Safe Mode.

### Step 1: Boot into Safe Mode

**If you can't log in:**

1. **At the login screen**, hold down the **Shift key**

2. **While holding Shift**, click the **Power icon** → **Restart**

3. **Keep holding Shift** until you see the blue screen

4. **Select "Troubleshoot"**

5. **Select "Advanced options"**

6. **Select "Startup Settings"**

7. **Click "Restart"**

8. **Press F6** for "Enable Safe Mode with Command Prompt"

**If you can log in with another account:**

1. **Hold Shift** and click **Start** → **Power** → **Restart**

2. Follow steps 4-8 above

### Step 2: Access Command Prompt

1. Your computer will restart and show a **black screen with white text**

2. You'll see: `C:\Windows\system32>`

3. This is the **Command Prompt**

### Step 3: Enable the Built-in Administrator

1. **Type this command** exactly and press Enter:
   ```cmd
   net user administrator /active:yes
   ```

2. You should see: **"The command completed successfully"**

### Step 4: Restart Normally

1. **Type:**
   ```cmd
   shutdown /r /t 0
   ```

2. **Press Enter**

3. Your computer will restart

### Step 5: Log In as Administrator

1. **At the login screen**, you'll see a new account: **"Administrator"**

2. **Click on it** (no password needed)

3. You'll log in to the Administrator account

### Step 6: Reset the User Password

1. **Right-click the Start button**

2. **Select "Computer Management"**

3. **Expand "Local Users and Groups"** → **Click "Users"**

4. **Right-click your user account** → **Select "Set Password"**

5. **Click "Proceed"**

6. **Enter a new password** twice

7. **Click "OK"**

### Step 7: Disable Administrator and Log In

1. **Open Command Prompt as Administrator:**
   - Right-click Start → **Windows Terminal (Admin)** or **Command Prompt (Admin)**

2. **Type:**
   ```cmd
   net user administrator /active:no
   ```

3. **Press Enter**

4. **Sign out** and **log in to your account** with the new password

5. **You're in!** 🎉

---

## Method 6: Windows Installation Media

This is the most reliable method when others don't work. You'll need a USB drive with Windows installer.

### Step 1: Create Windows Installation Media

**On another computer:**

1. **Go to:** https://www.microsoft.com/software-download/windows11 (or windows10)

2. **Click "Download Now"** under "Create Windows 11 Installation Media"

3. **Run the downloaded tool** (MediaCreationTool.exe)

4. **Accept the license terms**

5. **Select "Create installation media"**

6. **Click "Next"**

7. **Choose your language and edition**

8. **Select "USB flash drive"**

9. **Select your USB drive** (8GB or larger)

10. **Click "Next"** and wait (takes 20-30 minutes)

### Step 2: Boot from USB

1. **Insert the USB drive** into your locked computer

2. **Restart the computer**

3. **Press the boot menu key** repeatedly:
   - Common keys: **F12**, **F2**, **F9**, **F10**, **Esc**, **Del**
   - Look for "Boot Menu" or "Boot Options" on the screen during startup

4. **Select your USB drive** from the list

5. **Press Enter**

### Step 3: Access Command Prompt

1. **Wait for the Windows Setup** screen to appear

2. **Click "Next"**

3. **Click "Repair your computer"** (bottom-left corner)

4. **Select "Troubleshoot"**

5. **Select "Command Prompt"**

### Step 4: Backup and Replace Utilman.exe

This method temporarily replaces the Utility Manager with Command Prompt.

1. **Type this command** to find your Windows drive:
   ```cmd
   wmic logicaldisk get caption
   ```

2. **Look for C:, D:, E:**, etc. Your Windows is usually on **C:** or **D:**

3. **Check which drive has Windows** (replace `C:` if needed):
   ```cmd
   dir C:\Windows
   ```
   If you see folders like "System32," that's your Windows drive!

4. **Backup the Utility Manager** (replace `C:` with your Windows drive):
   ```cmd
   copy C:\Windows\System32\utilman.exe C:\Windows\System32\utilman.exe.bak
   ```

5. **Replace it with Command Prompt:**
   ```cmd
   copy C:\Windows\System32\cmd.exe C:\Windows\System32\utilman.exe
   ```

6. **Type "Yes"** or **"Y"** to overwrite

7. **Close the window** and **click "Continue"** to boot into Windows

### Step 5: Access Command Prompt at Login Screen

1. **At the Windows login screen**, click the **Accessibility icon** (bottom-right corner)
   - It looks like a person or a clock

2. **Command Prompt will open!** (instead of Utility Manager)

### Step 6: Reset the Password

1. **List all user accounts:**
   ```cmd
   net user
   ```

2. **Find your username** in the list

3. **Reset the password** (replace `YourUsername` with your actual username):
   ```cmd
   net user YourUsername NewPassword123
   ```
   Replace `NewPassword123` with your desired password

4. **Press Enter**

5. You should see: **"The command completed successfully"**

### Step 7: Restore Utilman.exe

1. **Boot from the USB again** (repeat Step 2-3)

2. **In Command Prompt, type:**
   ```cmd
   copy C:\Windows\System32\utilman.exe.bak C:\Windows\System32\utilman.exe
   ```

3. **Type "Yes"** to overwrite

4. **Close the window** and **click "Continue"**

### Step 8: Log In

1. **At the login screen**, enter your **new password**

2. **Press Enter**

3. **You're in!** 🎉

> [!IMPORTANT]
> Always restore utilman.exe! Leaving cmd.exe in its place is a security risk.

---

## Method 7: Third-Party Tools

Several free tools can reset Windows passwords. Use with caution!

### Popular Tools

1. **Ophcrack** - Free, open-source
   - Website: https://ophcrack.sourceforge.io/
   - Uses rainbow tables to crack passwords
   - Works on Windows XP through Windows 10

2. **Offline NT Password & Registry Editor** - Free
   - Website: https://pogostick.net/~pnh/ntpasswd/
   - Resets passwords by editing the registry
   - Works on all Windows versions

3. **PCUnlocker** - Paid (trial available)
   - Website: https://www.top-password.com/
   - User-friendly interface
   - Supports UEFI and Secure Boot

### General Steps (Ophcrack Example)

1. **Download the ISO** from the official website

2. **Create a bootable USB** using Rufus or similar tool

3. **Boot from the USB**

4. **Select your user account**

5. **Follow the on-screen instructions** to reset or reveal the password

6. **Restart and log in**

> [!WARNING]
> Only download from official websites! Third-party tools can contain malware. Use at your own risk.

---

## BitLocker Encrypted Drives

BitLocker is Windows' full-disk encryption. If enabled, password recovery is more complex.

### How to Know If You Have BitLocker

- You enter a password or PIN **before** Windows starts
- You see a blue screen asking for a BitLocker recovery key
- Settings → System → Storage → Manage BitLocker shows "On"

### Recovery Options

#### Option 1: Use Your Recovery Key

When you enabled BitLocker, you were given a 48-digit recovery key.

**Where to find it:**

1. **Microsoft Account:**
   - Go to: https://account.microsoft.com/devices/recoverykey
   - Sign in with your Microsoft account
   - Look for your device and recovery key

2. **Printed copy** - Check if you printed it

3. **Saved file** - Check USB drives or other computers

4. **Azure AD** (work computers) - Contact your IT department

**How to use it:**

1. **At the BitLocker screen**, click **"I forgot my PIN"** or **"Enter recovery key"**

2. **Type the 48-digit recovery key**

3. **Press Enter**

4. Windows will start normally

5. **Now reset your password** using Method 1, 2, or 3

#### Option 2: Suspend BitLocker (If You Can Log In)

If you can log in with another admin account:

1. **Open Command Prompt as Administrator**

2. **Type:**
   ```cmd
   manage-bde -protectors -disable C:
   ```

3. **Press Enter**

4. **Restart** and reset the password using other methods

5. **Re-enable BitLocker** after resetting:
   ```cmd
   manage-bde -protectors -enable C:
   ```

#### Option 3: Contact IT Support (Work Computers)

For company computers:

1. **Contact your IT department**

2. **Provide your computer name or serial number**

3. IT can retrieve the recovery key from Azure AD or MBAM

> [!WARNING]
> Without the recovery key, your data is permanently inaccessible. This is by design for security.

---

## Troubleshooting

### Problem: "We couldn't connect to the Microsoft password reset service"

**What it means:** No internet connection or Microsoft services are down

**Solution:**

1. **Check your internet connection**
   - Try resetting your router
   - Use an Ethernet cable instead of Wi-Fi

2. **Try again later** - Microsoft services might be temporarily down

3. **Use Method 6** (Installation Media) as an alternative

---

### Problem: "The user name or password is incorrect"

**What it means:** You're entering the wrong password (or it didn't reset properly)

**Solution:**

1. **Check Caps Lock** - Make sure it's off

2. **Try the old password** - Sometimes the reset doesn't take effect immediately

3. **Restart and try again**

4. **Use a different method** to reset the password

---

### Problem: Can't access Safe Mode

**What it means:** Windows won't boot into Safe Mode

**Solution:**

1. **Force Windows Recovery:**
   - Turn on your PC
   - When you see the Windows logo, **hold the power button** for 5 seconds to force shutdown
   - Repeat this **3 times**
   - On the 4th boot, Windows will enter Recovery Mode automatically

2. **From Recovery Mode**, follow Method 5 or Method 6

---

### Problem: "This PC can't run Windows 11" when booting from USB

**What it means:** Secure Boot or TPM requirements

**Solution:**

1. **You don't need to install Windows** - just use it for password reset

2. **Click "Repair your computer"** instead of "Install now"

3. **Follow Method 6** from Step 3 onwards

---

### Problem: USB boot option doesn't appear

**What it means:** Boot order is wrong or USB isn't bootable

**Solution:**

1. **Enter BIOS/UEFI settings:**
   - Restart and press **Del**, **F2**, **F10**, or **F12** (varies by manufacturer)

2. **Look for "Boot Order" or "Boot Priority"**

3. **Move USB to the top** of the boot order

4. **Save and exit** (usually F10)

5. **Restart** with USB inserted

---

### Problem: "The password does not meet the password policy requirements"

**What it means:** Your new password doesn't meet complexity requirements

**Solution:**

Create a password that includes:
- At least 8 characters
- Uppercase letters (A-Z)
- Lowercase letters (a-z)
- Numbers (0-9)
- Special characters (!@#$%^&*)

Example: `MyNewPass2024!`

---

### Problem: Lost access to encrypted files after password reset

**What it means:** EFS (Encrypting File System) files are tied to your old password

**Solution:**

**If you remember the old password:**

1. **Change your password back** to the old one temporarily

2. **Decrypt the files:**
   - Right-click the file/folder → **Properties**
   - **Advanced** → Uncheck **"Encrypt contents to secure data"**
   - **OK** → **Apply**

3. **Change to your new password**

4. **Re-encrypt if needed**

**If you don't remember the old password:**
- Encrypted files are likely unrecoverable
- This is a security feature by design

---

## Security Notes

> [!IMPORTANT]
> **Physical Access = Admin Access**
> 
> These methods show that physical access to a Windows PC allows password resets. Protect your computer with these measures:

### How to Protect Your Windows PC

#### 1. Enable BitLocker

Full-disk encryption protects your data even if someone resets your password.

**Windows 11/10 Pro, Enterprise, or Education:**

1. **Open Settings** (Win + I)

2. **Go to Privacy & Security** → **Device encryption** or **BitLocker**

3. **Turn on BitLocker**

4. **Save your recovery key** in multiple secure locations:
   - Microsoft account
   - USB drive
   - Printed copy in a safe

> [!WARNING]
> Without the recovery key, data recovery is impossible if you forget your password!

#### 2. Use a Strong Password

- At least 12 characters
- Mix of uppercase, lowercase, numbers, symbols
- Not a dictionary word
- Not personal information (birthdate, name, pet's name)
- Use a passphrase: `Coffee!Morning@2024#Sunrise`

#### 3. Use Windows Hello

Biometric authentication is more secure:

1. **Settings** → **Accounts** → **Sign-in options**

2. **Set up:**
   - **Fingerprint** (if you have a fingerprint reader)
   - **Face recognition** (if you have a compatible camera)
   - **PIN** (faster than password, device-specific)

#### 4. Enable Two-Factor Authentication

For Microsoft accounts:

1. **Go to:** https://account.microsoft.com/security

2. **Click "Two-step verification"**

3. **Turn it on**

4. **Add your phone number** or authenticator app

#### 5. Create a Password Reset Disk

**Before you forget your password:**

1. **Insert a USB drive**

2. **Search for "password reset disk"** in Start menu

3. **Click "Create a password reset disk"**

4. **Follow the wizard**

5. **Store the USB safely**

#### 6. Set Up Security Questions

**For local accounts on Windows 10:**

1. **Settings** → **Accounts** → **Sign-in options**

2. **Click "Update your security questions"**

3. **Choose three questions** and provide answers

4. **Remember your answers!** (they're case-sensitive)

#### 7. Regular Backups

Protect against data loss:

1. **Use File History:**
   - Settings → System → Storage → Advanced storage settings → Backup options

2. **Use OneDrive** for cloud backup

3. **Create system images** regularly

#### 8. Physical Security

- Use a cable lock for laptops
- Enable automatic screen lock:
  - Settings → Accounts → Sign-in options → Require sign-in: **When PC wakes up from sleep**
- Set screen timeout:
  - Settings → System → Power & sleep → Screen: **5 minutes**

#### 9. Secure Your BIOS/UEFI

1. **Enter BIOS** (press Del, F2, or F10 during startup)

2. **Set a supervisor/admin password**

3. **Disable boot from USB/CD** (or set HDD as first boot device)

4. **Enable Secure Boot** (if supported)

5. **Save and exit**

---

## Windows Version Quick Reference

| Windows Version | Release Year | Best Method |
|-----------------|--------------|-------------|
| Windows 11 | 2021 | Microsoft Account Reset / Installation Media |
| Windows 10 | 2015 | Security Questions / Installation Media |
| Windows 8/8.1 | 2012-2013 | Microsoft Account Reset / Installation Media |
| Windows 7 | 2009 | Installation Media / Third-Party Tools |

---

## Additional Resources

### Official Microsoft Support

- **Password Reset**: https://account.live.com/password/reset
- **Windows Support**: https://support.microsoft.com/windows
- **BitLocker Recovery**: https://support.microsoft.com/en-us/windows/finding-your-bitlocker-recovery-key-in-windows-6b71ad27-0b89-ea08-f143-056f5ab347d6

### Community Resources

- **Microsoft Community**: https://answers.microsoft.com/
- **Reddit**: r/windows, r/windows10, r/windows11
- **Ten Forums**: https://www.tenforums.com/

### Video Tutorials

Search YouTube for:
- "Windows 11 password reset"
- "Windows 10 forgot password"
- "Reset Windows password without disk"

---

## Final Tips

> [!TIP]
> **Prevention is Better Than Recovery!**
> 
> - Use a Microsoft account instead of a local account
> - Set up security questions for local accounts
> - Create a password reset disk
> - Use a password manager (Bitwarden, 1Password, LastPass)
> - Write down your password in a secure physical location
> - Save your BitLocker recovery key in multiple places

> [!CAUTION]
> **Always Have Authorization!**
> 
> Only use these methods on:
> - Your own personal computer
> - Computers you have explicit permission to access
> - Work computers with IT department approval
> 
> Unauthorized access is illegal and unethical!

---

---

**Remember:** This guide is for educational purposes and legitimate system recovery only. Always ensure you have proper authorization before attempting password recovery on any system.

**Good luck, and welcome back to your Windows PC! 🪟**

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

