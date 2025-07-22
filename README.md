# 🐧 My Terminal Setup on Fedora 42 KDE  

Welcome! This is a summary of how I’ve customized my terminal on **Fedora 42 KDE**, aiming for a balance of productivity, aesthetics, and performance.  

---

## 🖥️ Terminal Emulator: Kitty  

- **[Kitty](https://sw.kovidgoyal.net/kitty/)** — A fast, modern, GPU-accelerated terminal emulator.
- **Theme:** `1984 Orwellian`  
- **Font:** `FiraMono Nerd Font - Regular` *(with Nerd Font symbols for prompt icons)*  
- **Special Settings:**
  - `background_opacity` = `0.8`
  - `background_blur` = `4`

### 📄 Sample configuration (`kitty.conf`):
```conf
# Theme
include themes/1984_Orwellian.conf

# Transparency and blur
background_opacity 0.8
background_blur 4

# Font
font_family FiraMono Nerd Font
```
---
### 🐚 Shell: Zsh + Oh My Zsh
Zsh — A powerful and flexible shell.

Oh My Zsh — A framework for managing Zsh configuration.

### 🔌 Oh My Zsh Plugins
I use a minimal set of plugins to keep shell startup fast:

- git — Git aliases and helpers.
- zsh-autosuggestions — Command suggestions based on history.
- zsh-syntax-highlighting — In-line syntax highlighting.
- history — Enhanced history management.

### 🎨 Shell Theme: Powerlevel10k
Powerlevel10k — A fast, highly customizable theme for Zsh.

Paired with Nerd Fonts for icons and symbols support. 
```
# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
Then enable them in your .zshrc:
```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting history)
```
---
### 🖋️ Font: FiraMono Nerd Font
Download it from Nerd Fonts.

Recommended manual installation into ~/.local/share/fonts and refresh font cache:
```
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/FiraMono.zip
unzip FiraMono.zip -d ~/.local/share/fonts
fc-cache -fv
```
---
### ⚡ Fastfetch Configuration
- Fastfetch — A blazing-fast system information tool written in C, used instead of Neofetch.
  
### 🛠️ config.json
```
{
    "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
    "logo": {
        "source": "/home/santy/.config/fastfetch/ASCII.txt",
        "color": {"1":"white"}
    },
    "modules": [
        {
            "type": "title",
            "key": "User",
            "format": "{user-name}"
        },
        {
            "type": "title",
            "key": "Hostname",
            "format": "{host-name}"
        },
        "separator",
        {
            "type": "host",
            "key": "Model"
        },
        {
            "type": "os",
            "format": "{pretty-name} {version-id} {arch}"
        },
        "kernel",
        "uptime",
        {
            "type": "loadavg",
            "key": "Load Average"
        },
        "processes",
        {
            "type": "wm",
            "key": "Window Manager"
        },
        {
            "type": "de",
            "key": "Desktop Environment"
        },
        "shell",
        {
            "type": "terminal",
            "format": "{pretty-name} {version} {#37}█{#97}█ {#36}█{#96}█ {#35}█{#95}█ {#34}█{#94}█ {#33}█{#93}█ {#32}█{#92}█ {#31}█{#91}█ {#30}█{#90}█"
        },
        {
            "type": "cpu",
            "key": "CPU",
            "format": "{cores-logical} x {name}"
        },
        {
            "type": "gpu",
            "format": "{name}"
        },
        {
            "type": "memory",
            "key": "RAM"
        },
        {
            "type": "disk",
            "key": "Disk",
            "folders": "/"
        },

    ]
}
```
### 🎨 ASCII Art:
you can create your own ACII art based on image with this tool: https://lachlanarthur.github.io/Braille-ASCII-Art/
```
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⠛⠛⠲⢦⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠈⠲⢀⣀⡀⢀⣠⡤⢤⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠴⠖⠀⠀⠀⠀⠀⠀⠀⠀⠉⠛⠆⠀⠘⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢠⠖⠒⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠳⡄⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⢀⢸⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠸⠇⠀⠀⢹⡄⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⣼⠈⡇⠀⠀⠀⠀⠀⠀⠸⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣼⠁⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⢀⡇⠀⠹⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡴⠃⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⢸⠃⠀⠀⠙⠀⠀⣀⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⣀⡴⣋⡤⠖⠚⠙⠓⢤⠀⠀⠀⠀
⠀⢾⠒⠦⣼⠀⠀⠀⢀⢀⡏⠉⠉⠉⠳⣄⣀⠀⠀⢀⡴⢚⡽⠚⠁⣀⠀⠀⠀⠀⠀⠳⡄⠀⠀
⠀⠘⡆⠀⠀⠀⠀⢠⠎⣸⠀⠀⠀⠐⡇⠈⠿⠀⠀⠀⠙⠉⢀⡴⠋⠙⢦⠀⠀⠀⠀⠀⠘⣆⠀
⠀⠀⢻⡀⠀⡤⠴⠋⠀⡇⠀⠀⠀⠀⣧⠀⠀⠀⠀⠀⠀⠀⠩⡀⠀⠀⠈⢳⠀⠀⠀⠀⢀⣘⣆
⠀⠀⠈⣧⠀⢹⡀⠀⢰⠇⠀⠀⠀⠀⢹⡀⠀⠀⠀⠀⠀⠀⠀⠙⣆⠀⠀⠈⢳⡀⣠⣄⢸⡏⠋
⠀⠰⡏⠁⠀⠀⢳⡀⢸⠀⡀⠀⣠⣄⠘⡇⠀⠀⠀⠀⠀⠀⠀⠀⢸⡄⠀⠀⠀⢳⡟⠈⠙⠁⠀
⢀⡤⣽⠀⡤⠤⠞⠁⠘⠟⠹⣴⠃⠈⠙⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠙⠲⠤⠇⠀⠀⠀⠀⠀⠀⢠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢰⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⢀⣀⡀⠀⠀⠀⢠⠇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⢀⡖⠋⠉⠁⠙⣦⠀⠀⡾⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠓⠦⠼⠂⠀⠀⠀⠀⠈⠛⠛⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
```

---
### 📦 Quick Installation Summary
```
> **Note:**  
> If you're using an Ubuntu-based distribution, replace `dnf` with `apt` in the installation commands.

# Install kitty
sudo dnf install kitty

#install git (if u don't have)
sudo dnf install git

# Install zsh and set it as default
sudo dnf install zsh
chsh -s $(which zsh)

# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install Powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

# Set theme in ~/.zshrc
ZSH_THEME="powerlevel10k/powerlevel10k"

# Install fastfetch
sudo dnf install fastfetch
```
---
### 📸 Screenshots

### 🖥️ Fastfetch Output with Custom ASCII  
<img width="989" height="544" alt="image" src="https://github.com/user-attachments/assets/99fbfa4c-69db-4939-a049-8e344d23637e" />

### 🖥️ Running Cmatrix
<img width="989" height="544" alt="image" src="https://github.com/user-attachments/assets/e03b3cc8-82fa-4acc-85d5-289629607dc7" />

### 🖥️ With git init and AutoSuggestion
<img width="989" height="544" alt="image" src="https://github.com/user-attachments/assets/3ad760b2-cd56-4650-97e3-deafd66a49c5" />



