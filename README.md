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
## 翻譯需要多久的時間，才會上傳到程式的主分支？
每一天會檢查一次 po 檔案，當 po 檔案翻譯到一定的水準時就會發 request 至程式原始庫。
