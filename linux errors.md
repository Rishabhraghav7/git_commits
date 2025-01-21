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
after reboot , i noticed the change in my hostname 

then , i encounterd few errors 
starting with chrome

```

3791:3791:0322/163756.740493:ERROR:process_singleton_(3234)] The profile appears to be in use by another Chrome process (3234) on another computer (hyenvy-hyperland). Chrome has locked the profile so that it doesn't get corrupted. If you are sure no other processes are using this profile, you can unlock the profile and relaunch Chrome.
[3791:3791:0322/163756.740534:ERROR:message_box_dialog.cc(146)] Unable to show a dialog outside the UI thread message loop: Chrome - The profile appears to be in use by another Chrome process (3234) on another computer (hyenvy-hyperland). Chrome has locked the profile so that it doesn't get corrupted. If you are sure no other processes are using this profile, you can unlock the profile and relaunch Chrome
```
when i surfed the internet again i noticed a similar issue in 
```
https://bbs.archlinux.org/viewtopic.php?id=294107
```

i then noticed i dont have a chromium directory instread i had 

lrwxrwxrwx    - rishabh 21 Jan 16:52  google-chrome -> /run/user/1000/psd/rishabh-google-chrome

then after running 
```
ls -l /run/user/1000/psd/rishabh-google-chrome
```
i was able to detect the SingletonLock which caused the error then removed it by 
```
 sudo rm /run/user/1000/psd/rishabh-google-chrome/SingletonLockSingletonLock 

```
i additionally removed SingletonCookie , SingletonSocket along with it which are related to SingletonLock 

finally i was able to open chrome s