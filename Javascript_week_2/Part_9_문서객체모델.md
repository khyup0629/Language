# Part 9. 

+ [DOM의 개념](#DOM의-개념)
+ [Document 객체](#Document-객체)
+ [DOM 요소](#DOM-요소)
+ 

## DOM의 개념

> <h3>문서 객체 모델(DOM)이란?</h3>

문서 객체 모델(DOM, Document Object Model)은 XML이나 HTML 문서에 접근하기 위한 일종의 인터페이스입니다.

이 객체 모델은 문서 내의 모든 요소를 정의하고, 각각의 요소에 접근하는 방법을 제공합니다.

이러한 DOM은 W3C의 표준 객체 모델이며, 다음과 같이 계층 구조로 표현됩니다.

![image](https://user-images.githubusercontent.com/43658658/129890155-b05b62de-5b76-4c23-8fce-fcd44933ee71.png)

자바스크립트는 이러한 객체 모델을 이용하여 다음과 같은 작업을 할 수 있습니다.

 

- 자바스크립트는 새로운 HTML 요소나 속성을 추가할 수 있습니다.

- 자바스크립트는 존재하는 HTML 요소나 속성을 제거할 수 있습니다.

- 자바스크립트는 HTML 문서의 모든 HTML 요소를 변경할 수 있습니다.

- 자바스크립트는 HTML 문서의 모든 HTML 속성을 변경할 수 있습니다.

- 자바스크립트는 HTML 문서의 모든 CSS 스타일을 변경할 수 있습니다.

- 자바스크립트는 HTML 문서에 새로운 HTML 이벤트를 추가할 수 있습니다.

- 자바스크립트는 HTML 문서의 모든 HTML 이벤트에 반응할 수 있습니다.

> <h3>DOM의 종류</h3>

W3C DOM 표준은 세 가지 모델로 구분됩니다.

1. Core DOM : 모든 문서 타입을 위한 DOM 모델

2. HTML DOM : HTML 문서를 위한 DOM 모델

3. XML DOM : XML 문서를 위한 DOM 모델

> <h3>HTML DOM</h3>

HTML DOM은 HTML 문서를 조작하고 접근하는 표준화된 방법을 정의합니다.

모든 HTML 요소는 HTML DOM를 통해 접근할 수 있습니다.

## Document 객체

> <h3>Document 객체</h3>

Document 객체는 웹 페이지 그 자체를 의미합니다.

웹 페이지에 존재하는 HTML 요소에 접근하고자 할 때는 반드시 `Document 객체부터 시작`해야 합니다.

> <h3>Document 메소드</h3>

Document 객체는 HTML 요소와 관련된 작업을 도와주는 다양한 메소드를 제공합니다.

- HTML 요소의 선택

- HTML 요소의 생성

- HTML 이벤트 핸들러 추가

- HTML 객체의 선택

> <h3>HTML 요소의 선택</h3>

HTML 요소를 선택하기 위해 제공되는 메소드는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 50%;">메소드</th>
			<th style="width: 50%;">설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
			<p>document.getElementsByTagName(태그이름)</p>
			</td>
			<td>
			<p>해당 태그 이름의 요소를 모두 선택함.</p>
			</td>
		</tr>
		<tr>
			<td>
			<p>document.getElementById(아이디)</p>
			</td>
			<td>
			<p>해당 아이디의 요소를 선택함.</p>
			</td>
		</tr>
		<tr>
			<td>
			<p>document.getElementsByClassName(클래스이름)</p>
			</td>
			<td>해당 클래스에 속한 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>document.getElementsByName(name속성값)</td>
			<td>해당 name 속성값을 가지는 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>document.querySelectorAll(선택자)</td>
			<td>해당 선택자로 선택되는 요소를 모두 선택함.</td>
		</tr>
	</tbody>
</table>

> <h3>HTML 요소의 생성</h3>

새로운 HTML 요소를 생성하기 위해 제공되는 메소드는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 50%;">메소드</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
			<p>document.createElement(HTML요소)</p>
			</td>
			<td>
			<p>지정된 HTML 요소를 생성함.</p>
			</td>
		</tr>
		<tr>
			<td>document.write(텍스트)</td>
			<td>HTML 출력 스트림을 통해 텍스트를 출력함.</td>
		</tr>
	</tbody>
</table>

> <h3>HTML 이벤트 핸들러 추가</h3>

HTML 요소에 이벤트 핸들러를 추가하기 위해 제공되는 메소드는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 50%;">메소드</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
			<p>document.getElementById(아이디).onclick = function(){ 실행할 코드 }</p>
			</td>
			<td>마우스 클릭 이벤트와 연결될 이벤트 핸들러 코드를 추가함.</td>
		</tr>
	</tbody>
</table>

> <h3>HTML 객체의 선택</h3>

HTML DOM Level 1은 1998년에 정의되어, HTML5에서도 계속 사용되고 있습니다.

그 후 2004년에는 HTML DOM Level 3가 새롭게 정의되어, Level 1과 같이 사용되고 있습니다.

이러한 HTML DOM에서 제공하는 객체 집합(object collection)을 이용하면 HTML 객체를 손쉽게 선택할 수 있습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 30%;">객체 집합</th>
			<th style="width: 60%;">설명</th>
			<th style="width: 10%;">DOM Level</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>document.anchors</td>
			<td>name 속성을 가지는 &lt;a&gt;요소를 모두 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.applets</td>
			<td>applet 요소를 모두 반환함. <span style="color:#FF0000;">(HTML5에서 제외됨)</span></td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.body</td>
			<td>&lt;body&gt;요소를 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.cookie</td>
			<td>HTML 문서의 쿠키(cookie)를 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.domain</td>
			<td>
			<p>HTML 문서가 위치한 서버의 도메인 네임(domain name)을 반환함.</p>
			</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.forms</td>
			<td>&lt;form&gt;요소를 모두 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.images</td>
			<td>&lt;img&gt;요소를 모두 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.links</td>
			<td>href 속성을 가지는 &lt;area&gt;요소와 &lt;a&gt;요소를 모두 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.referrer</td>
			<td>링크(linking)되어 있는 문서의 URI를 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.title</td>
			<td>&lt;title&gt;요소를 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.URL</td>
			<td>HTML 문서의 완전한 URL 주소를 반환함.</td>
			<td>1</td>
		</tr>
		<tr>
			<td>document.baseURI</td>
			<td>HTML 문서의 절대 URI(absolute base URI)를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>document.doctype</td>
			<td>HTML 문서의 문서 타입(doctype)을 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.documentElement</p>
			</td>
			<td>&lt;html&gt;요소를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.documentMode</p>
			</td>
			<td>웹 브라우저가 사용하고 있는 모드를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.documentURI</p>
			</td>
			<td>HTML 문서의 URI를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>document.domConfig</td>
			<td>HTML DOM 설정을 반환함. <span style="color:#FF0000;">(더는 사용하지 않음)</span></td>
			<td>3</td>
		</tr>
		<tr>
			<td>document.embeds</td>
			<td>&lt;embed&gt;요소를 모두 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>document.head</td>
			<td>&lt;head&gt;요소를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.implementation</p>
			</td>
			<td>HTML DOM 구현(implementation)을 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.inputEncoding</p>
			</td>
			<td>HTML 문서의 문자 인코딩(character set) 형식을 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.lastModified</p>
			</td>
			<td>HTML 문서의 마지막 갱신 날짜 및 시간을 반환함</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.readyState</p>
			</td>
			<td>HTML 문서의 로딩 상태(loading status)를 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>document.scripts</td>
			<td>&lt;script&gt;요소를 모두 반환함.</td>
			<td>3</td>
		</tr>
		<tr>
			<td>
			<p>document.strictErrorChecking</p>
			</td>
			<td>오류의 강제 검사 여부를 반환함.</td>
			<td>3</td>
		</tr>
	</tbody>
</table>

## DOM 요소

> <h3>DOM 요소의 선택</h3>

HTML 요소를 다루기 위해서는 우선 해당 요소를 선택해야만 합니다.

자바스크립트에서 특정 HTML 요소를 선택하는 방법은 다음과 같습니다.

1. HTML 태그 이름(tag name)을 이용한 선택

2. 아이디(id)를 이용한 선택

3. 클래스(class)를 이용한 선택

4. name 속성(attribute)을 이용한 선택

5. CSS 선택자(selector)를 이용한 선택

6. HTML 객체 집합(object collection)을 이용한 선택

> <h3>HTML 태그 이름(tag name)을 이용한 선택</h3>

getElementsByTagName() 메소드는 HTML 태그 이름을 이용하여 HTML 요소를 선택합니다.

``` javascript
var selectedItem = document.getElementsByTagName("li");		// 모든 <li> 요소를 선택함.
      
for (var i = 0; i < selectedItem.length; i++) {
  selectedItem.item(i).style.color = "red";	// 선택된 모든 요소의 텍스트 색상을 변경함.
}
```

item() 메소드는 해당 HTML 객체 집합(obejct collection)에서 전달받은 인덱스에 해당하는 요소를 반환합니다.

HTML 요소의 style 프로퍼티를 이용하면, 해당 요소의 CSS 스타일을 변경할 수 있습니다.

> <h3>아이디(id)를 이용한 선택</h3>

getElementById() 메소드는 아이디를 이용하여 HTML 요소를 선택합니다.

``` javascript
var selectedItem = document.getElementById("even");	// 아이디가 "even"인 요소를 선택함.
selectedItem.style.color = "red";					// 선택된 요소의 텍스트 색상을 변경함.
```

자바스크립트에서 아이디(id)를 이용한 선택은 해당 아이디를 가지고 있는 요소 중에서 첫 번째 요소 단 하나만을 선택합니다.

따라서 여러 요소를 선택하고 싶을 때는 태그 이름이나 클래스와 같은 다른 방법을 사용해야 합니다.

> <h3>클래스(class)를 이용한 선택</h3>

getElementsByClassName() 메소드는 클래스 이름을 이용하여 HTML 요소를 선택합니다.

``` javascript
var selectedItem = document.getElementsByClassName("odd");	// 클래스가 "odd"인 모든 요소를 선택함.
for (var i = 0; i < selectedItem.length; i++) {
  selectedItem.item(i).style.color = "red";			// 선택된 모든 요소의 텍스트 색상을 변경함.
}
```

> <h3>name 속성을 이용한 선택</h3>

getElementByName() 메소드는 HTML 요소의 name 속성을 이용하여 HTML 요소를 선택합니다.

``` javascript
var selectedItem = document.getElementsByName("first");	// name 속성값이 "first"인 모든 요소를 선택함.
for (var i = 0; i < selectedItem.length; i++) {
  selectedItem.item(i).style.color = "red";			// 선택된 모든 요소의 텍스트 색상을 변경함.
}
```

> <h3>CSS 선택자(selector)를 이용한 선택</h3>

querySelectorAll() 메소드는 CSS 선택자(아이디, 클래스, 속성, 속성값 등)를 이용하여 HTML 요소를 선택합니다.

``` javascript
var selectedItem = document.querySelectorAll("li.odd");	// 클래스가 "odd"인 요소 중에서 <li> 요소만을 선택함.
for (var i = 0; i < selectedItem.length; i++) {
  selectedItem.item(i).style.color = "red";			// 선택된 모든 요소의 텍스트 색상을 변경함.
}
```

> <h3>HTML 객체 집합(object collection)을 이용한 선택</h3>

HTML DOM에서 제공하는 객체 집합(object collection)을 이용하여 HTML 요소를 선택할 수 있습니다.

``` javascript
var title = document.title; // <title> 요소를 선택함.
document.write(title);
```

> <h3>DOM 요소의 내용 변경</h3>

HTML DOM을 이용하면 HTML 요소의 내용(content)이나 속성값 등을 손쉽게 변경할 수 있습니다.

HTML 요소의 내용을 변경하는 가장 쉬운 방법은 innerHTML 프로퍼티를 이용하는 것입니다.

``` javascript
var str = document.getElementById("text");
str.innerHTML = "이 문장으로 바뀌었습니다!";
```

HTML 요소의 속성 이름을 이용하면 속성값도 변경할 수 있습니다.

``` javascript
<h1>속성 이름을 이용한 속성값 변경</h1>
<a id="link" href="http://tcpschool.com/html/intro">HTML 수업 바로 가기!</a><br><br>
<button onclick="changeLink()">자바스크립트 수업으로 바꾸기!</button>
	
<script>
  function changeLink() {
    var link = document.getElementById("link");				// 아이디가 "link"인 요소를 선택함.
    link.href = "http://tcpschool.com/javascript/intro";	// 해당 요소의 href 속성값을 변경함.
    link.innerHTML = "자바스크립트 수업 바로 가기!";		// 해당 요소의 내용을 변경함.
  }
</script>
```

> <h3>DOM 요소의 스타일 변경</h3>

HTML DOM을 이용하면 HTML 요소의 스타일(style)도 손쉽게 변경할 수 있습니다.

style 프로퍼티를 이용하여 HTML 요소에 CSS 스타일을 적용합니다.

``` javascript
<h1>DOM 요소의 스타일 변경</h1>
<p id="text">이 문자열의 기본색은 검정색입니다!</p>
<button onclick="changeRedColor()">빨간색 글자!</button>
<button onclick="changeBlackColor()">검정색 글자!</button>

<script>
  var str = document.getElementById("text");	// 아이디가 "str"인 요소를 선택함.
  function changeRedColor() {
    str.style.color = "red";				// 해당 요소의 글자색을 빨간색으로 변경함.
  }
  function changeBlackColor() {
    str.style.color = "black";				// 해당 요소의 글자색을 검정색으로 변경함.
  }
</script>
```

