# 開源專案翻譯庫
翻譯開源專案的 Git 庫。

## 如何參與翻譯
### 如何加入翻譯
發 issues 表示自己想加入這個開源專案翻譯庫。

### 如何翻譯
參閱 [自由軟體翻譯守則](https://docs.google.com/document/d/1Zs4CS_ZjN-imnImq4aEsiVYih8zkIkVZTSQim13_kYg)

當你準備要翻譯某個程式，那就直接 clone 後翻譯，
但建議翻譯一個程度後提交 (commit) 並推送 (push)。

翻譯軟體可使用 Poedit、Lokalize 等工具。翻譯後請透過 `msgfmt` 指令檢查更新檔案。
```
msgfmt -o /dev/null -c /your/po/file
```
> dev/null 的效果類似 Windows 上的 `>nil`

若要合併最新來源的 pot 檔案，請使用 `msgmerge` 指令：
```
msgmerge -o ./output_file.po source_file.po pot_file.pot
```
## FAQ
### 翻譯需要多久的時間，才會上傳到程式的主分支？
每一天會檢查一次 po 檔案，當 po 檔案翻譯到一定的水準時就會發 request 至程式原始庫。

### 我要如何在上游發布翻譯更新前，套用最新版本的翻譯？
使用 `msgfmt` 工具生成 mo 檔案，指令如下：
```
msgfmt -o [程式名稱].mo po_filename.po
```

使用 `[程式名稱].mo` 的原因在於 **大多數的程式 mo 檔案都是以 程式名稱.mo 命名**

然後將翻譯放至 /usr/share/locale/zh_TW/LC_MESSAGES，覆蓋原 [程式名稱].mo 即可。
### 我該如何寫 commit 紀錄？
- 不需太複雜
- 中英文皆可，但大部分會看 commit 記錄的人都能看得懂中文，所以不必強迫自己使用中文。

#### 範本
* (軟體名稱) 翻譯完成
* 多個軟體翻譯完成
* 翻譯完成

