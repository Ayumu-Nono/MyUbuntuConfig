# Display

ディスプレイそれぞれで倍率を設定できるようにする。

```
$ gsettings set org.gnome.mutter experimental-features "['scale-monitor-framebuffer']"
$ gsettings set org.gnome.mutter experimental-features "['x11-randr-fractional-scaling']"
```

リセットする

```
$ gsettings reset org.gnome.mutter experimental-features
```