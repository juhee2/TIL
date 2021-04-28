# 스택(Stack)

: LIFO(Last In First Out)의 자료형, 나중에 들어간 데이터가 제일 먼저 나옴!<br>
한쪽 방향에서만 입,출입이 가능하다

![스택](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Data_stack.svg/450px-Data_stack.svg.png)

[https://ko.wikipedia.org/wiki/스택](https://ko.wikipedia.org/wiki/%EC%8A%A4%ED%83%9D)

- 선언

    ```jsx
    import java.util.Stack;

    Stack<[자료형]> stack = new Stack<>();
    ```

- 기본 메소드
    - push([값])

        : 스택에 값 추가

    - pop()

        : 스택 요소 꺼내기(제거)

    - peek()

        : 스택 마지막 요소 값 출력

    - clear()

        : 스택 비우기

    - size()

        : 스택 크기(int) return

    - empty()

        ```java
        stack.empty(); // 비어있으면 true, 없으면 false
        ```

    - contains([값])

        stack에 값이 있는지 확인

        ```java
        stack.contains(1); // stack에 1있으면 true, 없으면 false
        ```
