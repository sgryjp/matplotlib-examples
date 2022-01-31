# matplotlib 事始め

- 2022-01-29 Suguru Yamamoto \<sgryjp@gmail.com\>

## コーディングスタイルについて

matplotlib では 2 種類のコーディングスタイルがサポートされている。

1. オブジェクト指向スタイル
2. pyplot を使うスタイル

前者は matplotlib の API そのものに近く、後者はそれを（MATLAB ユーザーにとって分かりやすい）グローバル関数で操作するようなもの、と考えて良いと思う。後者は内部的には前者を使うものなので、前者と後者は混ぜて使うこともできる。こうした事情があって、matplotlib のソースコードは同じことを実現していても人によって結構違いが出てしまいがち。なので、まずは **「複数のコーディングスタイルがある」** ことを覚えておくことをオススメする。その上で、先ほど書いた通り最終的にはオブジェクト指向スタイルの API が呼び出されるわけなので、**「困ったらオブジェクト指向 API のリファレンスを確認する」**、というクセを付けると良いと思う。それにあたって、matplotlib の Figure, Axes, Axis, Artist という概念を理解しておくと非常に API リファレンスを調べるのが楽になる。このあたりは matplotlib 公式のチュートリアル ["Basic Usage"](https://matplotlib.org/stable/tutorials/introductory/usage.html) が非常に分かりやすく説明しているので、一度読んでおくことを強くオススメしておく。

なお、当方は基本的にオブジェクト指向スタイルを使いつつ、ごく一部で pyplot（MATLAB 互換）を使うコーディングスタイルを選んでいる。matplotlib の公式サンプルコードなどで使われているスタイルと大体同じだと思うけれど、完璧にマネしているわけではないので、微妙に違いがあって混乱を招いてしまったら、スミマセン。

# import の方法

オブジェクト指向スタイルでも pyplot スタイルでも、matplotlib の大半の機能は次の import 一つで使用可能になる。

```python
import matplotlib.pyplot as plt
```

`pyplot` を `plt` という名前でインポートするこの書き方は、別に守らなければならない規則でも何でもないものの、
公式をはじめ matplotlib ユーザーの大半が使っているため、あえてこの書き方を避ける理由も無いと思う。
一種の「おまじない」として丸覚えしてしまうことをオススメしたい。

# 描画例

以下、いろいろなプロットの種類ごとにオプションと描画例を交えつつ、描き方を記していく。

## 基本的なグラフ

- 線グラフ (Line chart)
- [散布図 (Scatter plot)](scatter-plot.ipynb)
- 棒グラフ (Bar chart)
- stem (?)
- 面グラフ (Area chart)
- 画像・ヒートマップ (Image, Heatmap)
- 等高線 (Contour)
- quiver (?)

## 統計的なグラフ

- 一つの確率分布を可視化する
  - ヒストグラム (Histogram)
  - カーネル密度推定プロット (Kernel Density Estimate plot)
- 複数の確率分布を比較できる形で可視化する
  - 箱ひげ図 (Box plot)
  - バイオリンプロット (Violin plot)
  - ストリッププロット (Strip plot)
- 時間等の軸上にサンプルがあるか無いかを可視化する
  - イベントプロット (Event plot, Strip plot, ...)
- その他
  - 散布図行列
  - エラーバー (Error bar)
  - HexBin

## その他

- 地図
- ツリーマップ
- デンドログラム
- ラジアルツリー (Radial tree chart)
- ロウソク足チャート (Candlestick chart, OHLC chart, Open-High-Low-Close chart)
- ウォーターフォール
