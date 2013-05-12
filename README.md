說明
------------------
通過本插件，您可以編輯並保存目前編碼不被Sublime Text 支持的文件，特別是中日韓用戶使用的GB2312，GBK，BIG5，EUC-KR，EUC-JP 等。

![ConvertToUTF8](http://dl.dropbox.com/u/31937639/ConvertToUTF8/ConvertToUTF8.gif)

我現在正努力讓ConvertToUTF8 同時支持Sublime Text 2 和3。如果您覺得本插件對您有所幫助，您可以請我喝杯咖啡讓我保持清醒。謝！ :)

注意
------------------
** Linux 用戶：Sublime Text 2 和3 內嵌Python 版本中缺失幾個ConvertToUTF8 依賴的動態庫。您必須手工安裝這些文件才能讓本插件完全運作。

** OS X 用戶：Sublime Text 3 使用的內嵌Python 存在與Linux 版本相同的問題。

** 我已將此問題報告給Jon 但未收到任何回复，因此我將創建額外的插件來解決它。如果您急於在發布之前使用本插件，請與我聯繫獲取更多信息。

安裝
------------------
推薦使用[Package Control](http://wbond.net/sublime_packages/package_control) 查找*ConvertToUTF8* 進行自動下載安裝與更新。

如需手工安裝，請將本項目打包下載並解壓，將解壓後的文件夾名修改為*ConvertToUTF8* ，然後將此文件夾移動到Sublime Text 的*Packages* 文件夾下（可通過Sublime Text 菜單中的Preferences > Browse Packages 找到*Packages* 文件夾）。

您的文件夾應該看起來是這樣的：

![Folder Hierarchy](http://dl.dropbox.com/u/31937639/ConvertToUTF8/hierarchy.png)

設置
------------------
請查看ConvertToUTF8.sublime-settings 文件獲取詳細信息。為防止更新插件時被覆蓋，請將個人設置保存到User 目錄中名為ConvertToUTF8.sublime-settings 文件中。

* encoding_list：檢測失敗時顯示的編碼列表
* max_cache_size：最大編碼緩存數量，0 表示不緩存（默認為100）
* max_detect_lines：最大檢測行數，0 表示不限制（默認為600）
* preview_action：指定預覽模式下的動作，可選項：no_action 不作任何動作，convert_and_open 轉換編碼並打開（默認為no_action）
* default_encoding_on_create：指定新建文件的默認編碼（如GBK），空值表示使用Sublime Text 的default_encoding 設置（默認為空值）
* convert_on_load：啟用/禁用文件裝載時將窗口內容轉換成UTF-8編碼，可選項：always 自動轉換，never 不轉換（默認為always）
* convert_on_save：啟用/禁用文件保存時將其從UTF-8轉換成指定轉碼，可選項：always 自動轉換，never 不轉換（默認為always）

使用說明
------------------
多數情況下，本插件將自動對處理編碼相關的事項。

您也可以通過File > Set File Encoding to 菜單對文件編碼進行手工轉換。例如，您可以打開一個UTF-8 編碼的文件，指定保存為GBK，反之亦然。

注意：
* 如果convert_on_save 被設置為never，文件不會被保存成指定編碼
* 在文件編碼檢測過程完成前請勿編輯文件
* 若檢測結果不准確，請嘗試增大max_detect_lines 的值或手工指定編碼


常見問題
------------------
* 問：安裝後無法工作，要如何修復？

  答：請嘗試以下步驟：
  1. 重啟 Sublime Text
  2. 請確認插件目錄名為ConvertToUTF8（如果是通過Package Control 安裝的可略過此步驟）
  3. 參見[上述“注意”條目](#注意)
  4. 禁用其他編碼相關的插件
  5. 聯繫我

* 問：這個插件支持哪些編碼？

  答：只要您的系統支持的編碼應該都可使用。

* 問：為何有時重新激活窗口，裡面的內容會變亂碼？

  答：此問題是由重新載入引起的，且已修復，請更新*ConvertToUTF8* 插件到最新版本。

* 問：為什麼重新激活窗口時，ST2 問我文件“已經被修改。是否要重新載入？”

  答：原因與上一條相同。如果您有未保存的修改，請選擇“取消”。

* 問：在保存文件時，Sublime Text 為什麼提示將文件保存為UTF-8？

  答：沒有關係，本插件會自動將文件內容保存為原始編碼。

* 問：我的文件被保存為UTF-8，而且變成了亂碼，要如何恢復？

  答：請打開這個文件，並確認它的編碼是UTF-8，然後選擇菜單項目“File -> Save with Encoding -> Western (Windows 1252)”，關閉再重新打開該文件即可。

聯繫我
------------------
請發送您的問題或建議給我：sunlxy (at) yahoo.com 或http://weibo.com/seanliang