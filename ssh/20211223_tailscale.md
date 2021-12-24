# TailScaleを使ってみる

参考-->[Tailscaleを使って自宅Minecraft鯖を立てた話](https://zenn.dev/k1ch/articles/d671d44768cc73)

## 状況

LAN内でsshできる

## 準備

- `$ curl -fsSL https://tailscale.com/install.sh | sh`
- `$ sudo tailscale up --advertise-exit-node`

## 確認

管理画面からホストマシンのIPアドレスが見れるので、これを使って
```
$ ssh user@IPアドレス
```

LAN内からはアクセスできた。