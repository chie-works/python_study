## 86. 抽象クラス
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る</a>
</div>

```python
import abc

# 抽象クラスの定義
class Person(metaclass=abc.ABCMeta):   # ABCMeta を指定することで抽象クラスになる
    def __init__(self, age=1):
        self.age = age

    @abc.abstractmethod
    def drive(self):                   # 抽象メソッド（必ずサブクラスで実装しなければならない）
        pass

# Baby クラス
class Baby(Person):
    def __init__(self, age=1):
        if age < 18:
            super().__init__(age)      # 親クラスの初期化を呼ぶ
        else:
            raise ValueError           # 18歳以上ならエラー

    def drive(self):                   # 抽象メソッドを具体的に実装
        print('NG')                    # Baby は運転できない → NG

# Adult クラス
class Adult(Person):
    def __init__(self, age=18):
        if age >= 18:
            super().__init__(age)      # 親クラスの初期化を呼ぶ
        else:
            raise ValueError           # 18歳未満ならエラー

    def drive(self):                   # 抽象メソッドを具体的に実装
        print('OK')                    # Adult は運転できる → OK

# インスタンス生成と動作確認
baby = Baby()
baby.drive()   # → NG

adult = Adult()
adult.drive()  # → OK
```
## ✨ 学習のまとめ
- ` metaclass=abc.ABCMeta `によって抽象クラス化されている。
- ` @abc.abstractmethod `を付けた` drive() `は「必ずサブクラスで実装しなければならない」。
- そのため` Person `を直接インスタンス化するとエラーになる。
- 抽象クラス` Person `が「設計図」として存在し、サブクラスに` drive() `の実装を強制している。
- `Baby `と` Adult `はそれぞれの条件に応じて` drive() `を具体化している。

<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る<a>
</div>




