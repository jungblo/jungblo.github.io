---
title: "째깍악어 테스트 첫번째 글"
layout: post
category: 사용방법
tags: [React Native, php, Django, Mysql]
excerpt: "GITHUB 를 이용한 째깍악어 기술 블로그 작성 설명 및 운영방법 입니다."
---

GITHUB 를 이용한 째깍악어 기술 블로그 작성 설명 및 운영방법 입니다. 아래 내용을 참고해주세요.

# 글작성 스타일 지정

글작성시 스타일 지정에 관한 부분을 예시와 함께 나열했습니다.



상단에 아래와 같이 --- 중간 부분에 작성하여 게시글의 title, layout, category, tags, excerpt 를 작성합니다.

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

```python

# 제목작성 (줄 진하게)

```



## 제목작성 (줄 연하게)

```python

## 제목작성 (줄 연하게)

```



링크 : <http://ttcroc.com>

```python

링크 : <http://ttcroc.com>

```



__진하게__

```python

__진하게__

```



- __리스트 형식__

```python

- __리스트 형식__

```



`키박스`

```python

`키박스`

```



이미지 링크 [이미지 alt 내용](경로)
![틱톡](/images/posts/201806/vimium.jpg)

```python

![틱톡](/images/posts/201806/vimium.jpg)

```


코드 넣기
```python
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```



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




```python

| 분류 | 내용 |
|----------|------|
| 1번 분류 | 첫번째 내용 |
| 2번 분류 | 두번째 내용 |
| 3번 분류 | 세번째 내용 |
| 4번 분류 | 네번째 내용 |

```