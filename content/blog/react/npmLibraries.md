---
title: 'React 개발시 추천 npm 라이브러리'
date: 2022-12-2 16:41:13
category: 'React'
draft: false
---

## React Query 
[npm Link](https://www.npmjs.com/package/react-query)
<br>
React로 데이터를 가져오는 과정에는 일반적으로 많은 코드가 필요합니다. React Query를 사용하면 네트워크 요청을 할 때 작성하는 코드의 양을 줄일 수 있습니다. 훅을 사용하여 useQuery이전에 작성해야 했던 모든 React 코드를 대체할 수 있습니다. 상태 변수를 선언하지 않고도 필요한 모든 데이터를 제공합니다.

그럼에도 불구하고 데이터 검색을 더 쉽게 만드는 것은 React Query가 하는 일의 작은 부분만을 다루고 있습니다. 그 엄청난 힘은 우리가 만드는 요청을 캐시하는 능력에 있습니다. 결과적으로 이미 요청한 항목이 있으면 별도의 요청을 하지 않고 캐시에서 읽어오기만 하면 되는 경우가 많습니다.

이는 코드의 반복을 줄이고 API에 가해지는 부하를 줄이며 애플리케이션 관리를 간소화하기 때문에 매우 유용합니다.
```
npm i react-query
```
## React Hook Form
[npm Link](https://www.npmjs.com/package/react-hook-form)
<br>
React Hook Form은 간단한 데이터 유효성 검사를 허용하는 간단한 후크 기반 라이브러리입니다. 벤치마크에 따르면 다른 대안보다 훨씬 빠릅니다. React Hook Form의 후크 사용은 믿을 수 없을 정도로 자연스러운 느낌을 줍니다. 또한 참조(즉, 제어되지 않는 입력)를 사용하여 필드에서 값을 검색하여 표준 자바스크립트로 만듭니다.

Typescript로 작성되어 양식 값을 지원하기 위해 양식 데이터 유형을 작성하는 데 도움이 됩니다. 이 라이브러리를 사용하면 양식에 오류가 없어져 렌더링 시간이 영구적으로 단축됩니다. 또한 React의 상태 관리 라이브러리와 통합하여 사용할 수 있습니다.
```
npm i react-hook-form
```
## React Router
[npm Link](https://www.npmjs.com/package/react-router)
<br>
React Router는 개발자가 단일 페이지 앱에서 탐색을 간단하게 만들기 위한 최고의 구성 요소 라이브러리 중 하나입니다. 뿐만 아니라 라이브러리는 부드러운 화면 간 전환, 서버 측 렌더링 및 생생한 중첩 지원도 제공합니다.

React로 애플리케이션을 구축하는 경우 선언적으로 결합할 수 있는 특정 구성 요소가 있으면 도움이 됩니다. React 라우터는 이러한 구성 요소의 모음입니다.
```
npm i react-router
```
## Redux
[npm Link](https://www.npmjs.com/package/redux)
<br>
가장 인기 있는 상태 관리 라이브러리 중 하나는 Redux입니다. 20.9k GitHub 별과 3k 포크로 Redux는 최고의 구성 요소 라이브러리 범주에 속합니다. React UI의 라이브러리 구성 요소와 함께 사용하도록 특별히 제작되었지만 Vue, Angular, Ember 등과 같은 다른 프레임워크에서도 사용할 수 있습니다.

Redux는 React 구성 요소를 상태 조각에 연결하여 소품 및 콜백의 필요성을 줄입니다. 종종 개발자의 가장 친한 친구라고 합니다. Redux는 친환경 라이브러리이며 일관된 코드를 작성하는 데 도움이 됩니다. 또한 앱이 실행되는 동안 코드를 편집할 수 있습니다. React Native 에는 React-Redux라는 공식 Redux 라이브러리가 있습니다.
```
npm i redux
```
> 추가로 react-redux, redux-saga, redux-thunk

## Styled Components
[npm Link](https://www.npmjs.com/package/styled-components)
<br>
Styled component는 React가 CSS-in-JS 기술을 사용하여 JavaScript와 CSS를 결합하여 응용 프로그램의 구성 요소 수준 스타일을 허용하는 최신 방법 중 하나입니다. 즉, CSS 모듈의 후계자 역할도 합니다. 구성 요소의 시각적 스타일을 높임으로써 이 이니셔티브는 사용자 경험을 개선하는 것을 목표로 합니다. 따라서 React는 맞춤형 프론트엔드 UI를 구현하는 데 더 유연해졌습니다.
```
npm i styled-components
```

## @loadable/component


## Express
[npm Link](https://www.npmjs.com/package/express)
<br>
Express는 node.js의 웹 개발 프레임워크입니다. npm-stat.com에 따르면 Express가 출시된 2010년 5월부터 2019년 11월 현재 9억건이 넘는 다운로드 수를 기록했습니다. 사실 상, Node.js의 표준 프레임워크라고 볼 수 있는 Express는 다음과 같은 특징을 갖고 있습니다.

미들웨어
Express의 장점 중 하나는 ‘미들웨어’를 사용한다는 것입니다. 미들웨어는 Express가 요청(req)에 대한 응답(res)을 하기 전, 중간에서 특정 동작을 수행하는 프로그램을 의미합니다. 미들웨어를 통해 서버 통신 과정에서 수행되어야 하는 작업을 간편하게 처리할 수 있습니다. 예를 들어, 사용자 인증을 먼저 거친 후, 웹 페이지를 렌더링 하고 싶다면 인증 미들웨어를 작성하여 먼저 삽입해 주는 방식입니다.

라우팅
Node.js에 내제된 라우팅 기능보다 발전된 라우팅 기능을 제공합니다. 라우팅은 사용자가 보내는 URL에 따라 응답할 방법을 결정하는 것을 말합니다. Express는 REST API를 통해 라우팅 로직을 특정 디렉토리 아래에 모듈로 만들어 놓고 간편하게 불러와(require) 사용할 수 있습니다.

디버깅
응용 프로그램의 어느 부분에서 버그가 발생했는지 신속하게 찾아낼 수 있도록 쉬운 디버깅 매커니즘을 제공합니다. 내부적으로 디버그 모듈을 사용하여 경로 일치, 사용 중인 미들웨어 기능, 응용 프로그램 모드 및 요청-응답(request-response) 사이클 흐름을 기록하고 판단합니다.
Express를 이용해 별도의 코드를 작성하지 않고도 간단하게 웹 서버를 구현할 수 있는 방법을 확인해 보세요.
```
npm i express
```

## 그외
`prettier, jest, lodash, eslint, date-fns, axios, big.js, clsx, html-entities, js-cookie, immer `
