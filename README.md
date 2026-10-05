# Another ESPHome Alarmo Keypad

A dedicated, local Wi-Fi alarm keypad built with **ESPHome** for **Home Assistant and Alarmo**.

This project provides a physical keypad for entering a PIN, arming or disarming Alarmo, and displaying the current alarm status without relying on a tablet or touchscreen.

<p align="center">
  <img width="500" alt="Completed ESPHome Alarmo Keypad" src="https://github.com/user-attachments/assets/b1be64ae-bc8f-450d-bf97-a4670e824924" />
</p>

## Why I Built It

I already had an Android tablet that could control Alarmo, but I wanted a more reliable, dedicated way to disarm the house.

A tablet is great when everything is working properly, but tablets, apps, Wi-Fi connections, and dashboards can occasionally flake out. I wanted something simpler that could stay on the wall and have one primary job:

**Enter a PIN and control the alarm.**

I tend to follow the **KISS principle — Keep It Simple, Stupid.**

I didn't need fingerprint readers, RFID tags, cameras, or anything particularly fancy. I wanted a physical keypad, a small display, audible feedback, and a dedicated ESP32 controller that could communicate directly with Home Assistant through ESPHome.

The result is **Another ESPHome Alarmo Keypad**.

## Features

- Physical 4×4 PIN keypad
- Alarmo arm and disarm control
- SSD1306 OLED status display
- Audible buzzer feedback
- ESP32-C3 based
- ESPHome firmware
- Native Home Assistant integration
- Local network operation
- Custom PCB
- Custom 3D-printable wall enclosure
- Configurable Home Assistant automations

## Hardware

### Main Components

- **ESP32-C3 Super Mini** → [Amazon](https://amzn.to/4htXbUB)  
  Larger pack → [Amazon](https://amzn.to/3T9Ncfi)

- **4×4 Matrix Keypad** → [Amazon](https://amzn.to/4ACFlri)

- **SSD1306 128×64 OLED Display** → [Amazon – Yellow & Blue](https://amzn.to/4z5Livp)

- **Buzzer**  
  Active → [Amazon](https://amzn.to/4xStWB8)  
  Passive version used with the PCB → [Amazon](https://amzn.to/3TAuAVQ)

### A Note About the Keypad

The Tegg 4×4 keypad linked above works, but the solder pads can be somewhat fragile if you're not careful while soldering.

This was one of the reasons I eventually designed the custom PCB. The PCB provides a much cleaner and more secure way to connect the keypad and eliminates much of the point-to-point wiring used in the original prototype.

Membrane-style 4×4 keypads should also work if you prefer that style.

### OLED Display

The project uses an **SSD1306 128×64 OLED**.

You don't have to use the exact display linked above. Compatible SSD1306 displays are available in several colors, including white, blue, and yellow/blue combinations.

> **Affiliate Disclosure:** Some of the Amazon links above are affiliate links. I may receive a small commission if you purchase through them at no additional cost to you. These are components and tools that I personally purchased or used while developing this project.

## Optional Supplies

If you're building the original wired version or experimenting with the project, you may also want:

- [Breadboard](https://amzn.to/3VeKENz)
- [Wire](https://amzn.to/4ACFvPq)
- [Jumper Wire Kit](https://amzn.to/3VkdOea)
- [Project Box / Wood Craft Boxes](https://amzn.to/4dfnnBf)
- [Connectors](https://amzn.to/4AGSwr6)
- [USB-C Cables](https://amzn.to/4xXHJGL)
- [USB Power Adapters](https://amzn.to/3TgWXbA)

## Tools

A few basic electronics tools will make the build much easier:

- [Soldering Station](https://amzn.to/4hwRKEj)
- [Solder Flux](https://amzn.to/4hAHv27)
- [Wire Strippers](https://amzn.to/47r0Y0f)

## Wiring

The project can still be assembled without the custom PCB using the original wiring configuration.

<p align="center">
  <img width="500" alt="ESPHome Alarmo Keypad Wiring Diagram" src="https://github.com/user-attachments/assets/464e2e21-b95c-48a0-b6ee-26008b92c803" />
</p>

If you're building a new keypad, I recommend using the custom PCB farther down this page. It significantly reduces the amount of wiring required.

## ESPHome Firmware

The ESPHome configuration for the keypad is located in the **Firmware** folder.

Take some time to read through the configuration before using it. You'll need to copy or modify the appropriate components for your own ESPHome device and Home Assistant installation.

### Programming the ESP32-C3 Super Mini

Some new ESP32-C3 Super Mini boards may repeatedly enter a sleep/reset cycle and can be difficult to flash initially.

If the board won't enter programming mode:

1. Press and hold the **BOOT** button.
2. While continuing to hold BOOT, press and release **RESET**.
3. Release the **BOOT** button.
4. Try flashing the ESP32-C3 again over USB.

Once the initial firmware has been installed, ESPHome can normally handle subsequent updates.

## Home Assistant & Alarmo

Check out the **Automation Examples** included with the project.

The **key entered** automation is particularly important because it passes the PIN entered on the physical keypad to Alarmo.

My example automations have the device and entity IDs removed, so you'll need to select your own devices and entities in Home Assistant.

Using the Home Assistant automation GUI is probably the easiest way to configure those values.

The entered keypad code is available through:

`trigger.event.data.code`

That value can then be passed to Alarmo as part of your arm/disarm automation.

## Keypad Controls

The default configuration uses several of the keypad's function keys:

| Key | Function |
| --- | --- |
| `*` | Delete the last PIN digit entered |
| `C` | Clear the currently entered PIN |
| `A` | Press and hold to arm the alarm when using the example automation |
| `B` | Press and hold to arm Alarmo in **Night Mode** |
| `D` | Submit the entered PIN and disarm Alarmo |

Because the keypad events are exposed through ESPHome and Home Assistant, these controls can be modified to fit your own alarm setup.

## Original Prototype

The first version of this project was built using point-to-point wiring and installed inside a simple project box.

It wasn't particularly elegant, but it worked — and it proved the concept.

<p align="center">
  <img width="320" alt="Original Alarmo Keypad Prototype" src="https://github.com/user-attachments/assets/e1f1ee0b-10a0-4f80-8b6c-57bc8143987d" />
  <img width="291" alt="Original Alarmo Keypad Electronics" src="https://github.com/user-attachments/assets/158d2382-7808-4d67-bcd2-235490e1511f" />
</p>

### Original Prototype Demo

https://github.com/user-attachments/assets/e2140639-2b51-4e83-94c9-4a3a91e51b54

The prototype worked well enough that I decided it was worth turning into something cleaner and easier to reproduce.

---

# Updated PCB & 3D Printed Case

The original keypad worked, but there was quite a bit of hand wiring inside the project box.

It was time to make it a little **less janky**.

So I designed a custom PCB and matching 3D-printable enclosure specifically for the Alarmo keypad.

## Custom PCB

The custom PCB brings the **ESP32-C3 Super Mini, SSD1306 OLED display, 4×4 keypad, and buzzer** together into a much cleaner package.

It reduces the amount of point-to-point wiring required and makes the finished keypad easier to assemble, troubleshoot, and service.

<p align="center">
  <img width="45%" alt="Alarmo Keypad PCB Front" src="https://github.com/user-attachments/assets/a1162d3e-8dd0-4ddc-a72c-8e80d1786fd6" />
  <img width="45%" alt="Alarmo Keypad PCB Back" src="https://github.com/user-attachments/assets/f778a3d6-73c8-4dc4-976d-43beef11bbca" />
</p>

The PCB files are available in the **PCB** folder of this repository.

The PCB design is also available on [OSHWHub / OSHWLab](https://oshwlab.com/rockdown/another-esphome-alarmo-keypad).

You can still build the keypad using the original wiring diagram, but the PCB is the recommended approach for a new build.

## 3D Printed Enclosure

I also designed a custom enclosure for the complete keypad assembly.

The goal was to create something that could be mounted on the wall and look more like a finished alarm keypad rather than a collection of development boards and wires stuffed into a project box.

<p align="center">
  <img width="45%" alt="Alarmo Keypad 3D Printed Case Front" src="https://github.com/user-attachments/assets/ea5c2dcf-ef01-4767-9f10-308f13c043ae" />
  <img width="45%" alt="Alarmo Keypad 3D Printed Case Back" src="https://github.com/user-attachments/assets/9813a219-db86-4038-8ed1-7ca5638dacb2" />
</p>

The printable files are available in the **3D Print** folder of this repository.

### Print Settings

Recommended starting settings:

- **Material:** PLA or PETG
- **Layer Height:** 0.20 mm
- **Supports:** TBD
- **Infill:** TBD
- **Wall Loops:** TBD

I'll update the recommended settings as the enclosure continues to be refined and tested.

## Finished Keypad

Combining the custom PCB with the printed enclosure turns the original prototype into a much cleaner and more reproducible project.

<p align="center">
  <img width="500" alt="Completed ESPHome Alarmo Keypad" src="https://github.com/user-attachments/assets/b1be64ae-bc8f-450d-bf97-a4670e824924" />
</p>

It's still fundamentally the same simple idea I started with:

**A dedicated physical keypad that does its job without trying to be everything else.**

---

## Project Status

This project is actively being improved. Firmware changes, PCB revisions, enclosure updates, and additional Home Assistant automation examples may be added as I continue using and testing the keypad.

If you build one, modify the design, or find a better way to do something, feel free to share your version.

**Learn it. Build it. Put it into practice.**



