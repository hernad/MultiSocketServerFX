# MultiSocketServerFX
JavaFX UI server socket application demonstrating multiple socket client connections simultaneously.

This application is written in Java using the JavaFX API.  It represents the server side of a socket connection and can:

   - connect to a socket at a configurable port
   - handle multiple client socket connections at the same time and indicate the number of connections
   - receive text messages from a connected socket
   - send text messages to all connected sockets
   - retrieve sent and received messages

It is typically used in conjucntion with a client-side JavaFX UI application called ```SocketClientFX```.
It can be found here: https://github.com/jtconnors/SocketClientFX

This latest version of the source code is tagged ```1.0-JDK11-maven```.  It is modularized and as its name suggests, works with JDK11
and is built with the ```apache maven``` build lifecycle system.

Of note, the following maven goals can be executed:

   - ```mvn clean```
   - ```mvn dependency:copy-dependencies``` - to pull down dependent ```javafx``` and ```com.jtconnors.socket``` modules
   - ```mvn compile``` - to build the application
   - ```mvn package``` - to create the ```MultiSocketServerFX``` module as a jar file
   - ```mvn exec:java``` to run the application
   
Furthermore, additional ```.sh``` and ```.ps1``` files are provided in the ```sh/```
and ```ps1\``` directories respectively:
   - ```sh/run.sh``` or ```ps1\run.ps1``` - script file to run the application from the module path
   - ```sh/run-simplified.sh``` or ```ps1\run-simplified.ps1``` - alternative script file to run the application, determines main class from ```SocketClientFX``` module
   - ```sh/link.sh``` or ```ps1\link.ps1``` - creates a runtime image using the ```jlink``` utility
   - ```sh/create-appimage.sh``` or ```ps1\create-appimage.ps1``` - creates a native package image of application using JEP-343 jpackage tool
   - ```sh/create-dmg-installer.sh``` - creates a native MacOS dmg installer of this application using JEP-343 jpackage tool
   - ```ps1\create-exe-installer.ps1``` - creates a native Windows EXE installer of this application using JEP-343 jpackage tool
   - ```ps1\create-msi-installer.ps1``` - creates a native Windows MSI installer of this application using JEP-343 jpackage tool

Notes:
   - These scripts have a few available command-line options.  To print out
the options, add ```-?``` or ```--help``` as an argument to any script.
   - These scripts share common properties that can be found in ```env.sh``` or ```env.ps1```.  These may need to be slightly modified to match  your specific configuration.
   - In order to generate ```EXE``` or ```MSI``` installers for Windows, ISSC and/or WiX toolkits must be installed respectively and placed on the %PATH% variable.

See also:

- SocketClientFX: https://github.com/jtconnors/SocketClientFX
- SocketServerFX: https://github.com/jtconnors/SocketServerFX
- maven-com.jtconnors.socket: https://github.com/jtconnors/maven-com.jtconnors.socket
