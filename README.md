# another-esphome-alarmo-keypad

Scroll down for new updated PCB and 3d Printable case! <img width="100" height="75" alt="IMG_5698" src="https://github.com/user-attachments/assets/edaf75ed-bf33-46c9-adbf-09f2237deee3" />


A local wifi keypad for Alarmo

I wanted a keypad hardware that would display the alarm status and pin code entry for Alarmo. I have android tablet but it flakes out when my internet goes out. I wanted to have a more solid option for disarming the house if the tablet flaked out while we were out of the house. 

I like to follow the kiss method (kids look it up) and did not want tags or fingerprint sensors. Just want pin code entry with a dedicated controller.

Supplies

  * esp32-c3 supermini → [Amazon](https://amzn.to/4htXbUB)  bigger pack [Amazon](https://amzn.to/3T9Ncfi) 

This keypad is ok. The membrane versions might be better. The soldering pads on this Tegg keypad can break off if not careful. Working on a PCB that should make this a non issue. 
  * 4x4 matrix keypad  → [Amazon](https://amzn.to/4ACFlri)

You can get any ssd1306 display in the color you want white or blue or whatever
  * ssd1306 128x64 display → [Amazon - yellow and blue](https://amzn.to/4z5Livp)
  * buzzer not high decibels → active [Amazon](https://amzn.to/4xStWB8) or passive for PCB [Amazon](https://amzn.to/3TAuAVQ)

I do get a small commision for these links but I personaly did purchase these for this project. 

OPTIONALS:

Any wiring accessories you may want like a [breadboard](https://amzn.to/3VeKENz), [wire](https://amzn.to/4ACFvPq), [jumper wire kit](https://amzn.to/3VkdOea) ,  [project box(wood craft boxes are fun)](https://amzn.to/4dfnnBf), [connectors](https://amzn.to/4AGSwr6), [usb-c cords](https://amzn.to/4xXHJGL) and [powerbricks](https://amzn.to/3TgWXbA).

Tools:

[Soldering station](https://amzn.to/4hwRKEj), [solder flux](https://amzn.to/4hAHv27), [wire strippers](https://amzn.to/47r0Y0f)
      

Wiring

   <img width="350" height="250" alt="WiringDiagram" src="https://github.com/user-attachments/assets/464e2e21-b95c-48a0-b6ee-26008b92c803" />

Programing

  The esphome builder code is in the firmware folder. Please have a look and read. You must copy the components of the code you want into your own esphome builder device. 

  If you have a new C3 supermini it probably defaults to sleep and awake, over and over. You need to press and hold boot, then press reset and release, then release boot buttons. This method will allow the C3 supermini to program via usb.  

  Check out the Automation Examples. The key entered example will be needed to pass the code to alarmo. My examples have device ID's removed. You will need to update with your device and entity id's. The gui will be the best way to do that. Just note that {trigger.event.data.code} is the way to utilize the entered code. 

Usage

  The * key will delete a pin character entered. The C will clear the currently entered pin code. If you use the A key automation, pressing and holding the A key will arm the system. And finally if you enter your pin code and press D it still disarm Alarmo system. 

Project Example

<img width="320" height="224" alt="IMG_3555" src="https://github.com/user-attachments/assets/e1f1ee0b-10a0-4f80-8b6c-57bc8143987d" />

<img width="291" height="320" alt="IMG_3556" src="https://github.com/user-attachments/assets/158d2382-7808-4d67-bcd2-235490e1511f" />


https://github.com/user-attachments/assets/e2140639-2b51-4e83-94c9-4a3a91e51b54

Updated PCB & 3D Printed Case!

The original version of this project was built using point-to-point wiring and a project box. It worked, but I wanted something cleaner, easier to assemble, and a little less janky.

So I designed a custom PCB and a 3D printable enclosure specifically for the Alarmo keypad.

Custom PCB 

The PCB brings the ESP32-C3 Super Mini, SSD1306 OLED display, 4x4 keypad, and buzzer together into a much cleaner package. It greatly reduces the amount of hand wiring required and makes the finished keypad easier to assemble and service.

<p align="center">
  <img width="45%" alt="PCB front" src="https://github.com/user-attachments/assets/a1162d3e-8dd0-4ddc-a72c-8e80d1786fd6" />
  <img width="45%" alt="PCB back" src="https://github.com/user-attachments/assets/f778a3d6-73c8-4dc4-976d-43beef11bbca" />
</p>


The PCB files can be found in the PCB folder of this repository. or [availabe here]([https://amzn.to/47r0Y0f](https://oshwlab.com/rockdown/another-esphome-alarmo-keypad)  
3D Printed Case

I also designed a case to hold the complete keypad assembly. The goal was to make something that could be mounted on the wall and look more like a finished alarm keypad instead of a collection of development boards and wires stuffed into a project box.

<p align="center">
  <img width="45%" alt="3D printed case front" src="https://github.com/user-attachments/assets/ea5c2dcf-ef01-4767-9f10-308f13c043ae" />
  <img width="45%" alt="3D printed case back" src="https://github.com/user-attachments/assets/9813a219-db86-4038-8ed1-7ca5638dacb2" />
</p>

The printable files can be found in the 3D Print folder of this repository.

Finished Keypad

With the PCB and printed enclosure, the project is now much easier to reproduce and gives the Alarmo keypad a much more finished appearance.

<p align="center">
  <img width="500" alt="Completed Alarmo Keypad" src="https://github.com/user-attachments/assets/b1be64ae-bc8f-450d-bf97-a4670e824924" />
</p>




