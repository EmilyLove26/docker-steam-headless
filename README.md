# Headless Steam Service

Play your games in the browser with audio. Connect another device and use it with Steam Remote Play. 

## Features:
- Full video/audio noVNC web access to a Xfce4 Desktop
- NVIDIA GPU support
- Root access
- SSH server for remote terminal access

---
## Notes:

### ADDITIONAL SOFTWARE:
If you wish to install additional applications, you can generate a
script inside the `~/init.d` directory ending with ".sh". This will be executed on the container startup.

### STORAGE PATHS:
Everything that you wish to save in this container should be stored in the home directory or a docker container mount that you have specified. All files that are store outside your home directory are not persistent and will be wiped if there is an update of the container or you change something in the template.

### GAMES LIBRARY:
It is recommended that you mount your games library to `/games` and configure Steam to add that path.

### AUTO START APPLICATIONS:
In this container, Steam is configured to automatically start. If you wish to add additional services to automatically start, add them under **Applications > Settings > Session and Startup** in the WebUI.

### NETWORK MODE:
If you want to use the container as a Steam Remote Play (previously "In Home Streaming") host device you should create a custom network and assign this container it's own IP, if you don't do this the traffic will be routed through the internet since Steam thinks you are on a different network.

---
## Running:

For a development environment, I have created a script in the devops directory.


---
## TODO:
- Configure xorg.conf with no NVIDIA GPU
- Lock SSH access to user only (remove root access)
- Require user to enter password for sudo
- Document how to run this container
