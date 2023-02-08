# useEffect

#### ❔ 컴포넌트가 렌더링 될때마다 특정 작업을 실행할수 있도록 하는 리액트 hook

###### -> `hook` 이란 기존 class 바탕의 코드를 작성할 필요없이 상태값과 여러 react 의 기능을 사용할수 있도록 하는것!

### 사용법

```
const [count, setCount] = useState(0);
/*
    useState 는 [변수, 변수값세팅함수] = useState(초기값); 으로
    ex) const [value, setValue] = useState("HI");
    console.log(value); // HI
    setValue("BYE");
    console.log(value); // BYE
*/

useEffect(() => {
    document.title = `You clicked ${count} times`;
});

return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
```

위 코드는 button onClick이벤트로 클릭할때마다 setCount 함수를 발생시킨다!

- useEffect 에 인수를 하나 더 주면
  useEffect(() => {}, `[count]`); count 가 변경될때마다 `useEffect` 실행!
