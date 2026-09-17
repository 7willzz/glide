Glide
=====

[![Build Status](https://travis-ci.org/bumptech/glide.svg?branch=master)](https://travis-ci.org/bumptech/glide)

Glide は、メディアのデコード、メモリおよびディスクキャッシング、リソースのプーリングをシンプルで使いやすいインターフェースにまとめた、Android 向けの高速かつ効率的なオープンソースのメディア管理・画像読み込みフレームワークです。

![](static/glide_logo.png)

Glide は、動画の静止画、画像、アニメーション GIF の取得、デコード、表示をサポートしています。Glide には柔軟な API が含まれており、開発者はほぼすべてのネットワークスタックに組み込むことができます。デフォルトでは、Glide はカスタムの `HttpUrlConnection` ベースのスタックを使用しますが、Google の Volley プロジェクトや Square の OkHttp ライブラリに組み込むためのユーティリティライブラリも含まれています。

Glide の主な目的は、あらゆる種類の画像リストのスクロールを可能な限り滑らかかつ高速にすることですが、リモート画像の取得、リサイズ、表示が必要なほぼすべてのケースにおいても効果的です。

ダウンロード
--------
GitHub の [releases ページ][1] から jar をダウンロードできます。

または、Gradle を使用します:

```gradle
repositories {
    mavenCentral()
}

dependencies {
    compile 'com.github.bumptech.glide:glide:3.6.1'
    compile 'com.android.support:support-v4:19.1.0'
}
```

または、Maven を使用します:

```xml
<dependency>
    <groupId>com.github.bumptech.glide</groupId>
    <artifactId>glide</artifactId>
    <version>3.6.1</version>
    <type>aar</type>
</dependency>
<dependency>
    <groupId>com.google.android</groupId>
    <artifactId>support-v4</artifactId>
    <version>r7</version>
</dependency>
```

Proguard
--------
proguard の設定や使用方法によっては、proguard.cfg に以下の行を追加する必要がある場合があります:

```pro
-keep public class * implements com.bumptech.glide.module.GlideModule
-keep public enum com.bumptech.glide.load.resource.bitmap.ImageHeaderParser$** {
    **[] $VALUES;
    public *;
}
```

Glide の使い方は？
-------------------
さまざまなトピックに関するページについては [GitHub wiki][2] を、javadoc については [javadocs][3] を参照してください。

シンプルな使用例は以下のようになります:

```java
// For a simple view:
@Override
public void onCreate(Bundle savedInstanceState) {
    ...
    ImageView imageView = (ImageView) findViewById(R.id.my_image_view);

    Glide.with(this).load("http://goo.gl/gEgYUd").into(imageView);
}

// For a simple image list:
@Override
public View getView(int position, View recycled, ViewGroup container) {
    final ImageView myImageView;
    if (recycled == null) {
        myImageView = (ImageView) inflater.inflate(R.layout.my_image_view, container, false);
    } else {
        myImageView = (ImageView) recycled;
    }

    String url = myUrls.get(position);

    Glide.with(myFragment)
        .load(url)
        .centerCrop()
        .placeholder(R.drawable.loading_spinner)
        .crossFade()
        .into(myImageView);

    return myImageView;
}

```

OkHttp と Volley
-----------------
OkHttp と Volley のサポートは、依存関係として任意で組み込める統合ライブラリによって提供されます。統合ライブラリは、Maven または [releases ページ][1] から入手できます。

OkHttp または Volley 統合ライブラリの組み込み手順については、[Integration Libraries][12] の wiki ページを参照してください。

Android SDK バージョン
-------------------
Glide には最小 SDK バージョン 10 が必要です。

ライセンス
-------
BSD、一部 MIT および Apache 2.0。詳細については [LICENSE][16] ファイルを参照してください。

ステータス
------
[*バージョン 3*][14] は安定した公開リリースであり、Google の Android Camera アプリや 2014 年の Google IO アプリを含む複数のオープンソースプロジェクトで使用されています。*バージョン 4* は現在 `master` ブランチで開発中です。コメント・バグ報告・質問・プルリクエストを歓迎します！

ビルド
------
Gradle で Glide をビルドするのは非常に簡単です:

```shell
git clone git@github.com:bumptech/glide.git # use https://github.com/bumptech/glide.git if "Permission Denied"
cd glide
git submodule init && git submodule update
./gradlew jar
```

**注意**: *Android SDK* に *Android Support Repository* がインストールされていること、および `$ANDROID_HOME` 環境変数が SDK を指していることを確認してください。または、プロジェクトのルートに `sdk.dir=...` の行を含む `local.properties` ファイルを追加してください。

サンプル
-------
[Build](#build) セクションの手順に従ってプロジェクトをセットアップし、その後以下を実行します:

```shell
./gradlew :samples:flickr:run
./gradlew :samples:giphy:run
./gradlew :samples:svg:run
```
ビルド済みの APK は [releases ページ][1] でも入手できます。

開発
-----------
[Build](#build) セクションの手順に従ってプロジェクトをセットアップし、その後自由にファイルを編集してください。[Intellij IDEA 14][4] は Glide のソースとテストの両方を問題なくインポートでき、Glide の開発に推奨される方法です。

Intellij 14 でプロジェクトを開くには:

1. *File* メニューまたは *Welcome Screen* に移動します
2. *Open...* をクリックします
3. Glide のルートディレクトリに移動します。
4. `build.gradle` を選択します

ヘルプの取得
------------
特定の問題や機能リクエストを報告するには、[GitHub で新しい issue を開いてください][5]。質問、提案、その他については、[Glide のディスカッショングループ][6] に参加またはメールを送るか、IRC チャンネル [irc.freenode.net#glide-library][13] に参加してください。

コントリビューション
------------
プルリクエストを提出する前に、コントリビューターは Google の[個人コントリビューターライセンス契約][7]に署名する必要があります。

謝辞
------
* Glide のディスクキャッシュの基盤となっている[ディスクキャッシュ実装][8]について、**Android チーム** と **Jake Wharton** に感謝します。
* Glide の gif デコーダーの基盤となっている [gif デコーダー gist][9] について、**Dave Smith** に感謝します。
* [gradle-mvn-push][10] スクリプトについて、**Chris Banes** に感謝します。
* Glide の[素晴らしいロゴ][11]について、**Corey Hall** に感謝します。
* コードをコントリビュートし、issue を報告してくれたすべての方々に感謝します！

作者
------
Sam Judd - @samajudd

免責事項
---------
これは Google の公式製品ではありません。

[1]: https://github.com/bumptech/glide/releases
[2]: https://github.com/bumptech/glide/wiki
[3]: http://bumptech.github.io/glide/javadocs/latest/index.html
[4]: https://www.jetbrains.com/idea/download/
[5]: https://github.com/bumptech/glide/issues/new?body=**Glide%20Version/Integration%20library%20%28if%20any%29**%3A%0A**Device/Android%20Version**%3A%0A**Issue%20details/Repro%20steps/Use%20case%20background**%3A%0A%0A**Glide%20load%20line**%3A%0A%60%60%60java%0AGlide.with%28...%29.....load%28...%29.....into%28...%29%3B%0A%60%60%60%0A%0A**Layout%20XML**%3A%0A%60%60%60xml%0A%3C...Layout%3E%0A%20%20%20%20%3CImageView%20android%3AscaleType%3D%22...%22%20...%20/%3E%0A%3C/..Layout%3E%0A%60%60%60%0A%0A**Stack%20trace%20/%20LogCat**%3A%0A%60%60%60ruby%0Apaste%20stack%20trace%20here%0A%60%60%60
[6]: https://groups.google.com/forum/#!forum/glidelibrary
[7]: https://developers.google.com/open-source/cla/individual
[8]: https://github.com/JakeWharton/DiskLruCache
[9]: https://gist.github.com/devunwired/4479231
[10]: https://github.com/chrisbanes/gradle-mvn-push
[11]: static/glide_logo.png
[12]: https://github.com/bumptech/glide/wiki/Integration-Libraries
[13]: http://webchat.freenode.net/?channels=glide-library
[14]: https://github.com/bumptech/glide/tree/3.0
[15]: https://github.com/bumptech/glide/tree/master
[16]: https://github.com/bumptech/glide/blob/master/LICENSE