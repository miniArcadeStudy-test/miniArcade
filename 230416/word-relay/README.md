# miniProjects

## 3. DOM 객체 다루기\_ 끝말잇기 게임

```
시작
1. 몇명이 참가할지 선택한다.
2. 참가자 순서를 정한다.

스타트
3. 첫번째 사람이 제시어를 말한다.
4. if문을 통해서 제시어가 첫번째 시작 제시어인지 판단한다
 - 시작하는 제시어라면 제시어에 할당한다.
5. if문을 통해서 제시어가 있다면 제시어의 마지막 글자와 인풋값의 첫 글자가 같아야 다음 상대에게 순서를 넘긴다.
6. 틀렸을 때는 틀렸음을 표시하고, 맞으면 다음 사람이 단어를 말한다.

```

<br>

### **3.1 순서도 그리기**

**순서도(Flowchart)**

- 처리하고자 하는 문제를 분석하여 국제표준기구(ISO : International Standardization Organization)에서 지정한 기호와 흐름선을 활용,
  프로세스의 처리 순서를 포함한 단계 간의 상호관계를 알기 쉽게 나타낸 그림이다. 원고의 초안, 건축의 설계도와 같은 프로그래밍의
  기초가 되며 타인에게 전달, 크로스랭귀징, 유지보수 등에 기반이 되는 중요한 요소이다.

<br>

**일반적인 작성 규칙**

- 약속된 표준 기호를 사용한다.

- 흐름에 따라 위에서 아래로, 왼쪽에서 오른쪽으로 그리며 서로 교차하지 않도록 한다.
- 처리내용은 기호 내부에 간단명료하게 기술하고, 필요하면 외부의 주석기호에 추가기록하도록 한다.
- 한 면에 다 그릴 수 없거나 연속적인 표현이 어려울 때는 연결기호(연결자)를 사용한다.
- 문제가 복잡하고 어려울 때에는 처리 블록별로 나누어 단계적으로 그려나간다.

<br>

**순서도 작성**

- 시작과 끝: 타원
- 일반적인 처리: 사각형
- 조건(분기점): 마름모
- 화면 출력: 잘린 종이
- 데이터 입력: 평행사변형

![](img/flowchart.png)

**순서도 작성시 주의점**

- 기호 내에는 최대한 간략하게 내용을 기입하여 가독성을 향상시킨다.
- 비교/판단 기호 사용시 입/출력은 반드시 하나여야하며, 결과는 Yes or No여야 한다.
- 동일한 처리의 중복을 피한다.

<img src="img/flowchart_example.png" alt ="" width=50%>

<br>

### **3.2 HTML 화면 만들기**

- html 코드 작성

### **3.3 값 입력받아 변수에 저장하기**

- prompt(''): 사용자로부터 값을 전달받아 문자열로 받는다. 입력하지 않고 취소하면 null이 전달된다.
- alert(''): 단순한 알림창으로, 호출하면 확인을 누르기 전까지 다음 스크립트 실행이 중단됩니다. 디버깅 용도로 사용할 때는 console.log를 사용한다.
- confirm(''): 사용자의 확인을 요구하여 확인을 누르면 true, 취소를 누르면 false값을 반환한다.

### **3.4 HTML태그 선택하기**

```
// querySelector('')와 querySelectorAll('')의 차이점

document.querySelector('div'); : div 중에서 제일 첫번째만 선택됨
document.querySelectorAll('div'); div 모든 태그가 선택됨
```

```
// 선택자 사용하여 해당 태그 선택하기

태그로 선택하기 : document.querySelector('div span');
아이디로 선택하기: document.querySelector('#id(아이디명)');
클래스로 선택하기: document.querySelector('.class(클래스명)');
```

### **3.5 태그에 이벤트 달기**

- 이벤트: 사용자와 태그가 상호작용 (click, keyup, ...)
- 이벤트 리스너: 이벤트 발생이 자바스크립트가 직접 감지하지 못함. 그래서 자바스크림트가 HTML에서 발생하는 이벤트를 감지할 수 있게 해줌
- 콜백 함수: 특정 작업이 실행되고 난 뒤에 실행되는 함수

```html
<script>
  document
    .querySelector("선택자")
    .addEventListener("이벤트 이름", "리스너 함수");
</script>
```

### **3.6 첫 단어를 입력한 사람인지 판단하기**

```
// textContent의 사용

태그.textContent // 태그 내부의 문자열을 가져옴
태그.textContent = 값 // 태그 내부의 문자열을 해당 값으로 설정함
```

```
// 태그 내부의 문자열을 읽어오고 설정할 수 있는 프로퍼티

 - 태그.innerHTML: 해당 태그의 HTML, XML을 읽어오거나 설정할 수 있음(태그까지 모두 출력됨)
 - 태그.innerText: 사용자에게 보여지는 텍스트 값을 읽어옴(display:none은 출력되지 않음)
 - 태그.textContent: 해당 Node가 가지고 있는 텍스트 값을 그대로 읽어옴(display:none까지 출력됨)
```

### **3.7 올바른 단어인지 판단하기**

```
문자열

- 특정 문자 선택하기: 문자열[자랏수]
- 문자열의 길이: 문자열.length
```

### **3.8 틀렸을 때 오류 표시하기**

```
// 태그 내용 수정시
 - 일반적으로 .textContent를 사용
 - 입력 태그(input, select, textarea)는 .value 사용
```

### **3.9 순서도 최적화하기**

```
논리 연산자

논리곱(&&)연산자 (모두가 참이여야만 true/ 아니면 false)
 - true && true = true (**)
 - true && false = false
 - false && true = false
 - false && false = false

논리합(||)연산자(모두가 거짓이여만 false / 아니면 true)
 - true && true = true
 - true && false = true
 - false && true = true
 - false && false = false (**)
```

---