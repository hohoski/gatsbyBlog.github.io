---
title: '3장 자바스크립트 개발 환경과 실행 방법'
date: 2022-12-2 10:03:00
category: 'DeepDive'
draft: false
---

# 자바스크립트 실행 환경
모든 브라우저는 자바스크립트를 해석하고 실행할 수 있는 자바스크립트 엔진을 내장하고 있다.
브라우저뿐만 아니라 Node.js 도 자바스크립트 엔젠을 내장하고 있다.
따라서 브라우저가 아닌 다른 환경에서 자바스크립트를 실행하기 위해서는 Node.js 가 필요하다.<br>
주의해야 할 점은 브라우저와 Node.js는 용도가 다르다는 것이다. 브라우저는 HTML, CSS, 자바스크립트를 실행해 웹페이지를 브라우저 화면에 렌더링 하는것이 주된 목적이지만 Node.js는 브라우저 외부에서 자바스크립트를 실행 환경을 제공하는 것이 주된 목적이다.<br>
따라서 ECMAScript를 실행할 수 있지만 그외 브라우저 API들은 실행할 수 없다.
Node를 통해서 아래 예제를 실행하면
```js
const arr = [1,2,3];

arr.forEach(console.log);
```
위에 예제는 가능하지만 
```js
const arr = [1,2,3];

arr.forEach(alert);
```
위에 예제는 실행되지 않는다. alert 는 브라우저 에서만 동작하는 Web API 이기 때문이다.<br>

## Node.js 와 npm
2009년 라이언 달이 발표한 Node.js 는 크롬 V8 자바스크립트 엔진을 사용한다. <br>
npm(Node package manager)는 자바스크립트 패키지 매니저로 Node.js에서 사용할 수 있는 모듈들을 패키지화해서 모아둔 저장소 역할과 패키지 설치 및 관리를 위한 CLI(Command line interface)를 제공한다.<br>

Node.js 가 정상적으로 설치되면 터미널(윈도우 명령 프롬프트)에서 버전이 확인된다. <br>