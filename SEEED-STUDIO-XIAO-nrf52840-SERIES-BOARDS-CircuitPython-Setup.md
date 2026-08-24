# Seeed-Studio-XIAO-nrf52840-Series-Boards-CircuitPython-Setup

>[!NOTE]
>It is highly recommend to setup on Linux Machine.

# Steps
1. Connect `Seeed Studio XIAO nrf52840` Series Board to your computer via a USB data-transfer supported cable.
2. Double click on `RST` button rapidly to make board in Bootloader Mode.
   - It is shown as a mass storage device named `XIAO-SENSE`.
3. Download latest bootloader `.zip` file from [here](https://github.com/adafruit/Adafruit_nRF52_Bootloader/releases).
   - Latest version is `0.11.0`.
   - Keep an eye on it for latest versions.
4. Download `adafruit-nrfutil` by enter the following command in terminal:
```
pip3 install adafruit-nrfutil --break-system-packages
```
5. Open terminal in that folder where the bootloader `.zip` file is downloaded.
6. Type the following command to burn latest bootloader on board:
```
adafruit-nrfutil --verbose dfu serial --package file_name.zip -p PORT -b 115200 --singlebank --touch 1200
```
   - Replace `file_name.zip` with actual file name.
   - To get port number of board, run `ls /dev/ttyUSB*` or `ls /dev/ttyACM*`.
   - Replace `PORT` with actual port number.
7. Hit Enter.
   - Wait for sometime to burn.
   - After that, it is shown as a mass storage device named `XIAO-SENSE`.
8. Download latest CircuitPython `.uf2` file for `Seeed Studio XIAO nrf52840 BLE Sense` from [here](https://circuitpython.org/board/Seeed_XIAO_nRF52840_Sense/).
   - Download `.uf2` file for `Seeed Studio XIAO nrf52840` only from [here]().
9. Copy the `.uf2` file on `Seeed Studio XIAO nrf52840` or `Seeed Studio XIAO nrf52840 BLE Sense` board.
   - When it is copied successfully, the device is disconnected and reconnect as mass storage device named `CIRCUITPY`.
10. Done! `Seeed Studio XIAO nrf52840` or `Seeed Studio XIAO nrf52840 BLE Sense` is flash successfully with latest circuitpython firmware and last bootloader.