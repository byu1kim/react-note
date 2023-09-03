+++
title = "Conditional"
weight = 5
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

이제부터 좀 재밌는거 해볼거임

JSX에서 조건문 쓸 수 있음 !!! HTML이랑 쌉다름 ㅋ

우리 아까 배운거에서 계속 연장선임

App.js에서 프랍 보내서 Button.js로 보냈자나

만약에 그 프랍에 따라서 버튼 색깔이 바뀌는거 해보자구 !

근데 프랍이름이 좀 거지같으니까 그냥 name으로 바꿀게

```js
function Button({ name }) {
  let buttonColor;

  if (name === "sky") {
    buttonColor == "skyblue";
  } else {
    buttonColor == "yellow";
  }
  return <button style={{ backgroundColor: buttonColor }}>I'm a button for {name}</button>;
}

export default Button;
```

대충 코드 짜면 이렇게 되겠지?? 자바스크립트는 알고 있다고 들어서 설명 생략할게

궁금한거 있음 물어봐줘~~!!

하이튼 버튼컬러라는걸 정했는데 만약에 전달된 프랍이 `sky`면 스카이블루 라는 스트링을 저장하고

그 외에 전달되면 노란색으로 버튼컬러를 지정하는 코드얌

여까지 잘되는지 테스트하면서 해야해~~!!

부모컴포넌트에서 프랍 바꿔가면서 색깔 바뀌는지도 확인해봐!!

## Ternary operator

자 그담에 더 잼나는거 알려드림

저 위에 짠 코드를 단 몇줄로 고칠 수 있다면???

고쳐볼게

```js
function Button({ name }) {
  return <button style={{ backgroundColor: name == "sky" ? "skyblue" : "yellow" }}>I'm a button for {name}</button>;
}

export default Button;
```

작동 똑같이됨

일단 JSX안에서 조건문이 된다는 사실 !!!!!!

이렇게 한줄에 조건문 있는걸 Ternary operator라고해. 조건문 + true + false 인 세가지의 경우를 다 다뤄서 그렇게 말하는듯

형식은

`Condition ? true result : false result`

이렇게 됩니다 외우세용!

여기서 condition의 결과값이 true가 되는 경우를 `truthy`라 하고

그 반대로 false가 되는 경우를 `falsy`라 함

컨디션 이상하게 짜버리면 원하는 결과가 안나오니까

어떤 경우가 트루띠인지 펄시인지 구별 잘해야하거덩

자세한 건 구글이나 이걸 한번 읽어보셔용

https://sentry.io/answers/truthy-and-falsy-values-in-javascript/
