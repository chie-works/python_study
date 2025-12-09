## 88. クラス変数
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る</a>
</div>

**①クラス変数**
```python
class Person(object):
    kind = 'human'                     # ← クラス変数（全インスタンスで共有される）
    def __init__(self, name):
        self.name = name               # ← インスタンス変数（インスタンスごとに異なる）
    def who_are_you(self):
        print(self.name, self.kind)    # self.kind でクラス変数にアクセスできる

a = Person('A')
a.who_are_you()   # → "A human"
b = Person('B')
b.who_are_you()   # → "B human"
# kind はクラス変数なので、AもBも同じ 'human' を参照する
```

**②クラス変数：リストの場合**
```python
class T(object):
    words = []                   # ← クラス変数（全インスタンスで共有されるリスト）
    def add_word(self, word):
        self.words.append(word)  # self.words はクラス変数 words を参照

c = T()
c.add_word('add 1')
c.add_word('add 2')

d = T()
d.add_word('add 3')
d.add_word('add 4')

print(c.words)   # → ['add 1', 'add 2', 'add 3', 'add 4']
# c と d は同じクラス変数 words を共有しているため、両方の追加結果が混ざる
```
**②の回避策**
```python
class T(object):
    def __init__(self):
        self.words = []           # ← インスタンス変数（インスタンスごとに独立）
    def add_word(self, word):
        self.words.append(word)

c = T()
c.add_word('add 1')
c.add_word('add 2')
print(c.words)   # → ['add 1', 'add 2']

d = T()
d.add_word('add 3')
d.add_word('add 4')
print(d.words)   # → ['add 3', 'add 4']
# インスタンス変数なので、c と d の words は別々に管理される
```

## ✨ 学習のまとめ
- クラス変数 ：全インスタンスで共有される。リストや辞書を置くと「全員で同じものを編集」することになる。
- インスタンス変数 ：インスタンスごとに独立。個別の状態を持たせたい場合はこちらを使う。

<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る<a>
</div>




