## 81. クラスの継承
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る</a>
</div>

**基本の継承構造（空クラス**

` Car `クラスを定義し、それを継承した` ToyotaCar `を作る最小構成
```python
class Car(object):     # まずは空のクラス定義
    pass
class ToyotaCar(Car):  # Car を継承した ToyotaCar クラス（まだ何も追加していない）
    pass
```
**親クラスにメソッドを追加**

` Car `に` run() `を追加し、` ToyotaCar `は継承だけ。` Car `インスタンスで` run() `を呼び出す
```python
class Car(object):
    def run(self):
        print('run')

class ToyotaCar(Car):
    pass

car = Car()
car.run()   # → "run"
```
**継承した子クラスでも親メソッドを利用**

` ToyotaCar `は` Car `を継承しているので、親の` run() `をそのまま使える。
```python
class Car(object):
    def run(self):
        print('run')

class ToyotaCar(Car):
    pass

car = Car()
car.run()

toyotaCar = ToyotaCar()
toyotaCar.run()
```
**継承＋独自メソッド追加**

` TeslaCar `は` Car `を継承しつつ、独自メソッド` auto_run() `を追加
```python
class Car(object):
    def run(self):
        print('run')

class ToyotaCar(Car):
    pass

class TeslaCar(Car):
    def auto_run(self):
        print('auto run')

car = Car()
car.run()

toyota_Car = ToyotaCar()
toyota_Car.run()

tesla_Car = TeslaCar()
tesla_Car.run()
tesla_Car.auto_run()
```
**継承を使わずに独立したクラスを定義**

継承を使わないので、同じ` run() `をそれぞれ書く必要がある
```python
class Car(object):
    def run(self):
        print('run')

class ToyotaCar(object):
    def run(self):
        print('run')

class TeslaCar(object):
    def run(self):
        print('run')

    def auto_run(self):
        print('auto run')

car = Car()
car.run()

toyota_Car = ToyotaCar()
toyota_Car.run()

tesla_Car = TeslaCar()
tesla_Car.run()
tesla_Car.auto_run()
``

<div align="right">
  <a href="../README.md#section7">◀️READMEに戻る<a>
</div>




