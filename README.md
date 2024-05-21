== Arch Linux Bluetooth Troubleshooting ==

== Description ==
This repository contains instructions and resources for troubleshooting Bluetooth issues on Arch Linux systems. If you encounter errors like "No default controller available" or face difficulties with Bluetooth functionality, this guide will help you resolve them step by step.

== Instructions ==

=== Step 1: Identifying the Problem ===
sudo dmesg | grep -i bluetooth

=== Step 2: Finding the Missing Firmware ===
ls /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1a_2_hdr.bin

=== Step 3: Locating an Alternative Firmware File ===
ls ~/linux-firmware/mediatek

=== Step 4: Copying and Renaming the Firmware File ===
sudo cp ~/linux-firmware/mediatek/BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1a_2_hdr.bin

=== Step 5: Reloading Bluetooth Modules ===
sudo modprobe -r btusb
sudo modprobe btusb

=== Step 6: Restarting Bluetooth Service ===
sudo systemctl restart bluetooth.service

=== Step 7: Verifying Bluetooth Functionality ===
sudo dmesg | grep -i bluetooth
bluetoothctl scan on

=== Step 8: Additional Debugging Steps (if Necessary) ===
Follow further troubleshooting steps and additional actions if the issue persists.

== Contributing ==
Contributions to improve this guide are welcome! If you have additional tips or solutions for Bluetooth troubleshooting on Arch Linux, feel free to open a pull request.

== License ==
This repository and its contents are licensed under the MIT License.
