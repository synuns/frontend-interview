# state와 props

## 사용법

**State**

```js
function Welcome() {
  const [name, setName] = useState('Sara');
  return <h1>Hello, {name}</h1>;
}
```

컴포넌트 내부에서 관리하는 동적 데이터이다.

**Props**

```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
```

부모 컴포넌트에서 자식 컴포넌트로 값을 property로 전달하는 방식으로 사용한다.

## 특성

- state와 props 모두 일반 js 객체이다.
- state와 props의 변경은 렌더 업데이트를 발생시킨다.
- props는 읽기 전용으로 컴포넌트 내부에서 변경 불가능하다.

## 🌐reference

https://ko.reactjs.org/docs/faq-state.html

https://reactjs.org/docs/components-and-props.html

https://github.com/uberVU/react-guide/blob/master/props-vs-state.md