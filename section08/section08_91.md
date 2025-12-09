## 91. ファイルの作成
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る</a>
</div>

**新規作成または上書きモード**
```python
f = open('test.txt', 'w')
f.write('Test')   # ファイルに "Test" を書き込む
f.close()         # ファイルを閉じる（必須）
```

**追記モードで開く**
```python
f = open('test.txt', 'a')
f.write('Test')   # 既存の内容の末尾に "Test" を追加
f.close()
```
**改行**
```python
f = open('test.txt', 'w')
f.write('Test\n')   # "Test" と改行を出力
```
**print関数を使ってファイルに書き込み**
```python
print('A am print', file=f)                # "A am print" をファイルに出力
print('My', 'name', 'is', 'Mike', file=f)  # → デフォルトではスペース区切り
print('My', 'name', 'is', 'Mike', sep='#', end='!', file=f)
f.close()
```
## ✨ 学習のまとめ
- ` w モード ` : 新規作成または既存ファイルを上書き
- `a モード ` : 既存内容を残したまま末尾に追加
- ` .write() ` : 文字列をそのまま書き込む。改行は自動で入らないので` \n `が必要。
- ` print(..., file=f) ` : 標準出力ではなくファイルに書き込める。`sep `や` end `で出力形式を調整可能。
- ` close() ` : ファイルを閉じてリソースを解放。忘れると内容が保存されないこともある。


<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る<a>
</div>

