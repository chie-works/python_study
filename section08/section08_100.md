## 100. zipfileの圧縮展開
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る</a>
</div>

**ライブラリの読み込み**
```python
import glob
import zipfile
```
**ZIPファイルの作成（単純にファイル/ディレクトリを追加）**
```python
with zipfile.ZipFile('test.zip', 'w') as z:
    z.write('test_dir')            # ディレクトリを追加（ただし展開時に扱いづらい）
    z.write('test_dir/test.txt')   # ファイルを追加
```

**ZIPファイルの作成（globで再帰的にファイルを追加）**
```python
with zipfile.ZipFile('test.zip', 'w') as z:
    # glob.glob('test_dir/**', recursive=True) → test_dir以下の全ファイル・ディレクトリを取得
    for f in glob.glob('test_dir/**', recursive=True):
        print(f)       # 追加対象のパスを表示
        z.write(f)     # ZIPに追加（ディレクトリも含まれる）
```

**ZIPファイルの展開と特定ファイルの読み込み**
```python
with zipfile.ZipFile('test.zip', 'r') as z:
    z.extractall('test_zip')   # ZIPを展開 → test_zipディレクトリに展開される
    # ZIP内の特定ファイルを直接開く（展開せずに読み込める）
    with z.open('test_dir/sub_dir/subsub_dir/subsub.txt') as f:
        print(f.read())        # ファイル内容をバイト列で表示（例: b'Hello\n'）
```
## ✨ 学習のまとめ

**` zipfile.ZipFile(filename, mode) `**
- ` w ` ：新規作成（既存ZIPは上書き）
- ` r ` ：読み込みモード

**` z.write(path) `**
- ファイルやディレクトリをZIPに追加
- ディレクトリを追加すると展開時に空フォルダとして扱われる

**` glob.glob('dir/*', recursive=True) `**
- ディレクトリ以下のファイル・サブディレクトリを再帰的に取得
- ZIPにまとめて追加するのに便利

**` z.extractall(path) `**
- ZIPを指定ディレクトリに展開

**` z.open(filename) `**
- ZIP内の特定ファイルを直接開いて読み込める
- ` f.read() `はバイト列を返すので、文字列として扱うなら` f.read().decode() `が必要


<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る<a>
</div>




