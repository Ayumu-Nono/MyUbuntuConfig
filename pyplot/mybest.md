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
