## 94. seekを使って移動する
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る</a>
</div>

```python
with open('test.txt', 'r') as f:
    print(f.tell())       # 現在位置を表示（最初は 0）
    print(f.read(1))      # 1文字読み込む → ポインタが1進む

    f.seek(5)             # ポインタを「5バイト目」に移動
    print(f.read(1))      # その位置から1文字読み込む

    f.seek(14)            # ポインタを「14バイト目」に移動
    print(f.read(1))      # その位置から1文字読み込む

    f.seek(15)            # ポインタを「15バイト目」に移動
    print(f.read(1))      # その位置から1文字読み込む（EOFなら空文字）

    f.seek(5)             # 再び「5バイト目」に戻す
    print(f.read(1))      # その位置から1文字読み込む
```
## ✨ 学習のまとめ
**` f.tell() `**
- 現在のファイルポインタ位置を返す。最初は 0。
**` f.read(n) `**
- 現在位置から n 文字（バイト）読み込む。読み込んだ分だけポインタが進む。
**` f.seek(pos) `**
- ファイルポインタを` pos `バイト目に移動する。次の読み込みはその位置から始まる。
 

<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る<a>
</div>




