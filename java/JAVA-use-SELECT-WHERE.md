# JAVA-use-SELECT-WHERE

***

> ### 자바를 이용하여 DB에 조건이 있는 SELECT문을 실행시켜보자.

* ## main

```java
// 메인
public static void main(String[] args) {
	SearchMain sm = new SearchMain();
	try {
		// 조건 o
		sm.readCondition();
	} catch (ClassNotFoundException | SQLException e) {
		e.printStackTrace();
	}
}
```

***

* ## readCondition

```java
public void readCondition(String uid) throws ClassNotFoundException, SQLException {
	// 조건 조회 userName
	String sql = "SELECT * FROM userTBL WHERE userid = ?";
	// 연결 + 통로 생성
	Connection con = this.makeConnection();
	PreparedStatement ps = con.prepareStatement(sql);
	
	// [?] 채우기
	ps.setString(1, uid);
	// 조작문이 아닌 SELECT문은 [ResultSet]에 [.executeQuery]로 받아야한다
	ResultSet rs = ps.executeQuery();
	
	// [rs] 출력시키기
	while (rs.next()) {
		// 변수에 rs.get~값 데이터타입에 맞게 대입
		// [""] 안에 인덱스 [1,2,3...]번째인지 숫자를 넣어도 가능
		String userid = rs.getString("userid");
		String username = rs.getString("username");		// [ "username" -> 2 ] 가능
		int birthyear = rs.getInt("birthyear");
		String addr = rs.getString("addr");
		String mobile1 = rs.getString("mobile1");
		String mobile2 = rs.getString("mobile2");
		int height = rs.getInt("height");
		String mdate = rs.getString("mdate");
		
		// 한 줄씩 레코드 출력 
		System.out.println(userid + "," + username + "," + birthyear + "," + addr + ","
				+ mobile1 + "," + mobile2+ "," + height + "," + mdate);
	}
	// 순차 종료
	rs.close();
	ps.close();
	con.close();
}
```

***

* ## [mackConnection](https://github.com/gudwo0121/TIL/blob/master/java/JAVA-connect-DB.md)

```java
// 설명 생략 (링크 참조)
public Connection makeConnection() throws ClassNotFoundException, SQLException {
	Connection con = null;
	String driver = "oracle.jdbc.OracleDriver";
	String url = "jdbc:oracle:thin:@localhost:1521:xe";
	String id = "HR";
	String pwd = "1234";
    
	Class.forName(driver);
	con = DriverManager.getConnection(url, id, pwd);
    
	return con;
}
```

***

