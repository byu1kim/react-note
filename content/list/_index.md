+++
title = "List"
weight = 6
pre = "<i class='fas fa-book-open'></i> &nbsp"
+++

어쩌면 리액트의 꽃이라고 할 수 있는 ...

리스트 = 어레이 사용하기 ..

계속 해오던거 연장선으로 버튼 컴포넌트 가지고 놀아봅시다

```js
function Button({ name }) {
  const buttonList = ["Button1", "Button2", "Button3"]; // Declare array

  return (
    <>
      {buttonList.map((item, index) => (
        <button key={index}>{item}</button>
      ))}
    </>
  );
}
export default Button;
```

보면 알겠지만 저렇게 어레이를 선언하고 매핑을 해서 JSX 활용도 가능해

어레이 같은 자바스크립트 변수 쓸때는 `{}`요거로 항상 감싸주고! 안그러면 그냥 텍스트로 인식됨

그리고 중요한 `key` !!!!!

솔직히 저거 없어도 잘만 돌아감

그런데 어레이에 있는 아이템중에 얘가 어디에 속한건지 모르자나 ?? 그래서 key 를 지정하는거

map할 때 두번째 파람은 아이템 그 자체이고 두번째는 index (순서)가 넘어가는데

그게 그나마 유니크한 번호라 그걸로 key를 정해주는거야

`Array로 mapping 하는 경우 각 아이템은 key가 필요하다`

이 정도로 이해하고 넘어가시면 되겠습니다~!

---

자바스크립트에서 어레이는 공부햇을거라 생각하고 자세한건 생략 헤ㅔㅎ

map 말고도 어레이 쓸수 있는거는 아래 링크에서 확인하세요

리액트에서 저런거 개많이쓰임@@@ foreach 이런거 잘 안씀

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
