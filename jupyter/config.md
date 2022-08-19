# お気に入りconfig

## Nbextensions


拡張機能を色々使えるようになる
```
$ pip3 install jupyter-contrib-nbextensions
$ jupyter contrib nbextension install --user
$ jupyter nbextensions_configurator enable --user
```

## 補完

Hinterland にチェックを入れたあと、もし既にノートを開いているのであればF5などすると有効化します。


## テーマ

jupyterのテーマを設定
```
$ pip3 install jupyterthemes
$ jt -t chesterish -T -f roboto -fs 9 -tf merriserif -tfs 11 -nf ptsans -nfs 11 -dfs 8 -ofs 8
```

リセットするには
```
$ jt -r
```

## Vimキーバインド


### インストール

`$ jupyter --path`でクローン先を調べて、
```
$ git clone https://github.com/lambdalisue/jupyter-vim-binding /work/00/gi16/i16115/PlasmaResearch/myvenv/share/jupyter/nbextensions/vim_binding
```

VIM bindingのチェックを入れる。

### cssの調整

`~/.jupyter/custom/custom.css`を編集します。`div.cell.edit_mode` {という一行がありますので、その直前に下記を挿入します。

```
/* Jupyter cell is in normal mode when code mirror */
.edit_mode .cell.selected .CodeMirror-focused.cm-fat-cursor {
background-color: #000000 !important;
}
/* Jupyter cell is in insert mode when code mirror */
.edit_mode .cell.selected .CodeMirror-focused:not(.cm-fat-cursor) {
background-color: #000000 !important;
}
```

### カスタムキーバインド

`~/.jupyter/custom/custom.js`(スパコンの場合ログインディレクトリの中にある)の末尾に以下を記入。

```
require([
 'nbextensions/vim_binding/vim_binding',   // depends your installation
], function() {
  // Map jj to <Esc>
CodeMirror.Vim.map("jj", "<Esc>", "insert");
});
```