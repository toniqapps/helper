**_NOTE:_**  Make sure Java JDK is installed and JAVA_HOME is set to JDK path 

# Automatic Tomcat 8.5 Installation and Configuration as Windows Service
## Tomcat Installation

1. Download from the Apache Tomcat 8.5 [download](http://tomcat.apache.org/download-80.cgi)  page the Core 64-bit Windows zip (or the 32-Bit zip).
> *32-bit Windows zip (pgp, sha512) or 64-bit Windows zip (pgp, sha512)*
2. Unzip it (for example to C:\tomcat\)
3. That’s it. Now we have a ready-to-use Tomcat with default configuration values. But it isn’t install as a service.

## Installation and Configuration As Windows Service

1. Open cmd prompt (Run As Administrator) 
2.  Go to the bin folder in the installation folder of Tomcat (in the example  it’s C:\tomcat\apache-tomcat-8.5.*\bin)
```cmd
C:\Users\****> cd C:\apache-tomcat-8.5.43-windows-x64\apache-tomcat-8.5.*\bin
```
3.  Install Tomcat as service named tomcat8 by calling service.bat install <servicename>  
```cmd
C:\tomcat\apache-tomcat-8.5.11\bin>service.bat install tomcat8
```
3. tomcat8.exe //US//<servicename> followed by configuration parameter configures the Tomcat service. For example:
```cmd
C:\tomcat\apache-tomcat-8.5.11\bin>tomcat8.exe //US//tomcat8 --Startup=auto --JavaHome="C:\Program Files\Java\jre1.8.0_112" --JvmMs=2048 --JvmMx=4096 ++JvmOptions=-Dkey=value
```
4. Start the Tomcat service with net start <servicename>
```cmd
net start tomcat8
```
5. You can check on http://localhost:8080 whether Tomcat is installed correctly.
 
6. Stop the Tomcat service with net stop <servicename>
```cmd
net stop tomcat8
```
