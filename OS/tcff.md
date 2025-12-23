<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fedora Linux Complete Command Reference Guide</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
            color: #c9d1d9;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            line-height: 1.6;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: #0d1117;
            border-radius: 12px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
            overflow: hidden;
        }

        header {
            background: linear-gradient(135deg, #1f6feb 0%, #0969da 100%);
            padding: 40px;
            text-align: center;
            border-bottom: 3px solid #58a6ff;
        }

        h1 {
            color: #ffffff;
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .subtitle {
            color: #e6edf3;
            font-size: 1.2em;
            font-weight: 300;
        }

        nav {
            background: #161b22;
            padding: 20px;
            border-bottom: 1px solid #30363d;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav ul {
            list-style: none;
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }

        nav a {
            color: #58a6ff;
            text-decoration: none;
            padding: 8px 16px;
            border-radius: 6px;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        nav a:hover {
            background: #1f6feb;
            color: #ffffff;
            border-color: #58a6ff;
            transform: translateY(-2px);
        }

        .content {
            padding: 40px;
        }

        section {
            margin-bottom: 50px;
            padding: 30px;
            background: #161b22;
            border-radius: 8px;
            border: 1px solid #30363d;
        }

        h2 {
            color: #58a6ff;
            font-size: 2em;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #21262d;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        h3 {
            color: #79c0ff;
            font-size: 1.5em;
            margin: 25px 0 15px 0;
            padding-left: 15px;
            border-left: 4px solid #1f6feb;
        }

        h4 {
            color: #a5d6ff;
            font-size: 1.2em;
            margin: 20px 0 10px 0;
        }

        .command-block {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 20px;
            margin: 15px 0;
            transition: all 0.3s ease;
        }

        .command-block:hover {
            border-color: #58a6ff;
            box-shadow: 0 0 15px rgba(88, 166, 255, 0.2);
        }

        .command {
            background: #1c2128;
            color: #7ee787;
            padding: 12px 16px;
            border-radius: 6px;
            font-family: 'Consolas', 'Monaco', 'Courier New', monospace;
            font-size: 0.95em;
            margin: 10px 0;
            border-left: 3px solid #238636;
            overflow-x: auto;
            white-space: pre;
        }

        .description {
            color: #8b949e;
            margin: 10px 0;
            padding-left: 10px;
            font-size: 0.95em;
        }

        .note {
            background: #1c2d41;
            border-left: 4px solid #1f6feb;
            padding: 15px;
            margin: 15px 0;
            border-radius: 6px;
        }

        .note-title {
            color: #58a6ff;
            font-weight: bold;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .warning {
            background: #2d1e13;
            border-left: 4px solid #d29922;
            padding: 15px;
            margin: 15px 0;
            border-radius: 6px;
        }

        .warning-title {
            color: #d29922;
            font-weight: bold;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .tip {
            background: #1a2c1a;
            border-left: 4px solid #3fb950;
            padding: 15px;
            margin: 15px 0;
            border-radius: 6px;
        }

        .tip-title {
            color: #3fb950;
            font-weight: bold;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .example {
            background: #1c2128;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 15px;
            margin: 15px 0;
        }

        .example-title {
            color: #f778ba;
            font-weight: bold;
            margin-bottom: 10px;
        }

        code {
            background: #1c2128;
            color: #ff7b72;
            padding: 2px 6px;
            border-radius: 3px;
            font-family: 'Consolas', 'Monaco', 'Courier New', monospace;
            font-size: 0.9em;
        }

        ul, ol {
            margin-left: 30px;
            margin-top: 10px;
        }

        li {
            margin: 8px 0;
            color: #c9d1d9;
        }

        .icon {
            font-size: 1.2em;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background: #0d1117;
            border-radius: 6px;
            overflow: hidden;
        }

        th {
            background: #1f6feb;
            color: #ffffff;
            padding: 12px;
            text-align: left;
            font-weight: 600;
        }

        td {
            padding: 12px;
            border-bottom: 1px solid #30363d;
        }

        tr:hover {
            background: #161b22;
        }

        .support-section {
            background: linear-gradient(135deg, #1f6feb 0%, #0969da 100%);
            padding: 40px;
            text-align: center;
            border-radius: 8px;
            margin-top: 50px;
        }

        .support-section h2 {
            color: #ffffff;
            border: none;
            justify-content: center;
        }

        .support-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .support-btn {
            background: #ffffff;
            color: #0969da;
            padding: 12px 24px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            border: 2px solid #ffffff;
        }

        .support-btn:hover {
            background: transparent;
            color: #ffffff;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        footer {
            background: #0d1117;
            padding: 30px;
            text-align: center;
            border-top: 1px solid #30363d;
            color: #8b949e;
        }

        @media (max-width: 768px) {
            .content {
                padding: 20px;
            }

            h1 {
                font-size: 1.8em;
            }

            h2 {
                font-size: 1.5em;
            }

            nav ul {
                flex-direction: column;
            }
        }

        .scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: #1f6feb;
            color: #ffffff;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(31, 111, 235, 0.4);
        }

        .scroll-top:hover {
            background: #58a6ff;
            transform: translateY(-5px);
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🐧 Fedora Linux Complete Command Reference</h1>
            <p class="subtitle">Your comprehensive, beginner-friendly guide to mastering Fedora Linux</p>
        </header>

        <nav>
            <ul>
                <li><a href="#package">📦 Package Management</a></li>
                <li><a href="#system">⚙️ System Management</a></li>
                <li><a href="#hostname">🏷️ Hostname</a></li>
                <li><a href="#users">👥 Users & Groups</a></li>
                <li><a href="#files">📁 Files & Directories</a></li>
                <li><a href="#network">🌐 Networking</a></li>
                <li><a href="#firewall">🔥 Firewall</a></li>
                <li><a href="#selinux">🛡️ SELinux</a></li>
                <li><a href="#security">🔒 Security & Encryption</a></li>
                <li><a href="#disk">💾 Disk Management</a></li>
                <li><a href="#process">⚡ Process Management</a></li>
                <li><a href="#logs">📋 Logs</a></li>
                <li><a href="#time">🕐 Time & Date</a></li>
                <li><a href="#scripting">📝 Scripting</a></li>
                <li><a href="#monitoring">📊 Monitoring</a></li>
            </ul>
        </nav>

        <div class="content">
            <!-- Package Management Section -->
            <section id="package">
                <h2><span class="icon">📦</span> Package Management with DNF</h2>
                
                <div class="note">
                    <div class="note-title">💡 What is DNF?</div>
                    <p>DNF (Dandified YUM) is Fedora's powerful package manager. Think of it as an app store for your Linux system - it helps you install, update, and remove software easily and safely.</p>
                </div>

                <h3>Basic Package Operations</h3>
                
                <div class="command-block">
                    <h4>Update Your System</h4>
                    <div class="command">sudo dnf update</div>
                    <div class="description">
                        <strong>What it does:</strong> Updates all installed packages to their latest versions.<br>
                        <strong>When to use:</strong> Run this regularly (weekly) to keep your system secure and up-to-date.<br>
                        <strong>Beginner tip:</strong> This is like "Check for Updates" on Windows or Mac.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Install a Package</h4>
                    <div class="command">sudo dnf install firefox</div>
                    <div class="description">
                        <strong>What it does:</strong> Installs Firefox web browser (or any package you specify).<br>
                        <strong>Example:</strong> Replace "firefox" with "vlc" for VLC media player, "gimp" for image editor, etc.<br>
                        <strong>Beginner tip:</strong> DNF automatically handles all dependencies (other required software).
                    </div>
                </div>

                <div class="command-block">
                    <h4>Remove a Package</h4>
                    <div class="command">sudo dnf remove package_name</div>
                    <div class="description">
                        <strong>What it does:</strong> Uninstalls the specified package.<br>
                        <strong>Safe option:</strong> Use <code>sudo dnf autoremove package_name</code> to also remove unused dependencies.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Search for Packages</h4>
                    <div class="command">dnf search keyword</div>
                    <div class="description">
                        <strong>What it does:</strong> Searches for packages matching your keyword.<br>
                        <strong>Example:</strong> <code>dnf search video editor</code> finds video editing software.<br>
                        <strong>No sudo needed:</strong> Searching doesn't modify your system.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Get Package Information</h4>
                    <div class="command">dnf info package_name</div>
                    <div class="description">
                        <strong>What it does:</strong> Shows detailed information about a package (size, version, description).<br>
                        <strong>Use before installing:</strong> Check what a package does before installing it.
                    </div>
                </div>

                <div class="tip">
                    <div class="tip-title">💚 Pro Tip: Install Multiple Packages at Once</div>
                    <div class="command">sudo dnf install vlc gimp inkscape</div>
                    <p>This installs VLC, GIMP, and Inkscape in one command - saves time!</p>
                </div>

                <h3>Advanced Package Management</h3>

                <div class="command-block">
                    <h4>List Installed Packages</h4>
                    <div class="command">dnf list installed</div>
                    <div class="description">Shows all packages currently installed on your system.</div>
                </div>

                <div class="command-block">
                    <h4>View Update History</h4>
                    <div class="command">dnf history</div>
                    <div class="description">
                        <strong>What it does:</strong> Shows a history of all package installations, updates, and removals.<br>
                        <strong>Useful for:</strong> Tracking what changed on your system.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Undo Last Transaction</h4>
                    <div class="command">sudo dnf history undo last</div>
                    <div class="description">
                        <strong>What it does:</strong> Reverses the last package operation.<br>
                        <strong>Use case:</strong> If you installed something by mistake or it broke your system.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Clean Package Cache</h4>
                    <div class="command">sudo dnf clean all</div>
                    <div class="description">
                        <strong>What it does:</strong> Removes cached package files to free up disk space.<br>
                        <strong>When to use:</strong> If you're running low on disk space.
                    </div>
                </div>
            </section>

            <!-- System Management Section -->
            <section id="system">
                <h2><span class="icon">⚙️</span> System Management with systemctl</h2>

                <div class="note">
                    <div class="note-title">💡 Understanding Services</div>
                    <p>Services are programs that run in the background (like web servers, databases, etc.). systemctl helps you control them.</p>
                </div>

                <h3>Service Control</h3>

                <div class="command-block">
                    <h4>Start a Service</h4>
                    <div class="command">sudo systemctl start httpd</div>
                    <div class="description">
                        <strong>What it does:</strong> Starts the Apache web server (or any service).<br>
                        <strong>Common services:</strong> httpd (web server), sshd (remote access), mariadb (database).
                    </div>
                </div>

                <div class="command-block">
                    <h4>Stop a Service</h4>
                    <div class="command">sudo systemctl stop httpd</div>
                    <div class="description">Stops a running service immediately.</div>
                </div>

                <div class="command-block">
                    <h4>Restart a Service</h4>
                    <div class="command">sudo systemctl restart httpd</div>
                    <div class="description">
                        <strong>What it does:</strong> Stops and starts the service.<br>
                        <strong>When to use:</strong> After changing configuration files.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Check Service Status</h4>
                    <div class="command">systemctl status httpd</div>
                    <div class="description">
                        <strong>What it shows:</strong> Whether the service is running, stopped, or failed.<br>
                        <strong>Beginner tip:</strong> Green "active (running)" means it's working!
                    </div>
                </div>

                <div class="command-block">
                    <h4>Enable Service at Boot</h4>
                    <div class="command">sudo systemctl enable httpd</div>
                    <div class="description">
                        <strong>What it does:</strong> Makes the service start automatically when you boot your computer.<br>
                        <strong>Use for:</strong> Services you always want running (like SSH for remote access).
                    </div>
                </div>

                <div class="command-block">
                    <h4>Disable Service at Boot</h4>
                    <div class="command">sudo systemctl disable httpd</div>
                    <div class="description">Prevents the service from starting automatically at boot.</div>
                </div>

                <div class="tip">
                    <div class="tip-title">💚 Quick Combo: Enable and Start Together</div>
                    <div class="command">sudo systemctl enable --now httpd</div>
                    <p>This enables the service for boot AND starts it immediately - two commands in one!</p>
                </div>

                <h3>System Power Management</h3>

                <div class="command-block">
                    <h4>Reboot System</h4>
                    <div class="command">sudo systemctl reboot</div>
                    <div class="description">Safely restarts your computer.</div>
                </div>

                <div class="command-block">
                    <h4>Shutdown System</h4>
                    <div class="command">sudo systemctl poweroff</div>
                    <div class="description">Safely shuts down your computer.</div>
                </div>

                <div class="command-block">
                    <h4>Suspend System</h4>
                    <div class="command">sudo systemctl suspend</div>
                    <div class="description">
                        <strong>What it does:</strong> Puts your computer to sleep (low power mode).<br>
                        <strong>Resume:</strong> Press any key or power button.
                    </div>
                </div>
            </section>

            <!-- Hostname Management -->
            <section id="hostname">
                <h2><span class="icon">🏷️</span> Hostname Management</h2>

                <div class="note">
                    <div class="note-title">💡 What is a Hostname?</div>
                    <p>Your hostname is your computer's name on the network. It's like a nickname that identifies your machine.</p>
                </div>

                <div class="command-block">
                    <h4>View Current Hostname</h4>
                    <div class="command">hostnamectl</div>
                    <div class="description">
                        <strong>What it shows:</strong> Current hostname, operating system, kernel version, and more.<br>
                        <strong>Beginner tip:</strong> This is like "About This PC" on Windows.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Change Hostname</h4>
                    <div class="command">sudo hostnamectl set-hostname my-fedora-pc</div>
                    <div class="description">
                        <strong>What it does:</strong> Changes your computer's name to "my-fedora-pc".<br>
                        <strong>Rules:</strong> Use lowercase letters, numbers, and hyphens only (no spaces).
                    </div>
                </div>

                <div class="command-block">
                    <h4>Set Pretty Hostname (with spaces)</h4>
                    <div class="command">sudo hostnamectl set-hostname "John's Fedora Workstation" --pretty</div>
                    <div class="description">
                        <strong>What it does:</strong> Sets a human-readable name with spaces and special characters.<br>
                        <strong>Use case:</strong> For display purposes in GUI applications.
                    </div>
                </div>

                <div class="example">
                    <div class="example-title">📖 Real-World Example</div>
                    <p>If you have multiple computers, give them descriptive names:</p>
                    <div class="command">sudo hostnamectl set-hostname laptop-home
sudo hostnamectl set-hostname "Home Laptop" --pretty</div>
                    <p>Now your computer is easily identifiable on your network!</p>
                </div>
            </section>

            <!-- Security & Encryption Section -->
            <section id="security">
                <h2><span class="icon">🔒</span> Security & Encryption</h2>

                <div class="warning">
                    <div class="warning-title">⚠️ Important Security Note</div>
                    <p>Security is critical! These commands help protect your data and system. Always keep backups before making security changes.</p>
                </div>

                <h3>SSH Security</h3>

                <div class="command-block">
                    <h4>Generate SSH Key Pair</h4>
                    <div class="command">ssh-keygen -t ed25519 -C "your_email@example.com"</div>
                    <div class="description">
                        <strong>What it does:</strong> Creates a secure key pair for passwordless SSH login.<br>
                        <strong>Beginner explanation:</strong> Like creating a digital lock and key - more secure than passwords!<br>
                        <strong>Where it saves:</strong> ~/.ssh/id_ed25519 (private key) and ~/.ssh/id_ed25519.pub (public key).
                    </div>
                </div>

                <div class="command-block">
                    <h4>Copy SSH Key to Remote Server</h4>
                    <div class="command">ssh-copy-id user@remote-server.com</div>
                    <div class="description">
                        <strong>What it does:</strong> Copies your public key to a remote server for passwordless login.<br>
                        <strong>After this:</strong> You can login without typing a password!
                    </div>
                </div>

                <div class="command-block">
                    <h4>Secure SSH Configuration</h4>
                    <div class="command">sudo nano /etc/ssh/sshd_config</div>
                    <div class="description">
                        <strong>What to change:</strong><br>
                        • Set <code>PermitRootLogin no</code> - Prevents root login (more secure)<br>
                        • Set <code>PasswordAuthentication no</code> - Forces key-based authentication<br>
                        • Set <code>Port 2222</code> - Change default port (reduces automated attacks)<br>
                        <strong>After editing:</strong> Run <code>sudo systemctl restart sshd</code>
                    </div>
                </div>

                <h3>File & Disk Encryption</h3>

                <div class="command-block">
                    <h4>Encrypt a File with GPG</h4>
                    <div class="command">gpg -c sensitive_file.txt</div>
                    <div class="description">
                        <strong>What it does:</strong> Encrypts a file with a password.<br>
                        <strong>Output:</strong> Creates sensitive_file.txt.gpg (encrypted version).<br>
                        <strong>Beginner tip:</strong> Use a strong password - this is what protects your file!
                    </div>
                </div>

                <div class="command-block">
                    <h4>Decrypt a GPG File</h4>
                    <div class="command">gpg sensitive_file.txt.gpg</div>
                    <div class="description">
                        <strong>What it does:</strong> Decrypts the file back to its original form.<br>
                        <strong>You'll need:</strong> The password you used to encrypt it.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Create Encrypted Archive</h4>
                    <div class="command">tar -czf - folder_name | gpg -c > encrypted_backup.tar.gz.gpg</div>
                    <div class="description">
                        <strong>What it does:</strong> Creates a compressed, encrypted backup of a folder.<br>
                        <strong>Perfect for:</strong> Backing up sensitive documents before cloud upload.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Extract Encrypted Archive</h4>
                    <div class="command">gpg -d encrypted_backup.tar.gz.gpg | tar -xzf -</div>
                    <div class="description">Decrypts and extracts the encrypted archive.</div>
                </div>

                <h3>LUKS Disk Encryption</h3>

                <div class="note">
                    <div class="note-title">💡 What is LUKS?</div>
                    <p>LUKS (Linux Unified Key Setup) is full-disk encryption. It encrypts entire partitions, making data unreadable without the password.</p>
                </div>

                <div class="command-block">
                    <h4>Create Encrypted Partition</h4>
                    <div class="command">sudo cryptsetup luksFormat /dev/sdb1</div>
                    <div class="description">
                        <strong>What it does:</strong> Encrypts the partition /dev/sdb1.<br>
                        <strong>⚠️ WARNING:</strong> This ERASES all data on the partition!<br>
                        <strong>You'll be asked:</strong> To type "YES" in uppercase and set a passphrase.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Open Encrypted Partition</h4>
                    <div class="command">sudo cryptsetup luksOpen /dev/sdb1 my_encrypted_drive</div>
                    <div class="description">
                        <strong>What it does:</strong> Unlocks the encrypted partition.<br>
                        <strong>After this:</strong> Access it at /dev/mapper/my_encrypted_drive
                    </div>
                </div>

                <div class="command-block">
                    <h4>Close Encrypted Partition</h4>
                    <div class="command">sudo cryptsetup luksClose my_encrypted_drive</div>
                    <div class="description">
                        <strong>What it does:</strong> Locks the encrypted partition.<br>
                        <strong>Important:</strong> Always close before removing the drive!
                    </div>
                </div>

                <div class="example">
                    <div class="example-title">📖 Complete Encryption Example</div>
                    <p><strong>Scenario:</strong> Encrypt a USB drive for sensitive data</p>
                    <div class="command"># 1. Format partition with LUKS
sudo cryptsetup luksFormat /dev/sdb1

# 2. Open the encrypted partition
sudo cryptsetup luksOpen /dev/sdb1 secure_usb

# 3. Create filesystem
sudo mkfs.ext4 /dev/mapper/secure_usb

# 4. Mount it
sudo mount /dev/mapper/secure_usb /mnt

# 5. Use it normally, then unmount
sudo umount /mnt

# 6. Close encryption
sudo cryptsetup luksClose secure_usb</div>
                </div>

                <h3>Password & User Security</h3>

                <div class="command-block">
                    <h4>Change Your Password</h4>
                    <div class="command">passwd</div>
                    <div class="description">
                        <strong>What it does:</strong> Changes your user password.<br>
                        <strong>Password tips:</strong> Use 12+ characters, mix letters/numbers/symbols, avoid dictionary words.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Lock a User Account</h4>
                    <div class="command">sudo usermod -L username</div>
                    <div class="description">
                        <strong>What it does:</strong> Locks the user account (prevents login).<br>
                        <strong>Use case:</strong> Temporarily disable an account without deleting it.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Unlock a User Account</h4>
                    <div class="command">sudo usermod -U username</div>
                    <div class="description">Unlocks a previously locked account.</div>
                </div>

                <div class="command-block">
                    <h4>View Failed Login Attempts</h4>
                    <div class="command">sudo lastb</div>
                    <div class="description">
                        <strong>What it shows:</strong> Failed login attempts (potential security threats).<br>
                        <strong>Look for:</strong> Repeated failed attempts from unknown IPs.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Check Who's Logged In</h4>
                    <div class="command">who</div>
                    <div class="description">
                        <strong>What it shows:</strong> All currently logged-in users.<br>
                        <strong>Security check:</strong> Make sure you recognize all logged-in users!
                    </div>
                </div>
            </section>

            <!-- Scripting Section -->
            <section id="scripting">
                <h2><span class="icon">📝</span> Bash Scripting Essentials</h2>

                <div class="note">
                    <div class="note-title">💡 What is Bash Scripting?</div>
                    <p>Bash scripts are text files containing commands that run automatically. They're like mini-programs that automate repetitive tasks!</p>
                </div>

                <h3>Creating Your First Script</h3>

                <div class="command-block">
                    <h4>Create a Script File</h4>
                    <div class="command">nano my_script.sh</div>
                    <div class="description">Opens the nano text editor to create a new script.</div>
                </div>

                <div class="example">
                    <div class="example-title">📖 Basic Script Structure</div>
                    <div class="command">#!/bin/bash
# This is a comment - it explains what the script does

echo "Hello, World!"
echo "This is my first script!"</div>
                    <p><strong>Line 1:</strong> Shebang (#!) tells Linux this is a bash script<br>
                    <strong>Line 2:</strong> Comments start with # and are ignored<br>
                    <strong>echo:</strong> Prints text to the screen</p>
                </div>

                <div class="command-block">
                    <h4>Make Script Executable</h4>
                    <div class="command">chmod +x my_script.sh</div>
                    <div class="description">
                        <strong>What it does:</strong> Gives the script permission to run.<br>
                        <strong>Must do this:</strong> Every time you create a new script.
                    </div>
                </div>

                <div class="command-block">
                    <h4>Run Your Script</h4>
                    <div class="command">./my_script.sh</div>
                    <div class="description">
                        <strong>The ./ means:</strong> Run the script in the current directory.<br>
                        <strong>Output:</strong> You'll see "Hello, World!" and "This is my first script!"
                    </div>
                </div>

                <h3>Script Variables</h3>

                <div class="example">
                    <div class="example-title">📖 Using Variables</div>
                    <div class="command">#!/bin/bash

# Define variables
NAME="John"
AGE=25

# Use variables (with $)
echo "My name is $NAME"
echo "I am $AGE years old"

# Get user input
echo "What's your name?"
read USER_NAME
echo "Hello, $USER_NAME!"</div>
                    <p><strong>Variables:</strong> Store information for later use<br>
                    <strong>$NAME:</strong> Dollar sign retrieves the variable value<br>
                    <strong>read:</strong> Gets input from the user</p>
                </div>

                <h3>Conditional Statements (If/Else)</h3>

                <div class="example">
                    <div class="example-title">📖 If Statement Example</div>
                    <div class="command">#!/bin/bash

echo "Enter your age:"
read AGE

if [ $AGE -ge 18 ]; then
    echo "You are an adult!"
else
    echo "You are a minor."
fi</div>
                    <p><strong>-ge:</strong> Greater than or equal to<br>
                    <strong>-lt:</strong> Less than<br>
                    <strong>-eq:</strong> Equal to<br>
                    <strong>fi:</strong> Ends the if statement (if backwards!)</p>
                </div>

                <h3>Loops</h3>

                <div class="example">
                    <div class="example-title">📖 For Loop Example</div>
                    <div class="command">#!/bin/bash

# Loop through numbers 1 to 5
for i in 1 2 3 4 5
do
    echo "Number: $i"
done

# Loop through files
for file in *.txt
do
    echo "Found file: $file"
done</div>
                    <p><strong>for...do...done:</strong> Repeats commands for each item<br>
                    <strong>*.txt:</strong> Matches all .txt files in current directory</p>
                </div>

                <div class="example">
                    <div class="example-title">📖 While Loop Example</div>
                    <div class="command">#!/bin/bash

COUNTER=1

while [ $COUNTER -le 5 ]
do
    echo "Count: $COUNTER"
    COUNTER=$((COUNTER + 1))
done</div>
                    <p><strong>while:</strong> Repeats while condition is true<br>
                    <strong>$((COUNTER + 1)):</strong> Math operation (adds 1)</p>
                </div>

                <h3>Practical Script Examples</h3>

                <div class="example">
                    <div class="example-title">📖 System Update Script</div>
                    <div class="command">#!/bin/bash

echo "Starting system update..."

# Update package list
sudo dnf check-update

# Perform update
sudo dnf update -y

# Clean old packages
sudo dnf autoremove -y

echo "System update complete!"</div>
                    <p><strong>Use case:</strong> Automate weekly system updates<br>
                    <strong>-y flag:</strong> Automatically answers "yes" to prompts</p>
                </div>

                <div class="example">
                    <div class="example-title">📖 Backup Script</div>
                    <div class="command">#!/bin/bash

# Variables
SOURCE="/home/$USER/Documents"
BACKUP_DIR="/home/$USER/Backups"
DATE=$(date +%Y-%m-%d)
BACKUP_FILE="backup-$DATE.tar.gz"

# Create backup directory if it doesn't exist
mkdir -p $BACKUP_DIR

# Create compressed backup
tar -czf $BACKUP_DIR/$BACKUP_FILE $SOURCE

echo "Backup created: $BACKUP_FILE"</div>
                    <p><strong>Use case:</strong> Daily automated backups<br>
                    <strong>date +%Y-%m-%d:</strong> Gets current date (2024-01-15)<br>
                    <strong>mkdir -p:</strong> Creates directory if it doesn't exist</p>
                </div>

                <div class="example">
                    <div class="example-title">📖 Disk Space Monitor</div>
                    <div class="command">#!/bin/bash

# Get disk usage percentage
USAGE=$(df -h / | awk 'NR==2 {print $5}' | sed 's/%//')

echo "Current disk usage: $USAGE%"

# Alert if over 80%
if [ $USAGE -gt 80 ]; then
    echo "⚠️ WARNING: Disk usage is above 80%!"
    echo "Please free up some space."
else
    echo "✓ Disk space is OK"
fi</div>
                    <p><strong>Use case:</strong> Monitor disk space automatically<br>
                    <strong>awk:</strong> Extracts specific columns from output<br>
                    <strong>sed:</strong> Removes the % symbol</p>
                </div>

                <div class="tip">
                    <div class="tip-title">💚 Pro Tip: Schedule Scripts with Cron</div>
                    <div class="command"># Edit crontab
crontab -e

# Run backup script daily at 2 AM
0 2 * * * /home/user/backup.sh

# Run update script weekly on Sunday at 3 AM
0 3 * * 0 /home/user/update.sh</div>
                    <p>Cron runs scripts automatically at scheduled times!</p>
                </div>
            </section>

            <!-- Network Management -->
            <section id="network">
                <h2><span class="icon">🌐</span> Network Management</h2>

                <h3>Basic Network Commands</h3>

                <div class="command-block">
                    <h4>Show IP Address</h4>
                    <div class="command">ip addr show</div>
                    <div class="description">
                        <strong>What it shows:</strong> All network interfaces and their IP addresses.<br>
                        <strong>Look for:</strong> inet 192.168.x.x (your local IP) or inet 10.x.x.x
                    </div>
                </div>

                <div class="command-block">
                    <h4>Test Internet Connection</h4>
                    <div class="command">ping -c 4 google.com</div>
                    <div class="description">
                        <strong>What it does:</strong> Sends 4 packets to Google to test connectivity.<br>
                        <strong>Good result:</strong> 0% packet loss<br>
                        <strong>-c 4:</strong> Limits to 4 pings (otherwise it runs forever!)
                    </div>
                </div>

                <div class="command-block">
                    <h4>Show Network Connections</h4>
                    <div class="command">ss -tuln</div>
                    <div class="description">
                        <strong>What it shows:</strong> All active network connections and listening ports.<br>
                        <strong>Security check:</strong> Make sure you recognize all listening services!
                    </div>
                </div>

                <div class="command-block">
                    <h4>Download a File</h4>
                    <div class="command">wget https://example.com/file.zip</div>
                    <div class="description">
                        <strong>What it does:</strong> Downloads a file from the internet.<br>
                        <strong>Alternative:</strong> <code>curl -O https://example.com/file.zip</code>
                    </div>
                </div>
            </section>

            <!-- Firewall Section -->
            <section id="firewall">
                <h2><span class="icon">🔥</span> Firewall Management</h2>

                <div class="note">
                    <div class="note-title">💡 What is a Firewall?</div>
                    <p>A firewall controls what network traffic can enter or leave your computer. It's like a security guard for your network connections!</p>
                </div>

                <div class="command-block">
                    <h4>Check Firewall Status</h4>
                    <div class="command">sudo firewall-cmd --state</div>
                    <div class="description">
                        <strong>Output:</strong> "running" means firewall is active and protecting you!
                    </div>
                </div>

                <div class="command-block">
                    <h4>List Open Ports</h4>
                    <div class="command">sudo firewall-cmd --list-all</div>
                    <div class="description">
                        <strong>What it shows:</strong> All allowed services and open ports.<br>
                        <strong>Common ports:</strong> 22 (SSH), 80 (HTTP), 443 (HTTPS)
                    </div>
                </div>

                <div class="command-block">
                    <h4>Allow HTTP Traffic (Web Server)</h4>
                    <div class="command">sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload</div>
                    <div class="description">
                        <strong>What it does:</strong> Opens port 80 for web traffic.<br>
                        <strong>--permanent:</strong> Keeps the rule after reboot<br>
                        <strong>--reload:</strong> Applies the changes immediately
                    </div>
                </div>

                <div class="command-block">
                    <h4>Allow HTTPS Traffic (Secure Web)</h4>
                    <div class="command">sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload</div>
                    <div class="description">Opens port 443 for secure web traffic (SSL/TLS).</div>
                </div>

                <div class="command-block">
                    <h4>Open Custom Port</h4>
                    <div class="command">sudo firewall-cmd --permanent --add-port=8080/tcp
sudo firewall-cmd --reload</div>
                    <div class="description">
                        <strong>What it does:</strong> Opens port 8080 for TCP traffic.<br>
                        <strong>Use case:</strong> Custom applications or development servers.
                    </div>
                </div>

                <div class="warning">
                    <div class="warning-title">⚠️ Security Warning</div>
                    <p>Only open ports you actually need! Each open port is a potential security risk. Close ports when you're done with them.</p>
                </div>
            </section>

            <!-- Monitoring Section -->
            <section id="monitoring">
                <h2><span class="icon">📊</span> System Monitoring</h2>

                <div class="command-block">
                    <h4>View Running Processes</h4>
                    <div class="command">top</div>
                    <div class="description">
                        <strong>What it shows:</strong> Real-time view of running processes, CPU, and memory usage.<br>
                        <strong>How to exit:</strong> Press 'q'<br>
                        <strong>Sort by memory:</strong> Press 'M'<br>
                        <strong>Sort by CPU:</strong> Press 'P'
                    </div>
                </div>

                <div class="command-block">
                    <h4>Check Memory Usage</h4>
                    <div class="command">free -h</div>
                    <div class="description">
                        <strong>What it shows:</strong> Total, used, and free memory.<br>
                        <strong>-h flag:</strong> Human-readable format (GB/MB instead of bytes)
                    </div>
                </div>

                <div class="command-block">
                    <h4>Check Disk Usage</h4>
                    <div class="command">df -h</div>
                    <div class="description">
                        <strong>What it shows:</strong> Disk space usage for all mounted filesystems.<br>
                        <strong>Look for:</strong> Use% column - if it's over 90%, time to clean up!
                    </div>
                </div>

                <div class="command-block">
                    <h4>Check Folder Size</h4>
                    <div class="command">du -sh /path/to/folder</div>
                    <div class="description">
                        <strong>What it shows:</strong> Total size of a specific folder.<br>
                        <strong>Find large folders:</strong> <code>du -h --max-depth=1 | sort -hr</code>
                    </div>
                </div>
            </section>

            <!-- Support Section -->
            <div class="support-section">
                <h2>🚀 Keep This Project Going</h2>
                <p style="color: #e6edf3; margin: 20px 0;">Creating comprehensive guides like this takes time, research, and lots of coffee! ☕</p>
                <div class="support-buttons">
                    <a href="https://github.com/wikicrafter/Mytxt" class="support-btn">⭐ Star on GitHub</a>
                    <a href="https://ko-fi.com/gigaa" class="support-btn">☕ Buy Me a Coffee</a>
                    <a href="https://github.com/wikicrafter" class="support-btn">👤 Follow on GitHub</a>
                </div>
                <p style="color: #e6edf3; margin-top: 20px; font-style: italic;">Every star, every coffee, every follow makes a difference. Thank you for your support! 🙏✨</p>
            </div>
        </div>

        <footer>
            <p>📚 Fedora Linux Complete Command Reference Guide</p>
            <p>For educational purposes only. Always ensure you have proper authorization before executing system commands.</p>
            <p style="margin-top: 10px;">Made with ❤️ for the Linux community</p>
        </footer>
    </div>

    <div class="scroll-top" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">
        ↑
    </div>
</body>
</html>
