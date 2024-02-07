# OracleOfWar
## Installation Instructions
first install the latest version of rasbian and setup the box etc

then install the audio drivers with steps outlined here

https://learn.adafruit.com/adafruit-speaker-bonnet-for-raspberry-pi/overview

next install espeak for text to speech with 

sudo apt-get install espeak 

and use commands like

sudo espeak -s150 -g10 -a25 -v +f3 "Allied forces successfully incorporated"

to get speach to work

next is jenkins. follow the instructions here, but install java first.

https://www.jenkins.io/doc/book/installing/linux/

had to use this link to set the timeout value on the service to 500 since the RPi was so slow it was timing out

https://unix.stackexchange.com/questions/227017/how-to-change-systemd-service-timeout-value

have to give jenkins passwordless sudo permissions by creating a /etc/sudoers.d/jenkins file and pasting in jenkins ALL=(ALL) NOPASSWD: ALL

