# insertFromFile

***

* ## main

```java
// 메인
public static void main(String[] args) {
		DatabaseTest dt = new DatabaseTest();

		// 작업 + 작업확인
		try {
			dt.toDB();
		} catch (ClassNotFoundException | IOException | SQLException e) {
			e.printStackTrace();
		}
}
```

***

* ## tolist (File-to-List)

```java
// [sample.csv]를 [list]로 읽어들이는 작업 메소드
public ArrayList<DTO> toList() throws IOException {
		ArrayList<DTO> list = new ArrayList<DTO>();
		String line = null;

		File file = new File("./data/sample.csv");
		FileReader fr = new FileReader(file);
		BufferedReader br = new BufferedReader(fr);

		while ((line = br.readLine()) != null) {
			String[] data = line.split(",");
			int sno = Integer.valueOf(data[0].trim());
			String email = data[1].trim();
			int kor = Integer.valueOf(data[2].trim());
			int eng = Integer.valueOf(data[3].trim());
			int mat = Integer.valueOf(data[4].trim());
			int sci = Integer.valueOf(data[5].trim());
			int his = Integer.valueOf(data[6].trim());
			int tot = Integer.valueOf(data[7].trim());
			String teacher = data[8].trim();
			String grade = data[9].trim();
			String local = data[10].trim();

			DTO dto = new DTO(sno, email, kor, eng, mat, sci, his, tot, teacher, grade, local);
			list.add(dto);
		}
		br.close();
		fr.close();
		return list;
}
```

***

* ## toDB (List-to-DB)

```java
// [list]를 [DB]로 삽입하는 작업 메소드
public void toDB() throws IOException, ClassNotFoundException, SQLException {

	// toList 실행한 값을 이곳의 list에 불러오기
	ArrayList<DTO> list = this.toList();

	// 가변인 요소는 [?]로 명시
	String sql = "INSERT INTO studentTBL VALUES(?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)";

	// 연결 (DB 조작시 매번 해줘야함)
	Connection con = this.makeConnection();

	// [?]제외 쿼리문 보내기
	PreparedStatement ps = con.prepareStatement(sql);

	// 리스트의 크기만큼 [?]에 들어갈 데이터 삽입 반복
	for (int i = 0; i < list.size(); i++) {

		DTO temp = list.get(i);

		// [?] 채우기 ( n번째 속성, 넣을 값 )
		// 주의 : 1부터 시작 + 데이터타입 잘 맞춰서 대입
		ps.setInt(1, temp.getSno());
		ps.setString(2, temp.getEmail());
		ps.setInt(3, temp.getKor());
		ps.setInt(4, temp.getEng());
		ps.setInt(5, temp.getMat());
		ps.setInt(6, temp.getSci());
		ps.setInt(7, temp.getHis());
		ps.setInt(8, temp.getTotal());
		ps.setString(9, temp.getTeacher());
		ps.setString(10, temp.getGrade());
		ps.setString(11, temp.getLocal());

		// 작업여부 확인 (각 라인)
		int affectedCount = ps.executeUpdate();
		if (affectedCount > 0) {
			System.out.println("Insert into DB 작업완료");
		}
	}
    	// 작업 및 연결 종료
	ps.close();
	con.close();
}
```

***

* ## DTO

```java
// Data Transfer Object
public class DTO {

	private int sno;
	private String email;
	private int kor;
	private int eng;
	private int mat;
	private int sci;
	private int his;
	private int total;
	private String teacher;
	private String grade;
	private String local;

	public DTO() {}

	public DTO(int sno, String email, int kor, int eng, int mat, int sci, int his, int total, 
               String teacher, String grade, String local) {
		super();
		this.sno = sno;
		this.email = email;
		this.kor = kor;
		this.eng = eng;
		this.mat = mat;
		this.sci = sci;
		this.his = his;
		this.total = total;
		this.teacher = teacher;
		this.grade = grade;
		this.local = local;
	}
    
    	// 이하생략 [getter + setter]
}
```

***



