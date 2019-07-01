---
title: "React Native 와 PHP 의 데이터 전달"
name: 정블로
layout: post
category: 사용방법
tags: [ReactNative, php]
excerpt: "React Native 에서 webview 로 데이터를 보냈을때 값을 받고 결과값을 return 해보기"
---

React Native 에서 webview 로 데이터를 보냈을때 값을 받고 결과값을 return 해보기 (json 응용)

# 데이터 받기

프로젝트를 React Native에서 개발을 하다보면 어쩔수 없이 webview로 처리해야하는 경우가 부분적으로 생길 수 있다
webview로 처리했을때의 장점은 개발 진행의 가시성이 높고 유지보수에 용이하다는것이다
간단하게 json을 이용하여 php에서 값을 받게 되는 코드는 아래와 같다


# json으로 값 전달받기

```php

$react_post = json_decode(file_get_contents('php://input'));
$react_post = objectToArray($react_post); 

$value_name = $react_post["value_name"];


function objectToArray($d) {

        if (is_object($d)) {
         // Gets the properties of the given object
         // with get_object_vars function
         $d = get_object_vars($d);
        }

        if (is_array($d)) {
      
         /*
         * Return array converted to object
         * Using __FUNCTION__ (Magic constant)
         * for recursive call
         */
      
         return array_map(__FUNCTION__, $d);
      
        }else{
      
         // Return array
         return $d;
      
        }

}


```
전달되는 XML데이터를 파싱 하기전 읽어내기 위해 file_get_contents('php://input') 가 사용된다
그 후 json 문자열을 배열이나 객체로 변환해주는 json_decode 를 사용하여 변환 후
objectToArray() 함수에서 문자열 인덱스 배열을 일반 배열로 변환한다



# json으로 값 전달하기

React Native로 값을 리턴할때는 React Native에서 어떻게 받느냐에 따라 달라진다

```php


        <!-- 1 -->
        $result_arr = array
								(
								 'result_1'     => $result_1,
									'result_2'     => $result_2,
									'result_3' 	  => $result_3
								);
								
								$json_result=json_encode($result_arr);

								echo $json_result;
        
        
        
        
        
        <!-- 2 -->
        <script>
         $(document).ready(function(){
 
          $(".ok_enter").click(function(){
           window.postMessage("ok_enter_value");
          });
 
         });
        </script>
```

상황에 따라 php로 값을 전달하기만 하고 리턴을 받지 않을수도 있지만
php에서 내부적인 DB처리 또는 결과 값을 뽑은후 다시 React Native 로 리턴이 필요 할 수 있다

- __1. React Native 에서 webview를 띄운 화면에 위와 같이 결과 값을 echo 를 찍어서 React Native에서 해당 값들을 확인 할 수 있다. 예제1은 json을 응용한 전달방식이다.__
- __2. 클릭 이벤트를 통해 값을 전달해야 하는 경우 위와 같이 script 를 사용하여 전달 할 수 있다. 이때 핵심은 window.postMessage 이다.(참조 : <https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage>)__ 
- __3. 여러 방법으로 데이터를 보낼 수 있지만 curl을 사용하여 값을 전달하여도 무방하다.__

중요한 점은 네이티브앱과 웹페이지 간의 코드균형을 적절히 맞춰 개발 해 나간다면 앱 자체는 약간의 하이브리드 형태가 될 수 있지만
많은 수정이 발생하는 페이지일때 해당 페이지의 로직이 안정적으로 자리잡을때까지는 유지보수가 용이한 웹페이지와의 연계도 생각해볼만하다.



