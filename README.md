# Lab 0

## Objectives

This lab will serve to install and configure the development environment used to program the ESP32-S3 microcontroller used in MME 9654 at Western University. By the end of the lab each student should:

1. Have a functional copy of git installed for source code version control
2. Have a functional toolchain for developing programs with the ESP-IDF and uploading programs to an ESP32-S3 microcontroller
3. Be prepared for future exercises and development work

### Hardware Required

To complete this lab you will have to purchase an MME 9654 Lab Kit. The following items from the kit will be used:

* ESP32-S3-DevKitC-1 development board
* USB cable for microcontroller power supply and programming

In addition to the components contained in the Lab Kit, the following equipment is available in SEB 1068 for the purpose of conducting this laboratory:

* PC with Arduino IDE

While PCs are available, it is **highly recommended** that the development enviroment is installed on your own portable personal computer. The software is cross platform and may be installed on computers using Windows, Linux, or Mac OS as the operating system.

## Prelab Preparation

1. Purchase the MSE 9654 Lab Kit from the [Engineering Stores online store](https://estore.eng.uwo.ca). Bring your printed or electronic receipt to the lab.

## Exercises

1. Install [git](https://git-scm.com/downloads), if it is not already on your computer. If git exists on your computer, use `git --version` to check that it is a relatively recent version and upgrade if necessary. Note that while many graphical interfaces for git are intuitive and convenient to use, you are encouraged to interact with git on the command line, at least until the standard git workflow is fully understood.

2. Install the ESP-IDF toolchain. There are two main approaches for this:
    
    1. **ESP-IDF** This is the "official" method that relies on a collection of command line tools. While the installation process is more involved, this approach provides direct access to all of the tools and enables specific versions of the ESP-IDF to be used. This is particularly useful if new features or bug fixes are made available and are not yet supported by PlatformIO. The installation process is outlined [here](https://docs.espressif.com/projects/esp-idf/en/v5.1.2/esp32s3/get-started/index.html#manual-installation). For Windows installations, the use of the [PowerShell](https://learn.microsoft.com/en-us/powershell) environment is recommended over the standard Command Prompt environment.

        Once installed, projects can be developed using a text or code editor of your choice. [VSCode](https://code.visualstudio.com/) is highly recommended, even if PlatformIO is not used for development work. It is a feature-rich code editor that provides syntax highlighting and checking, version control integration, and many other useful features.

    2. **PlatformIO** This method relies on a defined "package" of the ESP-IDF. The installation process is straightforward; however, it is less flexible. Installation involves several steps:
    
        1. Install [VSCode](https://code.visualstudio.com/Download) and open it.
        2. Install the [PlatformIO VSCode](https://platformio.org/platformio-ide) extension from with VSCode as outlined [here](https://platformio.org/install/ide?install=vscode).
        3. Install the [Espressif32](https://docs.platformio.org/en/latest/platforms/espressif32.html) development platform. PlatformIO will automatically install it for any projects that include it as a dependancy; however, it can also be manually installed. Open a PlatformIO Core CLI terminal from **PLATFORMIO➞QUICK ACCESS➞Miscellaneous➞PlatformIO Core CLI** and enter the following command:
         `pio pkg install --global --platform "platformio/espressif32@^6.5.0"`

        Note that the Espressif32 v6.5.0 platform is tied to ESP-IDF v5.1.2.

    3. Clone this repository and upload the code found in the [code](code) folder to your ESP32-S3. You can follow the instructions [here](https://docs.espressif.com/projects/esp-idf/en/v5.1.2/esp32s3/get-started/index.html#build-your-first-project) for the steps involved. 
    
    Alternatively, the code can be built, uploaded, and monitored using PlatformIO. Note that the PlatformIO monitor does not show output from the USB port labelled UART. You will have to connect to the USB port labelled USB. If desired, a second cable may be used to connect to both ports (1 for programming and one for monitoring/debugging).
    
    4. Modify the code to change the message from "Hello world!" to "Welcome to MME 9654!". Use `menuconfig` to change the restart interval to 5 seconds. If using PlatformIO, open a terminal from **PLATFORMIO➞QUICK ACCESS➞Miscellaneous➞PlatformIO Core CLI** and launching menuconfig with the following command: 
    `pio run -t menuconfig`. When everything is working properly, commit your changes to your local repository. Use `git log` and `git diff` to show the changes that were made.

## Resources

* [ESP32-S3-DevKitC-1 v1.0](https://docs.espressif.com/projects/esp-idf/en/stable/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1-v1.0.html)
* [Espressif ESP-IDF Programming Guide](https://docs.espressif.com/projects/esp-idf/en/v5.1.2/esp32s3/index.html)

## Evaluation

| Task                | Maximum Marks |
|:--------------------|:-------------:|
| Git installed       | **10**        |
| Toolchain installed | **10**        |
| Code running        | **10**        |
| Code modified       | **10**        |
