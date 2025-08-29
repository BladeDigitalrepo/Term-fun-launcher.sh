```markdown
# Term-fun-launcher.sh

## Overview

A fun terminal launcher for Termux that provides quick access to visual and system tools!

## Installation

1. **Download the script:**
   ```sh
   curl -O https://raw.githubusercontent.com/BladeDigitalrepo/Term-fun-launcher.sh/main/term-fun-launcher.sh
   ```

2. **Make it executable:**
   ```sh
   chmod +x term-fun-launcher.sh
   ```

3. **Run the installer to set up all dependencies and the launcher:**
   ```sh
   ./term-fun-launcher.sh --install
   ```

4. **Start the launcher:**
   ```sh
   ./term-fun-launcher.sh
   ```

## Script

```bash
#!/data/data/com.termux/files/usr/bin/bash
# Terminal Fun Launcher 🎉

install() {
    echo "Updating package list and installing dependencies..."
    pkg update -y && pkg install -y cmatrix sl libcaca neofetch figlet toilet htop
    echo "All dependencies installed!"
    exit 0
}

if [[ "$1" == "--install" ]]; then
    install
fi

while true; do
    clear
    echo "==============================="
    echo "     🎮 Terminal Fun Menu 🎮"
    echo "==============================="
    echo "1) Matrix (cmatrix)"
    echo "2) Steam Train (sl)"
    echo "3) Terminal Fire (cacafire)"
    echo "4) System Info (neofetch)"
    echo "5) ASCII Art (figlet + toilet)"
    echo "6) Task Manager (htop)"
    echo "0) Exit"
    echo "-------------------------------"
    read -p "Choose an option [0-6]: " choice

    case $choice in
        1)
            cmatrix
            ;;
        2)
            sl
            ;;
        3)
            cacafire
            ;;
        4)
            neofetch
            read -p "Press enter to return to menu..."
            ;;
        5)
            read -p "Enter text for ASCII art: " art
            figlet "$art"
            toilet -f mono12 -F metal "$art"
            read -p "Press enter to return to menu..."
            ;;
        6)
            htop
            ;;
        0)
            echo "Goodbye!"
            exit 0
            ;;
        *)
            echo "Invalid option."
            sleep 1
            ;;
    esac
done
```

## Optional: Add to PATH

For easier access, move the script to a directory in your `PATH`:
```sh
mv term-fun-launcher.sh $PREFIX/bin/term-fun-launcher
chmod +x $PREFIX/bin/term-fun-launcher
```
Now launch it anytime with:
```sh
term-fun-launcher
```
```
