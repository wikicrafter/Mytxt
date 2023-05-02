PowerShell script that you can use to rename a file in the system32 directory:
```
$filePath = "C:\Windows\System32\file.dll"
$newName = "newFile.dll"
Rename-Item -Path $filePath -NewName $newName
```
To use this script, replace file.dll with the name of the file you want to rename and newFile.dll with the new name you want to give it.
<br>
CMD - ren C:\Windows\System32\file.dll newFile.dll
