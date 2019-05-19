# Apache Zeppelin

Apache Zeppelin 이란?

- Spark를 사용하는 데이터 분석 Notebook <br>

zeppelin에선 API 를 제공하기도 한다.
- https://zeppelin.apache.org/docs/0.7.0/rest-api/rest-notebook.html 여기 들어가면 친절하게 설명이 나와있다.
- 예를 들어, zeppelin notebook 에 저장한 paragraph을 비동기적으로 호출하고 싶다면, 아래 형태의 API를 사용하면 된다.  <br>
```
http://[zeppelin-server]:[zeppelin-port]/api/notebook/job/[noteId]/[paragraphId] 
```

### resource

- https://zeppelin.apache.org/
- https://zzsza.github.io/data/2018/06/02/apache-zeppelin/
- https://medium.com/apache-zeppelin-stories/%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EC%9D%BC%EA%B8%B0-2-apache-zeppelin-%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-f3a520297938