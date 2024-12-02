
# Minecraft Server Setup on Linux

## Introduction
This guide provides a step-by-step process to set up a Minecraft server on a Linux system. It includes installation, configuration, and optimization tips.

## Prerequisites
1. Update your system packages:
   ```bash
   sudo apt-get update
   sudo apt-get upgrade
   ```
2. Set your server to a static IP address.

## Installing Java
1. Download and install Java 21:
   ```bash
   sudo wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb
   sudo apt install ./jdk-21_linux-x64_bin.deb
   java -version
   ```

## Setting Up the Minecraft Server
1. Create a directory for the server:
   ```bash
   sudo mkdir <example>
   cd <example>
   ```
2. Download the PaperMC server jar file (version 1.21.1 at the time of writing):
   ```bash
   sudo wget https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/132/downloads/paper-1.21.1-132.jar
   ```
3. Move the jar file to the directory:
   ```bash
   mv paper.jar <example>
   ```

## Creating a Startup Script
1. Create the `start.sh` script:
   ```bash
   sudo touch start.sh
   sudo nano start.sh
   ```
2. Add the following to `start.sh`:
   ```bash
   java -Xmx1024M -Xms1024M -jar paper.jar nogui
   ```
   Adjust the RAM allocation as needed.
3. Make the script executable:
   ```bash
   sudo chmod +x <example>/start.sh
   ```
4. Run the server:
   ```bash
   sudo ./start.sh
   ```

## Agree to the EULA
1. Edit the `eula.txt` file:
   ```bash
   sudo nano eula.txt
   ```
2. Change `eula=false` to `eula=true`.

## Security and Configuration
1. Change ownership to avoid using root access:
   ```bash
   sudo chown -hR <USER> <example>
   ```
2. Edit `server.properties` to change the default port (e.g., 25566 or 25567) to make it less likely to be scanned:
   ```bash
   sudo nano server.properties
   ```
3. Set up port forwarding and whitelist your server:
   ```bash
   /whitelist on
   /whitelist add <Example>
   ```

## Additional Security
- Use [TCPShield](https://tcpshield.com/) for DDoS protection.
- Configure IP tables to allow specific ports using [this guide](https://gist.github.com/Maxopoly/6c925a1f18f9e2f3b9818d1c1582b17e).

## Optimization
For performance improvements, refer to [YouHaveTrouble's Minecraft Optimization Guide](https://github.com/YouHaveTrouble/minecraft-optimization).

## Plugins
Find Paper plugins at [Hangar](https://hangar.papermc.io/).

---
### Notes
- This guide will be updated in the future as needed.
