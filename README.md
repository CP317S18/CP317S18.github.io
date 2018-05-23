# 1. Introduction
## 1.1 Project Summary
_Shout!_  is a bluetooth low energy (BLE) mesh-based messaging application that is supported on Android and iOS. It allows users to talk to other users within a single messaging room as long as they are all connected to the same bluetooth mesh.

## 1.2 Purpose
This document will cover all of the requirements needed for _Shout!_ and will describe all of its amazing features and how they work.

The intended audience for this document will be the client (David Brown) and the project team. They will use this document to be reminded of the requirements of the project. The document will also be used as the basis for the project.

## 1.3 Scope
This document outlines the overall functionality, constraints and specifications of _Shout!_ an application available on multiple platforms intended for individuals within a certain radius to be able to message one another over a bluetooth low energy (BLE) mesh. _Shout!_ aims to bring individuals together by facilitating anonymous conversations regardless of phone type and internet access.

## 1.4 Definitions, Acronyms and Abbreviations

### 1.4.1 Acronyms and Abbreviations
- API: Application Program Interface - External software
- GUI: Graphical User Interface
- SRS: Software Requirement Specification.
- BLE : Bluetooth Low Energy. Wireless personal area network technology intended to reduce power consumption while maintaining a communication range

### 1.4.2 Definitions
- Blue Mesh Networking: Mesh is a new network topology option available for Bluetooth®Low Energy (LE)
- Devices: In our application, devices will consist of IOS and Android smartphones
- Nodes: Devices that are in a mesh network
- State Binding: Relationship between states where a change in one state can result in a change in another
- Unprovisioned Devices: Devices that are not in the mesh network
- Mesh: Network with many to many topology that allows many devices to communicate between many devices within the mesh
- Point to Point: One device can connect to many other devices in a network, but other devices cannot communicate directly with each other
- Radius: The distance allowed between two users to connect their devices, dependent on signal strength
- Chat: The string of messages sent by users into the application
- User: An individual connected to the chat

## 1.5 References
- [BLE](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)
- [Bluetooth Blue Mesh Networking](https://www.bluetooth.com/bluetooth-technology/topology-options/le-mesh/mesh-tech)

This SRS document is based on IEEE Std 830-1998.
				

# 2. Overall description
						
## 2.1 Product perspective 
_Shout!_ Is based on BLE mesh architecture. Major components include the networking protocol utilizing Core Bluetooth module and Androids Bluetooth API. IOS and Android frontend apps enabling chat serves as the other component. 

## 2.2 Product functions 
Users of _Shout!_ have the ability to chat with others supported through the bluetooth mesh implemented in the application. Users are limited to sending and receiving messages within the range of the mesh to others. If the user disconnects from their mesh, they can reconnect and receive the messages they missed as long they connect within a certain period of time. When users launch the app, they create a temporary username that will be used to communicate with other people. Users can view the number of people in the chat and the distance of users. 



## 2.3 User characteristics


The intended audience of _Shout!_ are users that seek to network with other users within their environment. _Shout!_ is accessible on iOS and Android. Users must have the technical expertise to use the basic functions of the devices on which _Shout!_ is installed. Experience using a messaging application will assist in the amount of time required to become familiar with the application. The user interface is intended to be intuitive such that there will be a short learning curve.

## 2.4 Constraints

_Shout!_ is based on the bluetooth mesh network and is restricted by the specifications of the protocol. Devices must be compatible with Bluetooth Low Energy (BLE) in order to receive and send messages. The application will be available to download on iOS and Android platforms. Therefore connectivity between the two operating system may be subjected to certain limitations. The interface of the application must also compile with Apple’s Human Interface Guidelines. 

The project includes development constraints such as time, cost and reliability. As the concept of the bluetooth mesh network is relatively new, there is a possibility that it will take longer to implement than expected. The bluetooth mesh network has not been implemented in the real world enough for its reliability to be known. Additionally, in order to publish the application on the Apple application store, a developer account is necessary. Since there is no funding for this project, this is a cost constraint. 
		
## 2.5 Assumptions and dependencies

It is assumed that all of the users devices are compatible with Bluetooth Low Energy (BLE) with core specification version 4.0 and higher. This includes all iPhones 4s and higher, iPads generation 3 and higher, and any android devices version 4.3 and higher.

The application will only function within the limitations of the device’s own capabilities. It is assumed that all users using _Shout!_ need to be within at least 200 feet of at least one other person in order to engage in conversation.

References used:
- [Bluetooth Special Interest Group](https://www.bluetooth.com/bluetooth-technology/topology-options/le-mesh/mesh-faq)
- [iPhone Faq](https://www.iphonefaq.org/archives/973945)
- [Android Developer](https://developer.android.com/guide/topics/connectivity/bluetooth-le)
- [PC World](https://www.pcworld.com/article/208778/Wi_Fi_Direct_vs_Bluetooth_4_0_A_Battle_for_Supremacy.html)

						
# 3. Technical Requirements 
(See 5.3.1 through 5.3.8 for explanations of possible specific requirements. See also Annex A for several different ways of organizing this section of the SRS.)

## 3.1 External Interfaces
- Bluetooth mesh protocol
- Send Message Packet
- Author key
- Message
- Timestamp






## 3.2 Performance requirements
The app will be able to support approximately 6000 users in one chat room
The app will handle text based data 
Most of the communication will be done within few seconds of a message being sent from a user, with larger chat rooms the time for each individual users to receive the message will increase

## 3.3 Security
_Shout!_ will have many security features:
Keep track of logs for user message history of current session
Enabling communication between distant users if closer links (nodes) create pathway
Check data integrity for communication
Communications securities to prevent users from hacking into other users devices

## 3.4 Portability
_Shout!_ will be a mobile application of futuristic capabilities, one of which includes cross platform communication. The platforms which _Shout!_  will operate on include Android and IOS, meaning _Shout!_  will be on the Apple App Store and Google Play Store. There will not be a personal computer (PC here onwards) version of _Shout!_  because creating a mobile application will take majority of the resources and so a PC version is infeasible.

## 3.5 Data Storage
Due to the technical architecture of _Shout!_ being based on BLE, messages on iOS will be stored on the core data and on Android in the Nexus Data eliminating our requirement for databases and ensuring data persistence.	

# 4. Appendixes 
Index 

# 5. Versions
Version 0.1 5/22/2018
Document outline created 

# 6. Authored By: 
- Adam Benwood (Product Perspective)
- Alex Keats (Overview)
- Andrew Badali (Introduction)
- Benjamin Segall (Specific Requirements)
- Christian Schaefer (Introduction and purpose)
- Delina Ghebrekristos (acronyms and Abbreviations)  
- Emily Hryb (Added to Definitions)
- Harry Sivashankaran (Definitions References)
- Jared Robinson (Overview)	
- Jessica Ngo (User characteristics, constraints)
- Malin Pho (Product function, constraints)
- Michelle Loo (GUI)
- Navreet Atwal (GUI)					
- Pranav Patel (Performance requirement, Security, Portability)
- Rumsha Rafi (GUI)
- Samani Puri (Product function)
- Tiffany Chan (Assumptions and Dependencies)
- Zakaria Hassen ( Scope & Definitions)











You can use the [editor on GitHub](https://github.com/CP317S18/CP317S18.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/CP317S18/CP317S18.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.


