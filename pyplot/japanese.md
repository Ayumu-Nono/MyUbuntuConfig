# グラフ要素を日本語にする

## xlabel

```
from matplotlib.font_manager import FontProperties

font_path = "/usr/share/fonts/opentype/noto/NotoSansCJK-Regular.ttc"
fp = FontProperties(fname=font_path)
ax.set_xticklabels(x, fontproperties=fp)
ax.set_title("ノミナル 20220907", fontproperties=fp)
```

## legend

```
from matplotlib.font_manager import FontProperties

font_path = "/usr/share/fonts/opentype/noto/NotoSansCJK-Regular.ttc"
fp = FontProperties(fname=font_path)
ax.scatter(x=x, y=y, label="{}".format("日本語"))
ax.legend(prop=fp)
```