# OSWA-ALFA-AWUS036ACH-DriverSetup

### Run this commands to setup the environment ---------------- Type A 
Reference: https://www.youtube.com/watch?v=Yr-8RmoNi70&t=97s


``` bash

#(1) Upgrading The Kali System - 6.8.11
sudo apt update
sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt install linux-headers-$(uname -r | sed 's,[^-]*-[^-]*-,,')
sudo reboot now

#(2) Installing Necessary Drivers 
sudo apt update
sudo apt install realtek-rtl88xxau-dkms
sudo apt install dkms

git clone https://github.com/aircrack-ng/rtl8812au
cd rtl8812au/
sudo make
sudo make install
lsusb
iwconfig

!To test:
sudo wifite

```

### Run this commands to setup the environment ---------------- Type B 
Reference: https://www.youtube.com/watch?v=hEXwOkyYNL0


``` bash

Environment:
[a] Settings > USB > Checked 'Enable USB Controller' > Checked 'USB 2.0'
[b] Once VM boots up, navigate Devices > USB > Select the Wifi Adapter to simulate attaching it 


#(1) Add the 2 lines below into the file#
sudo gedit /etc/apt/sources.list
deb http://http.kali.org/kali kali-last-snapshot main contrib non-free
deb http://http.kali.org/kali kali-experimental main contrib non-free

#(2) This will update from current kernel to 6.8.11#
sudo apt-get update && sudo apt upgrade


#(3) Install & unzip the zip folder in this repository in Desktop#
sudo apt install realtek-rtl88xxau-dkms
sudo apt install dkms

#(4) To test if it shows up. It it doesnt = previous drivers dont work with the current adapter#
iwconfig

#(5) Get the latest drivers from github
git clone https://github.com/aircrack-ng/rtl8812au
cd rtl8812au/
make
sudo make install

#(6) Plug out and plug in back the USB adapter from the computer 

#(7) To test if it shows up. This time should show up!#
iwconfig

```









