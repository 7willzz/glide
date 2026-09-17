# 貢獻指南
歡迎任何形式的貢獻。
我們使用 GitHub 來追蹤程式碼以及函式庫其他面向（文件、wiki 等）的錯誤與功能需求。


## 提出問題
提出一般性問題的最佳方式是發送電子郵件到我們的[郵件列表][2]，或加入 [#glide-library on freenode.org][3]。


## 回報問題
如有疑問，請回報 issue。我們寧可關閉幾個重複的 issue，也不願讓問題被忽略。
同樣地，如果你支持某個特定的功能請求，歡迎在該 issue 下留言讓我們知道。

若要回報新問題，請使用我們的 issue 範本，並盡可能填寫範本內容（移除不相關的部分）。

<pre>**Glide Version/Integration library (if any)**:
**Device/Android Version**:
**Issue details/Repro steps/Use case background**:

**Glide load line**:
```java
Glide.with(...).....load(...).....into(...);
```

**Layout XML**:
```xml
&lt;...Layout&gt;
    &lt;ImageView android:scaleType="..." ... /&gt;
&lt;/..Layout&gt;
```

**Stack trace / LogCat**:
```ruby
paste stack trace here
```
</pre>

你可以將[這個連結儲存為書籤或直接點擊][1]來建立新的 issue。
你提供的資訊越多，我們就越有可能幫得上忙。


## 貢獻程式碼
歡迎對程式碼庫的任何部分提交 Pull Request，尤其是整合函式庫（integration libraries）。
你可以在 [README.md][5] 中找到建置專案的說明。
我們的程式碼風格定義於 repo 中的 Intellij 專案檔，以及我們的 Checkstyle 設定中。
如果你想提交程式碼，但無法通過風格檢查，還是歡迎直接提交你的 Pull Request，我們可以協助你修正風格問題。
如果你想貢獻程式碼，你需要簽署 [Google 的個人貢獻者授權協議][4]；如果你忘記簽署，當你建立 PR 時 [googlebot](https://github.com/googlebot) 會提醒你。


[1]: https://github.com/bumptech/glide/issues/new?body=**Glide%20Version/Integration%20library%20%28if%20any%29**%3A%0A**Device/Android%20Version**%3A%0A**Issue%20details/Repro%20steps/Use%20case%20background**%3A%0A%0A**Glide%20load%20line**%3A%0A%60%60%60java%0AGlide.with%28...%29.....load%28...%29.....into%28...%29%3B%0A%60%60%60%0A%0A**Layout%20XML**%3A%0A%60%60%60xml%0A%3C...Layout%3E%0A%20%20%20%20%3CImageView%20android%3AscaleType%3D%22...%22%20...%20/%3E%0A%3C/..Layout%3E%0A%60%60%60%0A%0A**Stack%20trace%20/%20LogCat**%3A%0A%60%60%60ruby%0Apaste%20stack%20trace%20here%0A%60%60%60
[2]: https://groups.google.com/forum/#!forum/glidelibrary
[3]: http://webchat.freenode.net/?channels=glide-library
[4]: https://developers.google.com/open-source/cla/individual
[5]: /bumptech/glide