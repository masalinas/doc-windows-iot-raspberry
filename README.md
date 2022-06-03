## Description
Documentation Widows Iot Raspberry

## Flow steps

- **Step01**: Download [Windows IoT Core Edition for Raspberry Pi 2/3](https://go.microsoft.com/fwlink/?LinkId=846058) from microsoft

- **Step02**: Install 7x tool to unzip iso and msi files
```shell
sudo apt-get install p7zip-full
```

- **Step03**: Unzip iso file
```shell
7z x 17763.107.181026-1406.rs5_release_svc_prod2_amd64fre_IOTCORE_RPi.iso
```

- **Step04**: Unzip msi file
```shell
7z x Windows_10_IoT_Core_for_RPi2.msi
```

- **Step05**: Download ffu2img tool to create img from msi file
```shell
git clone https://github.com/t0x0/random.git
```

- **Step06**: Create img file to burn Raspberry Pi SD card
```shell
python3 ffu2img.py3 fil2dda957cfdb079d52c8f284117ff4a0b rpi.img
```

- **Step07**: Introduce SD card and check dev file
```shell
lsblk
```

- **Step08**: Burn img file in the SD card and sync
```shell
sudo dd if=rpi.img of=/dev/mmcblk0
sudo sync
```
