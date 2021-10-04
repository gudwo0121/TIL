# INSERT

***

* ## 레코드 삽입

> `INSERT INTO [테이블명]( [열1], [열2], ... ) VALUES ( [값1], [값2], ... );`

```sql
-- userTBL의 속성에 해당하는 레코드 삽입
INSERT INTO userTBL VALUES ('id', 'name', '010-123-4567');			-- 전부 삽입시 생략
INSERT INTO userTBL(userID, userName) VALUES ('id', 'name');		-- 일부 삽입시 해당 속성 명시
```

***

