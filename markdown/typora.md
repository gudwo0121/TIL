# Typora

***

## Heading

* 문서의 제목이나 소제목을 크기별로 표현

> `#`

```typora
# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6
```

***

## List

* 글머리 기호 생성

> `1. ~ n.` = **순서 있음**

```typora
1. 내용1
2. 내용2
3. 내용3
```

> `*` = **순서 없음**

```typora
* 내용1
* 내용2
* 내용3
```

***

## Fenced Code Block

* 특정 언어를 사용하는 것처럼 명시

> ` ```[언어 이름]``` `

```C
printf("Hello World");		// ```C```
```

```Java
System.out.println("Hello World");		// ```Java```
```

```python
print("Hello World")		# ```Python```
```

***

## Inline Code Block

* 실제 코드나 강조할 대상을 표현

> `'[내용]'`

```typora
나는 `홍길동`이다.
Java에서 주석처리 하는 방법은 `// 주석입니다.`이다.
```

💥 주의 : `''` (작은따옴표)가 아니라 ` `` `(backtick)입니다.

***

## Link

* 하이퍼링크 생성

> `[링크제목](URL)`

```typora
[네이버](https://naver.com)
[구글](https://google.com)
```

***

## Image

* 이미지 생성

> `![링크제목](이미지파일경로)`

```typora
![Image](C:/Wallpaper/image.jpg)
```

💥 주의 : 작성하는 파일이 속해있는 경로에 따로 `md-images`라는 폴더를 만들고, 그 안에 이미지가 저장되게 해야합니다.

***

## Blockquotes

* 인용문 생성 (좌측에 세로로 막대표시)

> `>`

```typora
1번은 이러하다 :
> 인용문1
2번은 이러하다 :
> 인용문2
```

***

## Table

* 표를 작성

> `ctrl + t`

```typora
[ctrl + t] 누르기
열과 행 설정
```

|   1행 1열   |   1행 2열   |   1행 3열   |
| :---------: | :---------: | :---------: |
| **2행 1열** | **2행 2열** | **2행 3열** |
| **3행 1열** | **3행 2열** | **3행 3열** |

***

## Text

* 텍스트 강조 (굵게 / 기울임)

> `**[내용]**` = 굵게

```typora
강조할 부분은 바로 **이것**입니다.
```

> `*[내용]*` = 기울임

```typora
강조할 부분은 바로 *이것*입니다.
```

> `***[내용]***` = 굵게 + 기울임

```typora
강조할 부분은 바로 ***이것***입니다.
```

***

## Horizon

* 항목간에 수평선을 그어 구분

> 3개 이상의 `***` / `---` / `___`

```typora
*** or **** or ***** ...
--- or ---- or ----- ...
___ or ____ or _____ ...
```

***

💥 커밋하면서 알게된 점 : 줄바꿈을 많이 해서 저장해도 다 붙여버린다.

❤[Typora 홈페이지](https://typora.io/)❤ 
