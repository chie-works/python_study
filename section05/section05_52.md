## 52. 位置引数のタプル化
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>

```python
# --- 通常の引数（固定個数） ---
def say_something(word1, word2, word3):
    print(word1)
    print(word2)
    print(word3)

say_something('Hi!', 'Mike', 'Nancy')  
# 引数を3つ渡す → Hi! / Mike / Nancy

# --- 可変長引数（*args） ---
def say_something(*args):
    print(args)        # タプルとして受け取る
    for arg in args:   # ループで展開できる
        print(arg)

say_something('Hi!', 'Mike', 'Nancy')  
# ('Hi!', 'Mike', 'Nancy') → タプルとして渡される

# --- 先頭の引数＋残りを *args で受け取る ---
def say_something(word, *args):
    print(word, args)  # 先頭は word、残りはタプル args
    for arg in args:
        print(arg)

say_something('Hi!', 'Mike', 'Nancy')  
# word = 'Hi!' / args = ('Mike', 'Nancy')

# --- タプルをアンパックして渡す ---
def say_something(word, *args):
    print(word, args)
    for arg in args:
        print(arg)

t = ('AAAAA', 'BBBBB')
say_something('Hi!', *t)  
# *t によって ('AAAAA', 'BBBBB') が展開される
# word = 'Hi!' / args = ('AAAAA', 'BBBBB')
```

<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>
