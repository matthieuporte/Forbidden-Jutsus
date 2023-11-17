

INTERNET
list internet points : sudo iw dev wlp2s0 scan | less

I3
/usr/bin/blurlock
~/.local/bin/rofi-power-menu

DOUBLE SCREEN
xrandr --output eDP-1 --auto --output HDMI-1 --auto --left-of eDP-1
xrandr --output eDP-1 --auto --output HDMI-1 --auto -o left --left-of eDP-1
xrandr -s 0
aliases : setup / setupl

WALLPAPER
feh --no-fehbg --bg-fill '/home/matthiru/Pictures/wallpapers/mandelbrot.png'
/usr/bin/wallpaper

TAILWIND
npx tailwindcss -i ./src/style/input.css -o ./dist/output.css --watch

FLY.IO
```
export FLYCTL_INSTALL="/home/matthiru/.fly";export PATH="$FLYCTL_INSTALL/bin:$PATH"
```

JEKYLL
```
export GEM_HOME="$(ruby -e 'puts Gem.user_dir')"
export PATH="$PATH:$GEM_HOME/bin"
gem list
gem update

bundle exec jekyll serve --livereload
```

REMOVE SPACES FROM FILES
```
find . -type f -name "* *.xml" -exec bash -c 'mv "$0" "${0// /_}"' {} \;
REMOVE SUBSTRING FROM FILE
for file in *; do mv "${file}" "${file//\SUBSTRING/}"; done
```

GIT
```
git checkout -b NAME
git ls-tree -r --name-only HEAD | tree --fromfile
tree . -I 'obj|bin|.idea|.git' -a
```

POSTGRESQL
sudo systemctl start postgresql
sudo systemctl enable postgresql
sudo systemctl status postgresql
su - postgres
psql


BLUETOOTH
systemctl start bluetooth.service
pulseaudio -k
bluetoothctl
-> power on
-> agent on
-> default-agent
-> scan on
-> pair [mac adress]
-> connect [mac adress]
set device as active in pavucontrol

COMMANDS
history
neofetch
xdg-open
setxkbmap