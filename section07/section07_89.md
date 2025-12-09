## 89. クラスメソッドとスタティックメソッド
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る</a>
</div>

**クラスメソッド**
```python
class Person(object):

    kind = 'human'                     # ← クラス変数（全インスタンスで共有される）

    def __init__(self):
        self.x = 100                   # ← インスタンス変数（インスタンスごとに異なる）

    def what_is_your_kind(self):
        return self.kind               # インスタンスメソッド（selfを通じて呼び出す）

    @classmethod
    def what_is_your_kind2(cls):
        # クラスメソッド（clsを通じて呼び出す）
        return cls.kind

# インスタンス生成
a = Person()       # ← インスタンス
b = Person         # ← クラスそのもの（インスタンスではない）

print('a : ', a)   # インスタンスの参照が表示される
print('b : ', b)   # クラスオブジェクトそのものが表示される

print('a.x : ', a.x)   # インスタンス変数はインスタンスからアクセス可能
# print('b.x : ', b.x) # ← クラスからはインスタンス変数にアクセスできないのでエラー

print('a.kind : ', a.kind)   # インスタンスからでもクラス変数にアクセス可能
print('b.kind : ', b.kind)   # クラスからもクラス変数にアクセス可能

print('a.what_is_your_kind() : ', a.what_is_your_kind())   # インスタンスメソッドはインスタンスから呼ぶのでOK
# print('b.what_is_your_kind() : ', b.what_is_your_kind()) # ← クラスから呼ぶとselfが渡されないのでエラー

print('a.what_is_your_kind2() : ', a.what_is_your_kind2()) # クラスメソッドはインスタンスからも呼べる
print('b.what_is_your_kind2() : ', b.what_is_your_kind2()) # クラスメソッドはクラスからも呼べる

print(Person.kind)                    # クラス変数に直接アクセス
print(Person.what_is_your_kind2())    # クラスメソッドに直接アクセス
```


**スタティックメソッド**
```pytohn
class Person(object):

    # スタティックメソッドの定義
    @staticmethod
    def about(year):
        # 引数 year を受け取り、文字列を出力する
        # self や cls は使わない（インスタンスやクラスに依存しない処理）
        print('about human {}'.format(year))

# スタティックメソッドの呼び出し
Person.about(1999)   # → "about human 1999" と出力される
```

## ✨ 学習のまとめ
**` クラスメソッド `**
- インスタンス変数 (self.x) ：インスタンスにしか存在しない。クラスからはアクセス不可。
- クラス変数 (kind) ：クラスとインスタンスの両方からアクセス可能。
- インスタンスメソッド (what_is_your_kind)：インスタンスから呼ぶ必要がある。クラスから呼ぶと` self `が不足してエラー。
- クラスメソッド (what_is_your_kind2)：クラスからもインスタンスからも呼べる。` cls `が自動的に渡される。

**` スタティックメソッド `**
- インスタンス (self) やクラス (cls) を受け取らない。
- 単なる「クラスに属する関数」として定義される。
- クラスからもインスタンスからも呼び出せる。
- Person.about(1999) → クラスから呼び出し。
- a = Person(); a.about(2000) → インスタンスから呼び出しも可能。
- クラスに関連するが、インスタンスやクラスの状態を使わない処理。


<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る<a>
</div>




