# Setting Up a Linux Minecraft Server

This guide outlines the process I use to set up a Linux-based Minecraft server. Follow the steps below to get your server up and running smoothly.

---

## Initial Setup

1. **Update the System**
   ```bash
   sudo apt-get update && sudo apt-get upgrade
Set a Static IP Address
Configure your server with a static IP address for consistent network connectivity.
Installing Java for Minecraft
Download and Install Java 21
bash
Copy code
sudo wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb
sudo apt install ./jdk-21_linux-x64_bin.deb
java -version
Ensure the output confirms Java 21 is installed.
Setting Up the Minecraft Server
Create a Directory for the Server

bash
Copy code
sudo mkdir *example*
cd *example*
Download PaperMC

bash
Copy code
sudo wget https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/132/downloads/paper-1.21.1-132.jar
Move the JAR File

bash
Copy code
mv paper.jar /*example*/
If you see mv: 'paper.jar' and '/*example*/paper.jar' are the same file, it’s already in the correct directory.
Create and Edit the Startup Script

bash
Copy code
sudo touch start.sh
sudo nano start.sh
Add the following line to the file:
bash
Copy code
java -Xmx1024M -Xms1024M -jar paper.jar nogui
Adjust the RAM allocation (-Xmx and -Xms) as needed.
Set Permissions and Start the Server

bash
Copy code
sudo chmod +x /*example*/start.sh
sudo ./start.sh
Agree to the EULA

bash
Copy code
sudo nano eula.txt
Change eula=false to eula=true and save the file.
Restart the Server

bash
Copy code
sudo ./start.sh
Security Enhancements
Change File Ownership

bash
Copy code
sudo chown -hR *USER* /*example*/
This prevents Java from needing sudo or root access.
Edit server.properties

bash
Copy code
sudo nano server.properties
Change the default port (e.g., 25566 or 25567) to reduce the likelihood of scans.
Port Forwarding

Configure port forwarding in your router to allow external access to your server.
DDoS Protection

Use TCPShield for additional protection (optional).
Set Up IPTables

Allow only the necessary port through the firewall: IPTables Example
Connecting to the Server
Find the IP Address

bash
Copy code
ip addr
Use this IP in Minecraft multiplayer, appending the port if it's non-default (e.g., IPAddress:PORT).
Enable and Configure the Whitelist

In-game commands:
plaintext
Copy code
/whitelist on
/whitelist add *Example*
Additional Resources
Optimization Guide

If your server is laggy, check out YouHaveTrouble’s Optimization Guide.
Paper Plugins

Browse and download plugins at Hangar.
Notes
I might expand this guide in the future, but it covers the essentials for now.
This is my first attempt at documenting my server setup process—feedback is welcome!
