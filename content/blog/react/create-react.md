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

#### yarn 설치  (글로벌)
- yarn 'npm install -g yarn' [참조](https://www.holaxprogramming.com/2017/12/21/node-yarn-tutorials/)

#### prettier 설정
- prettier `yarn add prettier --dev` [참조](https://dev-yakuza.posstree.com/ko/react/prettier/) <br>
  ROOT 에 .prettierrc.js 생성
```
module.exports = {
    ingleQuote: true,
    // 문자열은 작은 따옴표로 통일
    semi: true,
    //코드 마지막에 세미콜른이 자동 생성
    useTabs: false,
    //탭의 사용을 금하고 스페이스바 사용으로 대체
    tabWidth: 4,
    // 들여쓰기 너비는 4칸
    trailingComma: 'all',
    // 객체나 배열 키:값 뒤에 콤마 생성
    printWidth: 160,
    // 코드 한줄이 maximum 80칸
    arrowParens: 'avoid',
    // 화살표 함수가 하나의 매개변수를 받을 때 괄호 생략
};
```
#### eslint 설정 (react-app)
- `yarn add eslint-config-prettier eslint-plugin-prettier --dev`<br>
  - eslint-config-prettier : ESLint와 Prettier에 중복되는 Formatting 룰 삭제<br>
  - eslint-plugin-prettier : ESLint에 Prettier의 Formatting 기능 추가
- eslint `yarn add eslint-config-react-app eslint@^8.0.0 --dev`
  ROOT 에 .eslintrc.json 생성
```
{
    "extends": ["react-app", "plugin:prettier/recommended"],
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
>  참조 : [https://velog.io/@cookncoding/ESLint-Prettier-Airbnb-Style-Guide%EB%A1%9C-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0](https://velog.io/@cookncoding/ESLint-Prettier-Airbnb-Style-Guide%EB%A1%9C-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0) 

### mui 설치
- @mui/material @emotion/react @emotion/styled `yarn add @mui/material @emotion/react @emotion/styled @mui/styled-engine-sc` [Document](https://mui.com/material-ui/getting-started/installation/)

### styled-components 설치
- styled-components `yarn add styled-components` [Document](https://styled-components.com/)


- react-router `yarn add react-router react-router-dom`
- react-error-boundary `yarn add react-error-boundary` [참조](https://velog.io/@bbaa3218/React-%EC%97%90%EB%9F%AC-%EB%B0%94%EC%9A%B4%EB%8D%94%EB%A6%ACError-Boundary)


### 절대 경로 설정하기
Root에 tsconfig.json(typescript) or jsconfig.json 생성
```
{
    "compilerOptions": {
        "baseUrl": "src",
    },
    "include": ["src"]
}
```

***
## create react app 시 발생하는 npm ERR! code ENOVERSIONS 에러
```
npm ERR! code ENOVERSIONS
npm ERR! No valid versions available for react-create-app
```
[https://github.com/facebook/create-react-app/issues/8097](https://github.com/facebook/create-react-app/issues/8097) 

> npm cache clean —force  // 캐시 삭제 <br>
> npm uninstall -g create-react-app // CLI 지우기 <br>
> rm -rf /usr/local/bin/create-react-app // 강제로 폴더 지우기

---
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



## Material UI
[MUI Document](https://mui.com/material-ui/getting-started/installation/)
기본
`yarn add @mui/material @emotion/react @emotion/styled`
width styled-components
`yarn add @mui/material @mui/styled-engine-sc styled-components`
