# Arch Linux Bluetooth Troubleshooting

## Description
This repository provides comprehensive guidance and resources for resolving Bluetooth issues on Arch Linux systems. If you encounter errors such as "No default controller available" or encounter difficulties with Bluetooth functionality, this guide will assist you in resolving them step by step.

## Instructions

### Step 1: Identifying the Problem
```bash
sudo dmesg | grep -i bluetooth
```

### Step 2: Finding the Missing Firmware
```bash
sudo ls /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1a_2_hdr.bin

#This command checks if the necessary firmware file is present.
```

### Step 3: Locating an Alternative Firmware File
```bash
ls ~/linux-firmware/mediatek

#If the firmware file is missing, this command helps you find an alternative one.
```

### Step 4: Copying and Renaming the Firmware File
```bash
sudo cp ~/linux-firmware/mediatek/BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1a_2_hdr.bin

#Copy and rename the firmware file to the correct location.
```
### Step 5: Reloading Bluetooth Modules
```bash
sudo modprobe -r btusb
sudo modprobe btusb
```

### Step 6: Restarting Bluetooth Service
```bash
sudo systemctl restart bluetooth.service
```

### Step 7: Verifying Bluetooth Functionality
```bash
sudo dmesg | grep -i bluetooth
bluetooth scan on
```
###


sudo dmesg | grep -i bluetooth
