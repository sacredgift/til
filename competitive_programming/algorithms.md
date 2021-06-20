### いもす法(imos)
「ある連続する 区間 に、ある数 v を足す」という操作をK回繰り返した結果を、計算量 O (N+K) で高速に計算する方法。
```
def solve():
    # 入力処理
    N, Q = list(map(int, input().split()))

    # オセロの駒の初期化（最初はすべて黒）
    s = [0] * (N+1)
 
    # いもす法の加算処理
    for _ in range(Q):
        l, r = list(map(int, input().split()))  # 区間[l, r]の入力を受け取る
        s[l] += 1
        if r+1 != N+1:
            s[r+1] -= 1
    
    # いもす法の累積和（構築処理）
    ruiseki = [0] * (N+1)
    for i in range(1, N+1):
        ruiseki[i] += ruiseki[i-1] + s[i]
        if ruiseki[i]%2 == 0:
            # 裏返した回数が偶数なら、黒のまま
            ruiseki[i] = 0
        else:
            # 裏返した回数が奇数なら、白
            ruiseki[i] = 1
    
    # 答えを出力
    ans = "".join(list(map(str, ruiseki[1:])))
    print(ans)
 
 
if __name__ == "__main__":
    solve()
```

### 参考
[いもす法](https://imoz.jp/algorithms/imos_method.html)  
[Pythonでいもす法](https://takeg.hatenadiary.jp/entry/2019/08/28/213526)  
[AtCoder緑になるまでに勉強した基本的なアルゴリズムやデータ構造まとめ](https://qiita.com/Takayoshi_Makabe/items/65f20edbd970070419f4)  
