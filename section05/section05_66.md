## 66. 独自例外の作成
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section5">◀️READMEに戻る</a>
</div>

```python
raise IndexError('test error')
# ↑ 組み込み例外を明示的に発生させる例

# ユーザー定義例外クラス
class UppercaseError(Exception):
    pass  # Exception を継承して独自の例外を作る

def check():
    # words = ['apple', 'banana', 'orange']  # 正常なケース
    words = ['APPLE', 'banana', 'orange']    # エラーケース
    for word in words:
        if word.isupper():                   # 全て大文字の単語を検出
            raise UppercaseError(word)       # 実際に例外を発生させる

try:
    check()  # 関数を実行 → 'APPLE' が大文字なので UppercaseError が発生
except UppercaseError as exc:
    # ユーザー定義例外をキャッチしたときの処理
    print('This is my fault. Go next')
```

<div align="right">
  <a href="../README.md#section5">◀️READMEに戻る</a>
</div>
