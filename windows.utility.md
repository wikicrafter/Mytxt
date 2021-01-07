!

PsExec v2.2Group policy editor to run it use gpedit.msc if you are in w>or type: gpmc.msc
working with group policy is equivalent with register editor.

to block third party cookies then let's do next steps:
1. Launch GPO by typing gpedit.msc into the Search box and
pressing Enter.
 If you want to configure the policy for computer, navigate
to Computer Configuration ➤ Administrative Templates ➤
Windows Components ➤ Microsoft Edge .
 If you want to configure the policy for the user, navigate to
User Configuration ➤ Administrative Templates ➤ Windows
Components ➤ Edge UI.
 2. Within the Microsoft Edge folder on either configuration,
you will notice several settings listed on the right pane. On a
newly installed device, all of the settings will exhibit the Not
Configured status by default,





➤ Administrative Templates ➤
Start Menu and Taskbar ➤ Start Layout

 lusrmgr.msc  local user and group

GPO vs. DSC (Desired State Configuration )


1.Customize and rearange the Start/Sceen menu that you want for your user 


disable password revealbutton: Computer Configuration ➤ Administrative Templates ➤
Windows Components ➤ Credential User Interface

Preventing Users from Customizing Windows Using
 Registry Manipulation - User Configuration ➤ Administrative Templates ➤ System  : prevent access to registry editing tools
Note To allow RegEdit to run silently, you can use Registry Editor in silent mode using
the switch /s . Silent means that if you type RegEdit /s filename.reg at the command
prompt, you can import the filename.reg registry file directly into the registry without the
user being prompted. This is useful for scripting registry actions and automation scenarios. 



to prevent command promt access do next things: choose prevent access to command prompt



Other Important Policy Settings for Windows
Customization 

Show first sign-in
animation:
 Disables the first sign-in animation
that appears just after you create
a new user account and sign into
that account for the first time in
Windows 8 or later.
 Computer Configuration ➤
Administrative Templates ➤
System ➤ Logon 


Force a specific
background and
accent color
 Forces users to use a specific color
accent and background color,
especially for the Start Screen in
Windows 8 and 8.1. For this, you
must enable the policy setting and
define a HTML color code in the
available color option.
 Computer Configuration ➤
Administrative Templates
➤ Control Panel ➤
Personalization



Turn off switching
between recent
apps
 In Windows 8 and 8.1, you can move
cursor/pointer to top left corner
of screen, which lets you to switch
between currently opened apps. You
can configure this policy to enable or
disable (default) this functionality.
 User Configuration ➤
Administrative Templates
➤ Windows Components ➤
Edge U



Turn off toast
notifications on
the lock screen
 Turns off toast notifications from
apps on the lock screen. Other
 polices located at same path allow
you to customize the amount
of notifications you receive.
Applicable to Windows 8, Windows
Server 2012, or later.
 User Configuration ➤
Administrative Templates ➤
Start Menu and Taskbar ➤
Notifications 



Turn off automatic
download and
install of updates
 Turns off automatic updates
to installed Store apps on your
system. Applicable to Windows 8.1,
Windows Server 2012 R2, or later.
You can locate the policy to turn off
the Store app itself at this same path.
 Computer Configuration ➤
Administrative Templates
➤ Windows Components
➤ Store 



Allow telemetry In Windows 10, Microsoft collects
data such as crash logs, usage of
features, etc. to improve the OS in
successive builds. This policy helps
you limit how much data Microsoft
can take from your system. In
Enterprise-based editions, you can
completely block telemetry. In other
editions, it is possible to prevent
telemetry partially with this setting.
 Computer Configuration ➤
Administrative Templates
➤ Windows Components
➤ Data Collection and
Preview Builds 


Disable user
control over
preview builds
 Microsoft offers preview builds of
Windows 10 to Windows Insiders,
people who test these previews and
provide feedback to the company.
Using this policy setting, you can
customize the way users receive
newer preview builds on their
system. If you turn on or enable
the policy, users won't be able to
change their settings for the Choose
how preview builds are installed
section under Settings app ➤
Windows Updates.
 Computer Configuration ➤
Administrative Templates
➤ Windows Components
➤ Data Collection and
Preview Builds 



Low battery
notification level
 By default, Windows triggers low
battery notification at 10% battery
left; you can customize this setting
to enter your desired percentage. It
works for Windows Vista and later.
 Computer Configuration ➤
Administrative Templates
➤ System ➤ Power
Management ➤ Notification
Settings 



Untrusted font
blocking
 Using this security-based policy, you
can prevent programs from loading
untrusted fonts, or fonts that have not
been verified, to your Windows 10
system. You can also customize this
policy to unblock untrusted fonts but
create a log of events they make.
 Computer Configuration ➤
Administrative Templates
➤ System ➤ Mitigation
Options 



Items displayed in
Places bar
 The Places bar is basically the
items linked under Favorites in
File/Windows Explorer. To add
your desired folder manually to
the Places bar, you must browse
to the folder, right-click it, and
select Add current location to
Favorites . Using this setting, you
can customize the Places bar and
forcefully add your desired items
for users in your environment.
 User Configuration ➤
Administrative Templates
➤ Windows Components
➤ File Explorer ➤ Common
Open File Dialog



Show the Apps
view automatically
when the user goes
to the Start Screen
 With this setting, you can configure
Windows 8.1 such that when a user
tries to go to Start Screen, he/she
sees the Apps view instead of the
app tiles.
 User Configuration ➤
Administrative Templates ➤
Start Menu and Taskbar



Prevent users
from uninstalling
applications from
the Start Screen
 In Windows 8, Windows Server
 2012 and later, users are able to
uninstall apps straight from the
Start Screen. You can prevent this
from happening via this setting.
 User Configuration ➤
Administrative Templates ➤
Start Menu and Taskbar 


Allow all trusted
apps to install
 Generally, you can't install apps in
Windows 8 or later unless they are
installed via the Windows Store. To
allow Windows to install apps from
a trusted source other than from
the Store, you may configure this
policy and apply it on user systems.
 Computer Configuration ➤
Administrative Templates
➤ Windows Components ➤
App Package Deployment 



No auto-restart
with loggedon users for
scheduled
automatic updates
installation
 This policy setting helps you to
decide whether you want to have
automatic restart after you make
scheduled installation of Windows
Updates or not. When this setting is
Enabled, users are asked to reboot
manually and the system does not
automatically reboot. You can also
configure various Window Update
settings at this policy path.
 Computer Configuration ➤
Administrative Templates
➤ Windows Components ➤
Windows Update 


Force a specific
default lock screen
image
 Forces users to have a particular
lock screen wallpaper. In the policy
configuration options, you can
specify the wallpaper path. You
can type a local path, such as C:\
windows\web\screen\lockscreen.
jpg or a UNC path, such as \\Server\
Share\Corp.jpg . This setting only
applies to domain-joined machines.
 On this same path , you can also
locate the lock screen settings
to not display it at all, prevent
enabling slide show on it, and
prevent users from changing its
image. These settings work for
Windows 8 and later.
 Computer Configuration ➤
Administrative Templates
➤ Control Panel ➤
Personalization 





Show a “Run as
different user”
command on Start
 Generally, when we right-click a
program within File Explorer or at
the Start Screen, we see the option
to Run as administrator using which
program can be opened in elevated
mode. Via this policy, you can modify
the behavior to allow the Run as
different user option. You can then
run programs as the other users that
are available on your system . This is
especially helpful to administrators
while troubleshooting issues for a
specific user account and to observe
problems on it. This works well with a
domain as well as on a local machine.
This policy is available on Windows
8 or later.
 User Configuration ➤
Administrative Templates ➤
Start Menu and Taskbar 


■ Tip To configure Startup/Logon and Shutdown/Logoff scripts in GPO, navigate to GPO
➤ Computer/User Configuration ➤ Windows Settings ➤ Scripts. The configured scripts are
stored in the registry database at HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Windows\
System\Scripts for the computer side and HKEY_LOCAL_MACHINE\SOFTWARE\Policies\
Windows\System\Scripts at the user side. 




Important GPO Settings to Enable or Disable Windows Features
 GPO Setting Importance Policy Path (For GPMC,
include “Policies”
after Computer/User
Configuration)



Allow Cortana Cortana offers web search integration with
an offline search feature in Windows 10.
It can provide additional assistance, such
as real-time updates on weather forecast,
news, reminders and local information.
It can also accept multiple inputs such as
ink, voice, and gestures. To avoid extra or
unnecessary data consumption on mobile
devices, you may want to block Cortana
completely.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤ Searches 



Prevent the
usage of
OneDrive for
file storage
 In Windows 8 or later, OneDrive (formerly
SkyDrive) helps you to store and
synchronize your files between the cloud
server and your machine. In Windows
8.1 and later, Microsoft made an in-depth
integration of OneDrive with File Explorer.
With this policy, you may block usage of
OneDrive completely. Other OneDrivededicated settings are at this policy path.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤ OneDrive 



Turn off
Windows
Defender
 Windows Defender has been part of the
Windows family since Windows Vista. It is
the first line of defense against malware .
This policy can be used to disable
Windows Defender if you plan to use a
third-party security suite (although most
third-party anti-malware tools will disable
Windows Defender during installation).
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤ Windows
Defender 


 GPO Setting Importance Policy Path (For GPMC,
include “Policies”
after Computer/User
Configuration)


Prevent the
computer
from joining a
HomeGroup
 Specifies whether users can add computers
to a HomeGroup . By default, users can
add their computer to a HomeGroup on a
private network. Enabling this policy will
result in users losing the ability to add their
machine to a HomeGroup. This works with
Windows 7 or later.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤
HomeGroup 



Turn off
Windows Mail
application
 Blocks the Windows Mail application in
Windows Vista or later.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤ Windows
Mail 



Turn off
location
 For today's users, location is one of the
most important features in Windows. Most
of the apps available nowadays require
a location setting to provide the full user
experience. From a security point of view,
 location is a prime concern, especially for
apps like banking. This policy allows you
to control whether you want to share your
location with programs and settings or
not. Applicable to Windows 7 and later.
 User Configuration ➤
Administrative Templates
➤ Windows Components
➤ Location and Sensors 





Disable
Windows
error
reporting
 Whenever something unexpected occurs
on your Windows machine, such as crash
or freezing of programs, a log file is created.
The Windows Error Reporting Service
running in the background collects these
logs and may send them to Microsoft or
an internal server in your organization.
Enabling this policy will completely
disable the error reporting feature. It is
applicable to Windows Vista or later.
 User Configuration ➤
Administrative Templates
➤ Windows Components
➤ Windows Error
Reporting 




Allow the use
of biometrics
 Biometrics allows you to log in using
fingerprint or facial recognition. If your
system supports biometrics, then this
policy lets you disable this feature. This
setting works well in Windows 7, Windows
Server 2008 R2 systems, or later.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤
Biometrics 


Disable Wi-Fi
Sense
 Wi-Fi Sense is one of many new
features introduced in Windows 10. It
automatically locates and connects to
Wi-Fi hotspots. Wi-Fi Sense allows you
to join networks that your contacts in
Skype, Outlook, and Facebook share. The
feature is also available with Windows
Phone since version 8. This policy can
be configured to enable or disable Wi-Fi
Sense. It is applicable to Windows 10 Build
10586 (Version 1511) or later.
 Computer Configuration
➤ Administrative
Templates ➤ SCM: Wi-Fi
Sense 



Remove Task
Manager
 Task Manager ( taskmgr.exe ) lets you view
running processes and CPU memory
usage, and manage services. Using this
policy, you can configure whether users
can access Task Manager. When this policy
is enabled, users can't open Task Manager.
Within the policy path, you can configure
other policies such preventing users from
changing password on demand, locking
their system. You can remove all buttons
that can contribute to logging off users.
 User Configuration ➤
Administrative Templates
➤ System ➤ Ctrl+Alt+Del
Options 



Turn off
Autoplay
 Autoplay allows Windows to begin reading
data when you plug in a drive such as
USB, DVD, floppy etc. Though you can
manage Autoplay options in the Settings
app, with this policy you can configure
the setting via a GPO . When this policy is
Enabled , Autoplay won't work on CDROM and removable media drives, or it
can be disabled on all drives. You can find
other Autoplay customization policies on
this setting path.
 Computer Configuration
➤ Administrative
Templates ➤ Windows
Components ➤ Autoplay
Policies 



 Enhancing System Security by Using Security
Policies (GPO Subset ) 



Changing the Impact of User Account Control (UAC)
Prompts 

UAC 
There are four levels for UAC settings, which are as follows:
• Always notify : The UAC prompt appears when software/apps
try to make a change to the system or when you make changes
Windows settings. The screen will be dimmed and you need to
read the content of the prompt and provide your approval/denial,
if you are an administrator (see Figure  3-14 ). If you are standard
user, you need to enter the administrator's password. This is a
highly secure UAC level.
• Notify only when apps try to make changes to the system
(default) : Get notified only when apps/programs try to make
changes to your system and you accept/reject these operations.
The desktop will be dimmed when the UAC prompt appears. No
notification/prompt will be sent when you're changing settings.
• Notify only when apps try to make changes to system (but don't
dim desktop) : This level has the same effect as the previous one.
The only difference is that the desktop is not dimmed when the
UAC prompt appears.
• Never notify : This level disables UAC, and no notification/prompt
appears when either you or any app makes changes to the system.
This setting is not recommended due to the reduced security. 


With the help of security policies, you can configure various UAC settings. These
policies can be found at Security Settings ➤ Local Policies ➤ Security Options in the
Local Security Policy snap-in. There are 10 security policies dedicated to UAC, which are
shown in Figure  
1. Admin Approval Mode for the Built-In Administrator
account
 2. Allow UIAccess applications to prompt for elevation
without using the secure desktop
 3. Behavior of the elevation prompt for administrators in
Admin Approval Mode
 4. Behavior of the elevation prompt for standard users
 5. Detect application installations and prompt for elevation
 6. Only elevate executables that are signed and validated
 7. Only elevate UIAccess applications that are installed in
secure locations
 8. Run all administrators in Admin Approval Mode
 9. Switch to the secure desktop when prompting for elevation
 10. Virtualize file and registry write failures to per-user
locations
 



Managing Windows Firewall with Security Policies in GPO 




Accounts: Guest
account status
 If someone wants to use your Windows
machine but they do not have a
permanent account, they will need use a
Guest account. While users are on Guest
account, they can’t install new programs
to your machine and they don’t have any
access to user data of permanent account
profiles. This security setting determines if
the Guest account is enabled or disabled.
By default, the policy is Disabled. Guest
accounts are seldom used in practice.
 Security Settings
➤ Local Policies ➤
Security Options



Interactive logon:
Do not require
CTRL+ALT+DEL
 If this policy is enabled on a computer,
a user is not required to press the
CTRL+ALT+DEL key combination to
log on. You should note that not having
to press CTRL+ALT+DEL leaves users
susceptible to attacks that attempt to
intercept the user's passwords as the
attack can be initiated remotely. Requiring
CTRL+ALT+DEL before users log on
ensures that users are physically present
when entering their passwords. By default,
on domain-connected computers, this
setting is enabled for at least Windows 8 or
later and disabled for Windows 7 or earlier.
On stand-alone computers, the default
setting is Enabled.
 Security Settings
➤ Local Policies ➤
Security Options 




Take ownership of
files or other objects
 In many cases, we need to take ownership
of items such files, folders, and Active
Directory Objects (ADOs) . This security
policy helps you decide who can take
ownership of these objects from you are
the user group under your administration.
You can also discover other security
policies regarding user rights at this same
policy path.
 Security Settings
➤ Local Policies
➤ User Rights 



Account Lockout
Threshold
 If this policy is appropriately defined,
and a user login fails due to incorrect
credentials, the user will be blocked from
entering further login details for a specific
amount of time. You can modify the
number of failed attempts and also the
amount of time (using Account Lockout
Duration policy) that the user is locked out
of the system. The default value is 0, which
means the user will not be blocked, even
after entering incorrect credentials an
infinite number of times.
 Security Settings ➤
Account Policies ➤
Account Lockout
Policy


Key Points:
• Group Policy is used as a robust tool when customizing and
maintaining core features of Windows.
• You can force users to adopt specific settings and deploy a fixed
layout of the Start Menu/Screen with the help of a GPO.
• It is easy to disable Windows features, such as access to the
registry, or the ability to run the command prompt, or to open
Windows Firewall, via Advanced Security.
• The whole Control Panel, or access to selected applets in the
Control Panel, can be disabled from users with Group Policy.
• You can easily change your network name or alter its visibility
using the Network List Manager Policies within Group Policy


Renaming the Administrator Account
 We think that this is one of the best security policy settings you can configure. By default,
the built-in administrator account name is called Administrator . The Administrator
account is associated with a specific security identifier (SID ) key. Windows will verify
that the SID that is associated with the built-in Admin account. This policy setting can be
configured in the Security Policy snap-in ( secpol.msc ). It is located at Security Settings ➤
Local Policies ➤ Security Options.
 In the policy setting window shown in Figure  7-8 , you can type your desired name
by replacing Administrator . By doing so, you can enhance your Windows system security
and prevent hackers from searching out your default Administrative account on your PC.
You will need to reboot the machine to make this change effective. 




Note Renaming the Administrator account should be done only when it is badly
required. Sometimes it may cause breaking of services, or result in losing the ability to
install or use programs. Hence, be careful when renaming the Admin account . 


Disabling Access to the Control Panel and Settings App
 The Control Panel, as we all know, is the popular location for managing settings in
Windows. With the release of Windows 10, Microsoft has shifted and even duplicated
many of the options found in the Control Panel to a new Settings app. For the time being,
the Control Panel will still offer the same functionality as it did in previous versions of
Windows, and for many people this will be the default location for Windows settings.
 You can modify access to the Control Panel and the Settings app feature by using
Group Policy as required. The relevant policy setting can be found at following path  User Configuration ➤ Policies ➤ Administrative Templates ➤
Control Panel (in GPMC) and User Configuration ➤ Administrative Templates ➤ Control
Panel(in LGPO)

 Setting Custom Logon Screen Background Wallpaper
 With the help of this Group Policy tweak, you will be able to replace your wallpaper from the
current default logon screen background wallpaper to a choice of wallpaper of your own.
All you need to do is to configure the Always use Custom logon background wallpaper 
The policy can be found at Computer
Configuration ➤ Policies ➤ Administrative Templates ➤ System ➤ Logon (in GPMC) and
Computer Configuration ➤ Administrative Templates ➤ System ➤ Logon (in LGPO).



