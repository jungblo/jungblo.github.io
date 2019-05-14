---
title: "React-native 환경설정 부분"
name: 연경모
layout: post
category: 환경설정
tags: [ReactNative]
excerpt: "환경설정 과정 에서의 트러블슈팅 노트"
---



>
>링크 : <https://www.tutorialspoint.com/react_native/index.htm>
>위 주소의 내용을 따라가는 과정. (CRNA 방식)
<br>
><br>
>Practice_Machine<br>
>OS : Win10 x64<br>
>CPU : i7-8565U<br>
>RAM : DDR4 32GB<br>
>SSD#1 : nvme 512GB<br>
>SSD#2 : sata3 512GB<br>
>GPU : Intel UHD 620<br>
><br>
> --by. mo@tictoccroc.com



**00. 시작하기 전에**
cmd 창 제어 # cmd로 열 때 우클릭하여 관리자모드로 여는거 습관.
cd.. # 상위 폴더로 이동
dir  # 현 디렉터리 정보 확인

>안드로이드 가상머신 단축키
>
>ctrl + m 
>핫 리로드 기능
>
>rr
>reload



## 1. nodejs 설치 - LTS 버전: 10.15.3
링크 : <https://nodejs.org/ko/download/>
windows installer x64 다운로드, 실행하여 설치완료


## 2. nodejs 설치 확인 
cmd 창에서 아래 두 커맨드 입력
node -v
npm -v

LTS 버전: 10.15.3 기준
C:\REACT>node -v
v10.15.3

C:\REACT>npm -v
6.4.1


## 3. 리액트 네이티브 앱 만들기
C:\REACT>npm install -g create-react-native-app<br>
커맨드 창에 위 코드 입력시 아래 내용 출력되면서 설치 완료<br>
>C:\Users\one\AppData\Roaming\npm\create-react-native-app<br>
>C:\Users\one\AppData\Roaming\npm\node_modules\create-react-native-app\build\index.js<br>
>+ create-react-native-app@2.0.2<br>
>added 28 packages from 47 contributors in 2.944s<br>

3-4. dependency 설치<br>
jdk8 과 Python 을 설치해야 네이티브 프로젝트 만들 때 에러가 안 난다.<br>
jdk8 링크<br>
링크 : <https://www.oracle.com/technetwork/java/javaee/downloads/jdk8-downloads-2133151.html>


## 4.  리액트 네이티브 프로젝트 만들기
C:\REACT>create-react-native-app MyReactNative<br>
위 코드 실행시 MyReactNative 라는 폴더로 프로젝트 생성<br>
This command requires Expo CLI<br>
Do you want to install it globally [Y/n]? 에서 Y 입력<br>

4-1. 리액트 네이티브 프로젝트 만들 때 에러가 나는 경우<br>
jdk8 설치<br>
링크 : <https://www.oracle.com/technetwork/java/javaee/downloads/jdk8-downloads-2133151.html>

**No git binary found in $PATH 에러 발생시**<br>
git이 설치가 되지 않아서 생기는 문제이다.<br>
https://git-scm.com/download/win<br>
설치시 디폴트 에디터를 notepad++ 설정하고 싶다면 PATH 설정이 되어있어야 하므로 <br>
notepad++를 포터블에디션 말고 설치파일로 해야 함.<br>

**git 설치했는데도 No git binary found in $PATH 에러 사라지지 않는 경우**:
cmd 창을 껏다가 다시 켜야 PATH 설정된 것이 적용된다.<br>


## 5. 리액트 네이티브 CLI 만들기
C:\REACT>npm install -g react-native-cli


## 6. 리액트 네이티브 프로젝트 서버 실행해보기
C:\REACT>cd MyReactNative<br>
C:\REACT>npm start<br>
위 코드 실행시 커맨드 창에 QR코드가 나오면 실행이 된 것.<br>


7-1. 안드로이드 스튜디오 설치하기<br>
링크 : <https://developer.android.com/studio/><br>


## 7. 안드로이드 스튜디오로 에뮬레이터 실행하는 단계
ctrl + c 로 커맨드라인 탈출<br>
C:\REACT>npm run eject<br>
선택 창에서 첫 번째인 <br>
React Native: I'd like a regular React Native project. 선택<br>
유저 홈 스크린에 보일 내용 입력 : MyReactNative<br>
안드로이드 스튜디오 및 Xcode상 보일 내용 입력 : MyReactNative<br>
이후 <br>
code ELIFECYCLE<br>
errno 1<br>
로 시작하는 에러 발생시 무시<br>


## 8. 안드로이드 실행
C:\REACT>react-native run-android<br>



### 위 명령 입력시 나올 수 있는 에러 여러가지:<br>

**Error: Cannot find module '@babel/runtime/helpers/interopRequireDefault' 에러**<br>
리액트 네이티브의 버전에 따른 문제로 보여짐.<br>
C:\REACT>npm add @babel/runtime<br>
입력 후 react-native run-android 실행<br>
출처:<br>
링크 : <https://reactnativeforyou.com/unable-to-resolve-module-bable-runtime-helpers-interoprequiredefault-react-native-error-fix/>



**SDK location not found. Define location with sdk.dir in the local.properties file or with an ANDROID_HOME environment variable. 에러**<br>
해결책_1<br>
local.properties 이름으로 파일을 만들고 아래 내용을 유저이름만 바꿔서 복붙한다.<br>
sdk.dir = /C:\\Users\\유저이름\\AppData\\Local\\Android\\Sdk<br>
출처:<br>
링크 : <https://stackoverflow.com/questions/32634352/react-native-android-build-failed-sdk-location-not-found>
링크 : <https://www.tutorialspoint.com/react_native/react_native_environment_setup.htm>

해결책_2<br>
안드로이드 홈 환경변수 설정<br>
내 컴퓨터 우클릭 -> 속성 -> 고급 -> 환경변수 -> 시스템 변수 -> 새로 만들기<br>
ANDROID_HOME<br>
C:\Users\user_name\AppData\Local\Android\Sdk<br>
출처:<br>
링크 : <https://stackoverflow.com/questions/32634352/react-native-android-build-failed-sdk-location-not-found>



**Execution failed for task ':app:compileDebugJavaWithJavac'. 에러**<br>
해결책_1<br>
프로젝트를 CRNA 대신 다른 방법(init)으로 만든다.<br>
create-react-native-app  대신에<br>
react-native init  으로 만든다.<br>
출처: 페이스북 듀토리얼에서는 init로 프로젝트를 만드는데, 이 방법을 사용하면 에러가 안 남.<br>
링크 : <https://facebook.github.io/react-native/docs/tutorial>
init 와 CRNA(EXPO) 방식의 차이 출처:<br>
링크 : <https://github.com/react-community/create-react-native-app/issues/516>
 - Benzer1406 commented on Mar 17 2018<br>
<br>

해결책_2<br>
package.json 열어서 값을 수정한다.<br>
"react-native": "여기에 링크가 있을텐데, 이것을 아래 값으로 바꿔준다."<br>
"react-native": "0.57.5"<br>

출처:<br>
링크 : <https://github.com/facebook/react-native/issues/21722>



**No connected devices! 에러.**<br>
가상머신이 연결되어있지 않아 생기는 에러.<br>
<br>
안드로이드 스튜디오 들어가기<br>
1) New -> Open<br>
create-react-native-app 또는<br>
react-native init 로 만든 프로젝트 폴더 선택<br>

2) 안드로이드 가상 머신 만들기<br>
우측 상단 AVD Manager 클릭<br>
Create Virtual Device<br>
category : Phone, Name : Nexus5x<br>
x86 Images 선택<br>
Marshmallow x86 선택 후 next<br>
next가 활성화 되어있지 않으면 download 눌러서 해결<br>
이후 finish 로 마무리.<br>

3) 안드로이드 가상 머신 동작시키기<br>
AVD Manager 누르면 방금 만든 가상머신이 나옴<br>
우측 Actions 에 실행 버튼 클릭<br>
가상의 안드로이드 폰이 실행됨을 확인<br>



**가상머신에서 index.js 찾을 수 없다는 에러**<br>
CRNA 로 만들었을 때 index.js가 없어서, init로 만들어보니 있길래 내용을 가져옴.<br>
index.js 라는 이름으로 에러 나는 경로에 파일을 만들어 아래 내용을 붙여넣기 한다.<br>
<br>
/* <br>
 * @format <br>
 */ <br>
<br>
import {AppRegistry} from 'react-native';<br>
import App from './App';<br>
import {name as appName} from './app.json';<br>
<br>
AppRegistry.registerComponent(appName, () => App);<br>
<br>

출처:<br>
링크 : <https://github.com/react-community/create-react-native-app/issues/771>



<br>
### = = = = = Tutorials Point 말고 facebook 공홈 튜토리얼 = = = = =<br>
### = = = = = CRNA 가 아닌 react-native init 로 만드는 경우 = = = = =<br>
init 와 CRNA(EXPO) 방식의 차이 출처:<br>
링크 : <https://github.com/react-community/create-react-native-app/issues/516><br>
 - Benzer1406 commented on Mar 17 2018<br>

<br>
**1. 아래 파일들 설치**<br>
<br>
nodejs 설치 - LTS 버전: 10.15.3<br>
링크 : <https://nodejs.org/ko/download/><br>
windows installer x64 다운로드, 실행하여 설치완료<br>

jdk8<br>
링크 : <https://www.oracle.com/technetwork/java/javaee/downloads/jdk8-downloads-2133151.html><br>

Git<br>
링크 : <https://git-scm.com/download/win><br>

android-studio-ide<br>
링크 : <https://developer.android.com/studio/><br>



**2. 커맨드라인에서 아래 명령어 실행**<br>
node -v # nodejs 설치되었는지 확인<br>
npm -v # npm 설치되었는지 확인<br>
npm install -g react-native-cli # react-native 설치<br>
react-native init Project_Name # 해당 디렉토리에 프로젝트 생성<br>
cd Project_Name # 프로젝트 폴더로 이동<br>
react-native run-android # 안드로이드 코드 실행<br>



# 환경설정시 주의사항<br>

환경설정 적용시 마지막에 반드시<br>
expo r -c <br>
엑스포의 캐시를 없애주는 명령어를 반드시 입력한다.<br>

 _react[“default”].memo is not a function 에러 발생시<br>

redux가 7.0.0 버전부터 connect 시 memo를 사용하게끔 바뀌었는데<br>
expo에서 이를 지원하지 않아 생기는 문제.<br>
  
해결방안은 2 가지 중 하나를 선택하면 됨<br>

1.<br>
node_modules 폴더 삭제<br>
package.json 에서 react-redux 항목을 6.0.0 으로 수정.<br>
npm i<br>

2.<br>
npm install react-redux@6.0.1<br>
expo r -c<br>

링크 : <https://stackoverflow.com/questions/55691069/how-to-fix-reactdefault-memo-is-not-a-function-in-reactdefault-mem>
링크 : <https://github.com/reduxjs/react-redux/releases/tag/v7.0.1>





```python

```
