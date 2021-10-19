# Eclipse-Export-Import

***

> ### 이클립스를 이용하여 Export와 Import를 해보자.

1. ####  `Project Explorer`에서 Export할 프로젝트를 우클릭 -> `Export` -> `WAR file`

     ### <img src="md-images/export1.JPG" alt="1" style="zoom:80%;" />




2. ####  새로 뜬 창에서 기존 프로젝트 확인 -> `Browser`

     ### <img src="md-images/export2.JPG" alt="2" style="zoom:80%;" />




3. ####  파일 탐색기에서 `Export`할 경로 설정 -> 이때 오류는 확장자(`war`)가 없기 때문

     ### <img src="md-images/export3.JPG" alt="3" style="zoom:80%;" />




4. ####  확장자를 붙여주고 `Finish` -> 여기서 체크박스는 취향껏 체크

     ### <img src="md-images/export4.JPG" alt="4" style="zoom:80%;" />



***

1. ####  `Project Explorer` 우클릭 -> `Import` -> `WAR file`

     ### <img src="md-images/import1.JPG" alt="5" style="zoom:80%;" />




2. ####  새로 뜬 창에서 `Target runtime` 확인 -> `Browser`

     ### <img src="md-images/import2.JPG" alt="6" style="zoom:80%;" />




3. ####  `Export`했던 파일 확인 -> 열기

     ### <img src="md-images/import3.JPG" alt="7" style="zoom:80%;" />




4. ####  파일 추가 확인 -> 오류가 뜨는 이유는 이전에 `Export`했던 프로젝트와 이름이 같기 때문

     ### <img src="md-images/import4.JPG" alt="8" style="zoom:80%;" />




5. ####  이름 수정 -> `Finish`

      ### <img src="md-images/import5.JPG" alt="9" style="zoom:80%;" />




6. ####  `WAR file`을 `Import`한 프로젝트가 생성 확인

      ### <img src="md-images/import6.JPG" alt="11" style="zoom:80%;" /> 




***



* ### 자바로 `Export / Import`함으로써 모듈들을 더욱 더 효율적으로 관리가 가능하다.