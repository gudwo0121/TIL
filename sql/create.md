# CREATE

***

* ## 테이블 생성

> `CREATE TABLE [테이블명] ();`

```sql
-- userTBL 테이블 생성
CREATE TABLE userTBL (
    -- 테이블의 속성들
    userID            CHAR(4) PRIMARY KEY,
    userName          NVARCHAR2(5) NOT NULL,
    mobile            CHAR(15) NULL
);
```
***

