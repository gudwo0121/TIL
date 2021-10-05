# DELETE

***

* ## 레코드 삭제

> `DELETE FROM [테이블명] WHERE [조건];`

```sql
-- [userTBL]에서 [userName]이 "KIM"인 레코드를 삭제
DELETE FROM userTBL WHERE userName = 'KIM';
-- 주의 : [WHERE]절이 없다면 모든 레코드를 삭제
DELETE FROM userTBL;
```

***

