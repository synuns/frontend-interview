# diplay 속성 : inline, block, inline-block

## inline

- 전후 줄바꿈 없이 다른 엘리먼트들과 나란히 배치되는 속성이다.

- `inline` 엘리먼트에는 `<span>`, `<a>`, `<em>` 태그가 있다.

- `width`, `height` 속성은 무시되며 `margin`과 `padding`은 좌우에만 반영되며 상하에는 반영되지 않는다.

## block

- 전후 줄바꿈이 일어나 다른 엘리먼트들을 다른 줄로 밀어내고 혼자 한 줄을 차지하는 속성이다.

- block 엘리먼트에는 `<div>`, `<p>`, `<h1>` 태그가 있다.

- inline과는 달리 `width`, `height`, `margin`, `padding` 속성이 모두 반영된다.

## inline-block

- inline과 block 속성의 특성을 모두 가지고 있는 속성이다.

- `inline-block` 엘리먼트에는 `<button>`, `<input>`, `<select>`가 있다.

- inline처럼 줄바꿈 없이 다른 엘리먼트들과 나란히 배치되지만, block처럼 `width`, `height`, `margin`, `padding` 속성이 모두 반영된다.

- 내부적으로는 block 엘리먼트의 규칙을 따르면서 외부적으로는 inline 엘리먼트의 규칙을 따른다.

## 🌐reference

https://www.daleseo.com/css-display-inline-block/
