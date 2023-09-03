+++
title = "JSX"
weight = 3
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

컴포넌트에서 return 다음에 오는걸 JSX라고 함.

누가 봐도 HTML인데 굳이 JSX라고 불러야해?;; 라고 궁금할 수 있으나

자세히 보면 좀 다름.. 컴포넌트 가져오는 것도 그렇고 HTML에서 안되는게 몇개 있음

그리고 쓰는 방법도 좀 다름

그래서 JSX라고 하고 그만의 규칙이 또 있음 이제 이걸 알아볼거임

{{< vbox pink >}}
JSX : Javascript syntax for writing HTML in React
{{< /vbox >}}

#### Markup

```js
function Example() {
  return (
    <>
      <h1>Example page</h1>
      <p>Hello there!</p>
    </>
  );
}
```

자 보시면 알겠지만 JSX는 별게 없습니다

`return` 써주고 `()` 이걸로 묶고 `<> </>` 이걸로 또 묶어줌

그 안에는 평범한 HTML 쓰세용

근데 가끔 이렇게 쓰고싶은 경우가 있음

```js
return (
<section>section1</section>
<div>section2</div>)
```

차이점 보임?? 태그가 두개 있는데 이걸 `<> </>` 이걸로 안묶어줬잖아

그럼 리액트가 어라? 얘 덩어리가 두개가 있네? 하고 에러 던져버림

그니까 웬만하면 `<></>`로 꼭 묶어줘

```js
return (
  <section>
    section1
    <div>test test</div>
  </section>
);
```

이런식으로 태그 하나가 전체를 감싸는 경우엔 `<> </>` 이거 안써두 됨

#### Class

JSX와 HTML의 다른점 또 하나. 클래스..가 좀 다름

HTML에서 클래스 쓸라면
`<div class="name"></div>`
이런식으로 썻자나? 리액트에선 그렇게 하면 앱은 돌아가는데 콘솔에서 에러 메세지 뜸

그럼 어케쓰냐

```js
<div className="name"></div>
```

클래스말고 클래스네임으로 쓴다 ㅇㅋ? 이지피지?

#### Comment

기존에 썼던 코멘트 방식 `<!---->` 이거나 `//` 이거 jsx에서 안됨

`{/* */}` 이렇게 써주세용
괄호 열고 코멘트 하고 중간에 쓰고싶은말 쓰기~

#### Displaying Data

자바스크립트에서 사용한 variable을 jsx에서 쓸 수 있어

```js
function Example() {
  const name = "Name";

  return (
    <>
      <h1>Example page</h1>
      <p>Hello there, {name}</p>
    </>
  );
}
```

자 이러케 로직 부분에 우리가 변수 선언을 했자나

이걸 그냥 바로 갔다 쓸수 있음

벌써 개편하지 않음 ??? 굳이 다른 자바스크립트 파일 안열어도 여기서 한번에 다 가능한거임

데이터 쓰는 방법은 위에서 봐서 알겠지만 `{name}` 이렇게 괄호 열고 안에 변수 이름 ㄱㄱ

자 여까지 했으면 리액트 기본 개념은 끝났습니다

이제부터는 코딩을 위한 실전 개념 알아갈거임

더 궁금한 건 늘~~ 공식문서 참고하는 습관!

https://react.dev/learn

다음페이지로 가주세용 !
