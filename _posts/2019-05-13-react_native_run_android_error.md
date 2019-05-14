



---
title: "react-native run-android 시 발생하는 에러"
layout: post
category: 트러블슈팅
tags: [React Native]
excerpt: "react-native run-android 실행시 발생 가능한 2 가지 에러에 관하여."
---

<br>
<br>

## 1. No connected devices! 에러.
<br>

### 안드로이드 스튜디오 들어가서 디바이스를 실행시킨다. 
**1) New -> Open**<br>
create-react-native-app 또는<br>
react-native init 로 만든 프로젝트 폴더 선택<br>

**2) 안드로이드 가상 머신 만들기**<br>
우측 상단 AVD Manager 클릭<br>
Create Virtual Device<br>
category : Phone, Name : Nexus5x<br>
x86 Images 선택<br>
Marshmallow x86 선택 후 next<br>
next가 활성화 되어있지 않으면 download 눌러서 해결<br>
이후 finish 로 마무리.<br>

**3) 안드로이드 가상 머신 동작시키기**<br>
AVD Manager 누르면 방금 만든 가상머신이 나옴<br>
우측 Actions 에 실행 버튼 클릭<br>
가상의 안드로이드 폰이 실행됨을 확인하여 문제 해결<br>


<br>
<br>

## 2. SDK 에러
<br>

### 안드로이드 홈 환경변수 설정
내 컴퓨터 우클릭 -> 속성 -> 고급 -> 환경변수 -> 시스템 변수 -> 새로 만들기<br>
ANDROID_HOME<br>
C:\Users\user_name\AppData\Local\Android\Sdk<br>
출처:<br>
링크 : <https://stackoverflow.com/questions/32634352/react-native-android-build-failed-sdk-location-not-found><br>
링크 : <https://www.tutorialspoint.com/react_native/react_native_environment_setup.htm>






```python

```
