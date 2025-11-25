## . 
#### 📝 VSCodeで実行
<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>

```bash
# 変数 x に -10 を代入
x = -10

# if 文で条件分岐
if x < 0:  # x が 0 より小さい場合
    print('negative')  # 負の値であることを表示

# ここから別の例
# x = 0 の場合を想定したコメント
x = 10  # 今回は 10 を代入

if x < 0:  # x が 0 より小さい場合
    print('negative')
elif x == 0:  # x が 0 の場合
    print('zero')
elif x == 10:  # x が 10 の場合
    print('10')
else:  # 上記以外の値の場合
    print('positive')

# ネストした if 文の例
a = 5
b = 10

if a > 0:  # a が正の値の場合
    print('a = positive')
    if b > 0:  # さらに b が正の値の場合
        print('b = positive')
```
## 📝 学習のまとめ
- Pythonでは、インデント（字下げ）が正しく揃っていないと構文エラーになる

<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>
