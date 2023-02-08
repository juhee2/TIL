# 프로젝트에 typescript 설정하기

## 1. 처음 생성시 typescript 생성하기
```
npx create-react-app [프로젝트명] --template typescript
```

## 2. 파일확장자 `.tsx` 로 설정

❗ 설정후 index.tsx 에서
![image](https://user-images.githubusercontent.com/45550688/217563750-9c94916e-fa28-47ce-ba4c-b753c186b330.png)
`const root = ReactDOM.createRoot(document.getElementById("root"));` 에서<br>
`Argument of type 'HTMLElement | null' is not assignable to parameter of type 'Element | DocumentFragment'.
  Type 'null' is not assignable to type 'Element | DocumentFragment'.` 에러 발생시
  
🔧 getElementById 로 어떤 객체 type 을 받아오는지 기재해줘야함!<br>
  const root = ReactDOM.createRoot(document.getElementById("root") `as HTMLElement`);
  
 ## 3. typescript 설정파일
 프로젝트 폴더 바로 하위에
 `tsconfig.json` 생성
 ```
 // tsconfig.json 파일 내용
 {
  "compilerOptions": {
    "target": "es6",
    "lib": [
      "dom",
      "dom.iterable",
      "esnext"
    ],
    "baseUrl": "./src",
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx"
  },
  "include": [
    "src"
  ]
}
```

🔍 [설정관련 설명 페이지](https://www.typescriptlang.org/tsconfig)
 
 ## 4. 그래도 실행시 오류 발생하면
`@types/node`
`@types/react`
`@types/react-dom`
 패키지가 잘 설치 되었는지 확인<br>
 - `npm ls` 설치된 패키지 확인
 - `npm ls | findStr "찾을문자"` 특정 패키지 확인
 
