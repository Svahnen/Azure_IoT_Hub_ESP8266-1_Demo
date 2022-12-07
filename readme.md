<h1 align="center" id="top">Azure IoT Hub Demo with ESP8266</h1>

## Table of contents
- [About the project](#about-the-project)
    - [Resources used](#resources-used)
- [Overview](#overview)
- [Instructions](#instructions)
    - [Installation](#installation)
    - [Setup](#setup)
    - [Wiring](#wiring)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## About the project
This project demonstrates how to use an ESP8266 microcontroller to connect to Azure IoT Hub, Cosmos DB, and Power BI. The ESP8266 collects data from a DS18B20 temperature sensor and sends it to Azure IoT Hub, where it is stored in Cosmos DB and visualized in Power BI.


### Resources used
- ESP8266 microcontroller
- DS18B20 Temperature sensor
- Azure IoT Hub, Cosmos DB, and Power BI services

<p align="right">(<a href="#top">back to top</a>)</p>

## Overview
```
                                       +------------+
                                       |  DS18B20   |
                                       |  Sensor    |
                                       +------+-----+
                                              |
                                              |
                                              |
                                       +------v-----+
                                       | ESP8266     |
                                       |   MCU       |
                                       +------+-----+
                                              |
                                              |
                                              |
                                       +------v-----+
                                       | Azure IoT  |
                                       |   Hub      |
                                       +------+-----+
                                              |
                                              |
                                              |
                  +------v-----+       +------v-----+
                  | SMHI       |       | Cosmos DB  |
                  | Weather    |       | Warm path  |
                  +------+-----+       +------+-----+
                         |                    |
                         |                    |
                         |                    |
                  +------v-----+       +------v-----+
                  | CSV File   |       | Power Bi   |
                  | Cold path  |------->            |
                  +------+-----+       +------+-----+
```
The goal of this project is to demonstrate how to connect an ESP8266 microcontroller to Azure cloud services for data storage and visualization. The ESP8266 will collect temperature data from a sensor and send it to Azure IoT Hub, which will then store the data in Azure Cosmos DB. From there, the data can be accessed and visualized using Power BI, for reference SMHI is also used to get temperature from the closest station to the sensor so comparisons can be made.

<p align="right">(<a href="#top">back to top</a>)</p>

## Instructions
### Installation
1. Install the latest version of the Arduino IDE on your computer.
2. Install the ESP8266 board package in the Arduino IDE by following the instructions [here](https://github.com/esp8266/Arduino#installing-with-boards-manager).
3. Install the [Azure SDK for C](https://github.com/Azure/azure-sdk-for-c-arduino) library in the Arduino IDE library manager.
4. Install [DallasTemperature](https://github.com/milesburton/Arduino-Temperature-Control-Library) library and its dependencies in the Arduino IDE library manager.

### Setup
1. Create an Azure IoT Hub and an Azure Cosmos DB instance.
2. In the Arduino IDE, open the `Azure_IoT_Hub_ESP8266` example sketch and update your connection info in the iot_configs.h file.
```
// Wifi
#define IOT_CONFIG_WIFI_SSID "SSID"
#define IOT_CONFIG_WIFI_PASSWORD "PWD"

// Azure IoT
#define IOT_CONFIG_IOTHUB_FQDN "[your Azure IoT host name].azure-devices.net"
#define IOT_CONFIG_DEVICE_ID "Device ID"
#define IOT_CONFIG_DEVICE_KEY "Device Key"
```
3. Update the `getTelemetryPayload()` function with the specific data you want to send to Azure IoT Hub and Azure Cosmos DB.
4. Create a Message routing under the IoT Hub to forward the data to Cosmos DB.

### Wiring
Aliquip aute dolore in mollit ipsum mollit consequat do magna commodo mollit commodo. Sint voluptate culpa commodo adipisicing magna ut in consequat dolore quis minim. Do non dolor culpa ad veniam. Enim velit commodo exercitation id est culpa qui. Pariatur incididunt est laboris pariatur occaecat cillum. Enim consequat labore laborum ipsum adipisicing laboris duis eu excepteur. Commodo cillum tempor occaecat minim.
<img src="https://hackster.imgix.net/uploads/attachments/931857/esp82cover_2TmU7fOx4S.jpg?auto=compress%2Cformat&w=900&h=675&fit=min">

<p align="right">(<a href="#top">back to top</a>)</p>

## Troubleshooting
Ipsum qui enim non est enim magna ut enim ad pariatur consequat cupidatat. Adipisicing Lorem aliquip ad enim ea minim adipisicing sunt non Lorem nulla. Et tempor veniam ad amet ad eiusmod occaecat do commodo. Est eiusmod sunt labore anim amet sunt in incididunt officia exercitation consectetur qui Lorem sunt. Id nisi voluptate nostrud duis tempor et proident excepteur cillum. Nisi tempor sint cillum consequat aliquip aliquip. Velit excepteur sunt cillum exercitation commodo sit.

<p align="right">(<a href="#top">back to top</a>)</p>

## License
Culpa pariatur labore fugiat dolor ut laboris ad et Lorem cupidatat est mollit amet. Tempor laboris minim ex quis et irure cillum. Nisi occaecat ex ex ad nostrud dolore velit voluptate exercitation deserunt id ea. Nisi eu irure aliqua adipisicing dolore irure id pariatur non deserunt laboris pariatur duis. Anim excepteur deserunt amet qui.

<p align="right">(<a href="#top">back to top</a>)</p>