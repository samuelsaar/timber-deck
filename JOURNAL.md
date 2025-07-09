---
Title: "Timber Deck"
Author: "Samuel Saar"
Description: "A compact arm based personal computer with a custom keyboard built inside a wooden box"
Created_at: "2025-06-25"
---

# 25-06-2025 - Idea and Inital Design

I stumbled on an old Soviet era wooden box which, originally probably used for storing lab equipement, happenes to now have just enough room to house a small 5 row keyboard.

![IMG_8440](https://github.com/user-attachments/assets/d2d84883-6683-4bb0-9646-cac92f5b9bb4)



Inspired by this, I have decided to turn this box into a little personal computer cyberdeck thing. From the looks of things it shouldn't be too hard to fit a raspberry pi 5, a custom ~50% keyboard, a battery and a 7" screen in this, maybe even a speaker, we'll see.

![IMG_8443](https://github.com/user-attachments/assets/eab4b392-5da6-429c-8c8f-80e3b0d85a59)



Today was mostly spent modelling and experimenting with different concepts in Blender. The dimensions of things is roughly correct, but it's far from a functional design.

![Screenshot From 2025-06-23 10-08-59](https://github.com/user-attachments/assets/9e03b1c5-d571-4bc1-9e4c-d81140613740)
![Screenshot From 2025-06-25 21-33-12](https://github.com/user-attachments/assets/f81db2e8-68ff-4bb6-beae-5d34ec129f85)


### Total time ~6h

# 26-06-2025 - How Power?

Had a lot of other stuff going on so couldn't work on the project much. I researched my options for power and display and started making a bill of materials.

The power situation seems a bit more complicated than I initally figured as the Pi 5 needs 5V 5A over USB-C, while it is a standard that exists, it isn't one that anyone uses... Going with a power bank that can output 25W at a higher voltage and then using a buck converter to get it down to 5V 5A seems to be the simplest and most economical option. There are also some UPS HATs that take 18650 cells and output 5V 5A, those might also be worth considering.

### Total time ~1h

# 27-06-2025 - Power, Sound and Headache

I spent the day trying to figure out a final power and sound solution. I think I have the power pretty much figured out - a waveshare UPS that takes 3 18650 cells, it's fairly cheap, compact and it can be monitored from the Pi through GPIO pins. Sound is a bit more complicated as I want to have both, a built-in mono speaker and a stereo headphone jack. My current idea is to go with a small USB DAC (I should already have one somewhere) and wire it to both, the headphone out and the speaker amp. Then I'd power the amp from another usb port and have a hardware switch that can cut off the power to the amp. 

![Screenshot From 2025-06-28 00-16-09-min](https://github.com/user-attachments/assets/4d108004-927a-43cb-934a-646176d4c377)
![Screenshot From 2025-06-28 00-17-26-min](https://github.com/user-attachments/assets/c50f9d83-a536-4b89-ab9a-aa74fde0862e)

All this should work in theory, but now I have another small problem - I've run out of USB ports. I have one occupied by the DAC, another powering the amp, third powering the display and the last one is wired to the keyboard. I would like to have at the very least one usb port wired as the deck's external I/O. So I'll probably have to incorporate a usb hub in this build as well...

![Screenshot From 2025-06-28 00-11-12](https://github.com/user-attachments/assets/746b9f9b-5e03-43f5-8073-04f3e7e74a04)


### Total time ~4h

# 28-06-2025 - Finalizing Component Choices, Design for 3D Print

The audio setup should now be pretty much set. I chose a different driver due to the old one being way too expensive with shipping. I also figured that I don't need to worry about the speaker amp taking up a USB port as I can just get 5V from the Pi GPIO. I also picked out the display I'm going to use. It's a QLED IPS panel from Waveshare, a pricier option as far as 7" panels go, but it's the cheapest option I've found with a half decent color gamut. Also, Waveshare has wonderful documentation, they even provide 3D models of their products for download!

I also spent some time figuring out how everything would be connected together. 3D printed base with standoffs, which would be glued to the bottom of the case, would hold most components. For the front panel (the thing that the screen and speaker driver are glued to) would be made of plywood with a 3D printed pillar going down to the base into which it would be screwed into.

### Total time ~5h

# 29-06-2025 - Lot of something

Quite a productive day this time, I started with a quick fitment check of the Pi 5 and a couple of the cables I'll be using in the build. The DAC connected to the USB port came with a Razer headset that broke some time ago. The HDMI extension is the official one that Raspberry Pi offers, as one can see from the picture, I have made certain.. modifications to make it more flexible.

![IMG_8455](https://github.com/user-attachments/assets/dbb3a763-d182-4b65-8970-b0b7fad61bfa)

Spent a bunch time on designing the 3D printable parts and figuring out how components would be mounted. I also did a quick test print of the standoffs for the Pi to test out tolerances and heat-set inserts (a first for me, I've always used nuts or resorted to use hot glue before). The test was mostly succsessful, but I noticed that the pi wouldn't sit quite flush on the standoffs as some small resistors and the like on the bottom of the pi were interfering with the print so I made some slight adjustments to the standoffs in cad.

![Screenshot From 2025-07-01 17-51-05](https://github.com/user-attachments/assets/30a3bd95-0bb0-4996-bedf-501a2ce04a77)

![IMG_8461](https://github.com/user-attachments/assets/0c7f76f7-c3d9-4a4d-a377-450f6eb19775)

I also finalized some part choices and ordered a couple cheaper ones from Aliexpress that would take a longer time to arrive and I figured I would've had to buy with my own money anyways. Specifically, the internal HDMI cable to connect the display to the Pi, a panel mount ethernet extension and the amplifier board for the speaker.

### Total time ~7h

# 30-06-2025 - Lot of nothing

Was busy with other things so I couldn't work on the project.

### Total time 0h

# 01-07-2025 - Catching up, Making a BOM, Hello KiCad

Started the day off by logging in the last 2 days that I had missed to document.

Next up I made some sort of BOM, it obviously needs some work as I'm currently going over budget so I'll have to decide which parts I want to fund myself.

![Screenshot From 2025-07-01 18-07-57](https://github.com/user-attachments/assets/3b47ed7f-e25a-4830-93f1-66e0d5ba2363)

Spent rest of the day and half the night learning PCB design and KiCad, mostly following the wonderful [guide](https://www.youtube.com/watch?v=8WXpGTIbxlQ) by Joe Scotto. Still have some work to do on the PCB design, but it's most of the way there.

![Screenshot From 2025-07-02 01-50-12](https://github.com/user-attachments/assets/067a6997-be40-4c05-a136-c81b4c5f8646)

### Total time ~4h

# 02-07-2025 - KiCad, POG

Realized that I don't have the room to just slap the Pi Pico on the back of the PCB as I use through-hole components, so I spent some time figuring out a solution. I hoped that I could still mount the Pico inside the keyboard half somehow and just hand wire it to the pads that it'd be otherwise soldered to. The day was scorching hot so I didn't have the energy to actually implement that.

I also wanted to figure out how I'm gonna implement the firmware. QMK seems to support it, but when I wanted to use it and followed the documentation, I discovered that while the Pi Pico is supported, it isn't particularly well documented so I couldn't really wrap my head around how to use QMK. Then I looked into KMK and found a tool called [POG](https://pog.heaper.de/) which supposedly simplifies the Firmware writing process by offering a GUI tool for it. Seems like a great option and I'm probably going to go with it as the project is already quite complicated and I'm not sure if I have the time to figure out how to write firmware from scratch. 

### Total time ~3h

# 03-07-2025 - Finishing the PCB

I came back to the PCB design and figured out that there really isn't room for the Pico in the keyboard half of the deck, so I decided to implement a row of pads on the keyboard PCB to which I can solder a ribbon cable to, the other end of which will be soldered to the corresponding GPIO and ground pads on the Pico that's housed in the other half of the deck. That meant I had to redo the Pi Pico footprint nearly from scratch in KiCad, but I'm glad I did as it gave me a deeper understanding of how to use the software. I also wired all the rows and columns up to the pads on the PCB and added some mounting holes. 

![Screenshot From 2025-07-03 22-15-41](https://github.com/user-attachments/assets/4b853b6f-62f4-4926-8eac-8a6fc477c9ff)

All this took way longer than I had expected, and KiCad is kind of prone to crashing which has been a bit annoying. Though that might be due to me being on Wayland, KiCad devs are a bit infamous for refusing to implement proper Wayland support. 

![Screenshot From 2025-07-03 22-13-55](https://github.com/user-attachments/assets/833322ab-4045-4cb1-aac4-06223c6e91f5)

### Total time ~4h

# 04-07-2025 - Nothing

Away from home, coulnd't work on the project.

### Total time 0h

# 05-07-2025 - Nothing Pt.2

Away from home, coulnd't work on the project.

### Total time 0h

# 06-07-2025 - Nothing Pt.3

Home, but tired, didn't work on the project.

### Total time 0h

# 07-07-2025 - 

Figuring out and modeling the 3D printed parts for mounting the Pi Pico and keyboard pcb.

### Total time ~2h

# 08-07-2025 - 

Pretty much finishing the 3D model.

### Total time ~2h
