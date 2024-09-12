# OSWA-ALFA-AWUS036ACH-DriverSetup

### Run this commands to setup the environment 
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
