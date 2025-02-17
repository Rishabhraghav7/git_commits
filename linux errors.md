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

finally i was able to open chrome 


today i was facing an issue in updating my linux
```
error: GPGME error: No data
error: GPGME error: No data
error: GPGME error: No data
```

faced error like this 
then made a backup of mirror list
```
sudo mv /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak
```
 regenerated pacman key
 ```
sudo rm -rf /etc/pacman.d/gnupg
sudo rm -R /var/lib/pacman/sync
```

run pacman key to re-generate trust roots 
```
sudo pacman-key --init
sudo pacman-key --populate
```
update pacman as usual 

the above was the standard instuction given in the arch community which i have followed then there comes the new one 
```
error: alacritty: signature from "T.J. Townsend <blakkheim@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/alacritty-0.15.1-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: breeze-icons: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/breeze-icons-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: btrfs-progs: signature from "Tobias Powalowski <tpowa@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/btrfs-progs-6.13-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: btrfs-assistant: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/btrfs-assistant-2.1.1-1.4-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: garuda-assistant: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/garuda-assistant-3.0.0-1.1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: garuda-gamer: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/garuda-gamer-1.1.10-1.2-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kconfig: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kconfig-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: knotifications: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/knotifications-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kwindowsystem: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kwindowsystem-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kstatusnotifieritem: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kstatusnotifieritem-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: snapper-tools: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/snapper-tools-1.3.1-1.6-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: garuda-system-maintenance: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/garuda-system-maintenance-3.0.0-2.2-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: garuda-welcome: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/garuda-welcome-2.1.0-1.2-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: karchive: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/karchive-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kguiaddons: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kguiaddons-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: ki18n: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/ki18n-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kcolorscheme: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kcolorscheme-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kcoreaddons: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kcoreaddons-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kwidgetsaddons: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kwidgetsaddons-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kiconthemes: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kiconthemes-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: kirigami: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/kirigami-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: sonnet: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/sonnet-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: qqc2-desktop-style: signature from "Antonio Rojas <arojas@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/qqc2-desktop-style-6.11.0-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: wayland-protocols-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/wayland-protocols-git-1.41.r0.g71da8bd-1-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n]
error: failed to commit transaction (invalid or corrupted package (PGP signature))
Errors occurred, no packages were upgraded.
```

then was solved by 
```
sudo pacman-key --recv-key 3056513887B78AEB --keyserver keyserver.ubuntu.com
sudo pacman-key --lsign-key 3056513887B78AEB
```
taken form 
```
https://aur.chaotic.cx/docs
```

```
sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-keyring.pkg.tar.zst'
sudo pacman -U 'https://cdn-mirror.chaotic.cx/chaotic-aur/chaotic-mirrorlist.pkg.tar.zst'
```
the above 2 lines are will handle the installation of files form chaotic repos

then a normal yay or sudo pacman -Syu was enough