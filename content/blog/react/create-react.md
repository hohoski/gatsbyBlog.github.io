---
title: create-react
date: 2022-12-13 13:12:31
category: React
draft: false
---

## create react-app

[Create React App web site](https://create-react-app.dev/) 
```
npx react-create-app my-app
```

### library install
- yarn 'npm install -g yarn' [참조](https://www.holaxprogramming.com/2017/12/21/node-yarn-tutorials/)
- eslint `yarn add eslint`
- prettier `yarn add prettier --dev`
- react-router `yarn add react-router`
- react-router-dom `yarn add react-router-dom`
- styled-components `yarn add styled-components` [Document](https://styled-components.com/)
- react-error-boundary `yarn add react-error-boundary` [참조](https://velog.io/@bbaa3218/React-%EC%97%90%EB%9F%AC-%EB%B0%94%EC%9A%B4%EB%8D%94%EB%A6%ACError-Boundary)
- 

### scripts 의 eject 시에 발생하는 esLine error
[facebook-github issue/12070](https://github.com/facebook/create-react-app/issues/12070)<br>
`package.json` 내부 `eslintConfig` 속성에 아래 설정을 통해 해결.
```js
{
/*... snip ... */
"eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ],
    "env": {
      "NODE_ENV": "development"
    }
  },
/*... snip ... */
}
```
음.. eslint 파일 .eslintrc 파일을 생성 후 plugins 를 빼면 다시 에러..
```
    "plugins": ["react-app"],
    "extends": "react-app",
    "rules": {
        "no-unused-vars": "off",
        "react-hooks/exhaustive-deps": "off",
        "no-throw-literal": "off",
        "no-sequences": "off",
        "require-yield": "off",
        "jsx-a11y/anchor-has-content": "off",
        "jsx-a11y/anchor-is-valid": "off",
        "import/no-anonymous-default-export": "off",
        "no-useless-escape": "off"
    }
```

## Prettier
협업시 코드 포맷을 맞추기 위해 Prettier 설치<br>
Prettier는 코드 포맷터(Code formatter)로써 미리 코드 포맷을 정의하고, 해당 포맷에 맞게 코드를 수정해 주는 역할을 합니다.

### 설치
```
npm install --save-dev prettier
```
### 설정
React에서 Prettier를 사용하기 위해서는 사용할 코드 포맷을 미리 정의할 필요가 있습니다. 코드 포맷을 미리 정의하기 위해, `.prettierrc.js` 파일을 생성하고 다음과 같이 수정합니다.
```js
module.exports = {
  singleQuote: true,
  // 문자열은 작은 따옴표로 통일
  semi: true,
  //코드 마지막에 세미콜른이 자동 생성
  useTabs: false,
  //탭의 사용을 금하고 스페이스바 사용으로 대체
  tabWidth: 4,
  // 들여쓰기 너비는 4칸
  trailingComma: 'all',
  // 객체나 배열 키:값 뒤에 콤마 생성
  printWidth: 80,
  // 코드 한줄이 maximum 80칸
  arrowParens: 'avoid',
  // 화살표 함수가 하나의 매개변수를 받을 때 괄호 생략
};
```

### format check and formatting
```
"scripts": {
  ...
  "format": "prettier --check ./src",
  "format:fix": "prettier --write ./src"
},
```


## eslint
[eslint Document](https://eslint.org/docs/latest/) <br>
extents : `eslint-config-react-app [npm istall eslint-config-react-app]` 
```
{
    "extends": "react-app",
    "rules": {
        "no-unused-vars": "off",
        "react-hooks/exhaustive-deps": "off",
        "no-throw-literal": "off",
        "no-sequences": "off",
        "require-yield": "off",
        "jsx-a11y/anchor-has-content": "off",
        "jsx-a11y/anchor-is-valid": "off",
        "import/no-anonymous-default-export": "off",
        "no-useless-escape": "off"
    }
}
```

## Material UI
[MUI Document](https://mui.com/material-ui/getting-started/installation/)
기본
`yarn add @mui/material @emotion/react @emotion/styled`
width styled-components
`yarn add @mui/material @mui/styled-engine-sc styled-components`
