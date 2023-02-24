# Pyplot my favorite config

## 凡例

- 枠外右上:`plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left', borderaxespad=0)`

## 軸

- 正規化/標準化するか、単位を忘れずに
- axesは`plt.subplots_adjust(wspace=0.4, hspace=0.6)`


## フォント・解像度


```
plt.rcParams["font.family"] = "Arial"
plt.rcParams["font.size"] = 15
plt.rcParams["figure.dpi"] = 150

plt.rcParams["xtick.direction"] = "in"               #x軸の目盛線を内向きへ
plt.rcParams["ytick.direction"] = "in"               #y軸の目盛線を内向きへ
plt.rcParams["xtick.minor.visible"] = True           #x軸補助目盛りの追加
plt.rcParams["ytick.minor.visible"] = True           #y軸補助目盛りの追加
plt.rcParams["xtick.major.width"] = 1.5              #x軸主目盛り線の線幅
plt.rcParams["ytick.major.width"] = 1.5              #y軸主目盛り線の線幅
plt.rcParams["xtick.minor.width"] = 1.0              #x軸補助目盛り線の線幅
plt.rcParams["ytick.minor.width"] = 1.0              #y軸補助目盛り線の線幅
plt.rcParams["xtick.major.size"] = 10                #x軸主目盛り線の長さ
plt.rcParams["ytick.major.size"] = 10                #y軸主目盛り線の長さ
plt.rcParams["xtick.minor.size"] = 5                 #x軸補助目盛り線の長さ
plt.rcParams["ytick.minor.size"] = 5                 #y軸補助目盛り線の長さ
plt.rcParams["axes.linewidth"] = 1.5                 #囲みの太さ
```

## カラーマップ

軸ラベルを指数表記にするためにはこれ

```
mappable = ax.contourf(xx, yy, vv, cmap="jet", levels=10)
fmt = lambda x, pos: '{:.1e}'.format(x)
divider = mpl_toolkits.axes_grid1.make_axes_locatable(ax)
cax = divider.append_axes('right', '5%', pad='3%')
cbar = fig.colorbar(mappable, cax=cax, label=r"$\phi~[V]$", format=FuncFormatter(fmt))
ax.yaxis.set_major_formatter(ScalarFormatter(useMathText=True))
ax.ticklabel_format(style="sci",  axis="y",scilimits=(0,0))
ax.xaxis.set_major_formatter(ScalarFormatter(useMathText=True))
ax.ticklabel_format(style="sci",  axis="x",scilimits=(0,0))
ax.set_title(r"Potential $\Omega={}$".format(np.round(Omega, decimals=2)))
```
