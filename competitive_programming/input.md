### 入力処理
標準入力はinput関数で入力する（文字列(str)型で入力される）。
標準入力から整数を得たい場合、整数(int)型int(input())に変換する。
標準入力から浮動小数点数を得たい場合、浮動小数点数(float)型float(input())に変換する。
標準入力から得た文字列を区切りたい場合、split関数を用いてinput().split("区切り文字")と使用する。
split関数で区切り文字を指定しない場合input().split()、半角スペース で区切られる。
複数列の整数の標準入力を複数の変数に格納したい場合、map関数を用いてmap(int, input().split())と使用する。
複数列の整数の標準入力をリストに格納したい場合、map関数を用いてlist(map(int, input().split()))と使用する。
複数行の整数の標準入力をリストに格納したい場合、リスト内包表記で[int(input()) for 変数名 in range(入力行数)]と使用する。

### 参考
[AtCoderで始めるPython入門](https://qiita.com/KoyanagiHitoshi/items/3286fbc65d56dd67737c)
