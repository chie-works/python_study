## 92. withステートメントでファイルをopenする
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る</a>
</div>

```python
with open('test.txt', 'w') as f:
    f.write('test\n')

# withブロックを抜けると、自動的に f.close() が呼ばれる
# → 明示的に close() を書かなくても安全にファイルが閉じられる```
