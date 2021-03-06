# HTML5 시작

+ [HTML5 개요](#HTML5-개요)
+ [HTML5 변경사항](#HTML5-변경사항)
+ [HTML5 추가요소](#HTML5-추가요소)

## HTML5 개요

HTML5는 웹 상에서 콘텐츠(content)를 구성하고 보여주기 위한 HTML 언어의 최신 표준 권고안입니다.

HTML5는 HTML 4.01, XHTML 1.1 등을 대체하는 HTML의 차세대 표준입니다.

HTML5는 XML이나 XHTML과는 달리 문법적으로 매우 유연하게 대처합니다.

따라서 다음과 같은 사항들을 모두 문법적으로 허용합니다.

- 태그 이름에 대문자 사용
- 속성값에 따옴표 생략
- 속성값 생략
- 빈 태그의 종료 태그(/) 생략

> <h3>HTML5 문서의 기본 구조</h3>

HTML5에서는 DOCTYPE 선언이 매우 간단해졌습니다.

```
<!DOCTYPE html>
```

또한, 문자셋(character set)의 선언도 매우 간단해졌습니다.

HTML5에서의 기본 문자 인코딩(character encoding) 방식은 UTF-8입니다.

``` html
<!--HTML5 이전-->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
```

``` html
<!--HTML5-->
<meta charset="UTF-8">
```

## HTML5 변경사항

> <h3>HTML5에서 추가된 요소 및 타입</h3>

- 의미(semantic) 요소 : `<header>, <nav>, <main>, <section>, <aside>, <article>, <footer>, <figure>`
- 멀티미디어 요소 : `<video>, <audio>`
- 그래픽 요소 : `<canvas>, <svg>`
- input 요소의 타입 : number, date, time, calendar, range

> <h3>HTML5에서 추가된 자바스크립트 API</h3>

- Geolocation
- Drag and Drop
- Web Storage
- Application Cache
- Web Worker
- Server Sent Events

> <h3>HTML5에서 삭제된 기존 요소</h3>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 40%;">삭제된 기존 요소</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&lt;acronym&gt;</td>
			<td>&lt;abbr&gt; 태그로 대체</td>
		</tr>
		<tr>
			<td>&lt;applet&gt;</td>
			<td>&lt;object&gt; 태그로 대체</td>
		</tr>
		<tr>
			<td>&lt;basefont&gt;</td>
			<td>CSS로 적용</td>
		</tr>
		<tr>
			<td>&lt;big&gt;</td>
			<td>CSS로 적용</td>
		</tr>
		<tr>
			<td>&lt;center&gt;</td>
			<td>CSS로 적용</td>
		</tr>
		<tr>
			<td>&lt;dir&gt;</td>
			<td>&lt;ul&gt; 태그로 대체</td>
		</tr>
		<tr>
			<td>&lt;font&gt;</td>
			<td>CSS로 적용</td>
		</tr>
		<tr>
			<td>&lt;frame&gt;</td>
			<td>삭제</td>
		</tr>
		<tr>
			<td>&lt;frameset&gt;</td>
			<td>삭제</td>
		</tr>
		<tr>
			<td>&lt;noframes&gt;</td>
			<td>삭제</td>
		</tr>
		<tr>
			<td>&lt;strike&gt;</td>
			<td>CSS로 적용</td>
		</tr>
		<tr>
			<td>&lt;tt&gt;</td>
			<td>CSS로 적용</td>
		</tr>
	</tbody>
</table>

> <h3>웹 브라우저의 HTML5 지원</h3>
 
현재 최신 버전의 주요 웹 브라우저들은 모두 HTML5를 지원하고 있습니다.

하지만 HTML5의 새로운 요소들이 구형 버전의 웹 브라우저에서는 제대로 표현되지 못할 수도 있습니다.

따라서 구형 버전의 웹 브라우저에 자신이 알지 못하는 새로운 HTML 요소를 다루는 방법을 알려줘야만 합니다.

다음 예제는 웹 브라우저가 알지 못하는 새로운 HTML 요소를 어떻게 다뤄야 하는지 알려주는 방법을 보여줍니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>HTML5 Changes</title>
    <script>document.createElement("newPara")</script>
    <style>
      newPara {
        background-color: #F0F0F0;
        display: block;
        padding: 10px;
        font-size: 14px;
      } 
    </style> 
  </head>
  <body>
    <h1>새로운 HTML 요소의 정의</h1>
    <h2>제목 2입니다.</h2>
    <p>단락입니다.</p>
    <newPara>우리 수업에서만 사용하는 단락입니다!</newPara>
  </body>
</html>
```

`<head>` 내에 `<script>`를 선언하고 `document.createElement("새로운 요소 이름")`를 속에 적어줍니다.

그럼 기존에 HTML 요소에 없는 새로운 `<새로운 요소 이름>`의 태그를 생성합니다.

이후에 `<style>`을 통해 새로운 요소의 서식을 지정해줍니다.

위와 같은 방법을 사용하면 모든 새로운 요소를 웹 브라우저에 설명할 수 있습니다.

하지만 익스플로러 8과 그 이전 버전에서는 위와 같이 HTML 요소를 새롭게 정의하는 것을 허용하지 않습니다.

따라서 위와 같은 방법이 아닌 ***HTML Shiv 방법***을 사용해야 합니다.

> <h3>HTML Shiv 방법</h3>

우선 아래의 주석 코드를 `<head>`태그 내에 삽입합니다.

그러면 익스플로러 8과 그 이전 버전의 브라우저만이 이 자바 스크립트 파일을 읽고 적용할 것입니다.

이와 같은 방법으로 익스플로러 8과 그 이전 버전에서도 HTML5의 새로운 요소들을 자유롭게 사용할 수 있습니다.

이러한 방법을 HTML Shiv 방법이라고 하며, Sjoerd Visscher에 의해 개발되었습니다.

``` html
<!--[if lt IE 9]>
<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js">
</script>
<![endif]-->
```

## HTML5 추가요소

HTML5에서 추가된 의미(semantic) 요소

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
			<td>HTML 문서 사이를 탐색할 수 있는 링크(link)의 집합을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;main&gt;</td>
			<td>HTML 문서의 주요 콘텐츠(content)를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;section&gt;</td>
			<td>HTML 문서에서 섹션(section) 부분을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;article&gt;</td>
			<td>HTML 문서에서 독립적인 하나의 기사(article) 부분을 정의함.</td>
		</tr>
		<tr>
			<td>&nbsp;&lt;aside&gt;</td>
			<td>HTML 문서에서 페이지 부분 이외의 콘텐츠(content)를 정의함.&nbsp;</td>
		</tr>
		<tr>
			<td>&lt;figure&gt;</td>
			<td>HTML 문서에서 그래픽과 비디오 등의 독립적인 콘텐츠(content)를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;figcaption&gt;</td>
			<td>figure 요소를 위한 캡션을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;footer&gt;</td>
			<td>HTML 문서나 섹션(section) 부분에 대한 푸터(footer)를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;bdi&gt;</td>
			<td>기본 출력방향과는 다른 방향으로 출력되는 텍스트를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;mark&gt;</td>
			<td>하이라이팅된 텍스트를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;details&gt;</td>
			<td>사용자가 보거나 숨길 수 있는 추가적인 설명문을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;summary&gt;</td>
			<td>details 요소에 나타날 내용을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;dialog&gt;</td>
			<td>다이얼로그(dialog) 박스나 다이얼로그 윈도우를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;menuitem&gt;</td>
			<td>사용자가 팝업 메뉴(popup menu)를 통해 선택할 수 있는 메뉴의 아이템(menu item)을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;meter&gt;</td>
			<td>정해진 범위 내의 스칼라 치수를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;progress&gt;</td>
			<td>작업에 대한 진행 정도를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;ruby&gt;</td>
			<td>루비(ruby) 문자를 선언함.</td>
		</tr>
		<tr>
			<td>&lt;rt&gt;</td>
			<td>본문 위에 나타날 문자를 정의함.</td>
		</tr>
		<tr>
			<td>&lt;rp&gt;</td>
			<td>루비(ruby) 문자를 지원하지 않는 브라우저에서만 나타날 내용을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;time&gt;</td>
			<td>날짜와 시간을 정의함.</td>
		</tr>
		<tr>
			<td>&lt;wbr&gt;</td>
			<td>br 요소와는 달리 긴 단어가 화면의 맨 끝에 오면 상황에 따라 줄 바꿈 할 곳을 미리 정의함.</td>
		</tr>
	</tbody>
</table>

> <h3>HTML5에서 추가된 다양한 타입의 input 요소</h3>

- `<datalist>`	: input 요소에 대해 미리 정의된 옵션 리스트를 명시함.
- `<keygen>`	: form 요소 안에 두 개의 키(key)를 만들어주는 생성기를 명시함.
- `<output>`	: 스크립트 등으로 실행된 계산의 결과를 바로 나타냄.

> <h3>HTML5에서 추가된 input 요소의 타입</h3>

+ number
+ range
- color
- date
- time
- datetime-local
- month
- week
- email
- tel
- url
- search

> <h3>HTML5에서 추가된 form 요소의 속성</h3>

- autocomplete
- novalidate

> <h3>HTML5에서 추가된 input 요소의 속성</h3>

- autocomplete
- autofocus
- form
- formaction
- formenctype
- formmethod
- formnovalidate
- formtarget
- height and width
- list
- min and max
- multiple
- pattern
- placeholder
- required
- step

> <h3>HTML5에서 추가된 그래픽 요소</h3>

- `<canvas>` 	: 자바 스크립트를 이용한 그래픽 작업을 정의함.
- `<svg>`	: SVG를 이용한 그래픽 작업을 정의함.

> <h3>HTML5에서 추가된 멀티미디어 요소</h3>

- `<audio>`	: 오디오와 음악 등 오디오 파일을 명시함.
- `<video>`	: 비디오와 영화 등 비디오 파일을 명시함.
- `<embed>`	: 플러그인(plug-in)과 같은 HTML 문서에 삽입할 객체(object)를 명시함.
- `<source>` 	: 멀티미디어 요소의 원본에 대한 파일 형식 및 파일 주소를 여러 개 명시함.
- `<track>`	: 비디오 플레이어에 대한 텍스트 자막을 명시함.
