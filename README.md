# OSWA-ALFA-AWUS036ACH-DriverSetup

### Run this commands to setup the environment 

Download the repository and start the docker with the APs, the clients and nzyme for alerts. 

``` bash
sudo gedit /etc/apt/sources.list

**add the 2 lines below into the file** 
deb http://http.kali.org/kali kali-last-snapshot main contrib non-free
deb http://http.kali.org/kali kali-experimental main contrib non-free

**This will update from current kernel to 6.8.11***
sudo apt-get update && sudo apt upgrade
sudo apt install linux-headers-$(uname -r | sed 's,[^-]*-[^-]*-,,')
```
