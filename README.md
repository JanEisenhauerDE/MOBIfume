# MOBIfume

The all new mobile cyanoacrylate fuming system for the development of latent fingerprints at the scene, in fuming tents or fuming rooms.
This application is responsible for the MOBIfume controller of the system on a tablet.

## Prerequisites

- [Java SE Development Kit 8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) (oracle JDK)
- [Lombok](https://projectlombok.org/download) (Java Library with useful functions, must be installed to run preprocessor)
- [Inno Setup 6.0.2](http://www.jrsoftware.org/isdl.php) (Creates an .exe installer for windows)
    
## Building   

Execute the maven build process.
The jar file is located in `target/`.
The installer .exe file is located in `setup/Output`.

## Running (Windows)

1. Execute the installer on the windows tablet.
2. Go through the installation process. The target directory must be `C:\Program Files\MOBIfume\` otherwise the autostart won't work.

## Dependencies

- [JavaFX](https://openjfx.io/) - Library for client application (UI)
- [Lombok](https://projectlombok.org/download) - Library with useful functions (eg. getter/setter annotation)
- [GSON](https://mvnrepository.com/artifact/com.google.code.gson/gson) - Library to work with JSON
- [log4j](https://mvnrepository.com/artifact/log4j/log4j) - Library for Logging in Java
- [Eclipse Paho](https://www.eclipse.org/paho/) - MQTT Client

## Build With

- [Maven](https://maven.apache.org/) - Build Management Tool / Dependency Management
- [Inno Setup](http://www.jrsoftware.org/isinfo.php) - Compiler to build exe file

## Notes

- The program must be executed as administrator to automatically show/hide the on-screen keyboard TabTip.
- The program must be installed in `C:\Program Files\MOBIfume\` otherwise the autostart won't work.
- For autostart, windows task scheduler is used because this allows the program to start as admin.
- The installer overwrites the default user account picture in `C:\ProgramData\Microsoft\User Account Pictures\user.png` to set the mobifume icon as account picture.
- Program files are stored in `%localappdata%/MOBIfume`.
    It contains:
    - `languagesettings` stores the selected language.
    - `settings` stores the global settings.
    - `filter/` stores all filters for filter management. Files are manually editable (json format).
    - `language/` stores the localization files as properties. A new language can be added by simple add a file named `MOBIfume_xx_XX.properties` (replace xx_XX with country code) and copy/modify the key-value pairs from the other language files.
    - `paho/` contains files related to eclipse paho for the mqtt client connection
All files are deleted when the program is reinstalled or uninstalled.
- Log files are stored in `%userprofile%/documents/MOBIfume`. These files will never be deleted.
