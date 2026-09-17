<!-- github-global:langs:start -->
## 번역
[日本語](./translations/ja/README.md)
<!-- github-global:langs:end -->

Glide
=====

[![Build Status](https://travis-ci.org/bumptech/glide.svg?branch=master)](https://travis-ci.org/bumptech/glide)

Glide는 Android를 위한 빠르고 효율적인 오픈 소스 미디어 관리 및 이미지 로딩 프레임워크로, 미디어 디코딩, 메모리 및 디스크 캐싱, 리소스 풀링을 간단하고 사용하기 쉬운 인터페이스로 감싸 제공합니다.

![](static/glide_logo.png)

Glide는 비디오 스틸, 이미지, 애니메이션 GIF의 가져오기, 디코딩 및 표시를 지원합니다. Glide는 개발자가 거의 모든 네트워크 스택에 연결할 수 있는 유연한 API를 포함하고 있습니다. 기본적으로 Glide는 커스텀 `HttpUrlConnection` 기반 스택을 사용하지만, Google의 Volley 프로젝트나 Square의 OkHttp 라이브러리에 연결할 수 있는 유틸리티 라이브러리도 포함하고 있습니다.

Glide의 주요 초점은 이미지 목록의 스크롤을 최대한 부드럽고 빠르게 만드는 것이지만, 원격 이미지를 가져오고, 크기를 조정하고, 표시해야 하는 거의 모든 경우에도 효과적입니다.

다운로드
--------
GitHub의 [릴리스 페이지][1]에서 jar 파일을 다운로드할 수 있습니다.

또는 Gradle을 사용할 수 있습니다:

```gradle
repositories {
    mavenCentral()
}

dependencies {
    compile 'com.github.bumptech.glide:glide:3.6.1'
    compile 'com.android.support:support-v4:19.1.0'
}
```

또는 Maven을 사용할 수 있습니다:

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
proguard 설정 및 사용 방식에 따라 proguard.cfg에 다음 줄을 포함해야 할 수 있습니다:

```pro
-keep public class * implements com.bumptech.glide.module.GlideModule
-keep public enum com.bumptech.glide.load.resource.bitmap.ImageHeaderParser$** {
    **[] $VALUES;
    public *;
}
```

Glide는 어떻게 사용하나요?
-------------------
다양한 주제에 대한 페이지는 [GitHub 위키][2]를 참조하고, [javadoc][3]도 확인해 주세요.

간단한 사용 사례는 다음과 같습니다:

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

OkHttp 및 Volley
-----------------
OkHttp와 Volley에 대한 지원은 선택적으로 의존성으로 포함할 수 있는 통합 라이브러리를 통해 제공됩니다.
통합 라이브러리는 Maven 또는 [릴리스 페이지][1]를 통해 사용할 수 있습니다.

OkHttp 또는 Volley 통합 라이브러리를 포함하는 방법에 대한 지침은 [Integration Libraries][12] 위키 페이지를 참조하세요.

Android SDK 버전
-------------------
Glide는 최소 SDK 버전 10이 필요합니다.

라이선스
-------
BSD, 일부 MIT 및 Apache 2.0. 자세한 내용은 [LICENSE][16] 파일을 참조하세요.

상태
------
[*버전 3*][14]은 Android Camera 앱 및 2014 Google IO 앱을 포함하여 Google의 여러 오픈 소스 프로젝트에서 사용되는 안정적인 공개 릴리스입니다. *버전 4*는 현재 `master` 브랜치에서 개발 중입니다.
의견/버그/질문/풀 리퀘스트를 환영합니다!

빌드
------
Gradle로 Glide를 빌드하는 것은 매우 간단합니다:

```shell
git clone git@github.com:bumptech/glide.git # use https://github.com/bumptech/glide.git if "Permission Denied"
cd glide
git submodule init && git submodule update
./gradlew jar
```

**참고**: *Android SDK*에 *Android Support Repository*가 설치되어 있고, `$ANDROID_HOME` 환경 변수가 SDK를 가리키고 있는지 확인하거나, 루트 프로젝트에 `sdk.dir=...` 줄이 포함된 `local.properties` 파일을 추가하세요.

샘플
-------
[빌드](#build) 섹션의 단계에 따라 프로젝트를 설정한 후 다음을 실행하세요:

```shell
./gradlew :samples:flickr:run
./gradlew :samples:giphy:run
./gradlew :samples:svg:run
```
[릴리스 페이지][1]에서 미리 컴파일된 APK도 찾을 수 있습니다.

개발
-----------
[빌드](#build) 섹션의 단계에 따라 프로젝트를 설정한 후 원하는 대로 파일을 편집하세요.
[Intellij IDEA 14][4]는 Glide의 소스와 테스트를 모두 깔끔하게 가져올 수 있으며, Glide 작업에 권장되는 방법입니다.

Intellij 14에서 프로젝트를 열려면:

1. *File* 메뉴 또는 *Welcome Screen*으로 이동합니다.
2. *Open...*을 클릭합니다.
3. Glide의 루트 디렉터리로 이동합니다.
4. `build.gradle`을 선택합니다.

도움 받기
------------
특정 문제를 보고하거나 기능을 요청하려면 [GitHub에서 새 이슈를 열어주세요][5]. 질문, 제안 또는 기타 사항은 [Glide 토론 그룹][6]에 가입하거나 이메일을 보내주시거나, IRC 채널 [irc.freenode.net#glide-library][13]에 참여해 주세요.

기여하기
------------
풀 리퀘스트를 제출하기 전에 기여자는 Google의 [개인 기여자 라이선스 계약][7]에 서명해야 합니다.

감사의 말
------
* Glide의 디스크 캐시의 기반이 된 [디스크 캐시 구현][8]을 제공한 **Android 팀**과 **Jake Wharton**님.
* Glide의 gif 디코더의 기반이 된 [gif 디코더 gist][9]를 제공한 **Dave Smith**님.
* [gradle-mvn-push][10] 스크립트를 제공한 **Chris Banes**님.
* Glide의 [멋진 로고][11]를 만든 **Corey Hall**님.
* 코드를 기여하고 이슈를 보고해 주신 모든 분들!

작성자
------
Sam Judd - @samajudd

면책 조항
---------
이것은 공식 Google 제품이 아닙니다.

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