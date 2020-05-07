# Citrix-Receiver-Installation-script

How to install on ubuntu

## Installing the Package

Download the package from here (scroll down to the “Debian Packages” section).

```
https://www.citrix.com/downloads/citrix-receiver/linux/receiver-for-linux-latest.html
```

Install it.
```
sudo dpkg -i icaclient_13.10.0.20_amd64.deb
```
You can manually install the dependencies and then Citrix:

1. Download the 3 required dependencies from Launchpad (not providing direct links so you can check it's legit):

a. https://launchpad.net/ubuntu/bionic/amd64/libicu60/60.2-3ubuntu3 (libicu60_60.2-3ubuntu3_amd64.deb (7.7 MiB))

b. https://launchpad.net/ubuntu/bionic/amd64/libjavascriptcoregtk-1.0-0/2.4.11-3ubuntu3

(libjavascriptcoregtk-1.0-0_2.4.11-3ubuntu3_amd64.deb (1.8 MiB))

c. https://launchpad.net/ubuntu/cosmic/amd64/libwebkitgtk-1.0-0/2.4.11-3ubuntu3

(libwebkitgtk-1.0-0_2.4.11-3ubuntu3_amd64.deb (7.7 MiB))

 

## Install the files in that order in the terminal

(assuming the files are in the Downloads folder)
```
cd ~/Downloads
sudo dpkg -i libicu60_60.2-3ubuntu3_amd64.deb
sudo dpkg -i libjavascriptcoregtk-1.0-0_2.4.11-3ubuntu3_amd64.deb
sudo dpkg -i libwebkitgtk-1.0-0_2.4.11-3ubuntu3_amd64.deb
sudo dpkg -i icaclient_13.10.0.20_amd64.deb
```
This correctly installs Citrix Workspace. If you then get connection errors when trying to set it up, also implement step 3.

 

## Fix the certificate error.
```
sudo ln -s /usr/share/ca-certificates/mozilla/* /opt/Citrix/ICAClient/keystore/cacerts/
sudo c_rehash /opt/Citrix/ICAClient/keystore/cacerts/
```

