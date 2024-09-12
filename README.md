# OSWA-ALFA-AWUS036ACH-DriverSetup

### Run this commands to setup the environment ---------------- Type A 
Reference: https://www.youtube.com/watch?v=Yr-8RmoNi70&t=97s


``` bash

#(1) Add the 2 lines below into the file#
sudo gedit /etc/apt/sources.list
deb http://http.kali.org/kali kali-last-snapshot main contrib non-free
deb http://http.kali.org/kali kali-experimental main contrib non-free

#(2) This will update from current kernel to 6.8.11#
sudo apt-get update && sudo apt upgrade
sudo apt install linux-headers-$(uname -r | sed 's,[^-]*-[^-]*-,,')

#(3) Install & unzip the zip folder in this repository in Desktop#
cd /Desktop/8812au-20210629-main
sudo apt-get install bc mokutil build-essential libelf-dev linux-headers-`uname -r`

#(4) Install the driver
sudo ./install-driver.sh

#(5) Select the following choice to finish the installation#
Do you want to edit the driver options file now? (recommended) [Y/n] n
Do you want to apply the new options by rebooting now? (recommended) [Y/n] y

```

### Run this commands to setup the environment ---------------- Type B 
Reference: https://www.youtube.com/watch?v=hEXwOkyYNL0


``` bash

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
