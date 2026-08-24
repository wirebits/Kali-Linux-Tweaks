# esp-idf Setup

>[!NOTE]
>It is highly recommend to setup on Linux Machine.

# Steps
1. Update and Upgrade the Linux System
```
sudo apt update && sudo apt full-upgrade -y
```
2. Clone ESP-IDF your required version:
```
git clone --recursive --branch vX.X.X https://github.com/espressif/esp-idf.git
```
- X.X.X is the version.
- In my case, it is `5.5.1`.
- Wait for sometime to complete.
3. Go to `esp-idf` directory
```
cd esp-idf
```
4. Make `export.sh` executable
```
chmod +x export.sh
```
5. Run the `.sh` file
```
./install.sh
```
- Wait for sometime to complete.
6. Run the following command
```
. ./export.sh
```
7. Check your Shell
```
echo $SHELL
```
- It show either `/usr/bin/bash` or `/usr/bin/zsh` mostly.
8. Open `.bashrc` or `.zshrc` file using Nano with sudo.
```
sudo nano ~/.bashrc
```
```
sudo nano ~/.zshrc
```
9. Add the following line at the end of the file: 
```
alias idf='. $HOME/esp-idf/export.sh'
export IDF_PATH='$HOME/esp-idf'
```
10. Save and close the file.
11. Restart your system.
12. Done! esp-idf is successfully installed on your system.
- Open terminal in your project and just type `idf` abd hit enter.
- After that, idf is active in your project terminal.