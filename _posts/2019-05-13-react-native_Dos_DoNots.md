---
title: "기본 문법과 프레임워크 특징"
name: 연경모
layout: post
category: 사용방법
tags: [ReactNative]
excerpt: "되는 것과 안 되는 것 모음"
---




## 1. { Component } 사용하기


>import React, { Component } from 'react';
>export default class App extends Component {

>import React from 'react';
>export default class App extends React.Component {

>위와 아래의 declaration 은 사실 같은 것.
>중괄호 안에 써있으면 참조해 가져온다는 의미로 보임.



## 2. 프레임워크 구성요소

>기본적으로 .js 파일로 구성되어있다.
>각 .js 파일은 거의 동일한 형태로 구성된다.

**최상단 import**
	react 로부터 React, { Component } 불러오기<br>
	react-native 로부터 { StyleSheet, View } 등 불러오기<br>
	기본 제공 컴포넌트 이외에 expo 에서 가져오기 등 사용자 풀 다수 보유<br>
    
**클래스 선언 -> extends Component 또는 extends React.Component**
	state 정의
		- 해당 .js 파일에서 사용될 변수이며, key : value 쌍으로 이루어져 있다.
		- 클래스 생성시 내부에서 사용될 값이고, class initialize 역할을 한다.
		- 데이터 타입 명시하지 않는다. (매우 중요!!!! var 나 const 사용하면 안됨)
	render(){}
		- 중괄호 안에는 return 이 있는 부분과 그렇지 않은 부분으로 나뉘어진다.
	return() 과 render(){ 사이 부분
		- 정의된 state(전역번수) 로부터 return 시 사용될 지역변수를 할당 
		- state는 클래스 내부에서 정의된 것이기 때문에 this. 으로 접근해야 함.
	return()
		- 소괄호 안에 react-native 컴포넌트들을 위치시킨다.
			- <View>, <Text> 와 같은 것들.
		- 바로 위에서 선언한 지역변수를 가져오고 싶은 경우
		중괄호를 만들어 그 안에 지역변수명을 넣으면 호출된다.
		- 중괄호를 사용하지 않고 변수명 입력시 변수명으로 인식하지 않는다.

**최하단 css 요소 정의**
	- const styles = StyleSheet.create({});
		- react-native 컴포넌트 중 StyleSheet 라는 항목은 css를 사용하기 위함임.
		- key: value 쌍으로 만들어야 함.
		- value가 숫자인 경우와 문자열인 경우로 나뉨, 숫자가 아니면 전부 문자열
	
	
**기억할 점 **
-> 클래스 내부와 외부의 문법이 다르다.<br>
-> 클래스 내부는 3 부분으로 이루어져있고, 각 영역은 문법이 다르다 .<br>
-> 클래스는 render 이전, render와 return 사이, return 부분으로 이루어져 있다.<br>
-> render 이전 영역은 props 와 state 가 정의되는 구역이다.(자료형 선언은 안한다.)<br>
-> 클래스 외부와 문법이 같은 곳은 render와 return 사이 부분이다.<br>
	-> 이 부분에서는 변수 선언시 const, var 가능하다.<br>
-> return 부분은 HTML 태그와 유사한 react-native 컴포넌트들이 위치한다.<br>


### 위 내용을 기반으로, 무엇이 되는지 실험결과:



'''
  state = {
    isLoaded: false
  }
  render() {
    const isLoadede = this.state.isLoaded;
    return (
      <View style={styles.container}>
        {isLoadede ? null :
'''
>
> ==> <br>
>[가능] state 정의에 있는 isLoaded 를 this.state.isLoaded 로 호출하는 것<br>
>[가능] const isLoadede = this.state.isLoaded; 와 같이<br>
>	호출 후 새로운 이름으로 할당하여 return 에서 새로운 이름으로 사용하는 것<br>
>
    

'''
export default class App extends Component {
  render() {
    const { flex } = styles.container;
    return (
      <View>
        {flex ? 
        <View><Text>global local class var test</Text></View>
        : null }
        </View>
    );
  }
}
const styles = StyleSheet.create({
  container: {
    flex: 1,
'''

>
> ==><br>
>[가능] 클래스 밖에서 const로 정의한 변수를 render에서 호출<br>
>[가능] render 에서 호출하여 const로 정의한 것은 return 에서 중괄호로 대입이 가능<br>
>[불가능] StyleSheet.create 안에서 css 부분 key : value 입력시<br>
>		value 에 기존 css 에서 사용하는 shorthand property 는 적용되지 않음<br>
>		padding: “40 30 50 60”  이과 같이 쓰면 안되는 것.<br>
>

'''
==>
프레임워크 특징과, 업계에서 관행적으로 사용하는 코딩 양식은 아래와 같음.
  state = {
    isLoaded: false
  }
  render() {
    const { isLoaded } = this.state;
    return (
      <View style={styles.container}>
        {isLoaded ? null :
'''

>
>render 에서 state 호출시 새로운 변수명에 대입하지 않음.<br>
>이 때, 지역변수 선언시 {} 중괄호에 state의 key 값을 넣으면 같은 이름으로 불러와 사용<br>
><br>
>Prop 은 컴포넌트에 들어가는 **kwargs 이다.<br>
>




```python

```
