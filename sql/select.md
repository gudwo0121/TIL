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

					WHERE birthYear >= 1970 AND height >= 182;       -- 1970년 이후 출생이며 키는 182 이상인 열
					WHERE birthYear >= 1970 OR height >= 182;        -- 1970년 이후 출생이거나 키는 182 이상인 열
					
					WHERE height BETWEEN 180 AND 183;                -- 키가 180~183 사이인 열
					
					WHERE addr IN('경남','전남','경북');              -- 주소가 (경남 or 전남 or 경북)인 열
					
					WHERE userName LIKE '김%';                       -- 이름이 '김'으로 시작하는 모든 열
					                                                 -- [%] = 글자수 상관없이 무엇이든
					                                                 -- [_] = 한 글자 무엇이든
					                                                 -- [%]와 [_]를 맨 앞에 사용시 비효율적
					                                                 
----------------------------------------------------------------------------------------------------------------------------------------                                                                         
					-- 서브쿼리 = 좀 더 세밀한 추출을 위해 사용
					-- '김경호'의 키보다 큰 열
					WHERE height > (SELECT height FROM userTBL WHERE userName = '김경호');
					
					-- 오류 : 서브쿼리에서 2개 이상의 값이 발생
					WHERE height >= (SELECT height FROM userTBL WHERE addr = '경남');
					
					-- [ANY]는 2개 이상의 값의 합집합을 추출
					-- ex) '170'과 '173'이 발생 = '170'이상 채택
					WHERE height >= ANY (SELECT height FROM userTBL WHERE addr = '경남');
					
					-- [ANY]는 2개 이상의 값의 교집합을 추출
					-- ex) '170'과 '173'이 발생 = '173'이상 채택
					WHERE height >= ALL (SELECT height FROM userTBL WHERE addr = '경남');
					
					-- [ORDER BY]는 순서를 조절
					-- [ASC]는 오름차순(default 생략가능) / [DESC]는 내림차순
					ORDER BY height ASC;                             -- 키가 작은 순 정렬
					ORDER BY height DESC;                            -- 키가 큰 순 정렬
		
-----------------------------------------------------------------------------------------------------------------------------------------
        
-- [DISTINCT]는 중복 값을 하나만 출력
SELECT DISTINCT addr FROM userTBL;

-- [GROUP BY]은 추출된 내용을 그룹화
-- [HAVING]은 그룹화된 내용에 조건을 제시
-- [AS]는 별칭 지정
-- [SUM]은 [GROUP BY]와 같이 쓰임
SELECT userid AS "구매자", SUM(price*amount) AS "총 소비액" FROM buyTBL GROUP BY userid HAVING SUM(price*amount) > 1000;

-----------------------------------------------------------------------------------------------------------------------------------------

-- 3중 쿼리문에서 rownum 초기화
SELECT b.stdno
FROM
    ( SELECT ROWNUM r, a.*
        FROM
            ( SELECT stdno, ( kor + eng ) score
                FROM
                    studentTBL
                WHERE
                    localcode = 'B'
            ) a                                            -- a 서브쿼리 
    ) b                                                    -- b 서브쿼리
WHERE
    b.r = 5;                                               -- a 서브쿼리에서 바로 rownum을 사용하여 5번째를 추출하면
                                                           -- 실행이 불가하며 b 서브쿼리로 감싼 후 추출해야한다.
                                                           
-----------------------------------------------------------------------------------------------------------------------------------------

-- [WHERE]절에는 별칭을 사용불가
SELECT
    ( CASE acccode
            WHEN 'A'   THEN tot + 5
            WHEN 'B'   THEN tot + 15
            WHEN 'C'   THEN tot + 20
        END
    ) tscore, ( eng + kor ) ek                             -- [ek]라는 별칭을 정의한다 가정한다.
FROM
    studentTBL
WHERE
    ( eng + kor ) >= 120                                   -- [ek >= 120] 불가능, [WHERE]절에는 별칭을 쓸 수 없다.
ORDER BY tscore;

-----------------------------------------------------------------------------------------------------------------------------------------
```

***

