# UPDATE

***

* ## 레코드 수정

> `UPDATE [테이블명] SET [바꿀 값] WHERE [조건];`

```sql
-- [userTBL]에서 [userName]이 "KIM"인 레코드의 [mobile]값을 "011"로 변경
UPDATE userTBL SET mobile = "011" WHERE userName = "KIM";
-- [WHERE]절이 없다면 [모든 레코드]를 의미
-- [buyTBL]에서 모든 레코드의 [price]값을 1.5배로 변경
UPDATE buyTBL SET price = price * 1.5;
```

***

