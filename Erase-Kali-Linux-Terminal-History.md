# Erase-Kali-Linux-Terminal-History

# There are `2` ways : 
## Way - 1
1. Open Terminal.
2. Copy and paste the following command:
```
echo -n > ~/.zsh_history && fc -p ~/.zsh_history && exec zsh -c "clear; zsh"
```
3. Hit Enter.
4. Done!

## Way - 2
1. Open Terminal.
2. Open `.zshrc` file using any text editor.
3. At the bottom of the file, copy and paste the following command:
```
alias wipe='echo -n > ~/.zsh_history && fc -p ~/.zsh_history && exec zsh -c "clear; zsh"'
```
4. Save the file and exit.
5. Close the terminal and open again.
6. When type `wipe` in the terminal, the following command executes.
7. Done!