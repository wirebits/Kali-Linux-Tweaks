# nrf52840-Wireshark-Setup-BLE-Sniffer

# Steps
1. Go to official `nRF Connect for Desktop` website from [here](https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop).
2. Click on blue `Downloads` button.
3. Select `Linux (x86)` from `Choose Platform`.
   - There is an `AppImage` file name `nrfconnect-X.X.X-x86_64.AppImage`.
   - `X.X.X` is the version of `nRF Connect for Desktop`.
   - Latest is `5.2.1` but it can be changed in future so keep an eye on it.
4. Simply click on `nrfconnect-5.2.1-x86_64.AppImage` so it download on your system.
5. Open terminal in that folder where it is downloaded.
6. Type the following command to make it executable:
```
chmod 700 nrfconnect-5.2.1-x86_64.AppImage
```
7. Hit Enter.
8. Download `nRF Sniffer for Bluetooth LE` from [here](https://github.com/wirebits/Kali-Linux-Tweaks/releases/download/nRF-Sniffer-for-Bluetooth-LE/nrf_sniffer_for_bluetooth_le_4.1.1.zip).
9. Unzip the file.
10. Now, open `nRF Connect for Desktop` AppImage file by following command:
```
./nrfconnect-5.2.1-x86_64.AppImage
```
11. Wait for sometimes and it is open up.
12. Click on white `Decline` button.
13. Click on blue `Open Quick Start App` button.
14. Click on blue `Download` text to download `SEGGER J-Link` on the system.
    - It open up in a browser.
    - Latest is `V9.36` but it can be changed in future so keep an eye on it.
15. Click on `DEB Installer` in Linux category according to your system architecture.
    - For 32-Bit : `32-Bit DEB Installer`.
    - For 64-Bit : `64-Bit DEB Installer`.
16. Again click on `Download` button.
17. Click on `I accept these Terms of Use` checkbox.
18. Click on `Download Software` button.
19. Open terminal in that folder where it is downloaded.
20. Type the following command to install:
```
sudo dpkg -i JLink_Linux_V936_x86_64.deb
```
21. Enter your password and hit enter.
    - Wait for sometimes and it is successfully installed on your system.
22. Close `nRF Connect for Desktop` and open again by above command in step `10`.
23. Click on `Update` button in `Quick Start`.
    - It ask for update to latest version.
    - Latest is `1.8.0` but it can be changed in future so keep an eye on it.
24. Click on blue `Update to latest version` button.
    - Wait for sometimes and it is updated successfully.
25. Search for `Programmer` and simply install it by click on white `Install` button.
    - Wait for sometimes and it is installed successfully.
26. Close `nRF Connect for Desktop`.
27. Download `nrf-udev` debian file from [here](https://github.com/NordicSemiconductor/nrf-udev/releases/download/v1.0.1/nrf-udev_1.0.1-all.deb).
    - Latest is `1.0.1` but it can be changed in future so keep an eye on it.
28. Open terminal in that folder where it is downloaded.
29. Type the following command to install:
```
sudo dpkg -i nrf-udev_1.0.1-all.deb
```
30. Enter your password and hit enter.
    - Wait for sometimes and it is successfully installed on your system.
31. Open `nRF Connect for Desktop` by above command in step `10`.
32. Open `Programmer`.
33. Now, connect your Development Board to the PC/Laptop and press Reset button once.
34. Click on blue `Select Device` button.
    - It show connected baords as `Open DFU Bootloader`.
35. Select on `Open DFU Bootloader`.
    - It shows partitions on the left side with colour codes.
36. Click on `Add File` button.
    - Then click on `Browse...`.
37. Select proper `.hex` file in `nrf_sniffer_for_bluetooth_le_4.1.1/hex/` folder according to your board as given in following table:

|   Development Kit/Dongle   |             Firmware File Name            |
|:--------------------------:|:-----------------------------------------:|
|     nRF51 DK (PCA10028)    |     sniffer_nrf51dk_nrf51422_4.1.1.hex    |
|     nRF51 DK (PCA10031)    |   sniffer_nrf51dongle_nrf51422_4.1.1.hex  |
|     nRF52 DK (PCA10040)    |     sniffer_nrf52dk_nrf52832_4.1.1.hex    |
|   nRF52840 DK (PCA10056)   |   sniffer_nrf52840dk_nrf52840_4.1.1.hex   |
| nRF52840 Dongle (PCA10059) | sniffer_nrf52840dongle_nrf52840_4.1.1.hex |

38. Turn on `Auto read memory` and `Auto Reset` options.
39. Click on `Write` button.
    - Wait for sometimes and it is successfully flashed on your board.
40. Remove board from the system.
41. Open `WireShark`.
    - It is by default installed on Kali Linux.
42. Click on `Help` and then click on `About WireShark`.
43. Click on `Folders` tab.
44. Go to `Personal Extcap path` and double click on the path.
    - It ask for create path and click on `Create Extcap`.
    - It creates a folder named `extcap`.
45. Now, go to `nrf_sniffer_for_bluetooth_le_4.1.1/extcap/` and select all files and folders.
46. Copy all selected files and folders and paste in the `extcap` folder of `wireshark` folder.
    - Its default location is `/home/<USERNAME>/.local/lib/wireshark/extcap/`.
47. Now open terminal and type the following command to install the requirements:
```
pip3 install -r requirements.txt
```
   - Wait for sometimes and it is successfully installed on your system.
48. Now, type the following command to make `.sh` file executable:
```
chmod 700 nrf_sniffer_ble.sh
```
49. Hit Enter.
50. Now, type the following command to run the nRF Sniffer tool to list available interfaces:
```
./nrf_sniffer_ble.sh --extcap-interfaces
```
51. Hit Enter.
52. Now, go to `Personal Configuration` and double click on the path.
    - It ask for create path and click on `Create`.
    - It creates a folder named `wireshark`.
53. Now, go to `nrf_sniffer_for_bluetooth_le_4.1.1/` and select `Profile_nRF_Sniffer_Bluetooth_LE` folder.
54. Copy selected folder and paste in the `profiles` folder of `wireshark` folder.
    - Its default location is `/home/<USERNAME>/.config/wireshark/profiles/`.
55. Click on `Edit` and then click on `Configuration Profiles...`.
56. Click on `Profile_nRF_Sniffer_Bluetooth_LE` and then click on `OK`.
57. Connect your board to the PC/Laptop.
58. Now, Click on `Capture` and then click on `Refresh Interfaces`.
    - There is a interface name `nRF Sniffer for Bluetooth LE` start showing in list of interfaces.
59. Double click on it and it starts capturing Bluetooth LE packets.
    - The green led starts flickering.
60. Done! Your Development Board is now a BLE Sniffer.
