---
title: "Tutorials Point error handling"
name: 연경모
layout: post
category: 트러블슈팅
tags: [React Native]
excerpt: "Tutorials Point 를 따라가다 보면 나는 잘못한 게 없는데 에러가 나는 경우"
---


# [Tutorials Point 진행 오류]

>
>ScrollView
> - App.js 예제코드에 오류있음.
>   - 아래 에러 발생.
>      scroll_view.js 를 찾을 수 없다는 에러
>         - 만드는 파일은 ScrollView.js 인데 import를 scroll_view.js로 잘못 표기, 이를 수정시 해결완료
>      Invariant Violation: Element type is invalid
>         - export default App 추가시 에러 해결됨
>

<br>
<br>
<br>
<br>

>Image
> - App.js 예제코드에 오류있음.
>   - 아래 에러 발생.
>      ImagesExample.js 를 찾을 수 없다는 에러
>         - image_example.js 를 ImagesExample.js로 잘못 표기, 수정시 해결완료
>      Invariant Violation: Element type is invalid
>         - export default App 추가시 에러 해결됨
>   
>   - ReferenceError: SHA-1 for file C:\Users\one\Desktop\staticfile\pic.png >(C:\Users\one\Desktop\staticfile\pic.png) is not computed
>      - react-native 로부터 Image import 시 image 로 오타나면 아래 에러 도출
>      - react-native에서 가져오는 건 태그이지만, 태그를 통해 기능을 구현하기 때문에
>        이미지 처리작업을 위한 기능구현에 Image 태그가 사용됨, 이것이 제대로 불러와지지 않았기 때문에
>        SHA-1 쳌섬 결과가 매칭되지 않아 에러가 난 것으로 보임.
>
> - Requiring unknown module "575" 에러
>   - node.js 엔 문제 없지만 가상머신에서 나오는 에러.
>      - node.js가 문제 없는 걸로 보아 코드상의 문제는 없는 것으로 보임
>   - 재부팅 이후 아래 에러로 바뀜
>      - ReferenceError: SHA-1 for file C:\REACT\pic.jpg (C:\REACT\pic.jpg) is not computed
>      - 위와 동일한 에러이지만 Image 오타 없고, 예제 코드 복붙해도 증상 같음
>      - nodejs 삭제 후 npm install, npm install -g react-native-cli 해도 증상 동일함
>      - node_modules 와 nodejs 삭제 후  npm install, npm install -g react-native-cli 해도 증상 동일함
>      - 기존에 만들었던 ScrollView는 에러 없이 실행 되는 것을 확인
>      - expo init 로 만들어서 yarn start 시 문제 해결됨을 확인
>      


# 리액트 네이티브 공부는 유튜브에서 니콜라스 선생님을 추천합니다.

링크 : <https://www.youtube.com/watch?v=v1vE7G6YQCc&list=PL7jH19IHhOLNPOI3bEBtSw1Acp3fS0enw>
<br>
링크 : <https://www.youtube.com/watch?v=zG7328Qm0LQ&list=PL7jH19IHhOLOefIzCSQ03xlBekyi81FVv>
<br>





```python

```
