# Window 객체 
: BOM(Browser Object Model, 웹 브라우저 전체를 객체로 인식)의 기본 객체

### 💥 특징
- BOM중 가장 상위의 객체
- 브라우처 창이 열릴 때 마다 하나의 window객체가 생성
- window 생략가능

#### 사용 예제
- 팝업 호출
```javascript
window.open('about:blank', '빈창', 'width=300,height=600');
```

- 부모창, 자식창
```javascript
/* 부모창 */
window.open('호출 url','window창 이름','options');
var window = window.open('www.naver.com', 'naver', 'width=1290,height=800'); // 변수에 저장할수도 있음

/* 자식창 */
window.opener.document.[getElementById, getElementByTagName, getElementByClassName...].value // 부모창 요소 값 접근 가능
window.opener.parent.[부모창함수]; // 부모창 함수 호출
```
