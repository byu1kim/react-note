+++
title = "Style"
weight = 3
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

리액트에서 쓸 수 있는 스타일은 여러개가 있지,,, 자세한건 나중에 알아볼거고

지금 파트에선 딱 두개만 알아볼게

## className + css파일

이건 걍 자바스크립트랑 똑같아

css 파일 가져오고, 클래스네임 지정해주고, css해주면 끝

리액트 열면 생기는 기본적인 App.js에서 스타일하는 예시 들어볼게

[App.js]

```js
import "./App.css"; // 이렇게 css파일을 가져오고!

function App() {
  return <h1 className="App">Hello!</h1>; //클래스 네임 지정하고!
}

export default App;
```

[App.css]

```css
.App {
  color: blue;
}
```

이런식으로 적용하면 된다잉

## Inline style

그 담에 JSX안에서 css쓰는걸 인라인스타일이라해

한줄에 스타일 갈겨서 인라인 스타일 이라고 하는거 가틈 ㅎㅎ;;

```js
function App() {
  return <h1 style={{ color: "blue" }}>Example page</h1>;
}
```

일반 css랑 똑같은데 태그 하나하나에 스타일이라고 해주고 `괄호 2개` 써준담에 그 안에다가 스타일 써주면돼

주의할점은 background-color 같은건 `backgroundColor` 이렇게 camelCase로 대체해서 해주면 된다잉!
