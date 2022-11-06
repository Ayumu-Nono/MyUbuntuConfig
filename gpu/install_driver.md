# Install driver

## GPU確認

```
$ lspci | grep -i radeon
```

## ドライバーをインストール

OSバージョンを確認して、
```
ayumu@pheasant:~$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 22.04.1 LTS
Release:	22.04
Codename:	jammy
```

ここから
[https://www.amd.com/ja/support/graphics/radeon-500-series/radeon-rx-500-series/radeon-rx-550](https://www.amd.com/ja/support/graphics/radeon-500-series/radeon-rx-500-series/radeon-rx-550)
該当するバージョンをダウンロード

インストール
```
$ sudo dpkg -i amdgpu-install_22.20.50200-1_all.deb
```

