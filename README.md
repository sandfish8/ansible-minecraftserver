# Setup Mine Craft

An ansible playbook to setup a minecraft server  

To run the playbook, you'll want to do something like this:  
```
ansible-playbook -i hosts --user=ubuntu site.yml
```

## Start the Server by hand the first time to accept eula

```
$ cd /opt/minecraft-server/
$ ls
minecraft_server.jar
$ /usr/bin/java -Xms1024M -Xmx2048M -jar minecraft_server.jar nogui

[18:17:55] [Server thread/INFO]: Starting minecraft server version 1.8.9
[18:17:55] [Server thread/INFO]: Loading properties
[18:17:55] [Server thread/WARN]: server.properties does not exist
[18:17:55] [Server thread/INFO]: Generating new properties file
[18:17:55] [Server thread/WARN]: Failed to load eula.txt
[18:17:55] [Server thread/INFO]: You need to agree to the EULA in order to run the server. Go to eula.txt for more info.
[18:17:55] [Server thread/INFO]: Stopping server
[18:17:55] [Server Shutdown Thread/INFO]: Stopping server

$ cat eula.txt
#By changing the setting below to TRUE you are indicating your agreement to our EULA (https://account.mojang.com/documents/minecraft_eula).
#Sat Jan 23 18:17:55 UTC 2016
eula=false

$ sed -i'' -e 's/false/true/' eula.txt

$ cat eula.txt
#By changing the setting below to TRUE you are indicating your agreement to our EULA (https://account.mojang.com/documents/minecraft_eula).
#Sat Jan 23 18:17:55 UTC 2016
eula=true

# /usr/bin/java -Xms1024M -Xmx2048M -jar minecraft_server.jar nogui
[18:26:16] [Server thread/INFO]: Starting minecraft server version 1.8.9
[18:26:16] [Server thread/INFO]: Loading properties
[18:26:16] [Server thread/INFO]: Default game type: SURVIVAL
[18:26:16] [Server thread/INFO]: Generating keypair
[18:26:17] [Server thread/INFO]: Starting Minecraft server on *:25565
[18:26:17] [Server thread/INFO]: Using epoll channel type
[18:26:17] [Server thread/WARN]: Failed to load user banlist:
java.io.FileNotFoundException: banned-players.json (No such file or directory)
        at java.io.FileInputStream.open(Native Method) ~[?:1.7.0_80]
        at java.io.FileInputStream.<init>(FileInputStream.java:146) ~[?:1.7.0_80]
        at com.google.common.io.Files.newReader(Files.java:86) ~[minecraft_server.jar:?]
        at mb.g(SourceFile:124) ~[minecraft_server.jar:?]
        at kn.z(SourceFile:99) [minecraft_server.jar:?]
        at kn.<init>(SourceFile:25) [minecraft_server.jar:?]
        at ko.i(SourceFile:172) [minecraft_server.jar:?]
        at net.minecraft.server.MinecraftServer.run(SourceFile:421) [minecraft_server.jar:?]
        at java.lang.Thread.run(Thread.java:745) [?:1.7.0_80]
[18:26:17] [Server thread/WARN]: Failed to load ip banlist:
java.io.FileNotFoundException: banned-ips.json (No such file or directory)
        at java.io.FileInputStream.open(Native Method) ~[?:1.7.0_80]
        at java.io.FileInputStream.<init>(FileInputStream.java:146) ~[?:1.7.0_80]
        at com.google.common.io.Files.newReader(Files.java:86) ~[minecraft_server.jar:?]
        at mb.g(SourceFile:124) ~[minecraft_server.jar:?]
        at kn.y(SourceFile:91) [minecraft_server.jar:?]
        at kn.<init>(SourceFile:27) [minecraft_server.jar:?]
        at ko.i(SourceFile:172) [minecraft_server.jar:?]
        at net.minecraft.server.MinecraftServer.run(SourceFile:421) [minecraft_server.jar:?]
        at java.lang.Thread.run(Thread.java:745) [?:1.7.0_80]
[18:26:17] [Server thread/WARN]: Failed to load operators list:
java.io.FileNotFoundException: ops.json (No such file or directory)
        at java.io.FileInputStream.open(Native Method) ~[?:1.7.0_80]
        at java.io.FileInputStream.<init>(FileInputStream.java:146) ~[?:1.7.0_80]
        at com.google.common.io.Files.newReader(Files.java:86) ~[minecraft_server.jar:?]
        at mb.g(SourceFile:124) ~[minecraft_server.jar:?]
        at kn.A(SourceFile:107) [minecraft_server.jar:?]
        at kn.<init>(SourceFile:29) [minecraft_server.jar:?]
        at ko.i(SourceFile:172) [minecraft_server.jar:?]
        at net.minecraft.server.MinecraftServer.run(SourceFile:421) [minecraft_server.jar:?]
        at java.lang.Thread.run(Thread.java:745) [?:1.7.0_80]
[18:26:17] [Server thread/WARN]: Failed to load white-list:
java.io.FileNotFoundException: whitelist.json (No such file or directory)
        at java.io.FileInputStream.open(Native Method) ~[?:1.7.0_80]
        at java.io.FileInputStream.<init>(FileInputStream.java:146) ~[?:1.7.0_80]
        at com.google.common.io.Files.newReader(Files.java:86) ~[minecraft_server.jar:?]
        at mb.g(SourceFile:124) ~[minecraft_server.jar:?]
        at kn.C(SourceFile:123) [minecraft_server.jar:?]
        at kn.<init>(SourceFile:30) [minecraft_server.jar:?]
        at ko.i(SourceFile:172) [minecraft_server.jar:?]
        at net.minecraft.server.MinecraftServer.run(SourceFile:421) [minecraft_server.jar:?]
        at java.lang.Thread.run(Thread.java:745) [?:1.7.0_80]
[18:26:17] [Server thread/INFO]: Preparing level "world"
[18:26:18] [Server thread/INFO]: Preparing start region for level 0
[18:26:19] [Server thread/INFO]: Preparing spawn area: 4%
[18:26:20] [Server thread/INFO]: Preparing spawn area: 6%
[18:26:21] [Server thread/INFO]: Preparing spawn area: 9%
[18:26:22] [Server thread/INFO]: Preparing spawn area: 13%
[18:26:23] [Server thread/INFO]: Preparing spawn area: 19%
[18:26:24] [Server thread/INFO]: Preparing spawn area: 26%
[18:26:25] [Server thread/INFO]: Preparing spawn area: 32%
[18:26:26] [Server thread/INFO]: Preparing spawn area: 38%
[18:26:27] [Server thread/INFO]: Preparing spawn area: 46%
[18:26:28] [Server thread/INFO]: Preparing spawn area: 53%
[18:26:30] [Server thread/INFO]: Preparing spawn area: 58%
[18:26:31] [Server thread/INFO]: Preparing spawn area: 66%
[18:26:32] [Server thread/INFO]: Preparing spawn area: 73%
[18:26:33] [Server thread/INFO]: Preparing spawn area: 80%
[18:26:34] [Server thread/INFO]: Preparing spawn area: 88%
[18:26:35] [Server thread/INFO]: Preparing spawn area: 96%
[18:26:35] [Server thread/INFO]: Done (17.887s)! For help, type "help" or "?"

```
