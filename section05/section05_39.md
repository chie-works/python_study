## 39. while文とcontinue文とbreak文
#### 📝 VSCodeで実行
<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>

```bash
# while 条件で終了する基本パターン
count = 0
while count < 5:
    print(count)
    count += 1


# 無限ループを break/continue で制御するパターン
count = 0
while True:
    if count >= 5:
        break
    if count == 2:
        count += 1
        continue
    print(count)
    count += 1
```

<div align="right">
  <a href="../README.md#section5">READMEに戻る</a>
</div>
