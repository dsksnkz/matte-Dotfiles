#!/bin/bash

set -e

echo "🚀 Starting Hyprland Rice Installation..."

echo "1. Update system and install core official packages"
echo "📦 Installing core packages from official repositories..."
sudo pacman -Syu --noconfirm
sudo pacman -S --noconfirm btop cava clipse fastfetch helix nwg-displays hyprland blender firefox waybar rofi zed steam helium-browser-bin kitty git xdg-desktop-portal-hyprland nautilus ttf-font-awesome mission-center ttf-cascadia-code-nerd

echo "2. Check for an AUR helper (Yay), and install it if it's missing"
if ! command -v yay &> /dev/null; then
    echo "🔍 Yay not found. Installing yay (AUR Helper)..."
    sudo pacman -S --needed base-devel
    git clone https://aur.archlinux.org/yay.git /tmp/yay
    cd /tmp/yay && makepkg -si --noconfirm
    cd -
fi

echo "3. Install common AUR packages used in Hyprland rices"
echo "📦 Installing AUR packages..."
yay -S --noconfirm hyprshot yazi hyprlock hyprpicker awww pywal-16-colors nwg-displays mortrix-bin waypaper hyprmod
yay -S --noconfirm nvidia-dkms nvidia-utils lib32-nvidia-utils nvidia-settings


echo "4. Ensure the system target directory exists"
mkdir -p ~/.config

echo "5. Copy your configuration files into the system"
echo "📂 Deploying your custom configurations..."
cp -r .config/* ~/.config/

echo "✅ Installation complete! Please log out and select Hyprland at your login screen."
