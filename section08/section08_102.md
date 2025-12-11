## 102. subprocessでコマンドを実行する
#### 🖥 VSCodeで実行
<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る</a>
</div>

**外部コマンドを実行する**
```python
import subprocess

subprocess.run(["cmd", "/c", "ver"])  # 例: Windowsのバージョンを表示
```
**PowerShellを呼び出す**
```python
import subprocess

subprocess.run(["powershell", "Get-ChildItem"]) # PowerShellで Get-ChildItem を実行
```

**出力をPythonで受け取る**
```python
import subprocess

result = subprocess.run(["cmd", "/c", "dir"], capture_output=True, text=True)
print(result.stdout)
```

## ✨ 学習のまとめ
- cmd.exe を呼ぶ ：`  ["cmd", "/c", "dir"] `
- PowerShellを呼ぶ ： ` ["powershell", "Get-ChildItem"] `
- 出力をPythonで処理する ： ` capture_output=True `を使う
- 安全性重視 ： ` shell=True `は避け、リスト形式で渡す
 

<div align="right">
  <a href="../README.md#section8">◀️READMEに戻る<a>
</div>




