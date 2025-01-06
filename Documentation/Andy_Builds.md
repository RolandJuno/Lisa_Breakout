# Building the Lisa Breakout Board - A Modern Solution for Apple Lisa Computing

The Lisa Breakout Board project enables anyone to experience the Apple Lisa computing environment without requiring access to increasingly rare original hardware. This custom-designed PCB serves as an interface that replicates critical components of the Apple Lisa, allowing users to construct a functional system using modern, readily available parts. By integrating contemporary components like RGB2HDMI for video output alongside carefully reproduced Lisa-specific circuitry, this board provides an accessible entry point into Lisa computing while preserving the authentic experience of this groundbreaking system. The breakout board represents a bridge between vintage computing history and modern maker capabilities, opening up Lisa exploration to a broader community of retrocomputing enthusiasts.

The board's design prioritizes compatibility with original Lisa software while incorporating modern conveniences and reliability improvements. Each PCB can be assembled using standard soldering techniques and commonly available electronic components, making it a fun project for those with basic electronics experience. 


# What I did to build it - Andy Notes

I'm a horrible builder so after I built this I wanted to put down some notes.

 - I didn't need the keyboard adapter as I already have the USB adapter from arcane byte
    - https://www.tindie.com/products/arcanebyte/usb2lisa-keyboard-adapter/
- I have a working RGB2HDMI, TTL version (the basic one you get) and there is a Lisa config
    -  Using a real 2/5 mobo the Lisa config works out of the box, using the repro 2/5 mobo from alexthecat you need to tune the default Lisa config
    -  I have used many RGB2HDMIs from RetroHack shack and they have been great: https://retrohackshack.com/product/rgbtohdmi/
- I used Paul's notes and BOM to easily order all the parts, PCB from JCL
- I put the Floppy and Video/Ground blocks on the 'back' for easier access IMHO
- resistors have no polarity
- caps have polarity so do LEDs- make sure you get that right.
- put the keyboard interface on the 'back' so it can work with a real card-cage if you have one
- when testing HOOK UP SOUND - the Lisa will beep if things are working, use this to help when you don't have video.
- Lisa can boot without RAM- you just need an IO and CPU card to get some beeps and the video test screen
- Lisa 2/10 motherboard is completely different than the 2/5 and will not work with this break-out-board. Maybe Paul can make one for the 2/10 and we can have some MacXLs to play with.


Some images of the board I built and got working:

![IMG_7158](https://github.com/user-attachments/assets/fa1f86a3-fa89-4c23-9753-88ef43c632ae)
![IMG_7159](https://github.com/user-attachments/assets/88a1d8f6-0f00-4949-9805-a2c71bf573b2)
![IMG_7162](https://github.com/user-attachments/assets/e9587a7b-096d-486f-b42a-d4a4e40c8568)
![IMG_7163](https://github.com/user-attachments/assets/0bbad23f-cea9-4c8c-a6c8-a1c02f3ebdc0)
