# Pyenv install

## 準備

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

## 必要なものをinstall

```
$ sudo apt install -y \
build-essential \
libffi-dev \
libssl-dev \
zlib1g-dev \
liblzma-dev \
libbz2-dev \
libreadline-dev \
libsqlite3-dev \
libopencv-dev \
tk-dev \
git
```

## pyenvをinstall

```
$ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

## .bashrcの更新
```
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
$ source ~/.bashrc
```

## 確認

```
$ pyenv -v 
```
