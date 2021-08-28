# Keyboard Config

## Map

[https://qiita.com/macinjoke/items/746c0c0adb74cfdeb9e7](https://qiita.com/macinjoke/items/746c0c0adb74cfdeb9e7)

- `$ xmodmap -pke`: Show map

```terminal
$ xmodmap
xmodmap:  up to 4 keys per modifier, (keycodes in parentheses):

shift       Shift_L (0x32),  Shift_R (0x3e)
lock        Eisu_toggle (0x42)
control     Control_L (0x25),  Control_R (0x69)
mod1        Alt_L (0x40),  Alt_R (0x6c),  Meta_L (0xcd)
mod2        Num_Lock (0x4d)
mod3      
mod4        Super_L (0x85),  Super_R (0x86),  Super_L (0xce),  Hyper_L (0xcf)
mod5        ISO_Level3_Shift (0x5c),  Mode_switch (0xcb)
```

- `$ xmodmap .Xmodmap`: Apply
- `$ xmodmap .Xmodmap_default`: Reset
- `~/.bashrc`に`xmodmap /home/ayumu/Documents/MyUbuntuConfig/keyboard/.Xmodmap`を追加