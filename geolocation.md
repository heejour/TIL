# Http 사용시 Geolocation API

COVID-19 로 인한 마스크 대란이 일며 정부에서 마스크 5부제를 실시했고,  <br>
마스크 재고 조회가 가능하도록 3월 10일 19시 부터 Open API 를 제공하기 시작했다.

- 따로 React로 개발해둔 마스크맵을 기존 정적 라이브 코로나맵에 iframe으로 붙이려다보니 위치정보 제공 동의가 되지 않았음 <br>

    1. iframe 내에 allow="geolocation" 을 추가
    2. http 인 경우 보안상의 이유로 더이상 위치 정보 동의 제공이 되지 않아서 https 로 사용
```html
<iframe src="https://mask.livecorona.co.kr" frameborder="0" style="border:0;width:100%;height:35rem;padding-top:0;"allow="geolocation"></iframe>
```

### resource

- https://sites.google.com/a/chromium.org/dev/Home/chromium-security/deprecating-powerful-features-on-insecure-origins
- https://medium.com/witinweb/http-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C-%EC%82%AC%EC%9A%A9%EC%8B%9C-html5-geolocation-api-%EB%93%B1-%EC%9C%84%EC%B9%98%EC%A0%95%EB%B3%B4-%EC%82%AC%EC%9A%A9%EC%A0%9C%ED%95%9C%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC-e024772cc280