# Twitter Tech Talk 에서 나온 내용 정리

[Review]

3/22(금) 오늘 아침 스위치온에서 있었던 Twitter Tech Talk 에서 나온 내용 정리

### Talk<br>
7~8 년 정도 일함<br>
플랫폼 상의 건강한 정보를 위해 노력중

ML에 집중, <br>
Home TimeLine 을 만들어 소통을 늘리고 자기가 하고싶은 말을 공유 -> 소통의 느낌. <br>
자기의 이야기, 자기의 관심사에 집중<br>
소통을 유연하게 하는것

플랫폼의 현대화(modernization)<br>
기술이 빨리 변하기 때문에<br>
마지막 결과물이 잘 나올 수 있도록.<br>
조직적인 부분에서 어떻게 투자하는지도 중요함. lab 들이 여러개 있다. <br>
플랫폼 Data Center 에 투자하고있음<br>
오픈소스 커뮤니티, 외부적인 contribution 을 받음<br>
GCP, AWS, Big Query 를 활용해 빠르게 적용할 수 있도록 함. 5년전만해도 사용하지 않았던 부분이다.


### Q and A - Kakao krew to Twitter

#### 1. 가장 최근에 겪은 개발적 이슈? 그리고 어떻게 가고있는지?<br>
Privacy, Data protection, Secure<br>
개인정보 보호, 사생활 보호 가 확실해야 함<br>
고객의 신뢰를 얻어야 함

#### 2. Ruby 아직 사용 중 ?<br>
Ruby on Rails 사용했었음. 7년 전. 새로운 피쳐 넣고 하는데에 어려움을 겪음<br>
2년간 99% 를 루비에서 스칼라 microservice 로 바꿈

#### 3. 트위터의 플랫폼 리뉴얼 주기<br>
하드웨어, 네트워크 2~4년 주기 정도<br>
compute 플랫폼 4년정도 주기가 있음<br>
이제 kubernetes 로 넘어가려 한다<br>
서버를 계속 microservice 로 분해 하는 작업을 계속 진행중<br>
Graph QL

#### 4. 개발관련 사내 행사나 지원이 있는지 궁금함<br>
Hackathon 한다. Hack Weeks. 1년에 1주일동안.<br>
Bookmark 라는게 가장 인기가 좋았음<br>
상품개발만 하는게 아닌 자기계발도 진행<br>
가장 많은 코드를 지웠던(delete) 팀에게 그 상이 돌아갔었음<br>
2~3 명이 팀<br>
Demo, Presentation, Celebration 으로 진행<br>
Event Conference. 자기 일을 떠나 ML 기술 & 전략 생각해 볼 수 있는 시간도 가짐<br>
Twitter University. 사내에서 새로운 기술을 가르침. 새로운 개발자들을 계속 고용할 순 없기 때문에

#### 5. 퀄리티 필터라던가, 새로운 서비스를 넣을 때 사용자 반응 어떻게 보나?<br>
유저 리서치, 소수의 유저와 이야기 후 다수에게 반영<br>
데이터 사이언스, featuring 부분. A/B test<br>
global 서비스라, different culture, different language 를 반영하는게 어려웠다<br>
leverage 부분을 조정. 원래 280자 까지 가능한데 특정 국가 언어는 길이를 늘린다던가 함<br>
1000자 까지 늘렸던 적이 있는데,  영어나 독어 등 140 자 쓰던데에 비해서 많이 늘어났다. 한중일 어는 크게 늘어나진 않았음.<br>
10000자로 늘리진 않겠지만 사람들이 창의적으로 표현할 수 있게 하고싶다.<br>

#### 6. 3~4년 만에 리빌딩 한다고 했는데, 소스. 리비팅할 수 있는 테스트 전략. 개발문화? (번외로, finatra framework 가 도움이 많이 되었다. 고맙다.)
As-Is 를 작게 쪼개서 하나씩 새로 만들고 없앤다.
API Test, Query Test 를 많이 함

#### 7. 개발과 테스트가 같이 진행되는지?<br>
전 세계에 엔지니어, 리서처가 있어 지역별로 많이 테스트 해봄<br>
ProtoType, Test, Mock 으로 테스트<br>
몇 년 전, 빠르게 성장하던 시기엔 Test 잘 하지 못했다. 국가적 dimension으로 나눠서 머신러닝을 통해 국가별로 알고리즘이 잘 진행되고 있는지 확인한다.

#### 8. 스크럼, 애자일이 진행되고 있는지. 개발 방법론. 각각 너무 많은 브랜치가 있다고 하는데, 협업의 형태? legacy code는 어떻게 하는지?<br>
6, 7번에


### Q and A - Twitter to Kakao krew

#### 1. Kakao 에서 엔지니어로 개발할 때 가장 어려운 도전과제는? Challenging 한 것은 ?<br>
k : 비즈니스 인텔리전스 -> 핵심 성장 지표를 보는게 어렵다.<br>
t : DAU, New Users, .. Hypothesis. 만약 이렇게 하면 이렇게 될 거다.<br>
   Feature 들을 test, 결과 100~90% shipping 할 수 있는지 봄<br>
k : 커머스 서버 -> legacy code를 다루는 과정<br>
t : legacy code가 힘든건 마찬가지다. modernizing 하는거에 집중하는 것<br>
   on call, inbound, update, fixing bug 도 resource 가 컸음. 그래서 현대화 함

#### 2. 가장 자랑스러운 성과를 냈다고 생각하는건? <br>
k : 여러가지 복합 기술을 같이 함으로써 성과를 높이는 것<br>
t : branching-out, 다른 기술을 쓰기위해 팀을 바꾸기 좋다.<br>
k : 유저 데이터. 개인정보 보호 잘 하고 있다.<br>
t : Authorization. 기술 플랫폼을 만들어서 관리, 요청이 들어오면 필요할 때만.<br>
   데이터 접근 권한 범위를 좁혀서.<br>
   다양한 공간에 나눠서 보관<br>
   데이터 저장 할 때에도 저장해야하는 확실한 이유가 있어야함


#### + 개인적으로 질문한 내용
인프라는 트위터 예전부터 쓰던 AWS로 많이 쓰고 분석 쪽은 Google Big Query 나 facebook open source 인 presto 를 쓴다고 합니다. GCP 도 네트워크가 빨라서 많이 쓴다고 합니다. 
cf) presto : https://github.com/prestodb/presto


#### 요약
레거시 코드는 쪼개서 현대의 기술로 마이크로서비스로 바꿔나가고, 머신러닝을 이용한 가설검증을 지속함
플랫폼은 개인 정보와, 사생활 보호에 신경을 정말 많이 써야함아래의 글이 있었다. <br> 
이 글에 나온 내용에 한정해서 정리!
