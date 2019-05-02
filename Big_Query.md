# Big Query

Big Query란?

- Google의 페타바이트급 규모의 저비용 완전 관리형 분석 데이터 웨어하우스 <br>
- NoOps - 관리할 인프라가 없고 데이터베이스 관리자가 필요 없으므로, 데이터 분석에 집중하여 의미 있는 정보를 찾을 수 있음<br>
- 친숙한 SQL을 사용하고 종량제 모델을 활용할 수 있음<br> 
- 웹 UI 또는 명령줄 도구를 사용하거나 자바, .NET, Python 등의 다양한 클라이언트 라이브러리로 BigQuery REST API를 호출하여 BigQuery에 액세스할 수 있음<br> 
- 데이터를 시각화하거나 데이터를 로드하는 등 BigQuery와 상호작용하는 데 사용할 수 있는 다양한 타사 도구도 있음

<br>

- 슬롯 <br>
  - SQL 쿼리를 실행하는 데 필요한 연산 능력의 단위 
  - BigQuery는 쿼리 크기와 복잡성에 따라 각 쿼리에 필요한 슬롯 수를 자동으로 계산
  - 더 많은 슬롯에 액세스한다고 해서 더 빠른 쿼리당 성능이 보장되는 것은 아님
  - 그러나 슬롯 풀이 클수록 대용량 또는 매우 복잡한 쿼리의 성능은 물론 동시 작업 부하의 성능은 향상될 수 있음
  

TBU.. 


### resource

- https://cloud.google.com/bigquery/docs/
- facebook - Big Query User Group