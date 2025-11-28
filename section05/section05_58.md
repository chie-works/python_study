## 58. ラムダ
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section5">◀️READMEに戻る</a>
</div>

```python
l = ['Mon', 'tue', 'Wed', 'thu', 'fri', 'sat', 'Sun']

# --- 関数を引数として渡す例 ---
def change_words(words, func):
    for word in words:
        print(func(word))

def sample_func(word):
    return word.capitalize()

change_words(l, sample_func)

# --- ラムダ式を使う例 ---
def change_words(words, func):
    for word in words:
        print(func(word))

# ラムダ式で同じ処理を定義
sample_func = lambda word: word.capitalize()

# ラムダ式を直接渡す → capitalize
change_words(l, lambda word: word.capitalize())

# 別のラムダ式を渡す → lower
change_words(l, lambda word: word.lower())
```
## ✨ 学習のまとめ

- ラムダ式 = 無名関数を簡潔に書く方法
- 名前を付けなくても関数を作れる
- 1行で書ける（複雑な処理には不向き）
- 戻り値は式の結果（return は不要）
- 書式：`lambda 引数: 式`

```python
f = lambda x: x * 2
print(f(5))  # → 10
```

**関数を引数に渡す**
```python
l = ["Mon", "tue", "Wed"]
print(list(map(lambda w: w.lower(), l)))  # → ['mon', 'tue', 'wed']
```
**ソートのキー指定**
```python
data = [("apple", 3), ("banana", 1), ("cherry", 2)]
data.sort(key=lambda x: x[1])
print(data)  # → [('banana', 1), ('cherry', 2), ('apple', 3)]
```
**一時的な関数**
```python
print((lambda x, y: x + y)(10, 20))  # → 30
```

<div align="right">
  <a href="../README.md#section5">◀️READMEに戻る</a>
</div>


