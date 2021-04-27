# JUnit

- 기본 Annotations
  1. `@Test`<br>
  : 테스트를 수행할 메소드에 작성

  2. `@Before` , `@After`<br>
  : 각 테스트 메소드 별 전/후 에 호출

  3. `@BeforeClass` , `@AfterClass`<br>
  : Test 클래스 전/후 에 호출

  4. `@Ignore`<br>
  : 테스트 제외

  ```java
  // 호출 순서
  @BeforeClass
  @before
  @Test
  @After
  // 만약 @Test가 여러개라면 반복
  @before
  @Test
  @After
  // 반복 끝
  @AfterClass
  ```

### JUnit method

- assertArrayEquals(a, b)<br>
: 배열 a가 b와 일치함을 확인

- assertEquals(expected, actual)<br>
: 객체 a(expected : 예상값)와 b(actual : 실제값)가 일치함을 확인

- assertSame(a, b)<br>
: 객체 a와 b가 같은 객체임을 확인<br>
→ 두 객체가 동일한가? 검사<br>
(assertEquals는 값이 같은가 검사)

- assertTure(a)<br>
: 조건 a가 참인지 확인

- assertNotNull(a)<br>
: 객체 a가 null이 아님을 확인

# AssertJ
: 많은 assertion을 제공하는 자바 라이브러리<br>
에러메세지와 테스트코드의 가독성을 높여줌!

- 정적임포트하면 AssertJ의 다양한 API를 **클래스 이름없이 바로사용** 가능!

```java
import static org.assertj.core.api.Assertions.*;
```

```java
// 사용법
assertThat([ 값]).[값 검증을 위한 메소드]()

// ex) 문자열
assertThat("Hello, world! Nice to meet you.")
	.isNotEmpty() // 비어있지 않고
	.contains("Nice") // "Nice"를 포함하고
	.doesNotContain("hee") // "hee"를 포함하지 않고
	.startsWith("H") // "H"로 시작하고
	.endsWith(".") // "."으로 끝나고
	.isEqualTo("Hello, world! Nice to meet you."); // "Hello, world! Nice to meet you." 와 같다

// ex) 숫자
assertThat(3.14d)
	.isPositive() // 양수이고
	.isGreaterThan(3) // 3보다 크고
	.isLessThen(4) // 4보다 작고
	.isEqualTo(3, offset(1d)) // 오프셋 1 기준으로 3과 같고
	.isEqualTo(3.1, offset(0.1d)) // 오프셋 0.1 기준으로 3.1과 같고
	.isEqualTo(3.14); // 3.14와 같다
```

### 참고

- [https://www.daleseo.com/assertj/](https://www.daleseo.com/assertj/)
