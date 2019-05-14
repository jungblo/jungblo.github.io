---
title: "째깍악어 테스트 첫번째 글"
author: ["정블로"]
layout: post
category: 사용방법
tags: [React Native, php, Django, Mysql]
excerpt: "GITHUB 를 이용한 째깍악어 기술 블로그 작성 설명 및 운영방법 입니다."
---

GITHUB 를 이용한 째깍악어 기술 블로그 작성 설명 및 운영방법 입니다. 아래 내용을 참고해주세요.

# 글작성 스타일 지정

글작성시 스타일 지정에 관한 부분을 예시와 함께 나열했습니다.



글작성시 최상단에 아래와 같이 --- 중간 부분에 작성하여 게시글의 title, layout, category, tags, excerpt 를 작성합니다.

```python
---
title: "째깍악어 테스트 첫번째 글"
layout: post
category: 사용방법
tags: [React Native, php, Django, Mysql]
excerpt: "GITHUB 를 이용한 째깍악어 기술 블로그 작성 설명 및 운영방법 입니다."
---
```


아래는 내용 작성에 관한 예시 입니다.


# 제목작성 (줄 진하게)
아래 코드 참조
```python

# 제목작성 (줄 진하게)

```



## 제목작성 (줄 연하게)
아래 코드 참조
```python

## 제목작성 (줄 연하게)

```



링크 : <http://ttcroc.com>
아래 코드 참조
```python

링크 : <http://ttcroc.com>

```



__진하게__
아래 코드 참조
```python

__진하게__

```



- __리스트 형식__
아래 코드 참조

```python

- __리스트 형식__

```



`키박스`
아래 코드 참조
```python

`키박스`

```



이미지 링크 `[이미지 alt 내용](경로)`
![틱톡](/images/posts/201905/tictic.png)
아래 코드 참조
```python

![틱톡](/images/posts/201905/tictic.png)

```


코드 넣기
```python
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
위의 창을 `을 이용하여 감싸줍니다.
아래 코드 참조
```python

　```python
    import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
　```

```



테이블 형식

  | 분류 | 내용 |
  |----------|------|
  | 1번 분류 | 첫번째 내용 |
  | 2번 분류 | 두번째 내용 |
  | 3번 분류 | 세번째 내용 |
  | 4번 분류 | 네번째 내용 |


 옆으로 글자가 붙지 않도록 띄어쓰기에 주의하세요.
 
아래 코드 참조
```python

| 분류 | 내용 |
|----------|------|
| 1번 분류 | 첫번째 내용 |
| 2번 분류 | 두번째 내용 |
| 3번 분류 | 세번째 내용 |
| 4번 분류 | 네번째 내용 |

```


대제목 형식
>첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목
>
>-- by.째깍이

아래 코드 참조

```python

>첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목 첫번째 기술블로그 작성방법 게시글  째깍악어 프로덕트팀 기술블로그 제목
>
>-- by.째깍이

```