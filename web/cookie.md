# cookie

## set-cookie

`set-cookie`는 http response header에 cookie를 보낼때 사용한다.

이때 cookie에 대한 다양한 옵션들이 있다.

```json
Set-Cookie: <cookie-name>=<cookie-value>
Set-Cookie: <cookie-name>=<cookie-value>; Domain=<domain-value>
Set-Cookie: <cookie-name>=<cookie-value>; Expires=<date>
Set-Cookie: <cookie-name>=<cookie-value>; HttpOnly
Set-Cookie: <cookie-name>=<cookie-value>; Max-Age=<number>
Set-Cookie: <cookie-name>=<cookie-value>; Partitioned
Set-Cookie: <cookie-name>=<cookie-value>; Path=<path-value>
Set-Cookie: <cookie-name>=<cookie-value>; Secure

Set-Cookie: <cookie-name>=<cookie-value>; SameSite=Strict
Set-Cookie: <cookie-name>=<cookie-value>; SameSite=Lax
Set-Cookie: <cookie-name>=<cookie-value>; SameSite=None; Secure

// Multiple attributes are also possible, for example:
Set-Cookie: <cookie-name>=<cookie-value>; Domain=<domain-value>; Secure; HttpOnly
```

## MaxAge, Expires 옵션

MaxAge : 앞으로 몇초동안 쿠키가 유효할지 설정하는 옵션이다.

Expires : MaxAge와 비슷하지만 클라이언트 기준의 유효한 Date를 설정한다.

+ 설정하지 않으면?
  
  위 옵션을 설정하지 않으면 cookie는 session cookie가 된다. session과 같이 브라우저 탭이 닫힐 때까지 유지된다.

## Secure

쿠키를 전송해야 할 때 사용하는 프로토콜에 따른 쿠키 전송 여부를 결정한다. 만약 해당 옵션이 true로 설정된 경우, 'HTTPS' 프로토콜을 이용하여 통신하는 경우에만 쿠키를 전송할 수 있다.

## HttpOnly

자바스크립트에서 브라우저의 쿠키에 접근 여부를 결정한다. 만약 해당 옵션이 true로 설정된 경우, 자바스크립트에서는 쿠키에 접근이 불가하다.

명시되지 않는 경우 기본으로 false로 지정되어 있다.
만약 이 옵션이 false인 경우 자바스크립트에서 쿠키에 접근이 가능하므로 'XSS'공격에 취약하다.

## Samesite

Cross-Origin 요청을 받은 경우 요청에서 사용한 메소드와 해당 옵션의 조합으로 서버의 쿠키 전송 여부를 결정하게 된다.
사용 가능한 옵션은 다음과 같다.

- Lax : Cross-Origin 요청이면 'GET'메소드에 대해서만 쿠키를 전송할 수 있다.

- Strict : Cross-Origin이 아닌 same-site 인 경우에만 쿠키를 전송할 수 있다.

- None : 항상 쿠키를 보내줄 수 있다. 다만 쿠키 옵션 중 Secure 옵션이 필요하다. 이때 'same-site'는 요청을 보낸 Origin과 서버의 도메인이 같은 경우를 말한다.

```
CrossOrigin이 아닌 경우
samesite: Strict

CrossOrigin인 경우
samesite: none / secure: true
  only Method: Get samesite: Lax
```

## 🌐reference

https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie