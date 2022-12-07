---
title: react Hook
date: 2022-12-06 13:12:68
category: React
draft: false
---

## react hook
Hook은 React 버전 16.8부터 React 요소로 새로 추가되었습니다. <br>
Hook을 이용하여 기존 Class 바탕의 코드를 작성할 필요 없이 function 형태로 상태 값과 여러 React의 기능을 사용할 수 있습니다.
- Hook은 조건문, return문 에 상용할 수 없으며 React Component 내의 전역으로서만 사용가능하다.

## React 에서 지원하는 Hooks

### useState
컴포넌트의 state(상태)를 관리 할 수 있다.<br>
상태에 따라, 다른 화면 출력
```js
import { useState } from "react";
const App = () => {
  const [isMobile, setIsMobile] = useState(false);
  console.log(isMobile) // false
  setIsMobile(true);
  console.log(isMobile) // true
  return '';
}
```

### useEffect
렌더링 이후에 실행할 코드를 만들수 있다.<br>
어떤 변수가 변경될때마다(의존성), 특정기능이 작동하도록 할 수 있다.
- 비동기 방식
```js
import { useEffect } from 'react'
const App = (data) => {
  useEffect(() => {
    console.log('data Change'); // data 가 변경될 때 마다 해당 console.log 출력
    return () => {
      console.log('언마운트') // 컴포넌트 초기화에 사용 
    }
  }, [data])
  return '';
}
```
### useLayoutEffect
모든 DOM 변경 후 브라우저가 화면을 그리기(render)전에 실행되는 기능을 정할 수 있다.
- 동기 방식 ( 끝날때까지 React가 기다림 )
```js
import { useLayoutEffect } from 'react'
const App = (data) => {
  useLayoutEffect(() => {
    console.log('data Change'); // data 가 변경될 때 마다 해당 console.log 출력
    return () => {
      console.log('Layout이 사라짐') // 컴포넌트 초기화에 사용 
    }
  }, [data])
  return '';
}
```
### useContext
부모컴포넌트와 자식컴포넌트 간의 변수와 함수를 전역적으로 정의할 수 있다.
```js
// newContext.js
import { createContext } from "react"  // createContext 함수 불러오기
// context안에 homeText란 변수를 만들고, 공백("") 문자를 저장한다.
const newContext = createContext({
  homeText: "",
})
```
```js
import React from "react";
import Home from "./Home"; // 자식 컴포넌트 불러오기
import { newContext } from "./newContext"; // context 불러오기
const App = () => {
  // context에 저장할 정보를 입력한다.
  const homeText = "is Worked!"
  // NewContext.Provider로 우리가 만든 context를 사용할 부분을 감싸준다.
  return (
    <newContext.Provider value={{ homeText }}>
      <Home />
    </newContext.Provider>
  );
}
export default App;
```
```js
// Home.js
import React from "react";
import { useContext } from "react";
import { newContext } from "../newContext";
const Home = () => {
  // useContext hook 사용해서, newContext에 저장된 정보 가져오기
  const { homeText } = useContext(newContext);
  // 불러온 정보 사용하기!!
  return (  
    <p>{homeText}<p>
  );
}
export default Home;
```
> React에서 context 없이 변수나 함수를 자식 컴포넌트로 전달하려면 Prop을 이용한 부모자식에서만
> 가능하므로 자식이 자식컴포넌트가 계속 추가 될수록 계속 prop을 넘겨야 하는데
> context 를 이용하면 중간을 처지지 않고 바로 제일 하위 자식으로 전달할 수 있다. 

> 전달하고자하는 컴포넌트에 context를 만들면, 불필요한 호출이 추가될 수 있으므로, context 전용 파일을 만들어야 한다.
> [예시 조건] <br>
> 컴포넌트 : A, B, C, D  ( A가 최상위 컴포넌트 ) <br>
> 전달 : A -> D <br>
> A 컴포넌트에 context 생성 <br>
> D 컴포넌트에서 context 불러옴 <br><br>
> [실행 과정] <br>
> A가 렌더링되며, B, C, D를 차례로 불러옴 <br>
> D에서 context를 가져오기위해 A를 다시불러옴 <br>
> A를 다시 불러오면서, 불필요한 중복이 발생함

### useMemo
의존성 배열에 적힌 값이 변할 때만 값,함수를 다시 정의할 수 있다. ( 재랜더링시 정의 안함 )<br>
Memoization : 과거에 계산한 값을 반복해서 사용할때, 그 값을 캐시에 저장하는 것
- 재귀함수에 사용하면, 불필요한 반복 수행을 대폭 줄일 수 있다.
- 의존성을 가지므로, 첫렌더링시에만 저장할 변수를 설정할 수 있다.

```js
import { useMemo } from 'react'
const App = () => {
  const data = useMemo(() => "data", []);
  // 데이터 변수는 의존성 배열(dependency) []에따라 선언된다. ( []사용시, 첫 렌더링 시에 1번만 선언 )
  return '';
}
```
### useCallback
의존성 배열에 적힌 값이 변할 때만 값,함수를 다시 정의할 수 있다. ( 재랜더링시 정의 안함 )<br>
useMemo의 함수버전

```js
import { useCallback } from 'react'
const App = () => {
  const data = useCallback(() => console.log(data), []);
  // 데이터 변수는 의존성 배열(dependency) []에따라 선언된다. ( []사용시, 첫 렌더링 시에 1번만 선언 )
  return '';
}
```
### useRef
HTML요소(태그)나 컴포넌트의 메모리주소를 가져와, 객체(레퍼런스) 형식으로 관리할 수 있다.
- current 속성을 가지고 있는 객체를 반환한다.
- current 값이 바뀌어도, 재렌더링 되지 않는다.
- 재렌더링시에도, current 값은 없어지지 않는다.
```js
import React, { useRef } from "react";
const Field = () => {
  const inputRef = useRef(null);
  function handleFocus() {
    inputRef.current.focus();
  }
  return (
    <>
      <input type="text" ref={inputRef} />
      <button onClick={handleFocus}>입력란 포커스</button>
    </>
  );
}
```
#### forwardRef
useRef로 만든 래퍼런스를 상위 컴포넌트로 전달할 수 있다.
```js
import React, { useRef, forwardRef } from "react";
const Input = forwardRef((props, ref) => {
  return <input type="text" ref={ref} />;
});
function Field() {
  const inputRef = useRef(null);
  function handleFocus() {
    inputRef.current.focus();
  }
  return (
    <>
      <Input ref={inputRef} />
      <button onClick={handleFocus}>입력란 포커스</button>
    </>
  );
}
```
> forwardRef() 함수를 호출할 때 다음과 같이 익명 함수를 넘기면 브라우저에서 React 개발자 도구를 사용할 때 컴포넌트의 이름이 나오지 않아서 불편할 수가 있는데요.<br>
> React 개발자 도구에서 forwardRef() 함수를 사용해도 컴포넌트 이름이 나오게 하는 3가지 방법.
1. `forwardRef()` 함수에 익명 함수를 대신에 이름이 있는 함수를 넘깁니다.
```js
const Input = forwardRef(function Input(props, ref) {
  return <input type="text" ref={ref} />;
});
```
2. `forwardRef()` 함수의 호출 결과로 기존 컴포넌트를 대체합니다.
```js
function Input(props, ref) {
  return <input type="text" ref={ref} />;
}
Input = forwardRef(Input);
```
3. `forwardRef()` 함수의 호출 결과의 `displayName` 속성에 컴포넌트 이름을 설정해줍니다.
```js
const Input = forwardRef((props, ref) => {
  return <input type="text" ref={ref} />;
});
Input.displayName = "Input";
```
### useImperativeHandle
useRef로 만든 래퍼런스의 상태에 따라, 실행할 함수를 정의 할 수 있다.
```js
import {useRef, useImperativeHandle} from 'react'
const ImperativeTextInput = (props, ref) => {
  const textInputRef = useRef<TextInput | null>(null);
  
  // ref을 전달받아, 메소드를 만들어준다. ( 다른 ref 호출 가능 )
  useImperativeHandle(
    ref,
    () => ({
      focus() {
        textInputRef.current?.focus();
      },
      dismiss() {
        Keyboard.dismiss();
      },
    }),
    [],
  );
  return <TextInput ref={textInputRef} {...props} />;
};

export default forwardRef(ImperativeTextInput);
```

### useReducer
state(상태) 업데이트 로직을, reducer 함수에 따로 분리 할 수 있다.

```js
import React, { useReducer } from "react";

function init(initialState) {
  return { count: initialState };
}

function reducer(state, action) {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + action.payload };
    case "DECREMENT":
      return { count: state.count - action.payload };
    case "RESET":
      return init(action.payload);
    default:
      throw new Error("unsupported action type: ", action.type);
  }
}

const Counter = ({ initialCount }) => {
  const [state, dispatch] = useReducer(reducer, initialCount, init);

  return (
    <>
      <h2>{state.count}</h2>
      <button onClick={() => dispatch({ type: "RESET", payload: 0 })}>
        초기화
      </button>
      <button onClick={() => dispatch({ type: "INCREMENT", payload: 1 })}>
        증가
      </button>
      <button onClick={() => dispatch({ type: "DECREMENT", payload: 1 })}>
        감소
      </button>
      <button onClick={() => dispatch({ type: "kkkkkkkkk", payload: 1 })}>
        에러
      </button>
    </>
  );
};

export default Counter;
```


### useDebugValue
사용자 정의한 Hook의 디버깅을 돕기 위해 쓰이며 chrome React Developer Tools 을 통해 사용한 hook 의 데이터 값이나 혹은 label 식으로 입력하여 어떤 Hook 을 썻는지 알 수 있다.

```js
import { useDebugValue, useState } from 'react'
export const useUserInformation = (user) => {
  const [user, setUser] = useState(user);
  useDebugValue(`useUserInformation Hook ${user}`);
  return user;
}
```