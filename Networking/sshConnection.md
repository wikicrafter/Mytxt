* Create Key = ssh-keygen -t rsa -b 4096 -C "test@example.com”
* add key to agent = eval "$(ssh-agent -s)" Then enter in: ssh-add ~/.ssh/id_rsa :to add your created key.
* Copy it by command: clip < ~/.ssh/id_rsa.pub
* Last but not least save it where u want to save it
