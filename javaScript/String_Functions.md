# 문자열 관련 함수

#### `replace()`
: 어떤 패턴에 일치하는 일부 또는 모든 부분이 교체된 새로운 문자열 반환 함수
> 패턴에는 정규식이나 문자열 함수가 될수 있고, 교체 문자열은 문자열이나 함수일수 있음!

```javascript
var str = "이 문자열에서 pattern에 일치하는게 있다면 교체문자열로 변경!";

// 1. pattern이 string인 경우
str.replace("문자열", "String"); 
/*
  실행결과: 
  "이 String에서 pattern에 일치하는게 있다면 교체문자열로 변경!"
  해당 문자열에 해당하는 첫번째 문자열만 변경됨!
*/

// 문자열에 해당하는 전체를 변경하고 싶은경우
str.replaceAll("문자열", "String");
/*
  실행결과: 
  "이 String에서 pattern에 일치하는게 있다면 교체String로 변경!"
*/

// 2. pattern이 정규식인 경우
str.replace(/[a-z]+/, '영어');
/*
  실행결과:
  "이 문자열에서 영어에 일치하는게 있다면 교체문자열로 변경!"
  정규식에 일치하는 첫번째 문자열 교체 문자열로 변경
  
  ignore, global 옵션 사용
  /정규식/[g,i, gi]
  i : 대소문자 무시
  g : 문자열 전체에 대해 적용(replaceAll 과 같은 역할)
*/


```

<br>
<br>
<br>

#### 🌵참고
https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/replace#specifying_a_function_as_a_parameter
