# hd_rpi_zero

rpi_install

 - copy to boot follder,  "ssh" and "wpa_supplicant.conf"
 - ssh login ID = pi , pwd = raspberry

rpi disk speed test

  - sudo hdparm -Tt /dev/nvme0n1p1

rpi download command

 - sudo adb reboot loader

 - 
 
 #!/bin/bash

IMAGE_DIR=./
RKTOOL=./rkdeveloptool

sudo ./rkdeveloptool db ./MiniLoaderAll.bin 
sudo ./rkdeveloptool ef
#sudo ./rkdeveloptool rd 
sudo ./rkdeveloptool gpt ./parameter.txt 
sudo ./rkdeveloptool prm ./parameter.txt 
sudo ./rkdeveloptool ppt
echo "u-boot upload..."
sudo ./rkdeveloptool wlx uboot ./uboot.img 
echo "misc upload..."
sudo ./rkdeveloptool wlx misc ./misc.img 
echo "dtbo upload..."
sudo ./rkdeveloptool wlx dtbo ./dtbo.img 
echo "vbmeta upload..."
sudo ./rkdeveloptool wlx vbmeta ./vbmeta.img 
echo "boot upload..."
sudo ./rkdeveloptool wlx boot ./boot.img 
echo "recovery upload..."
sudo ./rkdeveloptool wlx recovery ./recovery.img 
echo "super upload..."
sudo ./rkdeveloptool wlx super ./super.img 
echo "loader upload..."
sudo ./rkdeveloptool ul ./MiniLoaderAll.bin 
sleep 1
sudo ./rkdeveloptool rd 
sleep 1