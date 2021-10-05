# Data type

***

* ## 숫자 데이터 형식

> `NUMBER(p, [s])`

```sql
-- [ 1234567.89 ]라는 숫자를 삽입한다고 가정한다

NUMBER                          -- [ 1234567.89 ] = 그대로 표현

NUMBER(9)                       -- [ 1234568 ] = 소수점 아래서 반올림

NUMBER(9, 2)                    -- [ 1234567.89 ] = 소수점 아래 2자리까지 표현

NUMBER(9, 1)                    -- [ 1234567.9 ] = 소수점 아래 2자리에서 반올림

NUMBER(*, 1)                    -- [ 1234567.9 ] = [*]은 최대를 뜻하며, 소수점 1자리까지 표현

NUMBER(6)                       -- 오류 = 7보다 작음
```

***

* ## 문자 데이터 형식

> `CHAR(n)` / `NCHAR(n)` / `VARCHAR2(n)` / `NVARCHAR(n)` 

```sql
CHAR(8) : 문자열 3자리 입력해도 8자리 잡음

NCHAR(8) : 전 세계 모든 문자(한글 포함)를 표현하기위해 써야함 = [N]이 안붙으면 영어만 받겠다는 뜻

VARCHAR(8) : 3자리 입력하면 3자리로 줄음 (늘어나는건 불가)

NVARCHAR2(8) : [N]과 [VAR]를 합친 개념
```

***

* ## 날짜 데이터 형식

> `DATE` / `SYSDATE`

```sql
DATE : 현재 [연, 월, 일, 시, 분, 초] 정보
SYSDATE : 현재 날짜를 출력

-- SYSDATE 예시
INSERT INTO mDate VALUES (SYSDATE);             -- 결과 : [ 21/10/04 ] 삽입
```

***

* ## NULL 값 처리

> `NULL` / `NOT NULL`

```sql
ex1 CHAR(5) NULL                          -- NULL값이 있어도 된다
ex2 CHAR(5) NOT NULL                      -- NULL값이 있으면 안된다
```

***

