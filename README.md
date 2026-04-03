# ESP32 Workshop Manual

Welcome to the **ESP32 Workshop Repository**.

This repository is created as a simple hands-on guide for learning how to work with the **ESP32 microcontroller board** through practical sensor and actuator experiments.

The workshop is designed especially for **design students and beginners**, focusing on interactive prototypes rather than heavy technical details.

---

## About the Workshop

The aim of this workshop is to introduce participants to **physical computing and interactive systems** using the ESP32.

Through a series of simple experiments, students will learn how digital systems can sense, respond, and interact with the physical world.

The workshop covers:

- sensing movement and proximity
- measuring environmental data
- controlling motion
- understanding responsive systems
- building interactive prototypes

---

## What You Will Learn

By the end of this workshop, you will be able to:

- connect sensors and actuators to ESP32
- upload code using Arduino IDE
- read sensor data
- control physical outputs
- prototype interactive design concepts
- understand basic hardware-software interaction

---

## Software Required

Before starting, install the following:

- **Arduino IDE**
- **ESP32 board package**
- required sensor libraries

---
## Installation

Please follow the folowing links for installation on your device.
- Windows systems: https://github.com/MARS-PESU/ESP32-workshop/blob/main/installation/windows.md
- MAC systems: coming soon
---

## Design Perspective

This workshop is built to help students explore **interactive product design, responsive environments, and physical computing**.

Possible applications include:

- interactive exhibitions
- smart furniture
- responsive lighting
- touchless interfaces
- kinetic installations
- environmental sensing systems

---

## Workshop Goal

The focus is not only on coding, but on understanding **how physical spaces and products can respond to people and environments**.

This bridges the gap between:

**design + technology + interaction**

---
# ESP32 Workshop Manual

Welcome to the **ESP32 Workshop Repository**.

This repository is created as a simple hands-on guide for learning how to work with the **ESP32 microcontroller board** through practical sensor and actuator experiments.

The workshop is designed especially for **design students and beginners**, focusing on interactive prototypes rather than heavy technical details.

---

## About the Workshop

The aim of this workshop is to introduce participants to **physical computing and interactive systems** using the ESP32.

Through a series of simple experiments, students will learn how digital systems can sense, respond, and interact with the physical world.

The workshop covers:

- sensing movement and proximity
- measuring environmental data
- controlling motion
- understanding responsive systems
- building interactive prototypes

---

## What You Will Learn

By the end of this workshop, you will be able to:

- connect sensors and actuators to ESP32
- upload code using Arduino IDE
- read sensor data
- control physical outputs
- prototype interactive design concepts
- understand basic hardware-software interaction

---

## Software Required

Before starting, install the following:

- **Arduino IDE**
- **ESP32 board package**
- required sensor libraries

---

## Arduino IDE 1 Installation (Windows)

Install the Arduino Software (IDE) on Windows

This document explains how to install the Arduino Software (IDE) on Windows machines.

### Download the Arduino Software (IDE)

Get the latest version from the [download page](https://www.arduino.cc/en/Main/Software). You should choose  the Installer (.exe) package. We suggest you use the first one that installs directly everything you need to use in the Arduino Software (IDE), including the drivers. 

When the download finishes, proceed with the installation and please allow the driver installation process when you get a warning from the operating system.

![Choose the components to install.](https://docs.arduino.cc/static/7edc579ab130f2d5a00d280375399930/9cb4e/DRV_Capture1.png)

Choose the components to install.

![Choose the installation directory.](https://docs.arduino.cc/static/5915d5555ed248ddee3eb45fc7b8109c/9cb4e/DRV_Capture2.png)

Choose the installation directory.

![Installation in progress.](https://docs.arduino.cc/static/41c08487e141ac305e09157041620d0b/ade6e/DRV_Capture3.png)

continue till you get the message for successful installation.

The process will extract and install all the required files to execute properly the Arduino Software (IDE)

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

## Installing CP210x USB to UART Bridge VCP Drivers (Windows PC)

Start by downloading the [CP210x USB Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads) from the official website. If you are on a Windows PC, you need to download the CP210x Windows Drivers folder highlighted in the image below.

![Installing CP210x USB to UART Bridge Drivers Windows PC](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Installing-CP210x-USB-to-UART-Bridge-Drivers-Windows-PC.png?resize=543%2C276&quality=100&strip=all&ssl=1)

After downloading the CP210x Windows Drivers, right-click the folder and unzip the installation files.

![Unzip the CP210x USB to UART Bridge Drivers on Windows PC](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Unzip-the-CP210x-USB-to-UART-Bridge-Drivers-on-Windows-PC.png?resize=171%2C181&quality=100&strip=all&ssl=1)

Open the unzipped folder and double-click the _CP210xVCPInstaller_x64.exe_ file to start the installation process.

![Open the Installation file for CP210x USB to UART Bridge Drivers Windows PC](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Open-the-Installation-file-for-CP210x-USB-to-UART-Bridge-Drivers-Windows-PC.png?resize=472%2C285&quality=100&strip=all&ssl=1)

Follow the installation wizard, click the “Next” button, and agree with the terms of use to complete the installation process.

![Complete the Installation wizard for CP210x USB to UART Bridge Drivers Windows PC](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Complete-the-Installation-wizard-for-CP210x-USB-to-UART-Bridge-Drivers-Windows-PC.png?resize=499%2C387&quality=100&strip=all&ssl=1)

The CP210x USB drivers have been installed successfully.

![Installation completed success for CP210x USB to UART Bridge Drivers Windows PC](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2024/02/Installation-completed-success-for-CP210x-USB-to-UART-Bridge-Drivers-Windows-PC.png?resize=499%2C387&quality=100&strip=all&ssl=1)

---

## This completes the installation part

For the rest of the stuff, see you in the workshop!

---

## Design Perspective

This workshop is built to help students explore **interactive product design, responsive environments, and physical computing**.

Possible applications include:

- interactive exhibitions
- smart furniture
- responsive lighting
- touchless interfaces
- kinetic installations
- environmental sensing systems

---

## Workshop Goal

The focus is not only on coding, but on understanding **how physical spaces and products can respond to people and environments**.

This bridges the gap between:

**design + technology + interaction**

---
<img width="400" height="193" alt="logoPesu" src="https://github.com/user-attachments/assets/6cd545a5-6dc9-4516-a34a-c22b87014fb3" />

<img width="781" height="256" alt="mars lab logo long" src="https://github.com/user-attachments/assets/9a40f841-da3f-40b2-a4de-cebf10d760b8" />


