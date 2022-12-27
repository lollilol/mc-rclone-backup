# mc-rclone-backup
A simple script to backup your minecraft server using rclone and 7zip
If you don't wanna execute the script as root you need to add "sudo" in front of every "systemctl" and give the user the right to execute "systemctl (without password if you wanna run it unattended)

## Hard dependency
This script currently has a hard dependency on **systemctl**, this is how i stop my minecraft servers.
Feel free to change it, depending on how you are gonna stop your minecraft server.

## Default settings
The default settings assume that 
* rclone (in path) and 7zip (**/usr/local/bin/7z**) is installed and executable.
* that the user executing the script has "NOPASSWD" sudo rights (so you dont have to type your sudo password), atleast to use the command to stop and start the server, in my case **systemctl (start|stop) mc@survival**
* that minecraft server(s) are stored in **/opt/minecraft/**
* the rclone remote is **mc:/**
* a logfile directory exists in **$HOME/logs/**
* a temporary directory (for zipping the files in) exists in **$HOME/tmp/**


### This is how the directory/file structure would look if the default settings are used:
```
 mc:
 └── February
     └── server
         ├── 2021.02.01-22.00_server-survival.7z
         ├── 2021.02.02-22.00_server-survival.7z
         ├── 2021.02.02-22.30_server-survival.7z
     └── world
         ├── 2021.02.01-22.00_world-survival.7z
         ├── 2021.02.02-22.00_world-survival.7z
         └── 2021.02.02-22.30_world-survival.7z
 └── March
     └── server
         ├── 2021.03.01-22.00_server-survival.7z
         ├── 2021.03.02-22.00_server-survival.7z
         ├── 2021.03.02-22.30_server-survival.7z
     └── world
         ├── 2021.03.01-22.00_world-survival.7z
         ├── 2021.03.02-22.00_world-survival.7z
         └── 2021.03.02-22.30_world-survival.7z
```
