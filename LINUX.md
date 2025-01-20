man {mannual}
```
man ls
man git
```

tdlr  {gist of command  }
```
tdlr ls
tdlr git
```
update
```
yay
sudo pacman -Syu
```
update type-2

```
garuda-update
```
update time , date (update as the network conned)
`sudo timedatectl set-ntp true

lock terminal
```
vlock
```
swaylock
--e{dont validate when provided empty}
```
swaylock --e
```
waylock
```
waylock
```

{lock secreen with a viewable interface}
```
gtklock
```
delete an application

R{remove}
c{config}
n{dependencies}
s{unwanted dependencies for the package}
```
yay -Rcns
```


	alt+ctrl+f3(tty terminal)

paste

when removed -o it copies to clipboard
```
xclip -selection clipboard -o

echo "Hello, World!" | xclip -selection clipboard
```
```
xsel --clipboard --output
```

poweroff
```
systemctl poweroff
sudo poweroff
sudo init 0
```
 creating a shortcut for linux command
 use alias
 let me build a short cut for directing to Documents folder
 ```
 alias docs="cd ~/Documents"
```
now when entered with docs it literally executes the cd Documents command

but this is a temporary change
once you start a new terminal / terminal emulator it doesn't have the changes saved
