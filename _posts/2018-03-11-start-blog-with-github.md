---
title: 블로그 갈아엎기
category: 개발
---

한국어를 지원할리 없는 해외 테마 개조하기.<br> 그리고 FOIT와의 전쟁.

<!--more-->

---

이전에 개발의 **'개'**자도 몰랐을 고등학교 1학년 때, [네이버 블로그](https://nus0319.blog.me/)를 운영했었다. 하지만 3년 뒤, 디자인과 개발을 조금이나마 알게 된 후 본 내 네이버 블로그는 너무 조잡했고, [네이버 블로그](https://nus0319.blog.me/)의 [돋움](https://en.wikipedia.org/wiki/Dotum) 폰트와 한정적인 스타일링이 마음에 들지 않았다.

>좀 더 깔끔하고 필요에 따라 스타일링이 자유로운 블로그가 필요했다.
><small>— [길범준](https://blog.beomjun.kr)</small>

처음에는 내가 좋아하는 디자인과 제일 가까운 [Medium](https://medium.com/)을 사용하려 했으나, 해외 서비스인 [Medium](https://medium.com/)은 커스텀 폰트도 지원하지 않고, 당연히 한국어 폰트는 전혀 지원하지 않았다. 그리고 페이스북에 올라왔던 친한 후배의 글을 다시 보게 됬다.

![Medium]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/1.png) <small>[Medium.com](https://medium.com/)의 영문 타이포는 정말로 예쁘다</small>

---

## 모든게 마음에 안들 땐, 직접 만들자 

그러다가 예전에 들은 [Github Pages](https://pages.github.com/)와 [Jerkyll](https://jekyllrb-ko.github.io/)를 사용해서 블로그로 쓸 수 있다는 말이 생각났다.


>방학을 뒹굴이라는 개념 아래, 완전히 낭비하고 있을 즈음, 내 자신이 블로그를 맘에 들어하고있지 않다는것을 깨달았다. 그래서 설날맞이 업데이트겸 좀 바꿔보기로 했다.
><small>— [진준기, 블로그 리디자인 이야기](http://w1nn3r.space/2018/02/17/blog-redesign/)</small>

고등학교 후배의 블로그는 내가 원했던 [Medium](https://medium.com/)의 깔끔함과  [Github Pages](https://pages.github.com/)와 [Jerkyll](https://jekyllrb-ko.github.io/)를 사용해서 수정이 자유로운 장점까지 완벽했다.

![후배의 블로그]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/2.png) <small>[후배의 블로그](http://w1nn3r.space/)는 마치 한국어 지원 Medium 같았다</small>

---

## 한국어를 위한 테마는 없다

[후배의 포스트](http://w1nn3r.space/2018/02/17/blog-redesign/)를 보고 후배가 사용한 테마를 그대로 사용하기 하려 했다. 테마의 이름은 [holo-alfa](https://github.com/steinvc/holo-alfa).

>Holo Alfa is a minimalist, mobile first Jekyll theme with focus on readability and content. Created for free and fun by Stijn. Also works great as a base to build your own theme on.
><small>— [steinvc/holo-alfa Repo.](https://github.com/steinvc/holo-alfa)</small>

그리고 열어본 블로그는 정말 [Medium](https://medium.com/)같았다. 한국어 지원 안되는것 까지 똑 닮았다.

![수정전 블로그]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/3.png) <small>후배의 예쁜 블로그 뒤엔 다 노-력이 있었다.</small>


---

## 폰트를 바꾸자 조금 더 똑똑한 방법으로.

한글 폰트가 지원되지 않으니 무작정 `CSS`에서 `@import`를 통해 폰트를 가져오고 기존 영어 폰트를 교체하면 해결될 문제 겠지만, 웹폰트를 사용하면 언제나 오는 문제가 있다.

* FOIT (Flash of Invisible Text)


>[FOUT](http://www.paulirish.com/2009/fighting-the-font-face-fout/)를 기억하십니까? [@font-face](https://css-tricks.com/snippets/css/using-font-face/)를 통해 사용자 정의 글꼴을 사용하는 경우 브라우저는 사용자 정의 글꼴이로드 될 때까지 [글꼴 스택](https://css-tricks.com/snippets/css/font-stacks/)에 대체 글꼴을 표시하는 데 사용됩니다. 이로 인해 불안정한 레이아웃 변경을 초래할 수있는 **"스타일없는 텍스트의 플래시"**가 만들어졌습니다. 우리는 [글꼴을 준비 할 때까지 텍스트를 보이지 않게 만드는 등의 방법](making the text invisible until the font was ready)으로 글꼴을 싸우는 기술을 개발했습니다.<br><br>몇 년 전, 브라우저는이 문제를 처리하기 시작했습니다. 그들은 텍스트가 아직로드되지 않은 사용자 정의 글꼴에 설정되어 있는지 감지하기 시작했으며 글꼴이로드 될 때까지 (또는 X 초가 지나면) 보이지 않게했습니다. 그것이 바로 FOIT : **"보이지 않는 텍스트의 플래시"**입니다. 폰트 애셋이 실패하거나 오랜 시간이 걸리는 경우 렌더링 시간 성능에 대해 정당한 관심이있는 사람들에게 X 초가 너무 길다. 최악의 경우,이 동작으로 인해 영구적으로 보이지 않는 콘텐츠가 생성 될 수 있습니다.
><small>- [FOUT, FOIT, FOFT (CSS Tricks)](https://css-tricks.com/fout-foit-foft/)


그렇기에 내가 찾은 방법은 [웹 폰트 로더](https://github.com/typekit/webfontloader)를 사용하는 것이다. 

먼저, 본문을 위한 세리프체, 제목을 위한 산세리프체를 한국어 지원 폰트로 바꾸기 위해 내가 사용한 폰트는,

* 본문용 서체 : '[KoPub 바탕체](http://www.kopus.org/biz/electronic/font.aspx)'
* 제목용 서체 : '[나눔스퀘어](http://hangeul.naver.com/2017/nanum)'

둘 다 무료 폰트이고, 내가 줄곧 쓰던 폰트들이다. 특히 [KoPub 바탕체](http://www.kopus.org/biz/electronic/font.aspx)는 **무료 폰트**임에도 불구하고 출판과 본문용 서체로 뛰어난 효과를 자랑하는 세리프 폰트이다. 이 폰트의 존재를 알려주신, [졸업한 고등학교](https://www.dimigo.hs.kr)에 계시던 영상 선생님께 언제나 감사하고 있다. 

---

## 웹 폰트 적용기

{% highlight html %}
<!-- html파일의 <head> 태그 안에 -->
<script>
    WebFontConfig = {
        custom: {
            families: ['KoPub Batang','NanumSquare'],
            urls: ['https://fonts.googleapis.com/earlyaccess/kopubbatang.css','https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css']
        }
    };
</script>
{% endhighlight %}

위 코드를 `<head>`안에 넣으면 `@import`, `<link>`가 해주는 역할과 똑같이 웹폰트 로더가 예쁘게 로드해준다.

하지만 웹폰트 로더 또한 `webfont.js`를 `<script>`를 통해 로드한 뒤 사용하는 방법이기 때문에, 웹폰트를 `webfont.js`를 다른 것 보다 먼저, 하지만 비동기로 로드에 DOM로드를 방해하지 않도록 해야했었다.  

{% highlight html %}
<script>
    WebFontConfig = {
        custom: {
            families: ['KoPub Batang','NanumSquare'],
            urls: ['https://fonts.googleapis.com/earlyaccess/kopubbatang.css','https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css']
        }
    };
    (function() {
        var wf = document.createElement('script');
        wf.src = ('https:' == document.location.protocol ? 'https' : 'http') +
            '://ajax.googleapis.com/ajax/libs/webfont/1.6.16/webfont.js';
        wf.type = 'text/javascript';
        wf.async = 'true';
        var s = document.getElementsByTagName('script')[0];
        s.parentNode.insertBefore(wf, s);
    })();
</script>
{% endhighlight %}

`webfont.js`를 불러오는 코드를 다른 `<script>`들 중 제일 앞에 추가하고, 비동기로 로드하는 활성화하는 코드를 추가했다.

그리고 나서 확인한 내 블로그는 이랬다.

![응 이게 뭐지?]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/4.png) <small>응? 왜 하나도 안보이지?</small>

![그리고 3초 뒤]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/5.png) <small>그리고 3초 뒤</small>

캡처를 했을 당시,[나눔스퀘어](http://hangeul.naver.com/2017/nanum) 폰트는 적용하지 않았음으로 제목이 보이는 건 당연했지만, 폰트를 적용한 본문이 하나도 보이지 않았다. 아무것도 보이지 않았던 본문은  [KoPub 바탕체](http://www.kopus.org/biz/electronic/font.aspx) 웹폰트가 다 로드 된 뒤 보여졌다. 웹폰트 로더를 추가했다고 바로 **FOIT**가 해결 되지 않았다.

![이게뭐야!]({{ site.baseurl}}/img/2018-03-11-start-blog-with-github/6.jpg) <small>이건 뭐야?</small>

---

## FOIT와 싸우자

알고보니 웹 폰트로더를 사용하면 그냥 폰트 로드를 해주는게 아니라, `<html>`태그 에 아래와 같은 클래스 명을 적용해서 웹 폰트 로드 상태를 알려주고 있었다.

{% highlight css %}
/* 웹폰트 로더가 <html>태그에 적용해주는 클래스 들*/
.wf-loading
.wf-active
.wf-inactive
.wf-<familyname>-<fvd>-loading
.wf-<familyname>-<fvd>-active
.wf-<familyname>-<fvd>-inactive
{% endhighlight %}
  
전체적인 폰트 로드 상태와 각 폰트들의 로드 상태를 알려주고 있었으나, 이걸 사용할 생각을 못했었다.
위 클래스 명을 `CSS`에 사용해서 아래와 같이 하면 FOIT가 해결되고, 웹 폰트가 적용되기 전까지 Fallback폰트를 적용해줬다!

{% highlight css %}
body {
  font-family: 'Nanum Myeongjo', '나눔 명조',Batang, '바탕', BatangChe, '바탕체', 'Apple Myungjo',serif;
}
html.wf-active body{
  font-family: "KoPub Batang", 'Jeju Myeongjo', 'Nanum Myeongjo', '나눔 명조',Batang, '바탕', BatangChe, '바탕체', 'Apple Myungjo',serif;
}
{% endhighlight %}

그러나 `font-weight:normal`인 폰트들은 다 적용됬지만, `font-weight:800`과 같은 굵기를 수정한 폰트들은 `.wf-active`가 적용 된 후 로드 됬었다. 일부 **FOIT**가 다 해결되지 않았다. 다시 구글을 찾아보다가 아까 뭔지 몰랐던 `fvd`에 대해 알게되었다. 

>FVD (Font Variation Description)
><small>- typekit, [fvd Repo](https://github.com/typekit/fvd)</small>

#### font-style
```
n: normal  (default)
i: italic
o: oblique
```

#### font-weight
```
1: 100
2: 200
3: 300
4: 400 (default, also recognized as 'normal')
5: 500
6: 600
7: 700 (also recognized as 'bold')
8: 800
9: 900
```

#### font-stretch
```
a: ultra-condensed
b: extra-condensed
c: condensed
d: semi-condensed
n: normal          (default)
e: semi-expanded
f: expanded
g: extra-expanded
h: ultra-expanded
```

예를 들어, [KoPub 바탕체](http://www.kopus.org/biz/electronic/font.aspx)의 `700`굵기 폰트를 사용하려면, fvd가 `n7`인 것이다.

이 fvd를 웹 폰트 로더에 추가하면 굵기 폰트의 **FOIT**가 해결된다.

 {% highlight html %}
 <script>
     WebFontConfig = {
         custom: {
             families: ['KoPub Batang:n7,n4','NanumSquare:n8'],
             urls: ['https://fonts.googleapis.com/earlyaccess/kopubbatang.css','https://cdn.rawgit.com/moonspam/NanumSquare/master/nanumsquare.css']
         }
     };
     (function() {
         var wf = document.createElement('script');
         wf.src = ('https:' == document.location.protocol ? 'https' : 'http') +
             '://ajax.googleapis.com/ajax/libs/webfont/1.6.16/webfont.js';
         wf.type = 'text/javascript';
         wf.async = 'true';
         var s = document.getElementsByTagName('script')[0];
         s.parentNode.insertBefore(wf, s);
     })();
 </script>
 {% endhighlight %}

이로서, FOIT해결을 완료했다!

이제 남은건 FOUT이지만, 아무리 노력해도 FOUT시간을 줄일 순 있었지만 없애지 못하였다 :(

해결법을 다시 한번 찾고 해결해 봐야겠다. 

---

## 한국어가 잘리면 안돼!

스타일과 블로그를 개조하고, 다시 본 블로그에 문제점은 단어가 자<br>꾸 잘린다는 것이<br>였다.

###### (중요) 위 텍스트는 일부러 잘랐다.

해결법은 생각보다 간단했다.

{% highlight css %}
p{
  word-break: keep-all;
  white-space: -moz-pre-wrap;
  white-space: -pre-wrap;
  white-space: -o-pre-wrap;
  word-wrap: break-word;
}
{% endhighlight %}

---

## 마치며...

아쉽게도 FOUT를 완벽히 수정하지 못했다. 그래도 웹 폰트 로더의 사용법을 자세히 알 수 있었고 무엇보다, **내 마음에 쏙 든다** 사랑스러운 블로그를 만들었으니, 앞으로 열심히 포스팅해야겠다.

---
