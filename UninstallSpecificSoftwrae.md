```
@echo off
echo Uninstalling Software...
echo.
wmic product where "Name='Type here software name'" call uninstall /nointeractive
echo.
echo Software has been uninstalled.
pause

```
