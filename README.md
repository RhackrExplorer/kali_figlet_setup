## How to Customize Kali Linux Terminal Like Hacker?

Welcome to our GitHub repository itsdk109 dedicated to customizing the Kali Linux terminal! Here, you'll find a comprehensive guide on how to personalize your terminal using Oh My Zsh, a powerful framework for managing Zsh configurations.

### 1. ** Open Terminal Prompt & Update and install figlet lolcat package**

```bash
sudo apt update
sudo apt install lolcat 
```

### 2. **After the terminal opens, type `nano ~/.zshrc` or `nano ~/.bashrc` and press enter.**

```bash
nano ~/.zshrc
```
or 

```bash
nano ~/.bashrc
```

### 3. **Copy the code provided below and paste it at the end of the opened file `~/.zshrc` or `~/.bashrc`.**
```bash

# Function to center text
center_text() {
    local term_width
    local padding
    local text="$1"

    term_width=$(tput cols)
    padding=$(( (term_width - ${#text}) / 2 ))

    printf "%*s%s\n" "$padding" "" "$text"
}

# Custom banner message for new terminals
if [ -n "$PS1" ]; then
    figlet -w 100 -c "your terminal banner name" | lolcat
    center_text "<<< your favorite quotes >>>" | lolcat
fi

# Redefine the clear command to show the banner and quote after clearing the screen
clear() {
    command clear
    if [ -n "$PS1" ]; then
        figlet -w 100 -c "your terminal banner name" | lolcat
        center_text "<<< your favorite quotes >>>" | lolcat
    fi
}

```

### Final Step:  Restart the Terminal 

```bash
source ~/.zshrc
```
or

```bash
source ~/.bashrc
```

Is snapshot ko follow karke aap apne Kali Linux terminal ko professional aur stylish bana sakte hain. Enjoy karein apne naye customized terminal ka look!.
