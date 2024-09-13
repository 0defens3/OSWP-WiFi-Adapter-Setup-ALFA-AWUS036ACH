# OSWA Wifi Adapter Setup (ALFA-AWUS036ACH)

### Commands To Be Executed In Sequence 
Reference: https://www.youtube.com/watch?v=hEXwOkyYNL0

### Environment:
[a] Running on VirtualBox with Kali Linux OS <br />
[b] Settings > USB > Checked 'Enable USB Controller' > Checked 'USB 3.0'<br />
[c] Once VM boots up, navigate: Devices > USB > Select the Wifi Adapter to simulate attaching it <br />

``` bash

#(1) Add the 2 lines below into the file#
sudo gedit /etc/apt/sources.list
deb http://http.kali.org/kali kali-last-snapshot main contrib non-free
deb http://http.kali.org/kali kali-experimental main contrib non-free

#(2) Upgrading Current Kernel To 6.8.11
sudo apt update
sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt install linux-headers-$(uname -r | sed 's,[^-]*-[^-]*-,,')
sudo reboot now

#(3) Installing Necessary Drivers 
sudo apt update
sudo apt install realtek-rtl88xxau-dkms
sudo apt install dkms

#(4) Installing Latest Drivers 
git clone https://github.com/aircrack-ng/rtl8812au
cd rtl8812au/
sudo make
sudo make install

#(5) Reboot The VM
#(6) Disconnect & Connect the Wifi Adapter & Wait - Now should be reflected 
iwconfig

#(6) Test If It Is Working! - This should be running normally
sudo wifite

```
### Once Completed:
Please remember to shut down the machine and create a snapshot to be able to revert changes anytime. 









