# コントリビューション
あらゆる種類のコントリビューションを歓迎します。
私たちは、コードだけでなくライブラリの他の側面（ドキュメント、Wiki など）についても、バグや機能のトラッキングに GitHub を使用しています。


## 質問する
一般的な質問をする最良の方法は、[メーリングリスト][2] にメールを送るか、[#glide-library on freenode.org][3] に参加することです。


## Issue の報告
迷ったら Issue を報告してください。問題が見過ごされるより、重複した Issue をいくつかクローズする方がましです。
同様に、特定の機能リクエストを支持する場合は、その Issue にコメントしてぜひお知らせください。

新しい Issue を報告する際は、Issue テンプレートを使用し、できる限りテンプレートに記入してください（無関係な部分は削除してください）。

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

[これをブックマークに保存するか、そのままクリック][1]すると、新しい Issue を作成できます。
提供していただける情報が多いほど、私たちが問題を解決できる可能性が高くなります。


## コードのコントリビューション
コードベースのすべての部分、特に統合ライブラリに関するプルリクエストを歓迎します。
プロジェクトのビルド方法については [README.md][5] を参照してください。
コードスタイルはリポジトリ内の Intellij プロジェクトファイルと Checkstyle 設定によって定義されています。
コードを投稿したいけれどスタイルチェックを通過させられない場合でも、遠慮なくプルリクエストを出してください。スタイルの問題の修正をお手伝いします。
コードをコントリビュートする場合は、[Google の個人コントリビューターライセンス契約][4] に署名する必要があります。忘れた場合、PR を作成する際に [googlebot](https://github.com/googlebot) から署名を求められます。


[1]: https://github.com/bumptech/glide/issues/new?body=**Glide%20Version/Integration%20library%20%28if%20any%29**%3A%0A**Device/Android%20Version**%3A%0A**Issue%20details/Repro%20steps/Use%20case%20background**%3A%0A%0A**Glide%20load%20line**%3A%0A%60%60%60java%0AGlide.with%28...%29.....load%28...%29.....into%28...%29%3B%0A%60%60%60%0A%0A**Layout%20XML**%3A%0A%60%60%60xml%0A%3C...Layout%3E%0A%20%20%20%20%3CImageView%20android%3AscaleType%3D%22...%22%20...%20/%3E%0A%3C/..Layout%3E%0A%60%60%60%0A%0A**Stack%20trace%20/%20LogCat**%3A%0A%60%60%60ruby%0Apaste%20stack%20trace%20here%0A%60%60%60
[2]: https://groups.google.com/forum/#!forum/glidelibrary
[3]: http://webchat.freenode.net/?channels=glide-library
[4]: https://developers.google.com/open-source/cla/individual
[5]: /bumptech/glide