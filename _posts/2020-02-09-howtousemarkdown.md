---
layout: post
title: "마크다운(Markdown) 기본 설명서"
tags: [Blog, Markdown]
comments: true
---

오늘은 Markdown을 제대로 사용해보기 위해 기본적인 사용법을 정리해볼까 합니다잉   
   
우선, 마크다운(Markdown)은 무엇일까요?
> 마크업 언어의 일종으로, 텍스트를 HTML로 변환하는 언어이며 도구입니다. 확장자는 .md를 씁니다.

그렇다면 마크업 언어는 무엇일까요?
> 태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한 가지이다.

특징은 이렇습니다.   
 - 사람이 읽고 쓰기 쉽다.   
 - 컴퓨터도 이해하기 쉽다.
 - Migration이 쉽다.

마크다운에 대해 깊게 이해할 필요는 없으니 여기까지 하고 사용법 들어갑니다!

---

### **제목(Header)**
```
# 제목1 - 가장 큰 사이즈
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6 
```
혹은 큰 제목과 작은 제목으로만 나눌 경우 아래와 같이 사용하면 됩니다.
```
큰 제목      작은 제목
===            ---
```
#이 6개 이상이면 더 이상 글자가 작아지지 않아요~~
`<h1>`부터 `<h6>`까지 대응됩니다.

---
### **강조(Emphasis)**
- Italic(기울임) : `*blah blah*` 혹은 `_blah blah_` = `<em>` `</em>` 태그   
- bold(굵음) : `**blah blah**` 혹은 `__blah blah__` = `<strong>` `</strong>`태그   
- cancel line(취소선) : `~~balh blah~~` = `<del>` `</del>`태그   
- under line(밑줄) : `<u>blah blah</u>`   

예시 한 번 볼게요.  
*Italic*
**Bold**   
~~Cancelline~~   
<u>under line</u>   

---
### **블록 인용구(Block quote)** ##
```
> This is block quote.
> I can use it.
>> This is second block quote.
```
`>` 키워드를 사용하여 인용구를 만들 수 있습니다.   
여러 층을 사용하기 위해선 `>>`, `>>>` 과 같이 겹을 늘리면 됩니다.   

예시 한 번 볼게요.
> This is block quote.   
> I can use it.
>> This is second block quote.

---
### **코드 블록(Code block)** ###
- ` ``` ` 혹은 `\~\~~`으로 감싼 텍스트
  
저는 보통 ` ``` `만 사용할려고 합니다. 그리고 ` ``` ` 다음에 언어 스크립트를 작성하시면 그에 맡게 하이라이팅을 지원해줍니다. ` ```c ` 이런식!  
   
예시 한 번 볼게요.

```c
#include <stdio.h>
int main(){
    printf("hello world!\n");
    return 0;
}
```
혹은
```java
public class Test{
    public static void main(String[] args){
        System.out.println("hello world!");
    }
}
```

---

### **목록(List)** ##
1. 순서가 있는 목록 (번호 목록)    
    - 숫자 `하나로!!` 표현하면 됩니다. (저도 이제 알았네요 ㅎㅎㅎ...)   
    ```
    1. blah blah   
    1. blah blah~
    1. blah blah~~
    ```

2. 순서가 없는 목록 (기호 목록)
    - `-`, `+`, `*` 를 사용하여 목록을 만들 수 있습니다.   
  
    ```
    - blah blah
    - blah blah~
    ```

    혹은 계층별로 나누고 싶다면 `tab`을 사용하여 들여쓰기로 구분할 수 있습니다.   

    ```
    - blah blah   
        - blah blah
    ```

... blah 라는 단어가 이렇게 치기 어려운 단어였나..?

---
### **링크(Link)** ###
문서 내 일반 url이나 `<>`안의 url은 자동으로 `<a>``</a>`로 변환됩니다.
```
github url : https://github.com
naver url : <https://naver.com>
[url 대신 표시할 명](https://google.com)
```
예시 한 번 볼게요.   

github url : https://github.com   
naver url : <https://naver.com>   
[my url](https://LazyyyDev.github.io)

---
### **이미지(Images)** ##
링크와 비슷하지만 맨 앞에 `!`를 붙입니다.
```
![이미지가 표시되지 않을 경우 나타나는 이름](Image Path)
```

>그렇다면, 링크와 이미지를 잘 조합한다면 이미지를 통해 링크를 들어가는 것도 가능하겠죠?

```
[![이미지명](Image Path)](URL)
```
위와 같이 설정하면 된답니다!

---
### **테이블(Table)** ###
```
| First Header  | Second Header | Third Header         |
| :------------ | :-----------: | -------------------: |
| First row     | Data          | Very long data entry |
| Second row    | **Cell**      | *Cell*               |
| Third row     | Cell that spans across two columns  ||
```
위와 같이 표현하면 된답니다.

정렬 기능은 헤더 셀 아래의 하이픈(`-`)에서 왼쪽, 오른쪽 혹은 양쪽에 콜론(`:`)을 붙이시면 원하는 곳으로 정렬이 된답니다.

예시 한 번 볼게요.   

| First Header  | Second Header | Third Header         |
| :------------ | :------------: | ------------: |
| First row     | Data          | Very long data entry |
| Second row    | **Cell**      | *Cell*               |
| Third row     | Cell that spans across two columns  ||

---
### **추가?** ###
1. 일반적으로 마크다운에서 한 줄 개행은 공백 3칸입니다.
2. 테이블을 작성할 때 항상 위아래로 개행 한 줄을 비워놓으세요!

---
### **마치며** ###
역시 하나하나 보기보다는 내가 사용해보고 이렇게 글을 올리면서 또 사용하니까 벌써 익숙해진 것 같아요.    
어떤 분야에서든 역시 뭐든 직접 해보고 반복적으로 사용해보는 것이 스스로의 성장에 큰 도움이 되는 것 같네요ㅎㅎㅎㅎ

---
### **앞으로** ###
1. 수학 수식을 마크다운으로 작성하는 것을 제가 나중에 쓸 일이 생긴다면 포스팅해보도록 하겠습니다.
2. 웹 또는 모바일 프로그래밍에 능숙해지기 위해 [edwith](https://www.edwith.org/)와 [inflearn](https://www.inflearn.com/) 에서 온라인 강의, 그리고 집에 있는 서적으로 기본적인 개념과 다양한 토이 프로젝트를 공부할 예정입니다.
3. 저처럼 컴공을 나왔음에도 불구하고 서툴고 모자란 분이 분명 계실 것이라 믿고(없으면 진짜 섭섭...)   
   프로젝트를 진행하는 동안의 불상사(다양한 에러 또는 문제)를 해결하는 것도 올려보겠습니다.