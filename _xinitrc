#! /bin/sh

# locale
export LANG=zh_CN.UTF-8
export LC_ALL="zh_CN.UTF-8"

# xinitrc.d
if [ -d /etc/X11/xinit/xinitrc.d ]; then
    for f in /etc/X11/xinit/xinitrc.d/*; do
        [ -x "$f" ] && . "$f"
    done
    unset f
fi

# Xresources
[[ -f ~/.Xresources ]] && xrdb -merge ~/.Xresources

# ime
export GTK_IM_MODULE=ibus
export XMODIFIERS=@im=ibus
export QT_IM_MODULE=ibus
ibus-daemon -x -d

# goagent
python2 /home/pright/utils/goagent/local/proxy.py &> /dev/null &

# volume icon
volumeicon &

# dropbox
dropboxd &

# rainlendar
rainlendar &

# clipit
clipit &

# batterymon 
#batterymon &

# awesome
exec awesome
