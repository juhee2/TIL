# Web Socket

<div>
<h5>웹 소켓이 나오기 까지...<h5>
HTTP, <code>Hyper Text Transfer protocol</code> <br>
Client → Server 로 url형태로 request 를 보내면 response 받는 형태! 꼭 요청이 있어야 응답을 받을 수 있다.
<br><br>
Ajax, <code>Asynchronous JavaScript and XML</code><br>
HTTP를 좀 더 효율적으로 쓰기 위해 url을 통해 response를 받을때 페이지 전체를 새로고침하여 받는게 아니라, 필요한 부분만 부분적으로 변경할 수 있다.
<br><br>
HTTP는 결과를 서버에서 바로 받고 Ajax는 XMLHttpRequest 객체를 통해 전송하고 받는다!
</div>
<br><br>
위의 방법은 다 client에서 요청이 있어야 server에서 정보를 전달해주는데

만약 _요청없이_ 서버에서 client로 전달해야한다면,,,

이런 상황에 맞게 나온것이 `Web Socket` 이다.

서버와 클라이언트간 *양방향 통신*을 가능하게 해준다!
