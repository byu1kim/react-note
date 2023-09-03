+++
title = "Component"
weight = 2
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

리액트로 만든 앱은 다 컴포턴트로 구성되어있음. 첨에 리액트 시작할 때 생성되는 App.js 이런거 전부 다 컴포넌트임

{{< vbox pink >}}
컴포넌트 = 로직 + 눈에 보이는 부분
{{< /vbox >}}

#### How to use Component

##### 1. Create component

src폴더 아래에 파일 아무거나 만든다. 젤 간단한거 버튼 만들어봅세.

파일 이름은 `Button.js` 로 해주세용

그리고 아래 코드를 직접 작성합니다 (복붙해도 되는데 그러면 감이 잘안올듯)

```js
// 파일 이름이랑 여기 함수 이름이랑 똑같이 해주면 좋음.
function Button() {
  // Logic goes here
  // 만약 나중에 버튼에 자바스크립트 효과 주고 싶으면 여기다 적는거임

  // Appearance (JSX)
  return <button>I'm a button</button>;
}

export default Button; // 다른 파일에서도 사용할 수 있게 export를 써줘야함. 이거 안해주면 다른 파일에서 이 컴포넌트가 존재하는지도 모름
```

##### 2. Use Component

리액트 앱 생성할 때 있는 App.js에서 버튼 컴포넌트 함 써볼게

[App.js]

```js
// 파일 가져오기 (import)
// 앞에 버튼은 아까 정한 함수이름, from 다음은 파일 경로임.
// 만약 컴포넌트 만들때 export 안하면 여기서 import가 안됨
import Button from "./Button.js";

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a className="App-link" href="https://reactjs.org" target="_blank" rel="noopener noreferrer">
          Learn React
        </a>
        {/* 이 쯤에다가 버튼 한번 추가해볼까? */}
        <Button />
      </header>
    </div>
  );
}
```

`<Button />` 이 부분이 컴포넌트 가져오는 부분임.

주목해야할게 컴포넌트 이름은 `대문자`로 해줘야해!

그리고 일반 태그랑 다르게 <이름 /> 이러케 슬래시 쳐줘야함

끝 ! 간단하지? 간단한 것들은 걍 외워두면 좋음

솔직히 컴포넌트 안쓰고 파일 하나에 (예를들면 App.js) 자바스크립트고 HTML이고 다 때려박을 수 있는데

그럼 코드가 넘 지저분해지고 라인 길어지고 나중에 관리 힘듬. 그래서 자주 쓰는거나 덩어리로 묶을 수 있는건 컴포넌트화 하는게 좋음.

첨에 할 때는 걍 한 페이지에 쭉 코드 짜보고 그담에 필요한거 컴포넌트로 나중에 만들어 됨
