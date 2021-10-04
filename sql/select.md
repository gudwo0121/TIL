# SELECT

***

* ## 테이블 정보 추출

> `SELECT [열 이름] FROM [테이블명] WHERE [조건];`

```sql
-- userTBL에서 모든 열(*) 추출
SELECT * FROM userTBL;

-- userTBL에서 userID 추출
SELECT userID FROM userTBL;

-- userTBL에서 [ userName = 'user' ]인 모든 열(*) 추출
SELECT * FROM userTBL WHERE userName = 'user';
```

***

