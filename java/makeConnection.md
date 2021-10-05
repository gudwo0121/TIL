# makeConnection

***

* ## main

```java
// 메인
public static void main(String[] args) {
		DatabaseTest dt = new DatabaseTest();
		Connection con = null;

		// 연결 + 연결확인
		try {
         	// DB 연결
            	con = dt.makeConnection();
            	// 연결여부 확인
            	if (con != null) {
                    System.out.println("연결완료");
                } else {
                    System.out.println("연결불가");
                }
            } catch (ClassNotFoundException | SQLException e) {
                e.printStackTrace();
            } finally {
                try {
                    // 연결 종료
                    con.close();
                } catch (SQLException e) {
                    e.printStackTrace();
                }
            }
}
```

***

* ## makeConnection

```java
// DB와 연결을 시켜주는 연결 작업 메소드
public Connection makeConnection() throws ClassNotFoundException, SQLException {
	Connection con = null;

	// DB 연결에 필요한 4가지 정보
	String driver = "oracle.jdbc.OracleDriver";
	String url = "jdbc:oracle:thin:@localhost:1521:xe";
	String id = "HR";
	String pwd = "1234";

	// 드라이버 로딩
	Class.forName(driver);
    
        // DB 연결 -> HR 접속
        con = DriverManager.getConnection(url, id, pwd);

        // 연결완료 : [con != null]
        // 연결불가 : [con == null]
        return con;
}
```

***

