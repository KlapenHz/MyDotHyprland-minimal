# MyDotHyprland-minimal

Minimal installation includes:
- Hyprland,
- waybar,
- wofi

Install packages:  
hyprland  
mako - notification daemon  
pipewire - multimedia framework for audio and screensharing  
wireplumber - session and policy manager for pipewire  
pulseaudio
pulseaudio-bluetooth  
pavucontrol  
xdg-desktop-portal-hyprland - An XDG Desktop Portal (later called XDP) is a program  
that lets other applications communicate swiftly with the compositor through D-Bus.
waybar - status bar

Optional:
sof-firmware - additional drivers   # For example if we don't see sound card  
                                    # with command: `pacmd list-cards`

pacman -S ...

Copy the files to ~/.config/hypr/

Setting display resolution if needed:

Check displays:
hyprctl monitors

If you need to change frequency:
cat /sys/class/drm/card<NUMBER>-<interface>/modes

More dailed information:
sudo pacman -S read-edid

cat /sys/class/drm/card<NUMBER>-<interface>/edid |parse-edid 

Change in: ~/.config/hypr/hyprland.conf 
for example from:
monitor=,preferred,auto,auto
to:
# monitor = name, resolution position, scale
monitor = DP-2,     2560x1440@144, 0x0,    1
monitor = HDMI-A-1, 1920x1080@144, 2560x0, 1
# workspace = name, number
workspace = DP-2,     1
workspace = HDMI-A-1, 2

# Waybar

Fonts installation:
sudo pacman -S ttf-font-awesome

Copy files to ~/.config/waybar/

Run manually:
type waybar

Stopping waybar:
killall waybar

Waybar only on one monitor
Add to the config:
"output": "eDP-1",
