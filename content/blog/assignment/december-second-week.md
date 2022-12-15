---
title: 12월 2주차
date: 2022-12-15 13:00:00
category: assignment
description : create-react-app
draft: false
---

- Terminal 을 통해 create-react-app 설치
- package.json 에 정의 되어 있는 library install
- package.json 에 scripts 에 정의 되어 있는 start 를 실행하여 설치 확인
- App.js 를 아래와 같이 만들기
```javascript
import './App.css';
import { useState } from 'react';
function App() {
  const [message, setMessage] = useState('Hello Word!!');
  return (
    <div className="App">
      {message}
      <button type="button">Message Change</button>
    </div>
  );
}
export default App;
``` 
- Hook useState 를 이해하고 `{message}`에 출력되는 'Hello Word!!' 를 버튼을 onClick 이벤트를 통해서 'Welcome!!' 로 문자 바꾸기   


