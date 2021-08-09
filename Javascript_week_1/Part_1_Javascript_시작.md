# Part 1. Javascript 개요

+ [자바스크립트](#자바스크립트)
+ [자바스크립트 소개](#자바스크립트-소개)
+ [자바스크립트 문법](#자바스크립트-문법)
+ [자바스크립트 출력](#자바스크립트-출력)
+ [자바스크립트 적용](#자바스크립트-적용)

## 자바스크립트

자바스크립트(JavaScript)는 객체(object) 기반의 스크립트 언어입니다.

HTML로는 웹의 내용을 작성하고, CSS로는 웹을 디자인하며, 자바스크립트로는 웹의 동작을 구현할 수 있습니다.

자바스크립트는 주로 웹 브라우저에서 사용되나, Node.js와 같은 프레임워크를 사용하면 서버 측 프로그래밍에서도 사용할 수 있습니다.

현재 컴퓨터나 스마트폰 등에 포함된 대부분의 웹 브라우저에는 자바스크립트 인터프리터가 내장되어 있습니다.

> <h3>자바스크립트의 특징</h3>

자바스크립트가 가지고 있는 언어적 특징은 다음과 같습니다.

1. 자바스크립트는 객체 기반의 스크립트 언어입니다.

2. 자바스크립트는 동적이며, 타입을 명시할 필요가 없는 인터프리터 언어입니다.

3. 자바스크립트는 객체 지향형 프로그래밍과 함수형 프로그래밍을 모두 표현할 수 있습니다.

C언어와 같은 언어는 소스 파일을 작성한 후, 해당 파일을 `컴파일(compile)`하여 사용자가 실행할 수 있는 `실행 파일(.exe)로 만들어 사용`합니다.

하지만 `인터프리터 언어`는 이러한 컴파일 작업을 거치지 않고, 소스 코드를 바로 실행할 수 있는 언어를 의미합니다.

자바스크립트는 웹 브라우저에 포함된 자바스크립트 인터프리터가 소스 코드를 직접 해석하여 바로 실행해 줍니다.

> <h3>자바와 자바스크립트</h3>

자바와 자바스크립트는 그 이름만 놓고 보면 서로 관련이 있는 언어로 생각되기 쉽습니다.

하지만 두 언어는 서로 직접적인 관련은 없으며, 비슷한 점보다는 다른 점이 훨씬 많습니다.

문법상 비슷한 부분은 두 언어의 문법이 모두 C언어를 기반으로 만들어졌기 때문입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 50%;">자바</th>
			<th style="width: 50%;">자바스크립트</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: left;">컴파일 언어</td>
			<td>인터프리터 언어</td>
		</tr>
		<tr>
			<td style="text-align: left;">타입 검사를 엄격하게 함.</td>
			<td>타입을 명시하지 않음.</td>
		</tr>
		<tr>
			<td style="text-align: left;">클래스(class) 기반의 객체 지향 언어</td>
			<td>프로토타입(prototype) 기반의 객체 지향 언어</td>
		</tr>
	</tbody>
</table>

## 자바스크립트 소개

자바스크립트를 사용하여 웹 프로그래밍에서 할 수 있는 일은 다음과 같이 매우 다양합니다.

1. 자바스크립트는 HTML의 '내용'을 변경할수 있습니다

2. 자바스크립트는 HTML의 '속성'을 변경할수 있습니다.

3. 자바스크립트는 HTML의 '스타일'을 변경할수 있습니다.

> <h3>HTML 요소의 내용 변경</h3>

자바스크립트를 사용하면 HTML 요소의 내용을 손쉽게 변경할 수 있습니다.

예를 들어, 버튼을 클릭하여 특정 `<p>`태그의 내용을 변경하는 것을 자바스크립트를 통해 구현할 수 있습니다.

> <h3>HTML 요소의 속성값 변경</h3>

자바스크립트를 사용하면 HTML 요소의 속성값을 간단히 변경할 수 있습니다.

예를 들어, 버튼을 클릭하여 특정 `<img>`태그의 src 속성값을 변경하는 것을 자바스크립트를 통해 구현할 수 있습니다.

> <h3>HTML 요소의 스타일 변경</h3>

자바스크립트를 사용하면 HTML 요소의 스타일을 손쉽게 변경할 수 있습니다.

예를 들어, 버튼을 클릭하여 특정 `<p>`태그의 스타일을 변경할 수 있습니다.

## 자바스크립트 문법

> <h3>프로그램(program)이란?</h3>

프로그램은 컴퓨터가 실행할 수 있는 명령(instruction)으로 이루어집니다.

컴퓨터 프로그래밍에서 컴퓨터가 실행할 수 있는 명령들을 실행문(statement)이라고 합니다.

즉, 프로그램이란 특정 결과를 얻기 위해서 컴퓨터에 의해 실행되는 실행문의 집합이라고 할 수 있습니다.

> <h3>자바스크립트 문법</h3>

자바스크립트의 실행문은 `세미콜론(;)`으로 구분됩니다.

``` html
var x = 10;
var result = x + 3;
```

자바스크립트는 대소문자를 구분합니다.

자바스크립트에서 변수나 함수의 이름, 예약어 등을 작성하거나 사용할 때에는 대소문자를 정확히 구분해서 사용해야 합니다.

``` html
var javascript = 10; // 변수 javascript와 JavaScript는 서로 다른 두 개의 변수로 인식됨.
var JavaScript = 20;
Var Script = 30; // 잘못된 실행문. 변수의 선언은 var 키워드로만 할 수 있으며 Var는 동작하지 않음.
```

> <h3>리터럴(literal)</h3>

리터럴은 직접 표현되는 값 그 자체를 의미합니다.

다음 예제에서 등장하는 값들은 모두 리터럴입니다.

``` html
12            // 숫자 리터럴
"JavaScript"  // 문자열 리터럴
'안녕하세요'  // 문자열 리터럴
true          // 불리언 리터럴
```

> <h3>식별자(identifier)</h3>

식별자는 변수나 함수의 이름을 작성할 때 사용하는 이름을 의미합니다.

자바스크립트에서 식별자는 `영문자(대소문자), 숫자, 언더스코어(&#95;) 또는 달러($)`만을 사용할 수 있습니다.

자바스크립트에서 식별자는 숫자와 식별자의 구별을 빠르게 할 수 있도록 숫자로는 시작할 수 없습니다.

자바스크립트는 유니코드(unicode) 문자셋을 사용합니다.

> <h3>식별자 작성 방식</h3>

자바스크립트에서는 식별자를 작성할 때 다음과 같은 작성 방식을 사용할 수 있습니다.

1. Camel Case 방식
2. Underscore Case 방식

Camel Case : 식별자가 여러 단어로 이루어질 경우에 첫 번째 단어는 모두 소문자로 작성하고, 그다음 단어부터는 첫 문자만 대문자로 작성하는 방식입니다.

Underscore Case : 식별자를 이루는 단어들을 소문자로만 작성하고, 그 단어들은 언더스코어(&#95;)로 연결하는 방식입니다.

자바스크립트에서는 식별자를 작성할 때 관행적으로 `Camel Case` 방식을 많이 사용합니다.

``` html
var firstVar = 10;           // Camel Case 방식
function my_first_func {     // Underscore Case 방식
    var firstLocalVar = 20;  // Camel Case 방식
}
```

> <h3>주석(comment)</h3>

주석(comment)이란 코드 내에 삽입된 일종의 설명문입니다.

자바스크립트 주석은 다음과 같은 두 가지 형식을 지원합니다.

```
1. 한 줄 주석 : // 주석문
2. 여러 줄 주석 : /* 주석문 */
```

## 자바스크립트 출력

자바스크립트는 여러 방법을 통해 결과물을 HTML 페이지에 출력할 수 있습니다.

자바스크립트에서 사용할 수 있는 출력 방법은 다음과 같습니다.

1. window.alert() 메소드

2. HTML DOM 요소를 이용한 innerHTML 프로퍼티

3. document.write() 메소드

4. console.log() 메소드

> <h3>window.alert() 메소드</h3>

자바스크립트에서 가장 간단하게 데이터를 출력할 수 있는 방법은 window.alert() 메소드를 이용하는 것입니다.

window.alert() 메소드는 브라우저와는 별도의 대화 상자를 띄워 사용자에게 데이터를 전달해 줍니다.

window 객체의 모든 메소드나 프로퍼티를 사용할 때는 window라는 접두사를 생략할 수 있습니다.

``` html
<h1>Window 객체의 alert() 메소드</h1>
<button onclick="alertDialogBox()">alert 대화 상자</button>
<script>
  function alertDialogBox(){
    alert("확인을 누를 때까지 다른 작업을 할 수 없어요!");
  }
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128689485-5eec6932-cf14-49f5-9049-37bddc5b609b.png)

> <h3>HTML DOM 요소를 이용한 innerHTML 프로퍼티</h3>

실제 자바스크립트 코드에서 출력을 위해 가장 많이 사용되는 방법은 HTML DOM 요소를 이용한 innerHTML 프로퍼티를 이용하는 방법입니다.

우선 document 객체의 getElementByID()나 getElementsByTagName() 등의 메소드를 사용하여 HTML 요소를 선택합니다.

그리고서 innerHTML 프로퍼티를 이용하면 선택된 HTML 요소의 내용(content)이나 속성(attribute)값 등을 손쉽게 변경할 수 있습니다.

``` html
<p id="text">이 문장을 바꿀 것입니다.</p>

<script>
  var str=document.getElementById("text");
  str.innerHTML= "이 문장으로 바뀌었습니다!";
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128690402-5b92dbef-60ac-488e-af09-e71278c967b0.png)

> <h3>document.write() 메소드</h3>

document.write() 메소드는 웹 페이지가 로딩될 때 실행되면, 웹 페이지에 가장 먼저 데이터를 출력합니다.

따라서 document.write() 메소드는 대부분 테스트나 디버깅을 위해 사용됩니다.

``` html
<script>
  document.write(4 * 5);
</script>
```

하지만 웹 페이지의 모든 내용이 로딩된 후에 document.write() 메소드가 실행되면, 웹 페이지 내에 먼저 로딩된 모든 데이터를 지우고 자신의 데이터를 출력하게 됩니다.

따라서 document.write() 메소드를 테스트 이외의 용도로 사용할 때에는 충분히 주의해서 사용해야 합니다.

``` html
<button onclick="document.write(4 * 5)">버튼을 눌러보세요!</button>
```

버튼을 누르기 전엔 버튼이 표시되어 있지만,

![image](https://user-images.githubusercontent.com/43658658/128690928-efe2384b-475a-473f-894a-85fbd0a0b47d.png)

버튼을 누르면 버튼이 사라지고 20이 나타납니다.

![image](https://user-images.githubusercontent.com/43658658/128690967-18757a9d-dc46-4ab7-a5cc-391615e98b26.png)

> <h3>console.log() 메소드</h3>

console.log() 메소드는 웹 브라우저의 콘솔을 통해 데이터를 출력해 줍니다.

대부분의 주요 웹 브라우저에서는 `F12`를 누른 후, 메뉴에서 콘솔을 클릭하면 콘솔 화면을 사용할 수 있습니다.

이러한 콘솔 화면을 통한 데이터의 출력은 좀 더 자세한 사항까지 출력되므로, `디버깅하는데 많은 도움을 줍니다.`

``` html
<p>F12를 눌러서 콘솔 화면을 열면 결과를 확인할 수 있습니다.</p>
<script>
  console.log(4 * 5);
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128692305-1738a884-d15e-48ef-b460-27117f2c5af0.png)

## 자바스크립트 적용

HTML 문서에 자바스크립트 코드를 적용하는 방법에는 다음과 같은 방법이 있습니다.

 

1. 내부 자바스크립트 코드로 적용

2. 외부 자바스크립트 파일로 적용

> <h3>내부 자바스크립트 코드</h3>

자바스크립트 코드는 `<script>`태그를 사용하여 HTML 문서 안에 삽입할 수 있습니다.

```
<script>
    document.getElementById("text").innerHTML = "여러분을 환영합니다!";
</script>
```

이렇게 삽입된 자바스크립트 코드는 HTML 문서의 `<head>`태그나 `<body>`태그, 또는 양쪽 모두에 위치할 수 있습니다.

``` html
<script>
    document.getElementById("text").innerHTML = "여러분을 환영합니다!";
</script>
...
<p>자바스크립트를 이용하면 현재 날짜와 시간 정보에도 손쉽게 접근할 수 있어요!</p>
<button onclick="printDate()">현재 날짜와 시간 표시하기!</button>
<p id="date"></p>
```

버튼을 클릭하면 버튼 밑에 현재 시간이 출력됩니다.

![image](https://user-images.githubusercontent.com/43658658/128693911-61b796a9-1bb7-400d-b8ed-640faf6065aa.png)

> <h3>외부 자바스크립트 파일</h3>

자바스크립트 코드는 HTML 문서의 내부뿐만 아니라 외부 파일로 생성하여 삽입할 수도 있습니다.

외부에 작성된 자바스크립트 파일은 .js 확장자를 사용하여 저장합니다.

해당 자바스크립트 파일을 적용하고 싶은 모든 웹 페이지에 `<script>`태그를 사용해 외부 자바스크립트 파일을 포함하면 됩니다.

```
example.js
function printDate() {
    document.getElementById("date").innerHTML = Date();
}
```

``` html
<script src="/examples/media/example.js"></script>
...
<h1>외부 자바스크립트 파일</h1>
<p>자바스크립트를 이용하면 현재 날짜와 시간 정보에도 손쉽게 접근할 수 있어요!</p>
<button onclick="printDate()">현재 날짜와 시간 표시하기!</button>
<p id="date"></p>
```

외부 자바스크립트 파일을 사용하면 웹의 내용을 담당하는 HTML 코드로부터 웹의 동작을 구현하는 자바스크립트 코드를 분리할 수 있습니다.

이렇게 하면 HTML 코드와 자바스크립트 코드를 각각 읽기도 편해지고, 유지 보수도 쉬워집니다.

또한, 외부 자바스크립트 파일은 웹 브라우저가 미리 읽어 올 수 있어 웹 페이지의 로딩 속도 또한 빨라집니다.

