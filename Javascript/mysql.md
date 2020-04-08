# MySQL 설치하기

node.js 로 API 개발 하다가 DB 연결 뭐로할지 찾아봄

```
npm install mysql
```
또는
```
npm install mysqljs/mysql
```

# MySQL 쿼리에 파라미터 넣기

```sql
const clubSn = req.params.clubSn;
const clubNm = req.params.clubNm;
const sql = 'SELECT * FROM CLUB WHERE CLUB_SN = ? AND CLUB_NM = ?';
dbconn.query(sql, [clubSn, clubNm], function(err, results, field){
	...
});
```




### resource
- https://www.npmjs.com/package/mysql#install
- https://junspapa-itdev.tistory.com/10