# Eclipse-use-SQL

***

> ### 이클립스를 이용하여 SQL Developer환경처럼 쿼리문을 실행시켜보자.

1. ####  이클립스 `상단메뉴` -> `Window` -> `Show View` -> `Data Source Explorer`

     * 만약 `Data Source Explorer`가 없다면, `Other...` -> `Data Source Explorer` 검색 -> `Open`




2. ####  하단에 생긴 `Data Source Explorer`창에 있는 `Database Connections` 우클릭

     ### <img src="md-images/java1.JPG" alt="2"  />




3. ####  새로 뜬 창에서 `Oracle` -> `Next`

     ### <img src="md-images/java2.JPG" alt="3" style="zoom:80%;" />




4. ####  우측 상단의 `아이콘` 클릭

     ### <img src="md-images/java3.JPG" alt="4" style="zoom:80%;" />




5. ####  노란색 라인 클릭 -> `Driver name` 수정 -> `JAR List`로 이동

     ### <img src="md-images/java4.JPG" alt="5" style="zoom:80%;" />




6. ####  기존에 있는 `ojdbc14.jar`은  `Clear All`을 눌러 삭제 -> `Add JAR/Zip...` 클릭 

     ### <img src="md-images/java5.JPG" alt="6" style="zoom:80%;" />




7. ####  파일탐색기로 미리 다운받아 두었던 `ojdbc6.jar`을 찾아서 추가 -> `Properties`로 이동

     ### <img src="md-images/java6.JPG" alt="7" style="zoom:80%;" />




8. ####  `자신의 DB 정보`로 수정 -> `OK`

     ### <img src="md-images/java7.JPG" alt="8" style="zoom:80%;" />




9. ####  최종 확인 -> `Test Connection` 확인 -> `Finish`

     ### <img src="md-images/java8.JPG" alt="9" style="zoom:80%;" />




10. ####  새로 생긴 `New Oracle` 우클릭 -> `Open SQL Scrapbook`

      ### <img src="md-images/java9.JPG" alt="10" style="zoom:80%;" />




11. ####  상단의 `SQL Scrapbook/Connection profile` 선택 -> `쿼리문` 입력

      ### <img src="md-images/java10.JPG" alt="11"  /> 




12. ####  `쿼리문` 드래그 & 우클릭 -> `Execute Selected Text`

      ### <img src="md-images/java11.JPG" alt="12" style="zoom:80%;" />




13. #### `쿼리문` 실행 결과 및 로그 확인

      ### <img src="md-images/java12.JPG" alt="13"  />
    
    

***



* ### 자바로 DB를 조작한 후에 `별도로 SQL Developer를 실행시킬 필요 없이`, `Read할 필요 없이` 결과를 보기 쉽게 확인할 수 있다.