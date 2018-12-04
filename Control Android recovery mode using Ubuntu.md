# Como instalar o ADB e Fastboot no Ubuntu, Debian e derivados

## Control Android recovery mode using Ubuntu

sudo apt-get install android-tools-adb android-tools-fastboot
sudo apt install android-tools-adb android-tools-fastboot
sudo apt-get -y install libqtgui4 libqt4-network libqt4-declarative
sudo apt-get install ntfs-config

adb version
adb --version
fastboot --version

adb reboot recovery  
adb reboot bootloader
fastboot oem unlock

adb devices

fastboot devices  

fastboot oem unlock

## root
- fastboot boot image/CF-Auto-Root-hammerhead-hammerhead-nexus5.img

### install imagens
- fastboot flash boot boot.img
- fastboot flash recovery <RECOVERY>.img
- fastboot flash recovery twrp-3.2.3-0-flounder.img
- fastboot flash recovery recovery.img


### usb outros
- mkdir --parent $HOME/.android
- wget -O $HOME/.android/adb_usb.ini https://raw.githubusercontent.com/NicolasBernaerts/ubuntu-scripts/master/android/adb_usb.ini
- lsusb
- adb shell busybox ls -l -a

### CÓDIGO PARA RECUPERAR

- fastboot oem fb_mode_clear
- fastboot reboot

### opçoes
- adb forward --list
- adb connect
- adb host-features
- List of devices attached 
- fastboot oem get_identifier_token
- sudo adb start-server
### ----------------------------------
- fastboot erase system -w
- fastboot erase boot
- fastboot update superawesomerom.zip
- fastboot reboot
- fastboot erase system
- fastboot erase data
- fastboot erase cache
- fastboot erase system -w

#### To restart adb with libusb and check that it worked, use
- adb kill-server; ADB_LIBUSB=1 adb start-server; adb host-features

### permissao
- sudo adb kill-server
- sudo adb start-server

``
fastboot:

    Improve output format, add a verbose output mode (-v).
    Clean up help output.
    Add product.img and odm.img to the list of partitions flashed by fastboot flashall.
    Avoid bricking new devices when using a too-old version of fastboot by allowing factory image packages to require support for specific partitions.

``

## QtADB requires :
- sudo apt-get -y install libqtgui4 libqt4-network libqt4-declarative
- wget -O qtadb.tar.gz http://motyczko.pl/qtadb/QtADB_0.8.1_linux64.tar.gz
- tar -xvf qtadb.tar.gz
- sudo mv ./QtADB*/QtADB /usr/local/sbin/qtadb
- sudo chmod +x /usr/local/sbin/qtadb
- rm qtadb.tar.gz
- rm -R QtADB*
- qtadb

### icone

qtadb.desktop
-------------
[Desktop Entry]
Encoding=UTF-8
Name=QtADB
Exec=qtadb
Icon=qtadb
Type=Application
Categories=Utility;

### drives
- https://github.com/neurobin/MT7630E/archive/release.zip
- cd ~/Downloads/MT7630E-release 
- sudo chmod +x install
- sudo ./install
- sudo apt-get install libusb-dev

### How To Install SPFlashTool In LInux
 - bionic
- sudo add-apt-repository ppa:torik-habib/bionic
- sudo apt-get update
- sudo apt install spflashtool
 - xenial 
- PPA SPFlashtool x64 x86 
- sudo add-apt-repository ppa:torik-habib/multimedia 
- sudo apt-get update 
- sudo apt install spflashtool
sudo adduser "user_pc" dialout 
example : sudo adduser hp dialout 
sudo reboot

### Developers
- https://developer.android.com/studio/releases/platform-tools
- https://mariano.eng.br/android-instalacao-cyanogenmod-atraves-ubuntu-linux-nexus/
- https://www.youtube.com/watch?v=sOmvL15npiw
- https://www.youtube.com/watch?v=maLWScgXflk
- https://mega.nz/#!9M8HTLAA!Z8gIeYCOKElbPHh-6kf5_JNIlZMQeW9AHsymAOLxC9o

## Renato de O. Lucena
- 11/2018
