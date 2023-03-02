# require과 import

둘 모두 모듈을 불러오는 키워드이다. 어떤 차이점이 있을까?

## require란?

`require` - `exports`는 NodeJS에서 사용하고 있는 CommonJS의 키워드이다. Ruby 언어 스타일과 비슷하다.

```js
/* CommonJS  */
const name = require('./module.js');
```

## import란?

`import` - `export`는 ES6(ES2015)에서 새롭게 도입된 키워드이다. Java와 Python의 방식과 비슷하다.

```js
/* ES6 */
import name from './module.js'
```

## 차이점

- require()는 CommonJS를 사용하는 node.js문이지만 import()는 ES6에서만 사용
- require()는 프로그램의 어느 지점에서나 호출 할 수 있지만 import()는 파일의 시작 부분에서만 실행할 수 있다. (그렇지만 import 전용 비동기 문법으로 파일 중간에 모듈 불러오기를 할 수 있다
- 하나의 프로그램에서 두 키워드를 동시에 사용할 수 없다
- 일반적으로 import()는 사용자가 필요한 모듈 부분 만 선택하고 로드 할 수 있기 때문에 더 선호된다. 또한 require()보다 성능이 우수하며 메모리를 절약한다.

## 🌐reference

https://inpa.tistory.com/entry/NODE-%F0%9F%93%9A-require-%E2%9A%94%EF%B8%8F-import-CommonJs%EC%99%80-ES6-%EC%B0%A8%EC%9D%B4-1
