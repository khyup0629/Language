# Part 4. HTML 공간 분할

+ [블록과 인라인](#블록과-인라인)
+ [iframe 요소](#iframe-요소)
+ [레이아웃](#레이아웃)

## 블록과 인라인

> <h3>HTML 요소의 타입</h3>

HTML의 모든 요소는 해당 요소가 웹 브라우저에 어떻게 보이는가를 결정짓는 display 속성을 가집니다.

대부분의 HTML 요소는 이러한 display 속성값으로 다음 두 가지 값 중 하나를 가지게 됩니다.

1. 블록(block)
2. 인라인(inline)

> <h3>블록(block) 타입의 요소</h3>

display 속성값이 블록(block)인 요소는 언제나 새로운 라인(line)에서 시작하며, 해당 라인의 모든 너비를 차지합니다.

`<p>, <div>, <h>, <ul>, <ol>, <form>`요소는 display 속성값이 블록(block)인 대표적인 요소입니다.

> <h3>&lt;div&gt;요소</h3>

`<div>`요소는 다른 HTML 요소들을 하나로 묶는 데 자주 사용되는 대표적인 블록(block) 요소입니다.

`<div>`요소는 주로 여러 요소들의 스타일을 한 번에 적용하기 위해 사용됩니다.

``` html
<div style="width:100%; color:green; background-color:lightgray; text-align:center">
  <h1>div요소를 이용한 스타일 적용</h1>
  <p>이렇게 div요소로 여러 요소들을 묶은 다음에 style 속성과 클래스 등을 이용하여 한 번에 스타일을 적용할 수 있습니다.</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/126499569-688d2821-2cfe-44c9-bb0d-48a386a9894f.png)

> <h3>인라인(inline) 타입의 요소</h3>

display 속성값이 인라인(inline)인 요소는 새로운 라인(line)에서 시작하지 않습니다.

또한, 요소의 너비도 해당 라인 전체가 아닌 해당 HTML 요소의 내용(content)만큼만 차지합니다.

`<span>, <a>, <img>`요소는 display 속성값이 인라인(inline)인 대표적인 요소입니다.

``` html
<h1>display 속성값 : 인라인</h1>
<p><span style="background-color:grey; color:orange">span요소</span>는 display 속성값이 인라인인 요소입니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126500022-6e05b8b7-d150-4157-ae39-9762a46b46c8.png)

> <h3>&lt;span&gt;요소</h3>

`<span>`요소는 텍스트(text)의 특정 부분을 묶는 데 자주 사용되는 인라인(inline) 요소입니다.

`<span>`요소는 주로 텍스트의 특정 부분에 따로 스타일을 적용하기 위해 사용됩니다.

``` html
<h1>span요소를 이용한 스타일 적용</h1>
  <p>이렇게
    <span style="border: 3px solid red">span요소로 텍스트의 일부분</span>
    만을 따로 묶은 후에 스타일을 적용할 수 있습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126500829-dba70a01-7ad2-48b5-a84e-7ae8f4218c87.png)

## iframe 요소

iframe이란 inline frame의 약자입니다.

iframe 요소를 이용하면 해당 웹 페이지 안에 어떠한 제한 없이 또 다른 하나의 웹 페이지를 삽입할 수 있습니다.

`<iframe src="삽입할페이지주소"></iframe>`

iframe 요소는 frame 요소와는 달리 종료 태그가 존재합니다.

또한, iframe 요소는 명시된 크기로 삽입되는 창의 크기가 고정됩니다.

``` html
<iframe src="/html/intro" style="width:100%; height:300px"></iframe>
```

> <h3>iframe 요소의 테두리 변경</h3>

iframe 요소는 기본적으로 검정색 테두리(border)를 가집니다.

이러한 테두리의 스타일은 style 속성에서 border 속성을 이용하면 변경할 수 있습니다.

테두리를 표현하고 싶지 않으면 style 속성에서 border 속성값을 none으로 설정하면 됩니다.

``` html
<iframe src="/html/intro" style="width:100%; height:300px; border: 3px dashed maroon"></iframe>
<iframe src="/html/intro" style="width:100%; height:300px; border: none"></iframe>
```

+ border: dashed는 점섬을 의미한다.

> <h3>iframe 요소의 페이지 변경하기</h3>

`<a>`태그를 이용하면 iframe 요소의 최초 페이지를 중간에 변경할 수 있습니다.

`<a>`태그의 target 속성과 iframe 요소의 name 속성을 연결하면, `<a>`태그를 통해 iframe 요소의 페이지를 변경할 수 있게 됩니다.

``` html
<h1>iframe 요소의 페이지 변경하기</h1>
<iframe src="/css/intro" name="frame_target" style="width:100%; height:400px"></iframe>
<p><a href="/php/intro" target="frame_target">PHP 수업 확인하러 가기 =></a></p>
<p>위의 링크를 클릭하면 iframe 요소의 페이지가 다른 페이지로 변경돼요!</p>
```

최초 frame에는 "/css/intro"가 열리지만 하이퍼링크를 클릭하면 frame에는 "/php/intro"가 열립니다.

![image](https://user-images.githubusercontent.com/43658658/126507675-f34b3541-512c-48f8-af72-29d6c66fafbd.png)

> <h3>프레임셋(frameset)</h3>

프레임셋(frameset)을 이용하면 하나의 브라우저 창에 둘 이상의 페이지를 표시할 수 있습니다.

이러한 프레임셋은 iframe 요소와는 달리 하나 이상의 페이지를 동시에 가질 수 있습니다.

또한, noresize 속성을 명시하지 않으면, 사용자가 마음대로 페이지의 크기를 조절할 수 있습니다.

프레임셋에서 각각의 페이지는 frame 요소로 표현됩니다.

frame 요소는 iframe 요소와는 달리 종료 태그를 가지지 않습니다.

noframes 요소는 해당 브라우저가 frame 요소를 지원하지 않을 때 보여지는 문자열을 저장합니다.

+ frameset, frame, noframes 요소는 **더는 HTML5 표준 권고안에서 지원하지 않습니다.**
+ 따라서 하나의 브라우저 창에 여러 페이지를 표현하고 싶을 때는 **iframe 요소를 사용하거나 CSS를 이용**하여 표현해야 합니다.

> <h3>수직 프레임셋</h3>

수직 프레임셋은 하나의 브라우저 창을 세로 방향으로 분리하여 표현합니다.

``` html
<frameset cols="25%,*,25%">
<frame name="left" src="/html/intro"/>
<frame name="center" src="/css/intro"/>
<frame name="right" src="/php/intro"/>
<noframes>
    <body> 이 브라우저는 frame태그를 지원하지 않습니다! </body>
</noframes>
</frameset>
```

> <h3>수평 프레임셋</h3>

수평 프레임셋은 하나의 브라우저 창을 가로 방향으로 분리하여 표현합니다.

``` html
<frameset rows="20%,60%,20%">
<frame name="top" src="/html/intro" noresize="noresize" />
<frame name="center" src="/css/intro" noresize="noresize" />
<frame name="bottom" src="/php/intro" noresize="noresize" />
<noframes>
    <body>이 브라우저는 frame태그를 지원하지 않습니다!</body>
</noframes>
</frameset>
```

위의 예제는 frame 요소에 noresize 속성을 명시하였으므로, 사용자가 창의 크기를 조절할 수 없습니다.

## 레이아웃

> <h3>HTML 레이아웃(Layout)</h3>

레이아웃(layout)이란 특정 공간에 여러 구성 요소를 보기 좋게 효과적으로 배치하는 작업을 의미합니다.

웹 페이지의 레이아웃은 웹 사이트의 외관을 결정짓는 매우 중요한 요소입니다.

HTML에서는 다음과 같은 방법으로 레이아웃을 작성할 수 있습니다.

1. div 요소를 이용한 레이아웃
2. HTML5 레이아웃
3. table 요소를 이용한 레이아웃

> <h3>div 요소를 이용한 레이아웃</h3>

div 요소는 CSS 스타일을 손쉽게 적용할 수 있으므로, 레이아웃을 작성하는데 자주 사용됩니다.

``` html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<title>HTML Layouts</title>
	<style>
		#header {
			background-color:lightgrey;
			height:100px;
		}
		#nav {
			background-color:#339999;
			color:white;
			width:200px;
			height:300px;
			float:left;
		}
		#section {
			width:200px;
			text-align:left;
			float:left;
			padding:10px;
		}
		#footer {
			background-color:#FFCC00;
			height:100px;
			clear:both;
		}
		#header, #nav, #section, #footer { text-align:center; }
		#header, #footer { line-height:100px; }
		#nav, #section { line-height:240px; }
	</style>
</head>
<body>
	<h1>div 요소를 이용한 레이아웃</h1>
	<div id="header">
		<h2>HEADER 영역</h2>
	</div>
	<div id="nav">
		<h2>NAV 영역</h2>
	</div>
	<div id="section">
		<p>SECTION 영역</p>
	</div>
	<div id="footer">
		<h2>FOOTER 영역</h2>
	</div>
</body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126511250-385d2f0d-246e-47da-9a66-b20e21bbefc8.png)

> <h3>HTML5 레이아웃</h3>

HTML5에서는 웹 페이지의 레이아웃만을 위한 별도의 새로운 요소들을 제공합니다.

이러한 요소들을 의미(semantic) 요소라고 합니다.

![image](https://user-images.githubusercontent.com/43658658/126512073-81d98d79-09d0-4f4f-8aee-fc2f65f8e6ae.png)

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>HTML Layouts</title>
    <style>
      header {
        background-color:lightgrey;
        height:100px;
      }
      nav {
        background-color:#339999;
        color:white;
        width:200px;
        height:300px;
        float:left;
      }
      section {
        width:200px;
        text-align:left;
        float:left;
        padding:10px;
      }
      footer {
        background-color:#FFCC00;
        height:100px;
        clear:both;
      }
      header, nav, section, footer { text-align:center; }
      header, footer { line-height:100px; }
      nav, section { line-height:240px; }
    </style>
  </head>
  <body>
    <h1>HTML5 레이아웃</h1>
    <header>
      <h2>HEADER 영역</h2>
    </header>
    <nav>
      <h2>NAV 영역</h2>
    </nav>
    <section>
      <p>SECTION 영역</p>
    </section>
    <footer>
      <h2>FOOTER 영역</h2>
    </footer>
  </body>
</html>
```

앞서 레이아웃을 div 요소로 분리하고 id를 header, nav, section, footer로 줬고 그에 따라 style 지정도 #을 앞에 붙여야 했습니다.

하지만 HTML5의 레이아웃을 사용하게 되면 태그로서 사용이 가능하고 style 지정에도 #을 붙일 필요가 없게 됩니다.

HTML5에서 제공하는 레이아웃만을 위한 의미(semantic) 요소는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>의미 요소</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&lt;header&gt;</td>
			<td>HTML 문서나 섹션(section) 부분에 대한 헤더(header)를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;nav&gt;</td>
			<td>HTML 문서의 탐색 링크를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;section&gt;</td>
			<td>HTML 문서에서 섹션(section) 부분을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;article&gt;</td>
			<td>HTML 문서에서 독립적인 하나의 글(article) 부분을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;aside&gt;</td>
			<td>HTML 문서에서 페이지 부분 이외의 콘텐츠(content)를 정의함.&nbsp;</td>
		</tr>
		<tr>
			<td>&lt;footer&gt;</td>
			<td>HTML 문서나 섹션(section) 부분에 대한 푸터(footer)를 정의함.</td>
		</tr>
	</tbody>
</table>

> <h3>table 요소를 이용한 레이아웃</h3>

table 요소를 이용하여 레이아웃을 작성하는 방법은 오래전에 사용하던 방식이며, **현재는 거의 사용하지 않습니다.**

table 요소는 레이아웃을 만들기 위해 설계된 요소가 아니므로, 테이블로 작성된 레이아웃은 수정이 매우 힘듭니다.
