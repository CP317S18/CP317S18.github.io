---
title: Shout! Requirements
annotater:
  -
    name: API
    tooltip: Application Program Interface
  -
    name: GUI
    tooltip: Graphical User Interface
  - 
    name: SRS
    tooltip: Software Requirement Specification
  - 
    name: BLE 
    tooltip: Bluetooth Low Energy
---
- [1. Introduction](#1-introduction)
  * [1.1 Project Summary](#11-project-summary)
  * [1.2 Purpose](#12-purpose)
  * [1.3 Scope](#13-scope)
  * [1.4 Definitions, Acronyms and Abbreviations](#14-definitions-acronyms-and-abbreviations)
    + [1.4.1 Acronyms and Abbreviations](#141-acronyms-and-abbreviations)
    + [1.4.2 Definitions](#142-definitions)
  * [1.5 References](#15-references)
- [2. Overall description](#2-overall-description)
  * [2.1 Product perspective](#21-product-perspective)
    + [2.1.2 Sample GUI - iOS](#212-sample-gui---ios)
    + [2.1.3 Sample GUI - Android](#213-sample-gui---android)
  * [2.2 Product functions](#22-product-functions)
  * [2.3 User characteristics](#23-user-characteristics)
  * [2.4 Constraints](#24-constraints)
  * [2.5 Assumptions and dependencies](#25-assumptions-and-dependencies)
- [3. Technical Requirements](#3-technical-requirements)
  * [3.1 External Interfaces](#31-external-interfaces)
  * [3.2 Performance requirements](#32-performance-requirements)
  * [3.3 Security](#33-security)
  * [3.4 Portability](#34-portability)
  * [3.5 Data Storage](#35-data-storage)
- [4. Interface Requirements](#4-interface-requirements)
  * [4.1 Description](#41-description)
  * [4.2 Specifics](#42-specifics)
- [5. Versions](#5-versions)
- [6. Authors](#6-authored-by)

# 1. Introduction
## 1.1 Project Summary
_Shout!_  is a bluetooth low energy [(BLE)](#15-references) mesh-based messaging application that is supported on Android and iOS. It allows users to talk to other users within a single messaging room as long as they are all connected to the same bluetooth [mesh](#142-definitions).

## 1.2 Purpose
This document will cover all of the requirements needed for _Shout!_ and will describe all of its features and how they work.

The intended audience for this document will be the client (David Brown) and the project team. They will use this document to be reminded of the requirements of the project. The document will also be used as the basis for the project.

## 1.3 Scope
This document outlines the overall functionality, constraints and specifications of _Shout!_ an application available on multiple platforms intended for individuals within a certain [radius](#142-definitions) to be able to message one another over a bluetooth low energy [(BLE)](#15-references) mesh. _Shout!_ aims to facilitate anonymous conversations with those nearby regardless of phone type and internet access.

## 1.4 Definitions, Acronyms and Abbreviations

### 1.4.1 Acronyms and Abbreviations
- API - Application Program Interface - External software
- GUI - Graphical User Interface
- SRS - Software Requirement Specification
- BLE - Bluetooth Low Energy. Wireless personal area network technology intended to reduce power consumption while maintaining a communication range.

### 1.4.2 Definitions
- Blue Mesh Networking - Mesh is a new network topology option available for Bluetooth®Low Energy (LE)
- Devices - In our application, devices will consist of IOS and Android smartphones
- Nodes - Devices that are in a mesh network
- Mesh - Network with many to many topology that allows many devices to communicate between many devices within the mesh
- Packets - Units of data moving through the mesh, containing information about the device identification, message, time and other data used for logs
- Radius - The distance allowed between two users to connect their devices, dependent on signal strength
- Chat - String of messages sent by users into the application

## 1.5 References
- [BLE](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)
- [Bluetooth Blue Mesh Networking](https://www.bluetooth.com/bluetooth-technology/topology-options/le-mesh/mesh-tech)

This [SRS](#141-acronyms-and-abbreviations) document is based on [IEEE Std 830-1998](https://bohr.wlu.ca/cp317/notes/IEEE_830.pdf).
				

# 2. Overall description
						
## 2.1 Product perspective 
_Shout!_ Is based on [BLE](#15-references) [mesh](#142-definitions) architecture. Major components include the networking protocol utilizing Core Bluetooth module and Androids Bluetooth [API](#141-acronyms-and-abbreviations). IOS and Android frontend apps enabling [chat](#142-definitions) serves as the other component. 

### 2.1.2 Sample [GUI](#212-sample-gui---ios) - iOS

<img width="300" height="533" src="cp317s18.github.io/homepage.png" align="left" hspace="70" />
<img width="300" height="533" src="cp317s18.github.io/chat ui 2.png" hspace="40" />

### 2.1.3 Sample [GUI](#213-sample-gui---android) - Android

## 2.2 Product functions 
Users of _Shout!_ have the ability to [chat](#142-definitions) with others supported through the bluetooth [mesh](#142-definitions) implemented in the application. Users are limited to sending and receiving messages within the range of the mesh to others. If the user disconnects from their mesh, they can reconnect but will not receive the messages that they missed. When users launch the app, they create a temporary username that will be used to communicate with other people. Users can view the number of people in the chat and the distance of users. In addition, _Shout!_ will implement a chat cool down feature to prevent message spamming, where a user can only send a message once every few seconds.

<img align="right" width="250" height="300" src="http://cp317s18.github.io/diagram2.png">

## 2.3 User characteristics

The intended audience of _Shout!_ are users that seek to network with other users within their environment. _Shout!_ is accessible on iOS and Android. Users must have the technical expertise to use the basic functions of the [devices](#142-definitions) on which _Shout!_ is installed. Previous experiences of using a messaging application such as [Facebook Messenger](https://itunes.apple.com/ca/app/messenger/id454638411?mt=8) will assist in the amount of time required to become familiar with the application. The user interface is intended to be simple and intuitive to allow users to operate and navigate the application with minimal resistance and confusion. A short explanation on the functionalities will be provided upon the first launch of the application to guide the users.

## 2.4 Constraints

_Shout!_ is based on the bluetooth [mesh](#142-definitions) network and is restricted by the specifications of the protocol. [Devices](#142-definitions) must be compatible with Bluetooth Low Energy [(BLE)](#15-references) in order to receive and send messages. The application will be available to download on iOS and Android platforms. Therefore connectivity between the two operating system may be subjected to certain limitations. The interface of the application must also compile with [Apple’s Human Interface Guidelines](https://developer.apple.com/ios/human-interface-guidelines/overview/themes/). 

The project includes development constraints such as time, cost and reliability. As the concept of the bluetooth mesh network is relatively new, there is a possibility that it will take longer to implement than expected. The bluetooth mesh network has not been implemented in the real world enough for its reliability to be known. Additionally, in order to publish the application on the Apple application store, a developer account is necessary. Since there is no funding for this project, this is a cost constraint. 
		
## 2.5 Assumptions and dependencies

It is assumed that all of the users [devices](#142-definitions) are compatible with Bluetooth Low Energy [(BLE)](#15-references) with core specification version 4.0 and higher. This includes all iPhones 4s and higher, iPads generation 3 and higher, and any android devices version 4.3 and higher.

The application will only function within the limitations of the device’s own capabilities. It is assumed that all users using _Shout!_ need to be within at least 200 feet of at least one other person in order to engage in conversation.

References used:
- [Bluetooth Special Interest Group](https://www.bluetooth.com/bluetooth-technology/topology-options/le-mesh/mesh-faq)
- [iPhone Faq](https://www.iphonefaq.org/archives/973945)
- [Android Developer](https://developer.android.com/guide/topics/connectivity/bluetooth-le)
- [PC World](https://www.pcworld.com/article/208778/Wi_Fi_Direct_vs_Bluetooth_4_0_A_Battle_for_Supremacy.html)

						
# 3. Technical Requirements 

## 3.1 External Interfaces
- Bluetooth [mesh](#142-definitions) protocol
- Message Packet
  - Author token
    - Key
    - Username
  - Message ID (to allow for segmenting messages over multiple packets, will be unique to an author) 
  - Message
  - Timestamp

## 3.2 Performance requirements
The app will be able to support approximately 6000 users in one [chat](#142-definitions) room and will handle text based data. 
Most of the communication will be done within few seconds of a message being sent from a user but, with larger chat rooms, the time for each individual users to receive the message will increase.

## 3.3 Security
_Shout!_ will have many security features:
- Keep track of logs for user message history of current session
- Enabling communication between distant users if closer links (nodes) create pathway
- Check data integrity for communication
	- Data [packets](#142-definitions) containing chats will be encrypted going through [nodes](#142-definitions)
	- The data packets will have text information and other details for logging messages
	- Packets will be logged on users devices once they are received
	- Packets will be validated from logs on users devices to be used to certify uncorrupted transmission
- Communications securities to prevent users from hacking into other users devices
	- Application will not have access to files on devices
	- Application will only be operating with data packets moving in the network of active nodes
	- Connected devices will be anonymous within the chat but each device will have unique identification

## 3.4 Portability
_Shout!_'s  capabilities include cross platform communication. The platforms which _Shout!_  will operate on include Android and iOS, meaning _Shout!_  will be on the Apple App Store and Google Play Store. There will not be a personal computer (PC here onwards) version of _Shout!_  because creating a mobile application will take majority of the resources and so at the moment a PC version is infeasible.

## 3.5 Data Storage
Due to the technical architecture of _Shout!_ being based on [BLE](#15-references), messages on iOS will be stored using the `Core Data Module` and on Android in the `Nexus Data Module` eliminating our requirement for databases and ensuring data persistence.	

# 4. Interface Requirements

## 4.1 Description
Due to the differing design restrictions and guidelines, the android and iOS versions will not be able to have the exact same interface. 
To get around some of these difficulties, the prototypes will be created using a platform called Figma which can be used to merge the designs to be as similar as possible. 

## 4.2 Specifics 
The specifics of the GUI and the languages used for iOS and Android are in the Design Specs Document

# 5. Versions
- Version 0.1 5/22/2018 `Document outline created` 
- Version 0.2 6/29/2018 `Further information added` 
- Version 0.3 7/22/2018 `Updated outdated information`

# 6. Authored by: 
- Alex Keats
- Adam Benwood 
- Andrew Badali 
- Benjamin Segall 
- Christian Schaefer
- Delina Ghebrekristos
- Emily Hryb 
- Harry Sivashankaran 
- Jared Robinson 	
- Jessica Ngo
- Malin Pho 
- Michelle Loo
- Navreet Atwal 					
- Pranav Patel 
- Rumsha Rafi 
- Samani Puri 
- Tiffany Chan 
- Zakaria Hassen

