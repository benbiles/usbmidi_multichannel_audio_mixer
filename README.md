# novation_launchcontrol_usbmidi_arduino
arduino novation launchcontrol usb midi usbhost

tInstructions to hook up an arduino to Novation LaunchControl and get midi messages into your arduino.

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


the file AIC3101_codec_control will inistialise the Codec and output audio coming in from I2S. The Launch control controls volume left and right with knobs 1 & 2

I will be working next on an 8 channel mixer DAC for 8 channel mix control.

