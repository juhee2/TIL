# Lombok

: getter/setter 와 같은 반복 메소드를 어노테이션으로 작성할수있게 해주는 라이브러리

|어노테이션|설명|
|--|----------|
|`@Getter` | 해당 클래스의 멤버변수에 대한 getter 메소드 작성 |
|`@Setter` | 해당 클래스의 멤버변수에 대한 setter 메소드 작성 |
|`@ToString`| 해당 클래스 객체 속성 내용을 String 으로 반환하는 메소드 작성 |
|`@NoArgsContructor` | 기본 생성자 작성 |
|`@Data`| 위 다섯 어노테이션의 기능을 합친 어노테이션 |
|`@RequiredArgsConstructor`| 파라미터를 포함한 생성자 작성<br> (final이나 Not NULL인 필드값만 파라미터로 받는 생성자를 만들어줌) |
|`@AllArgsConstructor`| 모든 멤버변수를 포함한 생성자 작성 |


#### 사용예제
<!-- 꼭 private 을 사용해야 하는지 확인~! -->
```java

public class Member() {
    String userId;
    String userPw;
    String userName;

    LocalDateTime regDt;
    boolean loginYn;
}

```

