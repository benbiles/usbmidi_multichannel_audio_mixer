usbmidi_multichannel_audio_mixer/

for now , arduino novation launchcontrol usb midi usbhost

For now this is working with the Novation LaunchControl control surface although I would like to write support for more control surfaces or maybe even write in some kind of learning code so new control surfaces can be added.

Myabe an EPROM could store the new contro surfaces data ?

Whatever it will end up being the aim is to make this project simple fast & low power.

anyway, for now..

Instructions to hook up an arduino to Novation LaunchControl and get midi messages into your arduino.

you will need

1 x LaunchControl
1 x Arduino UNO R3
1 x USBhost shield v2
1 x USB hub with enough power to power the LaunchControl
relevant usb cables

1/ connect the USBhost shield to the Arduino UNO R3

I found these 2 but there are others to
https://www.circuitsathome.com/products-page/arduino-shields/usb-host-sh...
https://www.sparkfun.com/products/9947

2/ download each zip folder from the 2 librarys linked below on GitHub
uncompress each zip file and put each individual folder with contents
into the Arduino IDE Library folder.

the required USBhost version 2.0 library
https://github.com/felis/USB_Host_Shield_2.0

the required USBH_midi library by Yuuichi
https://github.com/YuuichiAkagawa/USBH_MIDI

3/ Download my Arduino project file below.
http://www.benbiles.com/sites/default/files/LAUNCHcontrolBB_0.ino

4/ compile / upload to Arduino UNO with Arduino IDE.

5/ connect all usb leads making sure you have the usb hub between the arduino and the LaunchControl

6 /open serial console in arduino IDE and set the baudrate to 115200

press keys and turn knobs on the LaunchControl and you should see the relevent midi values 0-127 for faders

EDIT THE CODE AND GET THE NUMBERS TO DO THINGS FROM THE ARDUINO :) !!!!

the file USBmidi_control_CS4385_DAC initializes the CS4385_DAC and contols the 8 volumes of the DAC's output. I am using digital pin 2 on the arduino to control reset on the DAC. WARNING ! I have not programed any Mutec ( mute ) controls on the DACS startup, so don't blame me if you blow your speakers, ears etc !! The wiring diagram I used I copied from the softeare controlled wiring example in the datasheet. I set the inputs to I2S mode and FS speed to autodetect.

the older file AIC3101_codec_control will inistialise the Codec and output audio coming in from I2S. The Launch control controls volume left and right with knobs 1 & 2. ( this code constantly writes to the 2 volume registers ) the volume register writes are only written on detecting new USBmidi data now in the USBmidi_control_CS4385 code. so you can copy that if you need it. I wont be working on the AIC3101 file..



