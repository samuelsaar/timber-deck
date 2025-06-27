---
Title: "Timber Deck"
Author: "Samuel Saar"
Description: "A compact arm based personal computer with a custom keyboard built inside a wooden box"
Created_at: "2025-06-25"
---

# 25-06-2025 - Idea and Inital Design

**I stumbled on an old Soviet era wooden box which, originally probably used for storing lab equipement, happenes to now have just enough room to house a small 5 row keyboard.**

![IMG_8440](https://github.com/user-attachments/assets/d2d84883-6683-4bb0-9646-cac92f5b9bb4)



**Inspired by this, I have decided to turn this box into a little personal computer cyberdeck thing. From the looks of things it shouldn't be too hard to fit a raspberry pi 5, a custom ~50% keyboard, a battery and a 7" screen in this, maybe even a speaker, we'll see.**

![IMG_8443](https://github.com/user-attachments/assets/eab4b392-5da6-429c-8c8f-80e3b0d85a59)



**Today was mostly spent modelling and experimenting with different concepts in Blender. The dimensions of things is roughly correct, but it's far from a functional design.**

![Screenshot From 2025-06-23 10-08-59](https://github.com/user-attachments/assets/9e03b1c5-d571-4bc1-9e4c-d81140613740)
![Screenshot From 2025-06-25 21-33-12](https://github.com/user-attachments/assets/f81db2e8-68ff-4bb6-beae-5d34ec129f85)


### Total time ~6h

# 26-06-2025 - How Power?

**Had a lot of other stuff going on so couldn't work on the project much. I researched my options for power and display and started making a bill of materials.**

**The power situation seems a bit more complicated than I initally figured as the Pi 5 needs 5V 5A over USB-C, while it is a standard that exists, it isn't one that anyone uses... Going with a power bank that can output 25W at a higher voltage and then using a buck converter to get it down to 5V 5A seems to be the simplest and most economical option. There are also some UPS HATs that take 18650 cells and output 5V 5A, those might also be worth considering.**

### Total time ~1h

# 26-06-2025 - Power, Sound and Headache

I spent the day trying to figure out a final power and sound solution. I think I have the power pretty much figured out - a waveshare UPS that takes 3 18650 cells, it's fairly cheap, compact and it can be monitored from the Pi through GPIO pins. Sound is a bit more complicated as I want to have both, a built-in mono speaker and a stereo headphone jack. My current idea is to go with a small USB DAC (I should already have one somewhere) and wire it to both, the headphone out and the speaker amp. Then I'd power the amp from another usb port and have a hardware switch that can cut off the power to the amp. 

![Screenshot From 2025-06-28 00-16-09-min](https://github.com/user-attachments/assets/4d108004-927a-43cb-934a-646176d4c377)
![Screenshot From 2025-06-28 00-17-26-min](https://github.com/user-attachments/assets/c50f9d83-a536-4b89-ab9a-aa74fde0862e)

All this should work in theory, but now I have another small problem - I've run out of USB ports. I have one occupied by the DAC, another powering the amp, third powering the display and the last one is wired to the keyboard. I would like to have at the very least one usb port wired as the deck's external I/O. So I'll probably have to incorporate a usb hub in this build as well...

![Screenshot From 2025-06-28 00-11-12](https://github.com/user-attachments/assets/746b9f9b-5e03-43f5-8073-04f3e7e74a04)


### Total time ~4h

