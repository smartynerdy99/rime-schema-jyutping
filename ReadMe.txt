RIME 粵拼輸入法方案
===================


各文件用途：

- jyutping_zeng.schema.yaml RIME 拼字方案
- jyutping_zeng*.dict.yaml RIME 編碼方案
- refs/ 存放參考資料
  - chart.txt 查漏表格（內含非粵字）
  - Unihan/ 從 Unihan 數據庫中抽取的數據
    - trad2simp.txt 繁簡字對應表
    - variants.txt 異體字對應表
    - radicals.txt 康熙字典索引部首及獨立漢字對應表
    - jyutping.txt 粵字拼音碼表
  + OpenCC/ 「開放中文轉換」項目提供的資料
    https://github.com/BYVoid/OpenCC
- scripts/ 存放輔助文字處理之 BASH 腳本
  - GenDictData 用於產生 Unihan 粵字拼音碼表
  - GenSimpList 用於產生 Unihan 繁簡字對應表
  - GenVariants 用於產生 Unihan 異體字對應表
  - GetUserDict 用於取得 RIME 自動組詞數據
  - DelUserDict 用於清空 RIME 自動組詞數據
  - Deploy 用於部署拼寫及編碼方案
  - DeployDicts 僅用於部署編碼方案（辭典）
- web/
  - sort.html 可離線使用的排序工具。
    https://jyutping.github.io/rime-schema-jyutping/web/sort.html

[Unihan]: http://www.unicode.org/Public/8.0.0/ucd/Unihan.zip
          該壓縮包附有大量珍貴資訊，如字頻、拼音、形碼等。

[Unicode]: http://www.unicode.org/Public/8.0.0/
           該網站還提供了中日韓字表，康熙檢字表，及其它有用資料。


各文件內附註記：

- jyutping_zeng.schema.yaml RIME 拼字方案
  記有特殊功能：輸入中途切換漢語拼音或倉頡（蒼頡）碼模式或反查模式。
  以及說明方便普通用戶自行加入個人詞條或其它自定編碼所需建立的文件。
- jyutping_zeng.dict.yaml RIME 編碼方案
  介紹了好幾個有用的參考資料網站，以及編輯碼表注意事項。
- jyutping_zeng-*.dict.yaml
  拆分好的附屬辭典。

假如你有信心，亦不妨嘗試直接編輯以上文件。
將以上文件放置於用戶配置文件夾，然後重新部署 RIME 即可使用。

請留意調試信息（例如，存在重碼，自動註音時缺音，文件加載失敗）：
- 中州韻 /tmp/rime.ibus.*
- 小狼毫 %TEMP%\rime.weasel.*
- 鼠鬚管 $TMPDIR/rime.squirrel.*
調試時記得清空自動生成的用戶詞典 jyutping_zeng.userdb 清除副作用。

更詳盡的說明請見以下網上文檔：

RIME Wiki
https://github.com/rime/home/wiki
RIME 配置詳解
https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md


開發任務：

- 蒐集詞彙及讀音。
- 調整常用字字頻。
- 調整罕用字字頻。
- 調整簡化字字頻。
- 調整正讀、異讀、訓讀、破讀、懶音、错音相關字頻。

如發現错音漏音，請先在 chart.txt 做好標記。
若某字於詞彙中有變音，無必要另添單字字音，除非還有更多詞句使用該字音。

絕大部分數據均爲 TSV 格式，稍加編輯後即可以導入至辦公軟件提供的表格編輯工具。
提交新詞條時，可以提交 pull requests，或者直接新開一個 issue 並按以下格式記錄：
```
詞條1,粵拼,權重,備註
詞條2,粵拼,權重,備註
```
分隔符【,】可以被替換成任何符號，只要易於識别便可。
粵拼、權重以及備註均可略去不填。

另，在下非專業人士，若有錯漏，敬請多多指正。

你亦可以經由其它途徑間接爲該項目作出貢獻：

* 粵典網 words.hk
  開放的粵語網絡辭典。目前尚在開發中。若想參與編輯，請先加入 Facebook 小組：
  https://www.facebook.com/groups/words.hk.editors/


版權相關
========

該項目的資料未經同意，不可用於商業用途。

使用時請注明來源，確保大衆可以隨時取得最新信息，推進粵語發展。多謝合作。
