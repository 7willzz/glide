# 기여하기
모든 유형의 기여를 환영합니다.
저희는 코드뿐만 아니라 라이브러리의 다른 측면(문서, 위키 등)에 대해서도 GitHub를 버그 및 기능 트래커로 사용합니다.


## 질문하기
일반적인 질문을 하는 가장 좋은 방법은 [메일링 리스트][2]로 이메일을 보내거나 [#glide-library on freenode.org][3]에 참여하는 것입니다.


## 이슈 등록하기
확실하지 않으면 이슈를 등록하세요. 문제가 간과되는 것보다 중복 이슈를 몇 개 닫는 편이 낫습니다.
마찬가지로 특정 기능 요청을 지지한다면, 해당 이슈에 댓글을 달아 알려주세요.

새 이슈를 등록하려면 이슈 템플릿을 사용하고, 관련 없는 부분은 제거하면서 최대한 템플릿을 자세히 작성해 주세요.

<pre>**Glide 버전/통합 라이브러리 (있다면)**:
**기기/Android 버전**:
**이슈 상세/재현 단계/사용 사례 배경**:

**Glide 로드 라인**:
```java
Glide.with(...).....load(...).....into(...);
```

**레이아웃 XML**:
```xml
&lt;...Layout&gt;
    &lt;ImageView android:scaleType="..." ... /&gt;
&lt;/..Layout&gt;
```

**스택 트레이스 / LogCat**:
```ruby
paste stack trace here
```
</pre>

[이것을 북마크로 저장하거나 클릭][1]하여 새 이슈를 생성할 수 있습니다.
제공하는 정보가 많을수록 도움을 드릴 가능성이 높아집니다.


## 코드 기여하기
코드베이스의 모든 부분, 특히 통합 라이브러리에 대한 풀 리퀘스트를 환영합니다.
프로젝트 빌드 방법은 [README.md][5]에서 확인할 수 있습니다.
저희 코드 스타일은 저장소의 Intellij 프로젝트 파일과 Checkstyle 설정에 정의되어 있습니다.
코드를 제출하고 싶지만 스타일 검사를 통과하지 못하는 경우, 그래도 풀 리퀘스트를 올려주시면 스타일 문제를 해결하도록 도와드리겠습니다.
코드를 기여하려면 [Google 개인 기여자 라이선스 계약][4]에 서명해야 하며, 잊으신 경우 PR을 생성할 때 [googlebot](https://github.com/googlebot)이 요청할 것입니다.


[1]: https://github.com/bumptech/glide/issues/new?body=**Glide%20Version/Integration%20library%20%28if%20any%29**%3A%0A**Device/Android%20Version**%3A%0A**Issue%20details/Repro%20steps/Use%20case%20background**%3A%0A%0A**Glide%20load%20line**%3A%0A%60%60%60java%0AGlide.with%28...%29.....load%28...%29.....into%28...%29%3B%0A%60%60%60%0A%0A**Layout%20XML**%3A%0A%60%60%60xml%0A%3C...Layout%3E%0A%20%20%20%20%3CImageView%20android%3AscaleType%3D%22...%22%20...%20/%3E%0A%3C/..Layout%3E%0A%60%60%60%0A%0A**Stack%20trace%20/%20LogCat**%3A%0A%60%60%60ruby%0Apaste%20stack%20trace%20here%0A%60%60%60
[2]: https://groups.google.com/forum/#!forum/glidelibrary
[3]: http://webchat.freenode.net/?channels=glide-library
[4]: https://developers.google.com/open-source/cla/individual
[5]: /bumptech/glide