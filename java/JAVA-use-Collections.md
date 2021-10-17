# JAVA-use-Collections

***

> ### 자바에서 컬렉션을 활용하는 과정을 알아보자. 

* ## List

* ## Set

* ## Map

***

> ## List (ArrayList)

* 가변적인 배열을 써야하는 상황일 때 사용
* 중복 허용 + 순서 유지

```java
// List 선언, <> 안에는 데이터 타입을 명시
ArrayList<String> list = new ArrayList<String>();


// List [0]번쨰 인덱스에 "Kim" 추가
// 인덱스 값을 작성하지 않으면 자동으로 다음 인덱스에 추가
list.add(0, "Kim");
list.add("Lee")            // [1]번째 인덱스에 "Lee" 추가
    
    
// List [0]번째 인덱스의 값 조회
list.get(0);


// List [0]번째 인덱스의 값 수정
list.set(0, "Park")


// List 개수 확인
list.size();


// List [0]번째 인덱스의 값 제거
// 제거된 값(="Park") 리턴
list.remove(0);
// List "Lee"값 제거
// 제거 여부를 boolean(T/F) 값으로 리턴
list.remove("Lee");


// List 값 중에 "Kim" 포함 여부 확인
// boolean(T/F) 값으로 결과 리턴
list.contains("Kim");

// List 모든 값 삭제 = 초기화
list.clear();
```

***

> ## Set (HashSet)

* 배열의 중복 값을 체크해야하는 상황일 때 사용
* 중복 불가 + 순서 없음

```java
// Set 선언, <> 안에는 데이터 타입을 명시
HashSet<String> set = new HashSet<String>();


// Set에 "Kim" 추가
// 중복 값이 존재하면 False, 아니면 True 리턴
set.add("Kim");


// Set 조회
for (String str : set) {                            // 향상된 for문 활용
    System.out.print(str + " ");                    // str 출력 (넣은 순서대로 나오지 않는다)
}
```

***

> ## Map (HashMap)

* [ 중복 없는 고유한 값 (`Key`) ]을 기준으로 [ 다른 값 (`Value`) ]을 저장해야하는 상황일 때 사용
* `Key` (중복 불가) + `Value` (중복 허용)

```java
public void test1() {
		HashMap<String, Integer> map = new HashMap<String, Integer>();

		// 삽입
		map.put("one", new Integer(1));          // 자동 형변환
		map.put("two", 20);
		map.put("three", 3);

		// 사이즈
		int size = map.size();
		System.out.println(size);                // "3" 출력

		// 오토박싱
		Integer val = map.get("two");
		System.out.println(val);                 // "20" 출력

		// 수정 = 새로운 [Value]로 덮어씌워짐
		map.put("two", 2);                       // "20" -> "2"
		val = map.get("two");
		System.out.println(val);                 // "2" 출력

		// 제거 = 제거된 [Key]에 대응하는 [Value]를 리턴
		val = map.remove("three");
		System.out.println(val);                 // "3" 출력
		System.out.println(map.size());          // "2" 출력

		// 모든 [Key] 확인 = "Set<String> keys"으로 저장
		Set<String> keys = map.keySet();
		// "keys"에 저장된 [Key]를 한 줄로 나열
		Iterator<String> iter = keys.iterator();

		// 다음 [Key]가 있는지 검사 = boolean(T/F) 리턴
		while (iter.hasNext()) {
			// 다음 [Key]로 커서 이동
			String key = iter.next();
			// [Key]에 대응하는 [Value] 가져오기
			Integer value = map.get(key);
			System.out.println(key + " : " + value);     // "one : 1 \n two : 2" 출력
		}
	}
```

***

