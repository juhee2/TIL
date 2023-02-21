# Window 객체

: BOM(Browser Object Model, 웹 브라우저 전체를 객체로 인식)의 기본 객체

### 💥 특징

- BOM중 가장 상위의 객체
- 브라우처 창이 열릴 때 마다 하나의 window객체가 생성
- window 생략가능

#### 사용 예제

- 팝업 호출

```javascript
window.open("about:blank", "빈창", "width=300,height=600");
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

<br><br>

### 🌠 window.open 시 파라미터 `POST`로 전달하기

```html
<form id="sendForm" name="sendForm">
  <input id="sendData" name="sendData" value="전송할데이터" />
</form>
```

```javascript
var url = "호출할팝업페이지";
window.open(url, "popup", "width=500, height=300");

document.seadData.action = url; // form name 속성으로 접근
document.sendData.method = "post";
document.sendData.target = "popup";
document.sendData.submit();
```

호출한 팝업 jsp 파일에서

```jsp
<%
    String data = request.getParameter("sendData");
%>

// request 받아서 또는

<input type="hidden" id="data" value="${paramMap.sendData}"/>

```

로 받아서 사용할수 있다.
