---
title: VS Code でPython，Jupyter を動かす
tags: Python Jupyter VSCode
author: surei
slide: false
---
#　はじめに
　VS Codeを使っている人から勧められたのと，これ1つで様々な言語に触れることができるので入れることにしました．
その際，自分の知識が浅く苦労したので入れてみたいけどイマイチ分かんないって人の参考になるといいです．
また，今回はVS CodeでPythonプログラミングを始めようと考えているということなので，Pythonディストリビューションの１つである**Anacondaがダウンロードしてあるという仮定**で話を進めていきます．（Anacondaインストール時に同時にVs Codeをインストールするのではなく別途インストール）
その他，間違っている点や，もっと効率の良いやり方がありましたら教えてください．

追記しました（2019/03/10）
拡張機能について更新しました（2019/12/24）
編集しました（2020/4/19）

# 0. 環境
|||
|:----:|:------:|
|OS|Windows10|
|Anaconda|5.2.0|
|Python|3.6.7|


# 1. VS Codeをダウンロード
　まずは，[VS Code](https://code.visualstudio.com/Download)をダウンロードします．
　基本，何も考えずに[次へ]でいいと思いますが，「追加タスクの選択」というところで追加タスクの設定ができます．右クリックメニューからVS Codeを使いたい場合はコンテキストメニューに関する項目にチェックを入れておくといいかもしれません．ここでは，**利便性向上のため全てにチェックを入れること**をお勧めします．

# 2. VS Codeの拡張機能を入れる
　ダウンロードが完了し，VS Codeを立ち上げたらVS Codeのビューバーで[拡張機能]のアイコンをクリック（下の画像の赤枠）します．
![test.png](https://qiita-image-store.s3.amazonaws.com/0/208370/e72fd043-d48b-dc64-82ed-e5ec3747d670.png)
そして，目当ての拡張機能を検索（下の画像の赤枠）しダウンロードしていきます．
![test1.png](https://qiita-image-store.s3.amazonaws.com/0/208370/7a41f3de-3fef-f577-5d2a-6d636a7f440f.png)

今回はPythonとJupyterの他に私的おすすめをいくつかURLのリンクをつけて紹介します．

1.　[Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)：Pythonの拡張機能　
2.　~~[Jupyter](https://marketplace.visualstudio.com/items?itemName=donjayamanne.jupyter)：jupyterの拡張機能~~　(Pythonの拡張機能に組み込まれたため)
3.　[Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)：括弧に色がつく　
4.　[Japanese Language Pack for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-ja)：日本語で見られるようにする　
5.　[vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)：アイコンをが出るようになり，分かりやすくなる
6.　[indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow):インデントが把握しやすくなる
7.　[google this](https://marketplace.visualstudio.com/items?itemName=kameshkotwani.google-search):vscodeからgoogle検索に飛べる
8.　[Visual Studio IntelliCode](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode):補完が優秀になる
9.　[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense):パスの入力がちょっと楽になるかも
10.　[PrintCode](https://marketplace.visualstudio.com/items?itemName=nobuhito.printcode):書いたプログラムを他人に見せるとき印刷して見せれるようになる
11.　[zenkaku](https://marketplace.visualstudio.com/items?itemName=mosapride.zenkaku):全角スペースを強調してくれる

# 3. VS Codeで書いてみる
　早速，VS Codeで書いていきましょう．Windows/Linuxでは[Ctrl]+[Shift]+[P]キー（macOSでは[Shift]+[Command]+[P]キー）を押して、「コマンドパレット」と呼ばれるGUI要素を表示し，そこで「select interpreter」と入力しPython機能拡張が認識しているPython環境が一覧表示されるので，そこから使用したいものを選択します．今回は3.6.5を選択したとします．
![test.png](https://qiita-image-store.s3.amazonaws.com/0/208370/77f77a03-64ac-0e3b-ca5e-a3be039c9686.png)
![tset1.png](https://qiita-image-store.s3.amazonaws.com/0/208370/d9e2f4d5-a5e8-8eb9-d9e8-1187feba929a.png)
　次に，[フォルダーをひらく]をクリックし，ファイルを保存するフォルダーを選択します.
![test.png](https://qiita-image-store.s3.amazonaws.com/0/208370/e6dcd5ee-7cf4-ba6d-6c78-3bb0ac053008.png)
　今回は，ユーザーの中に[Python]と言う名前のフォルダーを作成しておき，そのフォルダーを選択することにします．
フォルダーを選択し開いたら，下の画像の赤枠で囲った[新しいファイル]をクリックし，ファイルを作成します．この際，ファイル名を拡張子を含めて入力してください．（ex．pythonのファイル→～～.py）
![test1.png](https://qiita-image-store.s3.amazonaws.com/0/208370/21149e22-c08b-21f1-364c-2da9fffd5bb2.png)

## Python
　まずはPythonのコードが動くか確認します．上の手順に従って[hello.py]というファイルを作ってください．

```python:hello.py
msg="Hello World"
print(msg)
```
これが無事に動くなら問題はないはずです．

## Jupyter
　次のにJupyterが動くか確認します．先ほどと同様に[test.py]というファイルを作ってください．

```python:test.py
# %%
test="test now "

# %%
print(test)

# %%
import matplotlib.pyplot as plt
import matplotlib as mpl
import numpy as np

x = np.linspace(0, 20, 100)
plt.plot(x, np.sin(x))
plt.show()

# %%
y = np.linspace(0, 20, 100)
plt.plot(y, np.cos(y))
plt.show()

# %%
import pandas as pd 
data = pd.read_csv("/Users/~~/Desktop/IRIS.csv")
data.head()

# %%
a_array = np.array([1,2,3])
b_array = np.array([4,5,6])

print(a_array+b_array)
```

　上のコードで先頭行の「#%%」は，Jupyter Notebookにおける「セル」の区切りを表し，これで区切られた領域が1つの実行単位となります．そのため，この行の上には［Run cell］というリンクが表示されます．![test.png](https://qiita-image-store.s3.amazonaws.com/0/208370/834e6285-c6b7-5978-96d6-f39eb54ec62f.png)
　[Run cell]をクリックするとそのセルを実行するのですが，その際に下の画像のようなものがでるかもしれません．これは，Jupyter Notebookを新規に起動するか，既に起動されているJupyter Notebookを指定するかの選択です．
![test1.png](https://qiita-image-store.s3.amazonaws.com/0/208370/c7d9cb5a-4256-66c8-5906-b2ee457d2a4e.png)
　今回は[Start a new notebook」を選択します．すると必要なパッケージがインストールされていれば，先頭のセルの内容が実行され，下のように別のエディタに実行結果が表示されます．されない場合には，condaコマンドあるいはpipコマンドで足りないものをインストールして下さい．
![twest.png](https://qiita-image-store.s3.amazonaws.com/0/208370/3d82485e-c6c2-3571-e0aa-155beea4ca17.png)
　このときに「Failed to Detect Jupyter Notebook」のようなメッセージが表示されたら，Windows/Linuxでは[Ctrl]+[Shift]+[P]キー（macOSでは[Shift]+[Command]+[P]キー）を押して，コマンドパレットから[Jupyter: Select an existing (local) Jupyter Notebook]コマンドを選択し，起動しているJupyter Notebookの中のいずれかを選択し実行するとうまく実行できるかもしれません．

#追記（2019/03/10）
　jupyterがpythonの拡張機能に組み込まれました．人によっては使いやすくなったのでしょうけど，自分は使いづらくなったと感じたため（主に可視化面で…目が痛くなる…）従来のような感じに戻してみました．

　入れる拡張機能は[これ（jupyter）](https://marketplace.visualstudio.com/items?itemName=yzhang.vscode-jupyter)です．これを入れることで，従来と同じような動きをしてくれます．

#追記（2020/4/19）
[これ（jupyter）](https://marketplace.visualstudio.com/items?itemName=yzhang.vscode-jupyter)もサポートが切れたため新たなPCで同一環境の構築ができなくなりました．
しかし，設定を少し弄れば似た似たような形のいなるのでその紹介です．
1. [ctrl]+[,]を押し，設定を開きます．
2. 「設定の検索」と表示されたウィンドウに「Data Science: Max Output Size」と入力します．
3. そこに書かれている数字を「-1」に変更します．
これでグラフ等の出力は今までと似たような形になります．

# おわりに
　上記の流れで行えば動くはずです．いろいろ至らないところがあるかもしれませんが，その点はコメント等で指摘してくれると嬉しいです．

# 参考サイト
https://www.sejuku.net/blog/40607
http://www.atmarkit.co.jp/ait/articles/1806/12/news041.html
http://www.atmarkit.co.jp/ait/articles/1805/22/news043.html
http://www.atmarkit.co.jp/ait/articles/1711/24/news034.html
