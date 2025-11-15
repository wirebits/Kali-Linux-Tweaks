# Install Arduino 2.X.X on Kali Linux

# Steps
1. Download latest `.AppImage` file of Arduini IDE for Linux according to your architecture from [here](https://www.arduino.cc/en/software/).
   - Latest version is `2.3.6` but it can be changed in future so keep an eye on it.
   - It is only for `64-bit` architecture.
2. Make the `.AppImage` file executable:
```
chmod +x arduino-ide_2.3.6_Linux_64bit.AppImage
```
3. Create a directory inside /opt directory:
```
sudo mkdir -p /opt/arduino-ide
```
4. Move the `.AppImage` file in that dierectory:
```
sudo mv arduino-ide_2.3.6_Linux_64bit.AppImage /opt/arduino-ide/
```
5. Create a desktop entry:
```
sudo nano /usr/share/applications/arduino-ide.desktop
```
6. Paste this entry and save:
```
[Desktop Entry]
Name=Arduino IDE
Exec=/opt/arduino-ide/arduino-ide_2.3.6_Linux_64bit.AppImage
Icon=arduino
Type=Application
Categories=Development;Electronics;
StartupNotify=true
```
7. Add user to dialout group
```
sudo usermod -aG dialout $USER
```
8. Reboot the system
```
sudo reboot
```
9. Now, Arduino IDE is accessible from anywhere in the system.
