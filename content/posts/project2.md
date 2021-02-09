+++ 
draft = false
date = 2019-12-07T23:23:45-08:00
title = "Project 2: Fluffy Finds"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
featuredImage ="/images/FluffyFinds/FluffyFindsLogo.png"
+++
# Summary:
- FluffyFinds is a tracking device that can track pets with pinpoint accuracy using GPS. Other functions of our project include: a perimeter sensor to detect if the pet enters/exits this specified range, a battery indicator to track battery life, a heat sensor to detect if the collar is on the pet, and a software application to receive notifications from the sensor and battery indicator.
- Some pet owners have a problem checking whether their pets are in close proximity. This can also happen with working animals or at animal shelters. It can become an inconvenience to all pet owners, or those working with animals, when they cannot determine if their pet has left the house to go outside if the animal(s) are hiding somewhere inside the house or shelter.
- The product that was made, Fluffy Finds, is a simple and easy-to-use for our consumers. The product is cost efficient and has all the important features needed in a pet tracker. Additionally, FluffyFinds has a door sensor, which no other pet-tracking product posses. It lets the user know whetehr or not the pet is inside or outside the house and will send a notification to the user whenever the pet enters or exits the house. If a pet is outside, useres are able to track its location through the device's GPS capabilities. The pet tracker also has a temperature sensor, which is used to detect if the pet is currently wearing the device. FluffyFinds will ultimately benefit pet owners who are looking to save money on simpler pet-tracking product that will accomplish all of their pet-tracking needs, without excessive features or costs.
  
# Demonstration:  
- {{<rawhtml>}}
<div class = "center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/BnWUZq5HKVE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
{{</rawhtml>}}
  - In the video, shows in general how each device works. 
  - Shows also how the each device sends data to the database then that is dynamically updated onto the user's mobile phone application.

# Mobile Application:
{{<rawhtml>}}
<div class = "center">
    <img src = "/images/FluffyFinds/FluffyFinds1.png" alt= "" width ="300" height = "550" />
    <img src="/images/FluffyFinds/FluffyFinds2.png" alt="" width ="300" height = "550"/>
</div>
{{</rawhtml>}}

# Devices:
- Prototype The Collar
  - ![](/images/FluffyFinds/collar.png)
- Prototype of The Door Sensor
  - ![](/images/FluffyFinds/door.png)

# Database:
- ![](/images/FluffyFinds/database.png)
  - General undsetanding of how both the Door Sensor and the GPS Tracker sends data to the database and is able to be viewed on a mobile application.

# Components:
- ### Collar:
  - Microprocesssor: [Arduino Nano](https://www.amazon.com/gp/product/B0097AU5OU/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)
  - 3GPS Module: [SIM5320A Mini Breakout Board](https://www.amazon.com/YONEIX-Cellular-Breakout-SIM5320A-Expansion/dp/B07JBW9QXV)
    - Used the GPS module have it able to connect to the internet and send and receive data. I have managed to have the device send what information we need to the database by sending the GPS location to the firebase database directly through HTTPS requests.
    - Reading the GPS location data and storing it into a string. Then sending the data straight to the Real-Time Database of Firebase so the Phone app can read the current location of the pet.
    - Used an [Ceramic Antenna](https://www.amazon.com/gp/product/B078Y2WNY6/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1) to gain access to 3G Cellular
    - Had used the T-mobile service to provide the device 3G.
  - [Battery Holder](https://www.amazon.com/Battery-Holder-Batteries-Charger-Storage/dp/B081RPBP18/ref=sr_1_6?dchild=1&keywords=aaa+battery+holder+switch&qid=1612836762&sr=8-6) 
  - Temperature Sensor: [LM34](https://www.ti.com/product/LM34#product-details##pps)
    - Chosen a temperature sensor, LM34, to be the one measuring the pets temperature and had made it capable of measuring temperature (Fahrenheit) to the tenth place.
- ### Door Sensor: 
  - [NodeMCU](https://www.amazon.com/HiLetgo-Internet-Development-Wireless-Micropython/dp/B010O1G1ES) 
  - [PIR Motion Sensor](https://www.amazon.com/gp/product/B00JOZTAC6/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1)
    - Had chosen the NodeMCU combined with the Adafruit Motion Sensor to be the design for the door sensor. It is able to detect if the pet goes through the door by the power of motion then send data to the Firebase Database through Wi-Fi to update phone app if the pet is inside or not.
  - [Battery Holder](https://www.amazon.com/Battery-Holder-Batteries-Charger-Storage/dp/B081RPBP18/ref=sr_1_6?dchild=1&keywords=aaa+battery+holder+switch&qid=1612836762&sr=8-6) 
    - Temporarily used a AAA battery holder as the base of our collar design and also the door motion sensor. We are attaching the other components onto the battery holder for our collar design and placing all components into a 3D-printed container
    - Was going to use a smaller [battery pack](https://www.amazon.com/Adafruit-328-Battery-Lithium-Polymer/dp/B01NAX9XYG), and was rechargable in the design. But didn't have enough time to implement it fully to the final prototype.
- ### Mobile Apllication & Database:
  - [Google Real-Time Database Firebase](https://firebase.google.com/)
    - Had chosen to use Google Firebase because its easy to implement with Flutter. Had to send values from  the user devices into its database and then can read values on the app from its database. 
  - Mobile Application Framework: [Flutter](https://flutter.dev/)
    - Picked Flutter to create a mobile application to display values from the Google Firebase database. Values including: GPS coordinates, temperature, house status (tells if pet is either inside or outside), and battery life.
# Cost Analysis
-   ![](/images/FluffyFinds/cost.png)

# Future Improvements:
-   Waterproof design
-   A better device than the motion sensor
    -   for example: an RFID sensor
- More secure syncing methods
  - ability to view a specific trackers data on multiple devices
- Smaller design
  - probably a design own PCB for the entire project
  - genereally reduce the size by changing to a lithium ion rechargable battery
    - this will greatly improve battery consumption
- iOS compatibility