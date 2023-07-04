### Clean Temp Files


#!/bin/bash

# Clean temporary files
echo "Cleaning temporary files..."

# Clean the system-wide temporary directory
sudo rm -rf /tmp/*

# Clean the user's temporary directory
rm -rf ~/tmp/*

echo "Temporary files cleaned."


<br>


