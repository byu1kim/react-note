+++
title = "State"
weight = 7
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

드디어 리액트의 꽃

스테이트를 ... 알려줄때가 된것 같다.....

스무스하게 스테이트를 이해하기 위해 거쳐야할 관문이 좀 많았다 그치

근데 스테이트 쓰는 순간 이제 넌 리액트를 할줄 아는 인간이 되는 것이다

ㅋㅋㅋ

## What is State

스테이트는 컴포넌트를 위한 변수라고 생각해봅시다

사실 변수보단 객체가 맞는 말인데 아직까진 우린 변수 개념에서만 쓸거임

스테이트 왜쓰냐고?? 페이지를 리로드 안해도 변수를 막바꿀수 이씀

어 그럼 이거랑 헷갈릴거 가틈

`let name;` 이거 쓰면 리로드 안해도 변수 바꿀수 있자나 >0<

ㄴㄴ let은 컴포넌트 내에서 저장이 안됨 ,, 그래서 스테이트를 쓰는거임

(스테이트 관련 자세한거는 내가 리서치해서 더 자세히 정리해줄게 ㅋㅋㅋㅋ 지금은 일단 사용법먼저!)

## How to use State

스테이트는 리액트에만 있는 개념이라 순수 자바스크립트로 쓰면 안되고

이거 사용할 수 있게 가져와야함

버튼 컴포넌트 계속 써보자

```js
import { useState } from "react";

function Button() {
  return (
    <>
      <button>+</button>
      <button>-</button>
    </>
  );
}
export default Button;
```

스테이트 활용 알아보기 위해 필요 없는 부분 지웠음

자 맨 첫번째줄에 `useState` import 한거 보이시나요~~

스테이트 쓰려면 저거 필수임 !! 리액트 내장된거임

우리 이제 뭐할거나면 버튼 클릭하면 숫자 바뀌는거 할거임

플러스 누르면 숫자가 올라가고 마이너스 누르면 숫자 내려가는거

그러려면 뭐가 필요할까????

.

.

.

.

.

생각할시간 드리는거임

1. 숫자 올라가는 이벤트랑 그 함수

2. 숫자 내려가는 이벤트랑 그 함수

3. 디스플레이 할 숫자

요런게 필요하겠지

```js
import { useState } from "react";

function Button() {
  let count = 0;
  function clickPlus() {
    count == 1;
  }

  function clickMinus() {
    count -= 1;
  }
  return (
    <>
      <button>+</button>
      <div>{count}</div>
      <button>-</button>
    </>
  );
}
export default Button;
```

머 대충 이렇게 되려나 ?????

근데 ..... 우리가 생각하는거처럼 안됨

왜냐면 변수가 실시간으로 안바뀜 ㅠ 이미 카운트는 디스플레이 됐으니까... let 따위로 변수는 변하지 않아....

스테이를 쓰면 어케되는지 보여줄게

```js
import { useState } from "react";

function Button() {
  const [count, setCount] = useState(0);

  function clickPlus() {
    setCount(count + 1);
  }

  function clickMinus() {
    setCount(count - 1);
  }

  return (
    <>
      <button onClick={clickPlus}>+</button>
      <div>{count}</div>
      <button onClick={clickMinus}>-</button>
    </>
  );
}
export default Button;
```

이거 그대로 복붙해서 써봐

그럼 우리가 원하는대로됨

오오 !!!!!

보면 페이지가 리로드 안됐는데도 숫자가 막변하지???

이게 바로 리액트의 꽃이 스테이트라는 것이다 ,,,

그럼 어케 쓰는지 설명들어가볼게

#### UseState

```js
const [count, setCount] = useState(0);
```

이 부분이 스테이트를 사용하는 건데,

[] 여기 대괄호 안에 첫번째 변수는 너가 사용할 변수야

두번째변수는 앞에 변수를 변화하기 위해 사용하는 함수같은 느낌이야

useState(...) 이 부분은 처음에 셋팅할 값이야

만약 너가 처음에는 아무것도 세팅 안하고 싶다 ?? `useState()` 이렇게만 해도 됨

이름은 너 맘대로 해도 됨, 어짜피 첫번째는 변수, 두번째는 그를 변화시키기 위한것 이기 때문에

하지만 코드 리딩이나 너가 쓸때 편하려고 모두가 첫번ㄹ째는 변수 이름, 두번째는 set변수이름 이러게 설정함

유즈 스테이트 덕분에 컴포넌트안에서 변수를 마음껏 변화시킬수 있지

변수 변화는 어케 시키냐면 이놈으로 : `setCount(newValue)`

함수개념이라고 햇자나? 함수처럼 파라미터 안에 새로운 변수를 넣으면 그게 이제 저 count의 값이 되는고양

이놈이 계산기 만들때 핵심 역할을 할것 ,,, 잘 기억해두도록 !!

---

자 여기까지 리액트 기초 끝~~!!

https://react.dev/learn

이 페이지를 처음부터 차근차근 읽어보면 좋을거여유

내가 설명한거 저기서 다 있는 내용이고 리액트 기초 오브 기초 다지기 위한 핵심임
