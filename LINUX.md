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

surf the internet with terminal
using duckduckgo search engine
```
ddgr "term to search "
```
i have installed it through paru this time

paru and yay are both AUR helpers which runs pacman (package manager) commands

paru is developed in rust while yay in go

another one to surf
its surfraw
installation
```
paru -S surfraw
```
```
surfraw S-engine "query"

surfraw google "linux tips"
```


```
animations {
    enabled = true

   

    bezier = myBezier, 0.05, 0.9, 0.1, 1.05

    animation = windows, 1, 7, myBezier
    animation = windowsOut, 1, 7, default, popin 80%
    animation = border, 1, 10, default
    animation = fade, 1, 7, default
    animation = workspaces, 1, 6, default
}
```

change permission to user 
```
sudo chown rishabh  animations.conf
```
