# 브라우저 저장소

## 브라우저 저장소의 종류

- cookie
- localstorage
- sessionstorage

## cookie

쿠키는 클라이언트가 서버에 방문한 정보를 클라이언트 단에 저장하는 작은 파일을 의미한다. 클라이언트의 브라우저 메모리 혹은 하드디스크에 저장 된다.

- 대략 4KB까지의 데이터를 저장할 수 있으며 유효 기간이 존재한다.

- 대부분의 브라우저가 지원한다.

- 클라이언트에 저장되기 때문에 보안에 취약하다는 단점이 있다.
  
  XSS(Cross-Site-Scripting)에 취약하기 때문에 중요한 정보를 쿠키에 저장하지 않도록 해야한다.

- set-cookie 속성을 사용할 수 있다.
  
  response header에 set-cookie 속성을 사용하면 클라이언트에 쿠키를 설정할 수 있다. 해당 쿠키는 사용자가 따로 처리하지 않아도 request header에 쿠키를 함께 보낸다.

  쿠키에 대한 정보를 매 헤더(HTTP Header)에 추가하여 보내기 때문에 상당한 트래픽을 발생시킨다.

## webstorage

기존의 저장소로 사용되었던 Cookie의 몇가지 단점을 개선하여 HTML5의 스펙으로 등장한 저장소이다.

webstorage에는 `Local Storage`와 `Session Storage`가 있다.

### Local Storage

- 브라우저를 종료해도 데이터는 유지된다.
- 데이터를 지우지 않으면 데이터는 영구적으로 보관된다.
- 도메인별로 local storage가 생성된다.
- windows 전역 객체의 localstorage 컬렉션을 통해서 저장과 조회가 가능하다.

### Session Storage

- reload해도 데이터는 유지되지만, 브라우저가 종료되면 데이터가 삭제된다.

- 브라우저 컨텍스트로 관리된다.
  
  같은 사이트의 같은 도메인이라고 할지라도 브라우저가 다르다면 다른 저장소를 생성한다.

- windows 전역 객체의 sessionStorage 컬렉션을 통해서 저장과 조회가 가능하다.