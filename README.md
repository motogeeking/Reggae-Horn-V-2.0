# Reggae-Horn-V-2.0
A fun "horn" project for your motorcycle or other vehicle. Heck, get creative and make a custom door bell or talking doll, whatever...

This is a project that I made for my little 125 SSR Razkull motorcycle. I found, by almost getting flattened by a driver that was texting, that the stock horn is not very effective. So I decided to create a horn that really couldn't be ignored. Its LOUD, very effective and not too hard to build. I added a couple of "fun" features to this project also. The project uses a Pic12f1840, an 8 pin, 8 bit microcontroller. I am sure that it can be done with an arduino or Atmel type micro, but Pics work well for me. The code is heavily commented, so if you want to convert it to something else, you can get a handle on what I am doing. It is programmed using Great Cow Basic, a free basic compiler available here...

http://gcbasic.sourceforge.net/Typesetter/index.php/Home

along with a PicKit 3 to flash the Pic.

The sound module is a DFPlayer Mini, a small MP3 player module that can play MP3 or WAV files when instructed by the micro. The unit is triggered by an opto-coupled input directly from your horn. I am using a 60 watt audio amplifier module and horn speaker for this project, but any combination of amplifier and speaker that can take a line level audio input will work. I am mixing the stereo output down to mono, but this unit can output full high quality stereo sound.

As far as connecting the circuit to your vehicle, the 12v power must come from a "switched" power source. This will kill the power to the circuit when the key is off, so your battery won't die unexpectedly. The input from your horn switch can be grabbed directly from the 2 spade lugs that connect to your existing horn. Just disconnect these from your horn and attach to the circuits horn input. This connection is opto-coupled and polarized, so check. One side is GND and the other is 12v when you press your horn button.

"This is not intended to be a replacement for a DOT approved horn. Use reponsibly". There... I said it.

********************************************************************************************
The following is taken from the code listing if you want to get a handle on how this works.
********************************************************************************************

A fun "horn" project for your motorcycle, or other vehicle, that can can play ANY sound you want in the form of an MP3 file.

This version plays sounds at two different instances...

1) when the key is first switched on (OPTIONAL start-up sound), and
2) when you press the horn button.

All sound files are stored on a microTF card as MP3 files. If you want only horn sounds (no start-up sounds), create a folder and name it "01" (without quotes). This is where your horns sounds will be stored. If you also want start-up sounds, create a second folder and name it "02" (without quotes). These folders need to be on the root of your microTF card and must contain at least one MP3 sound file.

NOTE: start-up sounds are optional. Do not create folder "02" if you don't want start-up sounds.                                           

All sound files must be named 001.mp3, 002.mp3, etc. or you can name the files 001MacSound.mp3, 002ReggaeHorn.mp3, 0003BikeBell.mp3, etc., but all must start with the 3 digit sequential number scheme

Sound file names can range from 001 - 099 in each folder.

Place your MP3 sound files into the appropriate folder according to how you want to use them. Either horn sounds (place in folder 01), or optional start-up sounds (place in folder 02).

Upon power up, the program will fetch the total number of folders and number of MP3 files in each folder. It will also recall the volume levels that you have set previously.

If you chose to use start-up sounds, upon turning on your key, the first MP3 file (001.mp3) in folder 02 will play to completion. If there is more than one MP3 file in folder 02, then the next file will play the next time you turn the key on. Be creative... Let your vehicle tell you how awesome you are, or play the Apple Mac startup sound or any other cool clip, every time you start your vehicle. You can use up to 99 sound files in each folder.

You may want the start-up sounds to play at a lower volume than the horn sounds, for instance if you are in your garage. The start-up volume level can be controlled using the potentiometer connected to pin 3 of the PIC12f1840. Just set it to a comfortable level.

Once the key is on, and the optional start-up sound is played, the unit will wait for you to press the horn button.

Since there is only one button, we have to creatively use it to do 3 different things... change the horn volume, select one of possibly many horn sounds and of course, as a button to activate the horn.

Just like a normal horn, simply pressing the horn button will play the current horn sound for as long as it is pressed, UP TO 5 SECONDS! This time can be changed with the variable "PressTimeOut". If the horn button is pressed passed this amount of time, the unit will cycle through all stored MP3 sounds in folder 01, for one second each at the same volume that you set to play the start-up sound using the potentiometer. This allows you to cycle through the sounds at a more comfortable volume level. Simply release the horn button when you hear the sound you want to use as your horn. This sound will be set as your horn sound and the volume will automatically be set back to the changeable horn volume (see below).

Pressing and holding the horn button while turning the power (key) on will allow you to change the horn volume. The unit will start at the lowest volume level and play the current horn sound for one second and stop, then increase the volume and play the horn sound again. This cycle will continue through 10 volume levels, from low to high as long as you keep holding the button. When you reach the volume you like, just release the button and that volume will be set and saved.
 
THIS PROJECT IS A NOVELTY AND IS NOT INTENDED AS A SUBSTITUTE FOR A DOT APPROVED MOTOR VEHICLE HORN! USE RESPONSIBLY!
