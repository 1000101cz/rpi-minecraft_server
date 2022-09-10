# rpi-minecraft_server
create minecraft server on rpi

# Install and start Minecraft server:

1) install Java (17 required for Minecraft 1.19.2)

   - `sudo apt install openjdk-17-jdk`

2) download BuildTools

   - `wget wget https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar`

3) run BuildTools for current minecraft version (1.19.2)

   - `java -Xmx1024M -jar BuildTools.jar --rev 1.19.2`
   - this can take some time

4) accept EULA

    - edit eula.txt file

5) start server (1.19.2 version)

   - `java -Xms512M -Xmx1008M -jar /home/stepan/minecraft/spigot-1.19.2.jar nogui`

6) wait until spawn area is created

7) connect to server (you can get IP address using ifconfig command), no need to specify port

# AutoStart Minecraft server on RPi boot

1) save `minecraftserver.service` file into `/lib/systemd/system/` folder on RPi

2) enable systemd service

   - `sudo systemctl enable minecraftserver.service`
