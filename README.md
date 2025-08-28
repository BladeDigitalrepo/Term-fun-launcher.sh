# Term-fun-launcher.git
pkg update -y && pkg install -y cmatrix sl libcaca neofetch figlet toilet htop

#!/data/data/com.termux/files/usr/bin/bash
# Terminal Fun Launcher 🎉

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
