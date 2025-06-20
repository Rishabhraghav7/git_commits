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




Installing a package through aur

i was stuck after executing yay kodelife
since it gave me ,
```
 PKGBUILDs up to date
/home/rishabh/.cache/paru/clone/kodelife/PKGBUILD
# Maintainer: Sol Bekic <s+aur at s-ol dot nu>
# Maintainer: kyrella <kyrella at pm dot me>
pkgname=kodelife
pkgver=1.1.1.175
pkgrel=1
pkgdesc='Real-time GPU shader editor, live-code performance tool and gra>
url='https://hexler.net/software/kodelife'
license=('unknown')
arch=('x86_64')
depends=('alsa-lib' 'libcurl-gnutls' 'gst-plugins-base-libs')
source=("https://hexler.net/pub/kodelife/$pkgname-$pkgver-linux-x64.zip")
sha256sums=('596f43361ea431b040a36ea6519991457f214ff94ae5f62ec9a1abb354a>

package() {
        install -D -m755 "$srcdir/KodeLife" "$pkgdir/usr/bin/KodeLife"
:...skipping...
/home/rishabh/.cache/paru/clone/kodelife/PKGBUILD
# Maintainer: Sol Bekic <s+aur at s-ol dot nu>
# Maintainer: kyrella <kyrella at pm dot me>
pkgname=kodelife
pkgver=1.1.1.175
pkgrel=1
pkgdesc='Real-time GPU shader editor, live-code performance tool and graphics prototyping sketchpad'
url='https://hexler.net/software/kodelife'
license=('unknown')
arch=('x86_64')
depends=('alsa-lib' 'libcurl-gnutls' 'gst-plugins-base-libs')
source=("https://hexler.net/pub/kodelife/$pkgname-$pkgver-linux-x64.zip")
sha256sums=('596f43361ea431b040a36ea6519991457f214ff94ae5f62ec9a1abb354a5f1c0')

package() {
        install -D -m755 "$srcdir/KodeLife" "$pkgdir/usr/bin/KodeLife"
}


~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
```
not sure how to proceed after this

then found a way from https://wiki.archlinux.org/title/Arch_User_Repository

it had the simple ways

git clone {repo-link}

cd {repo-name}

makepkg

pacman -U {file with .zst}

gets it installed


Got this error while updating my system 

```
(119/119) checking keys in keyring                 [---------------] 100%
(119/119) checking package integrity               [---------------] 100%
error: btrfs-assistant: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/btrfs-assistant-2.2-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: garuda-update: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/garuda-update-4.8.8-1-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: google-chrome: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/google-chrome-137.0.7151.119-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: hyprwayland-scanner-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/hyprwayland-scanner-git-0.4.4.r5.gaa38edd-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: wayland-protocols-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/wayland-protocols-git-1.45.r1.g0c79b5c-1-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: grimblast-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/grimblast-git-r132.189f32f-1-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: gtkd: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/gtkd-3.11.0-3-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: hyprpicker-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/hyprpicker-git-0.4.5.r8.gd6a1363-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: lapce-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/lapce-git-0.4.2.r103.ga289ebd-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: lf-git: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/lf-git-35.r22.gb76d254-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: mhwd-nvidia: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/mhwd-nvidia-575.64.1-1-any.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: visual-studio-code-bin: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/visual-studio-code-bin-1.101.1-1-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: zen-browser-bin: signature from "TNE <tne@garudalinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/zen-browser-bin-1.13.2b-3-x86_64.pkg.tar.zst is corrupted (invalid or corrupted package (PGP signature)).
Do you want to delete it? [Y/n] y
error: failed to commit transaction (invalid or corrupted package (PGP signature))
Errors occurred, no packages were upgraded.

```

NOTE  :  a clear of cache of the pacman didn't solve it 

 REASON :1 Outdated or broken `archlinux-keyring` or `garuda-keyring.

		 2. Corrupted local keyring or partial sync.


```
sudo pacman -Sy archlinux-keyring garuda-keyring
```

error faced after the above command 

```
[sudo] password for rishabh:     
:: Synchronizing package databases...
 garuda is up to date
 core is up to date
 extra is up to date
 multilib is up to date
 chaotic-aur           628.9 KiB   345 KiB/s 00:02 [---------------] 100%
warning: archlinux-keyring-20250430.1-1 is up to date -- reinstalling
error: target not found: garuda-keyring
```

```
sudo pacman -Sy archlinux-keyring --noconfirm
```

```
pacman -Ss keyring | grep -i chaotic
```

Look for any of the following:

- `chaotic-keyring`
    
- `garuda-common-settings`
    
- `garuda-system-maintenance`
    

If found:

```
sudo pacman -S chaotic-keyring
```

If All  Fails: Full Keyring Reset
