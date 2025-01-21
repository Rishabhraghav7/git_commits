today i have changed my host name from hyenvy-hyperland -> hpenvy-hyprland
i made a mistake by adding an additional e in hyprland while setting up my os
i was suggested to change my hostname in hosts
```
sudo nano /etc/hosts
```
after changing my name, i have rebooted my device and i didn't notice any change in my hostname 
so i surfed for alternate  way and came up with this one 
```
 sudo hostnamectl set-hostname hpenvy-hyprland
```
after reboot , i noticed the change 