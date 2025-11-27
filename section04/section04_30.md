## 30. 集合型の使い所
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section4">◀️READMEに戻る</a>
</div>

```python
my_frienda = {'A', 'B', 'C'}
A_frienda = {'B', 'D', 'E', 'F'}

# 共通部分（積集合）を求める
print(my_frienda & A_frienda)  # {'B'}

# リストを作成（同じ要素が重複している）
f = ['apple', 'banana', 'apple', 'banana']
print(f)  # ['apple', 'banana', 'apple', 'banana']

# リストを集合に変換 → 重複が自動的に取り除かれる
kind = set(f)
print(kind)  # {'apple', 'banana'}
```

<div align="right">
  <a href="../README.md#section4">◀️READMEに戻る</a>
</div>


