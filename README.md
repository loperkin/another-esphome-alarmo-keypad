# another-esphome-alarmo-keypad
A local wifi keypad for Alarmo

I wanted a keypad hardware that would display the alarm status and pin code entry for Alarmo. I have android tablet but it flakes out when my internet goes out. I wanted to have a more solid option for disarming the house if the tablet flaked out while we were out of the house. 

I like to follow the kiss method (kids look it up) and did not want tags or fingerprint sensors. Just want pin code entry with a dedicated controller.

Supplies

  *esp32-c3 supermini → [Amazon](https://amzn.to/4qy8IoZ)  bigger pack [Amazon](https://amzn.to/4jgqCdq) 

This keypad is ok. The membrane versions might be better. The soldering pads on this Tegg keypad can break off if not careful  
  *4x4 matrix keypad  → [Amazon](https://amzn.to/496OdZm)

You can get any ssd1306 display in the color you want white or blue or whatever
  * ssd1306 128x64 display → [Amazon - White](https://amzn.to/4jiPOQD) , [Amazon - blue](https://amzn.to/491VTfe) , [Amazon - yellow and blue](https://amzn.to/4aS9oRB)
  * buzzer not high decibels → [Amazon](https://amzn.to/4qw0NbN)

I do get a small commision for these links but I personaly did purchase these for this project. 

    OPTIONALS

      Any wiring accessories you may want like a bread board, wire, project box(wood craft boxes are fun), and connectors.

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




