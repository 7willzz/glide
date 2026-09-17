<!-- github-global:langs:start -->
## 翻譯
[日本語](./translations/ja/README.md)
<!-- github-global:langs:end -->

Glide
=====

[![Build Status](https://travis-ci.org/bumptech/glide.svg?branch=master)](https://travis-ci.org/bumptech/glide)

Glide 是一個適用於 Android 的高速且高效能的開源媒體管理與圖片載入框架，它將媒體解碼、記憶體與磁碟快取以及資源池化封裝在一個簡單易用的介面中。

![](static/glide_logo.png)

Glide 支援擷取、解碼與顯示影片縮圖、圖片以及動畫 GIF。Glide 提供了一個彈性的 API，讓開發者能夠接入幾乎任何網路堆疊。預設情況下，Glide 使用基於自訂 `HttpUrlConnection` 的堆疊，但也包含可接入 Google 的 Volley 專案或 Square 的 OkHttp 函式庫的公用程式庫。

Glide 的首要目標是讓任何形式的圖片清單捲動盡可能流暢快速，但 Glide 也適用於幾乎任何需要擷取、調整大小並顯示遠端圖片的情境。

下載
--------
你可以從 GitHub 的 [releases 頁面][1] 下載 jar 檔。

或使用 Gradle：

```gradle
repositories {
    mavenCentral()
}

dependencies {
    compile 'com.github.bumptech.glide:glide:3.6.1'
    compile 'com.android.support:support-v4:19.1.0'
}
```

或使用 Maven：

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
根據你的 proguard 設定與使用方式，你可能需要在 proguard.cfg 中加入以下幾行：

```pro
-keep public class * implements com.bumptech.glide.module.GlideModule
-keep public enum com.bumptech.glide.load.resource.bitmap.ImageHeaderParser$** {
    **[] $VALUES;
    public *;
}
```

如何使用 Glide？
-------------------
請參閱 [GitHub wiki][2] 以了解各種主題的頁面，並查看 [javadocs][3]。

簡單的使用範例如下：

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

OkHttp 與 Volley
-----------------
對 OkHttp 與 Volley 的支援由整合函式庫提供，你可以選擇性地將其加入為相依套件。
這些整合函式庫可透過 Maven 或 [releases 頁面][1] 取得。

有關加入 OkHttp 或 Volley 整合函式庫的說明，請參閱 [Integration Libraries][12] wiki 頁面。

Android SDK 版本
-------------------
Glide 要求最低 SDK 版本為 10。

授權條款
-------
BSD，部分為 MIT 與 Apache 2.0。詳情請參閱 [LICENSE][16] 檔案。

狀態
------
[*第 3 版*][14] 是一個穩定的公開版本，已在 Google 的多個開源專案中使用，包括 Android 相機應用程式以及 2014 年的 Google IO 應用程式。*第 4 版* 目前正在 `master` 分支上開發中。
歡迎提供意見／回報錯誤／提問／提交 pull request！

建置
------
使用 gradle 建置 Glide 相當簡單直接：

```shell
git clone git@github.com:bumptech/glide.git # use https://github.com/bumptech/glide.git if "Permission Denied"
cd glide
git submodule init && git submodule update
./gradlew jar
```

**注意**：請確保你的 *Android SDK* 已安裝 *Android Support Repository*，並且你的 `$ANDROID_HOME` 環境變數指向該 SDK，或在專案根目錄中新增一個包含 `sdk.dir=...` 一行的 `local.properties` 檔案。

範例
-------
依照 [Build](#build) 章節中的步驟設定專案，然後執行：

```shell
./gradlew :samples:flickr:run
./gradlew :samples:giphy:run
./gradlew :samples:svg:run
```
你也可以在 [releases 頁面][1] 上找到預先編譯的 APK。

開發
-----------
依照 [Build](#build) 章節中的步驟設定專案，然後依你的需求編輯檔案。
[Intellij IDEA 14][4] 可以順利匯入 Glide 的原始碼與測試，是使用 Glide 的建議方式。

若要在 Intellij 14 中開啟專案：

1. 前往 *File* 選單或 *Welcome Screen*
2. 點擊 *Open...*
3. 導覽至 Glide 的根目錄。
4. 選擇 `build.gradle`

取得協助
------------
若要回報特定問題或提出功能請求，請[在 Github 上開啟新的 issue][5]。若有問題、建議或其他任何事項，請加入或寄信至 [Glide 的討論群組][6]，或加入我們的 IRC 頻道：[irc.freenode.net#glide-library][13]。

貢獻
------------
在提交 pull request 之前，貢獻者必須簽署 Google 的[個人貢獻者授權協議][7]。

致謝
------
* 感謝 **Android 團隊** 與 **Jake Wharton** 提供 Glide 磁碟快取所基於的[磁碟快取實作][8]。
* 感謝 **Dave Smith** 提供 Glide 的 gif 解碼器所基於的 [gif decoder gist][9]。
* 感謝 **Chris Banes** 提供他的 [gradle-mvn-push][10] 腳本。
* 感謝 **Corey Hall** 為 Glide 設計的[精美標誌][11]。
* 感謝所有貢獻程式碼與回報問題的人！

作者
------
Sam Judd - @samajudd

免責聲明
---------
這不是 Google 的官方產品。

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