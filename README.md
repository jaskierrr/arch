# arch
commands for arch

# install bspwm

pacman -S bspwm sxhkd picom polybar dmenu alacritty nitrogen lightdm lightdm-gtk-greeter thunar

cd ~/.config/  
mkdir bspwm sxhkd polybar picom  
cp /usr/share/doc/bspwm/examples/bspwmrc bspwm/  
cp /usr/share/doc/bspwm/examples/sxhkdrc sxhkd/  
cp /etc/xdg/picom.conf picom/  
cp /etc/polybar/config.ini polybar/  

chmod +x bspwm/bspwmrc  
systemctl enable lightdm  


nano bspwm/bspwmrc  
#AutoStart apps  
sxhkd &  
picom --config /home/YourUserName/.config/picom/picom.conf &  
nitrogen --restore &  
polybar &  

# all nerd-fonts install
sudo pacman -S $(pacman -Sgq nerd-fonts)

# mediakeys
install playerctl for pipewire  

#Raise volume  
XF86AudioRaiseVolume  
  pactl set-sink-volume @DEFAULT_SINK@ +5%  
 
#Lover volume  
XF86AudioLowerVolume  
  pactl set-sink-volume @DEFAULT_SINK@ -5%  
 
#Mute  
XF86AudioMute  
  pactl set-sink-mute @DEFAULT_SINK@ toggle  
 
#Play  
XF86AudioPlay  
    playerctl play-pause  
 
#Next  
XF86AudioNext  
    playerctl next  
   
#previous  
XF86AudioPrev  
    playerctl previous  
 
#Stop  
XF86AudioStop  
    playerctl stop  
