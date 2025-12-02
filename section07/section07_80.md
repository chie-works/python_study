## 80. コンストラクタとデストラクタ
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る</a>
</div>

```python
class Person(object):
    # コンストラクタ（インスタンス生成時に自動で呼ばれる）
    def __init__(self, name): 
        self.name = name         # インスタンス変数 name を初期化

    def say_something(self):     # インスタンスメソッド
        print('I am {}. hello'.format(self.name))
        self.run(3)

    def run(self, num):          # インスタンスメソッド
        print('run' * num)

    # デストラクタ（インスタンスが破棄されるときに自動で呼ばれる）
    def __del__(self):
        print('good bye')

# インスタンス生成 → コンストラクタ __init__ が呼ばれる
person = Person('Mike')

# インスタンスメソッド呼び出し
person.say_something()

# インスタンスを明示的に削除するとデストラクタ __del__ が呼ばれる
# del person

print('##################')
```

## ✨ 学習のまとめ
**コンストラクタ**：` __init__ `
- インスタンス生成時に呼ばれる
- インスタンス変数の初期化や準備処理を行う

**デストラクタ**：` __del__ `
- インスタンスが破棄されるときに呼ばれる
- 明示的に` del person `したときや、プログラム終了時に呼ばれる
- 実際には「ガーベジコレクションのタイミング」に依存するので、必ず呼ばれるとは限らない


<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る<a>
</div>




