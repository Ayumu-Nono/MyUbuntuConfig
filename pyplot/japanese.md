# グラフタイトルを日本語にする

## 

```
fig, ax = plt.subplots(nrows=1, ncols=1, facecolor="white", figsize=(6, 5), sharey=True)

font_path = "/usr/share/fonts/opentype/noto/NotoSansCJK-Regular.ttc"
fp = FontProperties(fname=font_path)
ax.set_xticklabels(x, fontproperties=fp)
ax.set_title("ノミナル 20220907", fontproperties=fp)
```