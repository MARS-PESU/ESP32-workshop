# Setup instractions for mac users

## Arduino IDE 1 Installation (macOS)

This document explains how to install the Arduino Software (IDE) on macOS machines.

### Download the Arduino Software (IDE)

Get the latest version from the [download page](https://www.arduino.cc/en/software). The file is in Zip format. If you use Safari it will be automatically extracted. If you use a different browser you may need to extract it manually.

![Open the downloads folder.](https://docs.arduino.cc/static/922f3da9190232439fbb9c43f3115031/a6d36/Downloads-Folder-MacOS.png)

Open the downloads folder.

Copy the Arduino application bundle into the Applications folder (or elsewhere on your computer).

![Copy to the Applications folder.](https://docs.arduino.cc/static/9fd0d7870a6bfc29a9113a62953fe4e8/a6d36/Application-Folder-MacOS.png)

Copy to the Applications folder.

---

## Installing the ESP32 Board in Arduino IDE (Windows, Mac OS X, Linux)

There’s an add-on for the Arduino IDE that allows you to program the ESP32 using the Arduino IDE and its programming language. In this tutorial we’ll show you how to install the ESP32 board in Arduino IDE whether you’re using Windows, Mac OS X or Linux.


### Installing ESP32 Add-on in Arduino IDE

To install the ESP32 board in your Arduino IDE, follow these next instructions:

1. In your Arduino IDE, go to **File**> **Preferences**
    
    ![Installing ESP32 Add-on in Arduino IDE Windows, Mac OS X, Linux open preferences](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2016/12/arduino-ide-open-preferences.png?resize=196%2C340&quality=100&strip=all&ssl=1)
    
2. Enter the following into the “Additional Board Manager URLs” field:
    
    https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
    
    Then, click the “OK” button:
    
    ![Installing ESP32 Add-on in Arduino IDE Windows, Mac OS X, Linux enter URLs](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2022/04/ESP32-URL-Arduino-IDE.png?w=828&quality=100&strip=all&ssl=1)
    
    **Note:** if you already have the ESP8266 boards URL, you can separate the URLs with a comma as follows:
    
    https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json, http://arduino.esp8266.com/stable/package_esp8266com_index.json
    
3. Open the Boards Manager. Go to **Tools** > **Board** > **Boards Manager…**
    
    ![Installing ESP32 Add-on in Arduino IDE Windows, Mac OS X, Linux open boards manager](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/boardsManager.png?resize=628%2C568&quality=100&strip=all&ssl=1)
    
4. Search for **ESP32** and press install button for the “**ESP32 by Espressif Systems**“:
    
    ![ESP32 Add-on in Arduino IDE Windows, Mac OS X, Linux Installed](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/installing.png?resize=786%2C443&quality=100&strip=all&ssl=1)
    
5. That’s it. It should be installed after a few seconds.
    
    ![ESP32 Board add-on in Arduino IDE installed](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2019/07/ESP32-Board-add-on-in-Arduino-IDE-installed.png?resize=786%2C443&quality=100&strip=all&ssl=1)

---

## Installing CP210x USB to UART Bridge VCP Drivers (Mac OS X)

Start by downloading the [CP210x USB Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads) from the official website. If you are on Mac OS computer, you need to download the CP210x Mac OSX Driver folder highlighted in the image below.

![Installing CP210x USB to UART Bridge Drivers Mac OS Computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Installing-CP210x-USB-to-UART-Bridge-Drivers-Mac-OS-Computer.png?resize=543%2C276&quality=100&strip=all&ssl=1)

After downloading the Mac OSX VCP Driver, unzip the installation files.

![Unzip the CP210x USB to UART Bridge Drivers on Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Unzip-the-CP210x-USB-to-UART-Bridge-Drivers-on-Mac-OS-X-computer.png?resize=466%2C100&quality=100&strip=all&ssl=1)

Open the unzipped folder and double-click the _SiLabsUSBDriverDisk.dmg_ file to start the installation process.

![Open the Installation file for CP210x USB to UART Bridge Drivers Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Open-the-Installation-file-for-CP210x-USB-to-UART-Bridge-Drivers-Mac-OS-X-computer.png?resize=750%2C149&quality=100&strip=all&ssl=1)

Open the Install CP210x VCP driver file:

![Open the Installation file CP210X VCP Driver Mac OS X computer 2](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Open-the-Installation-file-for-CP210x-USB-to-UART-Bridge-Drivers-Mac-OS-X-computer-2.png?resize=750%2C342&quality=100&strip=all&ssl=1)

Click the “**Open**” button.

![Open File on Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Open-File-on-Mac-OS-X-computer.jpg?resize=750%2C621&quality=100&strip=all&ssl=1)

Follow the installation wizard and complete all the steps.

![Continue with the CP210x USB to UART Bridge Drivers Installation on Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Continue-with-the-CP210x-USB-to-UART-Bridge-Drivers-Installation-on-Mac-OS-X-computer.png?resize=750%2C546&quality=100&strip=all&ssl=1)

In some cases, your computer might block the installation, so you need to open your System Settings.

![Mac OS X System blocked installing unknown software](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Mac-OS-X-System-blocked-installing-unknown-software.png?resize=750%2C518&quality=100&strip=all&ssl=1)

Then, click the “**Allow**” button to allow the CP210x drivers to be installed.

![Allow CP210x USB to UART Bridge Drivers Installation on Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Allow-CP210x-USB-to-UART-Bridge-Drivers-Installation-on-Mac-OS-X-computer.png?resize=750%2C334&quality=100&strip=all&ssl=1)

Finally, you should see the Success message.

![Installation success completed CP210x USB to UART Bridge Drivers on Mac OS X computer](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Installation-success-completed-CP210x-USB-to-UART-Bridge-Drivers-on-Mac-OS-X-computer.png?resize=750%2C548&quality=100&strip=all&ssl=1)

---

## This completes the installation part

For the rest of the stuff, see you in the workshop!
