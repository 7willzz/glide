# 貢献
あらゆる種類の貢献を歓迎します。
私たちは GitHub を、コードだけでなくライブラリのその他の側面(ドキュメント、Wiki など)に関するバグや機能のトラッカーとして使用しています。


## 質問
一般的な質問をする最良の方法は、[メーリングリスト][2]にメールを送るか、[freenode.org の #glide-library][3] に参加することです。


## Issue の報告
迷ったときは、Issue を報告してください。問題に気づかれないままにするよりも、重複した Issue をいくつかクローズする方がましです。
同様に、特定の機能リクエストを支持する場合は、Issue にコメントしてお知らせください。

新しい Issue を報告する際は、Issue テンプレートを使用し、できる限り多くの項目を記入してください(無関係な部分は削除してください)。

<pre>**Glide のバージョン/統合ライブラリ(あれば)**:
**デバイス/Android バージョン**:
**Issue の詳細/再現手順/ユースケースの背景**:

**Glide のロード行**:
```java
Glide.with(...).....load(...).....into(...);
```

**レイアウト XML**:
```xml
&lt;...Layout&gt;
    &lt;ImageView android:scaleType="..." ... /&gt;
&lt;/..Layout&gt;
```

**スタックトレース / LogCat**:
```ruby
paste stack trace here
```
</pre>

[これをブックマークに保存するか、そのままクリック][1]して、新しい Issue を作成できます。
提供していただける情報が多ければ多いほど、私たちが助けになれる可能性が高くなります。


## コードの貢献
コードベースのすべての部分、特に統合ライブラリに関するプルリクエストを歓迎します。
プロジェクトのビルド手順は [README.md][5] にあります。
コードスタイルは、リポジトリ内の Intellij プロジェクトファイルと Checkstyle の設定で定義されています。
コードを提出したいけれどスタイルチェックを通過させられない場合は、そのままプルリクエストを出していただいて構いません。スタイルの問題の修正をお手伝いします。
コードを貢献する場合は、[Google の個人コントリビューターライセンス契約][4]に署名する必要があります。署名を忘れた場合は、PR を作成する際に [googlebot](https://github.com/googlebot) から求められます。


[1]: https://github.com/bumptech/glide/issues/new?body=**Glide%20Version/Integration%20library%20%28if%20any%29**%3A%0A**Device/Android%20Version**%3A%0A**Issue%20details/Repro%20steps/Use%20case%20background**%3A%0A%0A**Glide%20load%20line**%3A%0A%60%60%60java%0AGlide.with%28...%29.....load%28...%29.....into%28...%29%3B%0A%60%60%60%0A%0A**Layout%20XML**%3A%0A%60%60%60xml%0A%3C...Layout%3E%0A%20%20%20%20%3CImageView%20android%3AscaleType%3D%22...%22%20...%20/%3E%0A%3C/..Layout%3E%0A%60%60%60%0A%0A**Stack%20trace%20/%20LogCat**%3A%0A%60%60%60ruby%0Apaste%20stack%20trace%20here%0A%60%60%60
[2]: https://groups.google.com/forum/#!forum/glidelibrary
[3]: http://webchat.freenode.net/?channels=glide-library
[4]: https://developers.google.com/open-source/cla/individual
[5]: /bumptech/glide