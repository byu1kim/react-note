+++
title = "Basic"
weight = 1
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

## What is React?

**리액트는 자바스크립트의 라이브러리!** 메타가(구 페북) 만들었음. 웹사이트나 모바일 앱의 `View`(눈에 보이는 부분)을 개발하는 라이브러리.

쉽게 말해 걍 자바스크립트인데 좀 더 편하게 개발할라고 이것저것 모아둔 툴 중 하나임. 다만 리액트가 사용하는 유저도 많고 소스도 많아서 많이 쓰임.

{{< vbox pink >}}

<b>Library (라이브러리)</b><br>

개발할 때 필요한 <span class="hey">자원</span>들을 모아둔 것. 도움말, 메세지, 미리 작성된 코드, 함수 등 재사용이 가능한 기능을 미리 구현하는 것. <br>
ex) React, jQuery, Node.js에서 npm으로 설치한 것들
<br>
<br>
<b>Framework (프레임워크)</b><br>
개발할 때 필요한 <span class="hey">기본 뼈대(구조).</span> 기본적인 코드, 알고리즘, DB커넥션을 예로 들 수 있음.<br>
프레임워크라하면 보통 라이브러리를 포함함.
ex) Java의 Spring, Python의 Django, Angular, Vue.js

{{< /vbox >}}

정의상 리액트는 라이브러리긴 한데 프레임워크처럼 사용할 수 있어서 프레임워크로도 여겨진다함

## Why React?

왜? 하필 리액트? 라고 궁금할까봐 ㅎ

#### **1. 설계의 조직화**

졸라릐 번거롭게 매 페이지마다 html, style, js file 굳이 굳이 안만들어도됨. 한페이지에 다 쌉가.

설계하는 페이지 막 20개 있다 생각해보셈. 각 페이지마다 html/style/js 파일 있으면 쳐다보기도 싫을듯

(있어보이게 말하고싶으면 **organization, reusability, flexibility** 때문에 리액트 쓴다 하면됨 ㅎ)

**Component(컴포넌트)** 사용이 그 중 대표적인 예인데, 리액트로 코드 짤 때는 페이지 별로 짜고 그 안에 자잘한 기능들 나눠서 또 쪼갬. 스니팻 오브 스니펫,, 컴포넌트는 리액트하면서 자주 쓰게 될거라 자세한 내용 생략할게유. 걍 코드 덩어리라고 생각하셈

#### **2. DOM**

리액트의 꽃 oh oh **Virtual DOM** ohoh

{{< vbox pink >}}

<b>DOM (Document Object Model)</b><br>
HTML에 자바스크립트 연결하기 위한 개념.
<br>
<br>
<b>Virtual DOM</b><br>
메모리에서 DOM을 미리 처리하고 저장한 후 나중에 실제 DOM이랑 동기화하는 개념.
{{< /vbox >}}

기존 DOM을 쓰면 자바스크립트 사용될때마다 페이지 다시 새로고침;;(Re-rendering). 글자 다섯번 고치면 5번 리렌더되는 매직~! 그럼 페이지가 너무 느려지겠지용

그래서 생긴게 VirtualDOM임. 말그대로 가상의 DOM, 메모리에 가상으로 만들어서 자바스크립트를 사용하게 하니까 수정 막 해도 리렌더 안되니까 당연히~~~ 속도가 빠르겠지요? 그래서 씀

**결론: 빠르다**

그 외의 장점은 차근차근 리액트를 쓰면서 알아가봅시다잉 그럼 리액트 깔아봅세 ㄱㄱ

## How to setup

#### 1. Install Node

노드가 이미 설치되어 있다면 이 부분 스킵하세용

**노드 설치되어있는지 확인하는 법**

Window : Command Prompt, Mac : Terminal 열고 이거 치셈

```
node -v
```

밑에처럼 나오면 깔려있는 거임 (nn은 설치되어있는 버전 숫자임)

```
v16.nn.n
```

없으면 여기 들어가서 다운로드 받고 설치ㄱ : https://nodejs.org/en/download

#### 2. React Quick Start

자 아까 열어둔 커맨드 프롬트(윈도우) 혹은 터미널(맥) -너 컴터 뭔지 몰라서 두개 다 알려줌- 암튼 거기에 이러케 치셈 : `npx create-react-app [폴더이름]`
폴더이름 대신에 당연히 너가 원하는 이름으로 변경하고.. 밑에는 예시가 되겠음.

아 참고로 너가 현재 위치한 경로 기준으로 폴더가 생성되니까 너가 편하게 접근할 수 있는 폴더에서 만들면 좋음. 이걸 커맨드에서 하는게 귀찮을테지만,, 명령어 정리해드림.

나의 경우 걍 데스크탑에 저장함.

> 간단 명령어 모음

| 명령어 | 의미                                     |
| ------ | ---------------------------------------- |
| cd     | 해당 폴더로 이동                         |
| cd /   | 최상위 폴더로 이동 (루트디렉토리)        |
| cd ..  | 한 단계 상위 폴도로 이동 (뒤로가기 같은) |
| pwd    | 현재 어떤 디렉토리에 있는지 알려줌       |
| ls     | 현재 폴더에 어떤 하위 폴더 있는지 보여줌 |

(마.. 맞을걸..? 맥이랑 윈도우랑 헷갈림 써보고 안되면 구글 고고!)

암튼 아래 명령어 실행하면 현 폴더 위치에서 리액트 폴더 생성됨

```
npx create-react-app calculator
```

그리고 나서 방금 만든 폴더로 입장

```
cd calculator // 방금 만든 프로젝트(폴더) 이름
```

자 이제 매직 스타또 : 리액트 실행하기

```
npm start
```

그럼 자동으로 localhost:3000 오픈 됨. 닫으셈 우리 이제 폴더 정리해야함. 아까 커맨드 창에서 `컨트롤 + c` 누르면 종료될거임.

#### **3. Folders in React**

VSC에서 방금 만든 폴더를 오픈해봅시다.

![name](/basic1.png?width=20pc)

이러케 생김. 밑에 사진에 빨간줄 친거 거침없이 지우도록.

![basic2](/basic2.png?width=25pc)

그리고 `index.js`에 들어가서 아래 복붙 (원래 있는거 다 지우고)

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

그 다음 `App.js` 들어가서 아래 복붙

```js
import "./App.css";

function App() {
  return <div>ㅎㅇ</div>;
}

export default App;
```

자 이제 앱을 좀 수정했으니 어떻게 실행되는지 봐야하는데,, 커맨드 다시 켜서 every time hit 'npm start'하면 졸라 귀찮겠지요?

메뉴에서 `Terminal > New Terminal` 선택합니다. 그럼 하단에 커맨드창 나옴. 이제 여기서 npm start 하면 됨.

```
npm start
```

자 이제 기본 세팅 끝~~~

다음 시간에 만나요~~~

#### Docs

모르는게 있으면 공식 문서에서 찾아보는 습관을 들이도록 합시다.

- Eng

  https://legacy.reactjs.org/docs/getting-started.html

- Kor

  https://ko.legacy.reactjs.org/docs/getting-started.html
