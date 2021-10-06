# CREATE

***

* ## 테이블 생성

> `CREATE TABLE [테이블명] ();`

```sql
-- userTBL 테이블 생성
CREATE TABLE userTBL (
    -- 테이블의 속성들
    userID            CHAR(4) PRIMARY KEY,		-- PRIMARY KEY(PK)는 NOT NULL + UNIQUE의 특징을 가짐
    userName          NVARCHAR2(5) NOT NULL,
    mobile            CHAR(15) NULL
);

-- 새로운 테이블 생성과 동시에 다른 테이블의 속성들의 값 복사
CREATE TABLE userTBL2 AS (SELECT * FROM userTBL);     -- userTBL의 값들을 그대로 userTBL2에 넣기
```
***

