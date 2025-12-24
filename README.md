# another-esphome-alarmo-keypad
A local wifi keypad for Alarmo

I wanted a keypad hardware that would display the alarm status and pin code entry for Alarmo. I have android tablet but it flakes out when my internet goes out. I wanted to have a more solid option for disarming the house if the tablet flaked out while we were out of the house. 

I like to follow the kiss method (kids look it up) and did not want tags or fingerprint sensors. Just want pin code entry with a dedicated controller.

Supplies

  *esp32-c3 supermini → [Amazon](https://www.amazon.com/Teyleten-Robot-Development-Supermini-Bluetooth/dp/B0D47G24W3)

      This keypad is ok. The membrane versions might be better. The soldering pads on this Tegg keypad can break off if not careful  
  *4x4 matrix keypad  → [Amazon](https://www.amazon.com/Tegg-Keypad-Matrix-Tactile-Arduino/dp/B07QBNT56V)

      You can get any ssd1306 display in the color you want white or blue or whatever
  * ssd1306 128x64 display → [Amazon](https://www.amazon.com/SSD1306/s?k=SSD1306)
  * buzzer not high decibels → [Amazon](https://www.amazon.com/dp/B0CWHH9ZYB)

    OPTIONALS

      Any wiring accessories you may want like a bread board, wire, project box(wood craft boxes are fun), and connectors.

Wiring

   <img width="350" height="250" alt="WiringDiagram" src="https://github.com/user-attachments/assets/464e2e21-b95c-48a0-b6ee-26008b92c803" />

Programing

  The esphome builder code is in the firmware folder. Please have a look and read. You must copy the components of the code you want. 

  If you have a new C3 supermini it probably defaults to sleep and awake over and over. You need to press and hold boot, then press reset and release, then release boot buttons. This method will allow the C3 supermini to program via usb.  

  Check out the Automation Examples. The Key entered example will be needed to pass the code to alarmo. My examples have device ID's removed. You will need to update with your device and entity id's. The gui will be the best way to do that. just note that {trigger.event.data.code} is the way to utilize the entered code. 

Usage

  The star key will delete a key entered. The C will clear the currently entered pin code. If you use the A key automation, pressing and holding the A key will arm the system. And finally if you enter your pin code and press D it still disarm Alarmo system. 
