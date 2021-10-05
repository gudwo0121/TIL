# ROLLBACK-COMMIT

***

* ## 되돌리기

> `ROLLBACK;`

```sql
-- 실수로 userTBL의 내용을 삭제
DELETE FROM userTBL;
X 행이 삭제되었습니다.

-- 다시 복구
ROLLBACK;
롤백이 완료되었습니다.
```

***

* ## 확정짓기

> `COMMIT;`

```sql
-- 고의로 userTBL의 내용을 삭제
DELETE FROM userTBL;
X 행이 삭제되었습니다.

-- 삭제 확정
COMMIT;
커밋이 완료되었습니다.
```

***

