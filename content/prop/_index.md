+++
title = "Prop"
weight = 4
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

자 우리 이제 컴포넌트 배웠자나

전 페이지에서 `App.js`에서 `Button.js`를 가져온거 기억하지?

이때 App.js이 parent component, Button.js는 child component라함

그럼 Prop은 머냐???????????

부모 컴포넌트에서 자식컴포넌트로 변수를 보내는거야

{{< vbox pink >}}
Prop : Passing data from parent to child coomponent
{{< /vbox >}}

이해를 쉽게 코드로 예를 들어볼게

#### Parent component : App.js

```js
import Button from "./Button.js";

function App() {
  const name = "Sky";

  return (
    <div className="App">
      자 여기가 부모 컴포넌트 페이지다
      <Button propName={name} />
    </div>
  );
}
```

아까 버튼 컴포넌트 부를 때 name이란 변수를 이렇게 보내주는거야

근데 무작정 보내면 안되고 자식 컴포넌트에서 받겠다라고 선언한 변수만 받을 수 있어

먼말이냐고? 차일드 컴포넌트 봐보자

#### Child component : Button.js

```js
function Button({ propName }) {
  return <button>I'm a button for {propName}</button>;
}

export default Button;
```

보면 여기서 propName이라고 함수 이름 옆에 선언한게 보이지?

그럼 이 버튼 컴포넌트는 앞으로 이런 변수를 받겠다고 정한거야

Syntax주의! 괄호 안에 무작정 쓰면 안되고 {} 이거 써주고 안에 써야함.

보면 알겠지만 내가 보내려는 프랍이랑 차일드에 있는 프랍 이름이랑 똑같아야함

예를들어 부모 컴포넌트에서 `<Button prop={name} />` 이러케 보냈는데

자식 컴포넌트에서 `function Button({name}){...}` 이렇게 선언되어있다? 리액트가 프랍을 매칭을 못시켜서 에러남;;

#### Props more than 2

**Parent Component**

```js
...
  return (
    <div className="App">
      자 여기가 부모 컴포넌트 페이지다
      <Button propName={name} prop="haha" propppp="hoho" />
    </div>
  );
...
```

**Child Component**

```js
function Button({ propName, prop, proppp }) {
  return <button>I'm a button for {propName}</button>;
}
...
```

부모 컴포넌트에서는 걍 스페이스만 때려주면 되고

자식컴포넌트에서는 쉼표로 구분해주면 프랍 여러개도 보낼 수 있음!

자 지금까지 잘 따라와줘서 고맙고

이거 그대로 다 리액트에 직접 해봐야함

하나하나 타이핑해보고 실행해보고 어떻게 나오는지 나와는지 봐야해

간단해서 읽으면 이해될 수 있는데 막상 해보면 쉼표 잘못찍고 이래서 에러 많이나서 개 킹받거덩

더 복잡한거 나오기전에 여까지 이해하고 버튼 컴포넌트 만들어보면 좋아용
