# Data type

***

* ## 숫자 데이터 형식

> `NUMBER([정수 자릿수], [소수점 이하 자릿수])`

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

> `CHAR(글자수)` / `NCHAR(글자수)` / `VARCHAR2(글자수)` / `NVARCHAR(글자수)` 

```sql
CHAR(8) : 문자열 3자리 입력해도 8자리 잡음

NCHAR(8) : 전 세계 모든 문자(한글 포함)를 표현하기위해 써야함 = [N]이 안붙으면 영어만 받겠다는 뜻

VARCHAR2(8) : 3자리 입력하면 8자리가 알아서 3자리로 줄음 (늘어나는건 불가)

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

* ## 형변환

> `CAST ([값] AS [변환할 타입])`

```sql
-- 실수인 수량(amount)의 평균을 NUMBER(3) 형식에 맞춰서 정수형으로 변환하여 추출
SELECT CAST(AVG(amount) AS NUMBER(3)) FROM buyTBL;
```

> `TO_CHAR([숫자], ['타입'])`
```sql
-- 앞의 숫자를 뒤의 타입으로 형변환
SELECT TO_CHAR(12345, '$999,999') FROM DUAL;                            -- $12,345
SELECT TO_CHAR(12345, '$000,999') FROM DUAL;                            -- $012,345
SELECT TO_CHAR(12345, 'L999,999') FROM DUAL;                            -- \12,345
SELECT TO_CHAR(SYSDATE, 'YYYY/MM/DD HH:MM:SS') FROM DUAL;               -- 2021/10/07 11:11:11 (현재 시각)
```


> `TO_NUMBER(['문자'])`

```sql
-- 문자로된 숫자를 10진수의 숫자로 형변환
SELECT TO_NUMBER('0123'), TO_NUMBER('1234.456') FROM DUAL;              -- 123  1234.456
```

> `TO_DATE(['문자'], ['날짜형식'])`
```sql
-- 문자로 된 날짜를 날짜형 데이터로 형변환
SELECT TO_DATE('20211007', 'YYYYMMDDHH24MISS') FROM DUAL;               -- 21/10/07
SELECT TO_DATE(SYSDATE) FROM DUAL;                                      -- 21/10/07
```
***

