# useQuery

#### ❔ 조회한 데이터를 따로 저장해두고 있어 같은 데이터를 조회할때 다시 서버로 부터 조회하는게 아니라 캐시에서 바로 꺼내올 수 있도록 해주는 <b>react-query</b> 의 hook

<br>

### 사용법

```
const queryResult = useQuery("querykey", queryFn); // Object return
```

인수로 캐시에 저장할때 querykey 를 id 처럼 고유의 key 값을 입력해줘야하고,
데이터를 실제 가져오는 함수를 입력한다.

querykey는 배열도 가능하다!

queryFn에 인수가 필요한 함수가 들어갈때에는 익명함수를 이용해 감싸준다!

```
const { isLoading, data } = useQuery(["use", "query"], ()=> callDataApi(param);

function callDataApi(param) {
    ~~
}
```
