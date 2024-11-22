# MinecraftServerGuideLinux
#Here is the setup I use to setup my linux minecraft Servers

First (sudo apt-get update and sudo apt-get upgrade)
set the server to a static IP address
Installing Java (sudo wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb) and (sudo apt install ./jdk-21_linux-x64_bin.deb) then type (java -version) this should be Java 21
the type (sudo mkdir *example*)
the type (cd *example*) to put you into the directory
then to download type (sudo wget https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/132/downloads/paper-1.21.1-132.jar) at the time of typing this is 1.21.1 paper


We will now move the jar file to the directory(mv paper.jar /*example*) if you get this mv: 'paper.jar' and '/*example*/paper.jar' are the same file it was already in the location FYI the file for paper.jar will have the version at the end
then to create the startup script we will type (sudo touch start.sh)
then to edit it we will type (sudo nano start.sh)
then in the nano type (java -Xmx1024M -Xms1024M -jar paper.jar nogui) you can change the amount of ram but I will not for the example
now change the permissions so you can run the start.sh file (sudo chmod +x /*example*/start.sh
then to start it type (sudo ./start.sh)
then to agree to the eula type (sudo nano eula.txt) change false to true and save it
repeat this step and your server will be up (sudo ./start.sh)
now for security run this (sudo chown -hR *USER* /*example*) this is so you dont have to give java sudo/root access
then type (sudo nano server.properties) and change the default port example: 25566 or 25567 so your server is less likely to be scanned
then after that you can portforward and give access to your friends
then to protect your server you can use (https://tcpshield.com/) for DDoS protection but I will not be going into that.
some extra security will also be IPtables and to allow that port alone through 
use this https://gist.github.com/Maxopoly/6c925a1f18f9e2f3b9818d1c1582b17e

To connect to the server go to multiplayer and type the IPAddress:PORT
to find the IP you can type (ip addr) or (ifconfig)
Now in the game make sure you setup a whitelist we dont want any random person joining your server do (/whitelist on) and (whitelist add *Example*)
#Minecraft server optimization guide
YouHaveTrouble is the goat a if you start having or your server is laggy this guide should help you out
https://github.com/YouHaveTrouble/minecraft-optimization

you can get your paper plugins here (https://hangar.papermc.io/)

#Might Add More to this in the future but this is good for now
# Starting documentation on what I do to setup Servers
