# JWT (Json Web Token)

JWT 란?

- 웹표준 (RFC 7519) 으로서 두 개체에서 JSON 객체를 사용하여 가볍고 자가수용적인 (self-contained) 방식으로 정보를 안전성 있게 전달 

- 수많은 프로그래밍 언어에서 지원함
- 자가 수용적 (self-contained)  <br>

Use Case
- 회원 인증
- 정보 교류

구성
- [header].[payload].[signature]
- '.'을 구분자로 3가지 문자열로 구성됨
- 라이브러리 사용시 토큰을 자동으로 인코딩/해싱 작업 해줌

header
- 타입, 해싱알고리즘 두가지의 정보를 가짐
- typ : 토큰의 타입 지정. 타입이 JWT 라는 것
- alg : 해싱 알고리즘 지정. 보통 HMAC SHA256 이나 RSA 가 사용됨. 알고리즘은 토큰을 검증 할 때 사용되는 signature 부분에서 사용됨 

payload
- 토큰에 담을 정보가 들어있음. 정보의 한 조각을 claim 이라고 부르고 name/value 한쌍으로 이뤄져있음. 토큰에는 여러개의 클레임들을 넣을 수 있다.
- 클레임의 종류 세가지 : registered, public, private

signature
- 서명은 헤더의 인코딩값과, 정보의 인코딩값을 합친 후 주어진 비밀키로 해쉬를 해 생성

### resource

- https://velopert.com/2389
- https://bezkoder.com/react-express-authentication-jwt/