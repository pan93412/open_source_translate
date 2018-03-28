# 開源專案翻譯庫
翻譯開源專案的 Git 庫，接受 Pull request。
## 如何上傳翻譯
透過 pull request 將您的更新上傳至 "guest" Git 分支。

若翻譯有一定貢獻者，會提供 Git 的讀寫權限。
## 如何翻譯
參閱 [自由軟體翻譯守則](https://docs.google.com/document/d/1Zs4CS_ZjN-imnImq4aEsiVYih8zkIkVZTSQim13_kYg)

翻譯軟體可使用 POEdit、Lokalize 等工具。翻譯後請透過 `msgfmt` 指令檢查更新檔案。
```
msgfmt -c /your/po/file
```

若要合併最新來源的 pot 檔案，請使用 `msgmerge` 指令：
```
msgmerge -o ./output_file.po source_file.po pot_file.pot
```
## FAQ
### 翻譯需要多久的時間，才會上傳到程式的主分支？
每一天會檢查一次 po 檔案，當 po 檔案翻譯到一定的水準時就會發 request 至程式原始庫。

### `vdragon` 分支是？
vdragon 為這個項目的貢獻人之一。而 vdragon 分支是他自己的翻譯進度。

請勿發 PR 至該分支。

### master、guest 分支的差別？
- master
  驗證完成的內容，即將要將翻譯傳至上游。
- guest
  **未經驗證** 的內容，假如你是要將翻譯編譯成 mo 檔案並自用，**建議不要使用這個 branch 的版本**
- 其他 branch
  **未經驗證、甚至未翻譯完成** 的內容。同 guest 建議

### 我要如何在上游發布翻譯更新前，套用最新版本的翻譯？
使用 `msgfmt` 工具生成 mo 檔案，指令如下：
```
msgfmt -o [程式名稱].mo po_filename.po
```

使用 `[程式名稱].mo` 的原因在於 **大多數的程式 mo 檔案都是以 程式名稱.mo 命名**

然後將翻譯放至 /usr/share/locale/zh_TW/LC_MESSAGES，覆蓋原 [程式名稱].mo 即可。
