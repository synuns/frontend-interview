# position

말 그대로 HTML 요소가 어떻게 문서 상에 배치되는지를 결정하는 css 속성이다.

화면 상의 정확한 위치를 지정하기 위해서 `top`, `right`, `bottom`, `left` 속성과 함께 사용된다.

## position의 종류

- position: static
- position: relative
- position: absolute
- position: fixed
- position: sticky

## position: static

속성을 지정하지 않으면 기본값으로 static이 적용된다.
문서의 일반적인 흐름에 따라서 배치되는 속성이며, `top`, `right`, `bottom`, `left`, `z-index` 속성의 영향을 받지 않는다.

```html
<div>
  <div>static1</div>
  <div>static2</div>
  <div>static3</div>
</div>
```

예를 들어서 다음과 같이 세가지 요소가 있다면, 화면 상에 나란히 배치된다.

## position: relative

문서의 일반적인 흐름에 따라서 배치되는 것은 `static`과 동일하지만, `top`, `right`, `bottom`, `left`에 따라서 위치 조정이 가능하다.

이때, 조정되는 위치는 아무것도 적용하지 않았을 때의 원래 자리이며 조정된 요소는 다른 요소에 영향을 주지 않으며 `static` 상태일 때의 레이아웃을 유지한다.

```html
<div>
  <div>static1</div>
  <div>relative2</div>
  <div>static3</div>
</div>
```

예를 들어서 `relative2`의 offset을 `top`, `right`, `bottom`, `left`를 이용하여 임의로 조정했을 경우에 `static1`과 `static3`는 `relative2`의 위치와 관계없이 원래의 자리를 유지한다.

## position: absolute

문서의 일반적인 흐름과 관계없이 배치되며 페이지 레이아웃의 공간을 차지하지 않는 속성이다. 때문에 다른 요소와는 상호작용하지 않는 특성을 가지고 있다. relative와 같이  `top`, `right`, `bottom`, `left`에 따라서 위치 조정이 가능하다.

`absolute`라는 속성의 이름과는 다르게 상대적으로 배치되는 특성을 가지고 있는데, position된 부모 요소를 기준으로 배치된다. position된 부모 요소는 쉽게 이야기하면 `static이 아닌 요소`를 말한다. 만약에 static이 아닌 부모 요소가 존재하지 않는다면 DOM 트리의 최상위에 있는 body가 기준이된다.

```html
<div>
  <div>static1</div>
  <div>absolute2</div>
  <div>static3</div>
</div>
```

예를 들어서 absolute2가 static 요소 사이에 배치되더라도 양쪽의 두 static은 absolute2가 존재하지 않는 것 처럼 나란히 배치되게 된다.

## position: fixed

fixed는 스크롤 위치와 관계 없이 항상 같은 위치를 유지하는 속성이다. 이러한 특성 때문에 navigation이나 채팅, floating button 같은 UI를 구현하는 데에 많이 사용된다.

fixed의 배치 기준은 다른 부모 요소가 아니라 viewport를 기준으로 하며 absolute와 같이 레이아웃에서 공간을 차지하지 않는다.

## position: sticky

sticky는 말 그대로 끈끈하게 붙어있는 듯한 속성이다. 

문서의 흐름에 따라 배치되며, `top`, `right`, `bottom`, `left`의 영향을 받지 않는다. 그러나 스크롤을 내리면 화면의 상단에 붙어서 화면에서 사라지지 않는다.

## 🌐reference

https://developer.mozilla.org/en-US/docs/Web/CSS/position
https://www.daleseo.com/css-position/