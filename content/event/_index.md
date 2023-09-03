+++
title = "Event"
weight = 7
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

자바스크립트에서 쓰던 이벤트를 리액트에서는 어떻게 쓸까????

자바스크립트를 기억해보셈

엘레멘트 지정하고.. 애드이벤트리스터 어쩌고저쩌고...

쓸게 졸라 많았음

하지만 리액트는 다름

역시나 빠르게 예시로 보여줘보겠음

전 페이지에서 쓰던 버튼 컴포넌트로 계속 놀아보자구

## React event

```js
function Button({ name }) {
  const buttonList = ["Button1", "Button2", "Button3"];

  function handleButtonClick() {
    console.log("Button is clicked!");
  }

  return (
    <>
      {buttonList.map((item, index) => (
        <button key={index} onClick={handleButtonClick}>
          {item}
        </button>
      ))}
    </>
  );
}
export default Button;
```

차이점이 보이시나요????

네네 버튼 태그 옆에 `onClick`을 더하고 괄호에다가 함수이름을 적어주면 됩니다

지긋지긋한 `{}` 이 괄호를 잊지 말아주세염

로직 관련된 것들은 전부 컬리브라켓으로 감싸주기,,, 기억할것 !

근데 !!! 중요한건 !!! 함수 부를때 () 이거 안씀 . 오로지 이름만 !

리액트가 벌써 좋아지면 어떡하쥐

ㅋㅋㅋㅋㅋ

## Event with parameter

만약 함수에 파라미터를 전달해야할 때 신택스가 살짝 바뀌기 때문에

여기서 짚고 넘어가보겠음

```js
function Button({ name }) {
  const buttonList = ["Button1", "Button2", "Button3"];

  function handleButtonClick(name) {
    console.log(`Button ${name} is clicked!`);
  }

  return (
    <>
      {buttonList.map((item, index) => (
        <button key={index} onClick={() => handleButtonClick(item)}>
          {item}
        </button>
      ))}
    </>
  );
}
export default Button;
```

보,, 보이시나요 차이점!!!!

함수이름 대신에 `()=> handleButtonClick(item)`이라고 한 부분..!!!

`onClick={handleButtonClick(item)}` 이렇게 하면 안됩니다용 ,,

왜 안되는지는 나도 모르겠어 어딘가에서 그 이유를 읽어본거 같은데,, 까먹음 ㅎ

이유 아시는 분 알려주세용~~~~
