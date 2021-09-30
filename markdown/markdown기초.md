# MarkDown

**********

### 개요

* 2004년 존 그루버가 만든 **텍스트 기반**의 가벼운 마크업 언어
* 최초 마크다운에 비해 확장된 문법(표, 주석 등)이 있지만, 본 수업에서는 **Github** 에서 사용 가능한 문법(*Github Flavored Markdown*)을 기준으로 설명

*********

### 특징

* 워드프로세서(한글/*MS word*)는 다양한 서식과 구조를 지원하며, 문서에 **즉각적으로 반영**
* 마크다운은 가능한 읽을 수 있도록 최소한의 문법으로 구조화 (*make it as readable as possible*)

***

### 문법

###### *Heading*

* 문서의 **제목**이나 **소제목**으로 사용 

  * **#**의 개수에 따라 대응되는 수준(*Heading level*)이 있으며, ***h1 ~ h6***까지 표현 가능

  * 문서의 구조를 위해 작성되며 글자 크기를 조절하기 위해 **사용되어서는 안됨**

|     Markdown      |           HTML           |
| :---------------: | :----------------------: |
| # Heading level 1 | <h1> Heading level 1<h1> |
| # Heading level 2 | <h2> Heading level 1<h2> |
| # Heading level 3 | <h3> Heading level 1<h3> |
| # Heading level 4 | <h4> Heading level 1<h4> |
| # Heading level 5 | <h5> Heading level 1<h5> |
| # Heading level 6 | <h6> Heading level 1<h6> |



###### *List*

* *List*는 순서가 있는 리스트(*ol*)와 순서가 없는 리스트(*ul*)로 구성
* *Tip*) ***Typora***에서 ***tab***으로 하위 항목, ***shift + tab***으로 상위 항목



###### *Fenced Code Block*

* 코드 블록은 *backtick* 기호 3개를 활용하여 작성 (``` )
* 코드 블록에 특정 언어를 명시하면 Syntax Highlighting 적용 가능
  * 일부 환경에서는 적용이 되지 않을 수 있음



###### *Inline Code Block*

* 코드 블록은 backtick 기호 1개를 인라인에 활용하여 작성(``)



###### *Link*

* `[문자열](url)`을 통해 링크를 작성 가능
  * 특정 파일들 포함하여 연결 시킬 수도 있음



###### *Image*

* `![문자열](url)`을 통해 링크를 작성 가능
  * 특정 파일들 포함하여 연결 시킬 수도 있음



###### *Blockquotes* (인용문)

* \> 를 통해 인용문을 작성



###### *Table* (표)

* 표는 아래의 문법을 참고

  * 일부 지원 안되는 환경도 있음

  * Typora Tip) ctrl + t로 생성 가능



###### *Text* 강조

* 굵게(bold), 기울임(Italic)을 통해 특정 글자들을 강조



###### 수평선

* 3개 이상의 asterisks (***), dashes (---), or underscores (___)



*****

### 관련 자료

* GitHub Flavored Markdown (   [https://github.github.com/gfm/](url)   )
* Mastering Markdown (   [https://guides.github.com/features/mastering-markdown/](url)   )
* Markdown Guide (  [https://www.markdownguide.org/](url)   )

****

### MarkDown Tools

* Jekyll
* Gatsby
* Hugo
* Hexo

