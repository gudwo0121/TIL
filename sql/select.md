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
					                                                 
					WHERE 
					
```

***

