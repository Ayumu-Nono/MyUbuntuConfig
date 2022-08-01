# How to export from jupyter

## install

Ubuntu
```
$ sudo apt-get update
$ sudo apt-get install pandoc
$ sudo apt-get install texlive-xetex
```

Pip
```
$ pip3 install nbconvert
```

## PDF

```
$ jupyter nbconvert --to pdf xxx.ipynb
```

If you face error, try
```
$ jupyter nbconvert --to webpdf xxx.ipynb
```

## Japanese

日本語で出力したいとき。

```
$ sudo apt-get update
$ sudo apt-get install texlive-lang-japanese
```

```
$ jupyter --path
config:
    /home/basicuser/.jupyter
    /usr/local/etc/jupyter
    /etc/jupyter
data:
    /home/basicuser/.local/share/jupyter
    /usr/local/share/jupyter
    /usr/share/jupyter
runtime:
    /home/basicuser/.local/share/jupyter/runtime
```
でパスを表示して`index.tex.ja2`を探す。

例
`xxx/myvenv/share/jupyter/nbconvert/templates/latex`

中身を変更

```
\documentclass[11pt]{article}
--> 
\documentclass[xelatex,ja=standard]{bxjsarticle}
```

