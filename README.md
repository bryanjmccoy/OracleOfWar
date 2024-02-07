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

install printer drivers using 

sudo apt-get update
sudo apt-get install git cups wiringpi build-essential libcups2-dev libcupsimage2-dev

and then

cd
git clone https://github.com/adafruit/zj-58
cd zj-58
make
sudo ./install

then run 
sudo lpadmin -p ZJ-58 -E -v serial:/dev/usb/lp0?baud=9600 -m zjiang/ZJ-58.ppd
sudo lpoptions -d ZJ-58

next install enscript with

sudo apt install enscript

and install lpr with

sudo apt install cups-bsd

setup the new media type in the /etc/enscript.cfg file

finally test using

sudo echo "Lure iron juggernaut onto weak floor inside Hounds of Barrakas." |enscript -d ZJ-58 -fCourier24 -M ZJ -r -B
