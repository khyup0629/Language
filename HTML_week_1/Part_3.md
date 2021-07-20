# Part 3. HTML 기본 요소

+ [HTML 스타일(Style)](#HTML-스타일Style)
+ [HTML 색](#HTML-색)
+ [HTML 배경](#HTML-배경)
+ [HTML 링크(Link)](#HTML-링크Link)
+ [HTML 이미지(Image)](#HTML-이미지Image)
+ 

## HTML 스타일(Style)

HTML 요소의 style 속성(attribute)을 이용하면 CSS 스타일을 HTML 요소에 직접 설정할 수 있습니다.

하지만 이러한 style 속성을 이용한 방법은 오직 단 하나의 HTML 요소에만 스타일을 적용할 수 있습니다

`<태그이름 style="속성이름:속성값">`

> <h3>배경색 변경(background-color)</h3>

다음 예제는 style 속성을 이용하여 배경색을 변경하는 예제입니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body style="background-color:#33CCFF">
    <h1 style="background-color:white">
      style 속성을 이용한 배경색 변경
    </h1>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126269404-61badcdf-d470-4ac9-9b0c-c87c85e3f897.png)

> <h3>자색 변경(color)</h3>

다음 예제는 style 속성을 이용하여 글자색을 변경하는 예제입니다.

``` html
<h1 style="color:maroon">
  style 속성을 이용한 글자색 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269516-cee40c4c-0326-47cd-87b2-dc7c7159124c.png)

> <h3>글자 크기 변경(font-size)</h3>

다음 예제는 style 속성을 이용하여 글자 크기를 변경하는 예제입니다.

``` html
<h1 style="font-size:250%">
  style 속성을 이용한 글자 크기 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269643-a8f38de0-56b6-4b2e-bb53-81274a3cd936.png)

> <h3>문단 정렬 변경(text-align)</h3>

다음 예제는 style 속성을 이용하여 문단 정렬을 변경하는 예제입니다.

속성값은 'left', 'center', 'right', 'justify'를 사용할 수 있습니다.

+ justify : 신문이나 잡지와 같이 길이를 유동적으로 조절해서 각 줄의 너비를 똑같이 맞추는 정렬법(양쪽 정렬)

``` html
<h1 style="text-align:center">
  style 속성을 이용한 문단 정렬 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269845-c6e7ee47-deb3-43fd-be67-a728ee05abba.png)

> <h3>여러 스타일의 설정</h3>

style 속성을 이용하여 여러 CSS 스타일을 한 번에 적용할 수 있습니다.

style 속성값에 사용되는 CSS 속성(property)과 속성값들은 세미콜론(;)을 이용하여 구분합니다.

CSS 속성을 하나만 사용할 때나, 여러 개의 CSS 속성 중 맨 마지막 CSS 속성은 세미콜론(;)을 생략할 수 있습니다.

``` html
<body style="background-color:#33CCFF">
	<h1 style="background-color:white; color:maroon; text-align:center; font-size:150%">
		style 속성을 이용하여 한 번에 스타일링 하기!
	</h1>
</body>
```

## HTML 색

> <h3>HTML 색(Color) 표현</h3>

HTML에서 색을 표현하는 방법은 다음과 같이 세 가지 방법이 있습니다. 

1. 색상 이름으로 표현
2. RGB 색상값으로 표현
3. 16진수 색상값으로 표현

> <h3>색상 이름으로 표현</h3>

W3C에서 정의한 16개의 HTML4 표준 색상 이름은 아래와 같습니다.

![image](https://user-images.githubusercontent.com/43658658/126275486-4871d045-d846-4f8e-afb4-9bfe1d611461.png)

현재는 주요 브라우저가 140개의 색상 이름을 모두 지원하고 있습니다.

색상 이름은 대소문자를 구분하지 않습니다.

``` html
<h1 style="color:blue">색상 이름으로 표현된 파란색</h1>
<h1 style="color:green">색상 이름으로 표현된 녹색</h1>
<h1 style="color:silver">색상 이름으로 표현된 은색</h1>
<h1 style="color:teal">색상 이름으로 표현된 청록색</h1>
<h1 style="color:red">색상 이름으로 표현된 빨간색</h1>
```

> <h3>RGB 색상값으로 표현</h3>

모니터나 스크린은 빨간색(Red), 녹색(Green), 파란색(Blue)을 혼합하여 색을 표현합니다.

HTML에서도 위와 같이 세 가지 색을 가지고 색을 표현하는 RGB 색상을 사용합니다.

RGB 색상의 기본색(Red, Green, Blue)은 각각 0부터 255까지의 범위를 가집니다.

``` html
<h1 style="color:rgb(0,0,255)">RGB 색상값으로 표현된 파란색</h1>
<h1 style="color:rgb(0,128,0)">RGB 색상값으로 표현된 녹색</h1>
<h1 style="color:rgb(192,192,192)">RGB 색상값으로 표현된 은색</h1>
<h1 style="color:rgb(0,128,128)">RGB 색상값으로 표현된 청록색</h1>
<h1 style="color:rgb(255,0,0)">RGB 색상값으로 표현된 빨간색</h1>
```

> <h3>16진수 색상값으로 표현</h3>

16진수 색상값은 RGB 색상값을 각각 16진수로 변환한 것입니다.

따라서 각각의 기본색(Red, Green, Blue)은 각각 00부터 FF까지의 범위를 가집니다.

예를 들면, 빨간색을 나타내는 RGB 색상값인 rgb(255,0,0)은 16진수 색상값으로는 #FF0000이 되는 것입니다.

``` html
<h1 style="color:#0000FF">16진수 색상값으로 표현된 파란색</h1>
<h1 style="color:#008000">16진수 색상값으로 표현된 녹색</h1>
<h1 style="color:#C0C0C0">16진수 색상값으로 표현된 은색</h1>
<h1 style="color:#008080">16진수 색상값으로 표현된 청록색</h1>
<h1 style="color:#FF0000">16진수 색상값으로 표현된 빨간색</h1>
```

## HTML 배경

> <h3>HTML 배경(Background)</h3>

HTML 문서의 기본 배경(background)은 흰색입니다.

또한, HTML 요소들도 각자 자신만의 배경을 가지고 있습니다.

HTML에서는 이러한 배경을 다음과 같이 변경할 수 있습니다.

1. 배경을 다른 색으로 변경
2. 배경을 다른 이미지로 변경

> <h3>배경색을 다른 색으로 변경</h3>

HTML5 이전까지는 bgcolor 속성을 이용하여 HTML 요소의 배경색을 다른 색으로 변경할 수 있었습니다.

하지만 HTML5부터는 bgcolor 속성을 더 이상 지원하지 않으며, CSS를 이용하여 배경색을 변경하도록 하고 있습니다.

다음 예제는 CSS 스타일을 이용하여 배경색을 다른 색으로 변경하는 예제입니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body>
    <h1>배경으로 이미지 삽입하기</h1>
    <p>단락의 배경색은 어떻게 바뀌었을까?</p>
  </body>
</html>
<style>
  body { background-color: lightblue; }
  h1 { background-color: rgb(255, 128, 0); }
  p { background-color: #FFFFCC; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/126272655-6aafd2e0-6306-4851-992d-dab2ab0f35a8.png)

+ CSS의 background 속성을 이용하면, 더욱 다양한 방법으로 배경색을 설정할 수 있습니다.

> <h3>배경을 다른 이미지로 변경</h3>

background 속성을 이용하면 HTML 요소의 배경을 이미지(image)로 설정할 수 있습니다.

`<태그이름 background="이미지주소">`

``` html
<body background="/examples/images/img_background_good.png">
	<h1>배경으로 이미지 삽입하기</h1>
</body>
```

![image](https://user-images.githubusercontent.com/43658658/126272843-a8a43fb5-dbf9-4f2c-876a-bfa126074005.png)

+ 배경으로 이미지를 사용하면 웹 페이지의 로딩시간이 증가하게 됩니다. 따라서 보통은 작은 사이즈의 이미지를 패턴(pattern)으로 만들어 배경 이미지로 반복 설정합니다.

## HTML 링크(Link)

오늘날 웹 페이지에는 다른 페이지나 다른 사이트로 연결되는 수많은 하이퍼 링크(hyperlink)가 존재합니다.

이러한 하이퍼 링크를 간단히 링크(link)라고도 부르며, HTML에서는 `<a>`태그로 표현합니다.

`<a href="링크주소">단어</a>`

위 문법으로 하이퍼링크를 걸면 '단어'에 하이퍼링크가 걸리게 된다.

`<a>`태그의 href 속성은 링크를 클릭하면 연결할 페이지나 사이트의 URL 주소를 명시합니다.

`<a>`태그는 텍스트나 단락, 이미지 등 다양한 HTML 요소에 사용할 수 있습니다.

``` html
<h1>a태그로 링크 걸기</h1>
<a href="/html/intro">
	<h2>이 링크를 클릭해 보세요!</h2>
</a>
```

> <h3>target 속성</h3>

`<a>`태그의 target 속성은 링크로 연결된 문서를 어디에서 열지를 명시합니다.


<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>target 속성값</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>_blank</td>
			<td>링크로 연결된 문서를 새 창이나 새 탭에서 오픈.</td>
		</tr>
		<tr>
			<td>_self</td>
			<td>링크로 연결된 문서를 현재 프레임(frame)에서 오픈. (기본설정)</td>
		</tr>
		<tr>
			<td>_parent</td>
			<td>링크로 연결된 문서를 부모 프레임(frame)에서 오픈.</td>
		</tr>
		<tr>
			<td>_top</td>
			<td>링크로 연결된 문서를 현재 창의 가장 상위 프레임(frame)에서 오픈.</td>
		</tr>
		<tr>
			<td>프레임(frame) 이름</td>
			<td>링크로 연결된 문서를 지정된 프레임(frame)에서 오픈.</td>
		</tr>
	</tbody>
</table>


``` html
<h1>a태그의 target 속성값</h1>
<h2><a href="/html/intro" target="_blank">blank</a></h2>
<h2><a href="/html/intro" target="_self">self</a></h2>
<h2><a href="/html/intro" target="_parent">parent</a></h2>
<h2><a href="/html/intro" target="_top">top</a></h2>
<h2><a href="/html/intro" target="myframe">myframe</a></h2>
<iframe name="myframe" style="width:50%; height: 330px"></iframe>
```

![image](https://user-images.githubusercontent.com/43658658/126274236-c5725994-6299-41d1-954d-34755cb8fd3e.png)

> <h3>링크의 상태(state)</h3>

HTML 링크의 상태는 다음과 같이 네 가지로 구분할 수 있습니다.


<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>링크의 상태</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>link</td>
			<td>아직 한 번도 방문한 적이 없는 상태 (기본설정)</td>
		</tr>
		<tr>
			<td>visited</td>
			<td>한 번이라도 방문한 적이 있는 상태</td>
		</tr>
		<tr>
			<td>hover</td>
			<td>링크 위에 마우스를 올려놓은 상태</td>
		</tr>
		<tr>
			<td>active</td>
			<td>링크를 마우스로 누르고 있는 상태</td>
		</tr>
	</tbody>
</table>


웹 브라우저에서 링크가 연결되어 있는 텍스트의 색상은 다음과 같습니다.

- 기본적으로 링크가 걸린 텍스트는 밑줄에, 텍스트 색상이 파란색으로 변경됩니다.
- visited 상태의 링크는 밑줄에, 텍스트 색상이 보라색으로 변경됩니다.
- active 상태의 링크는 밑줄에, 텍스트 색상이 빨간색으로 변경됩니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
    <style>
      a:link { color: teal; }
      a:visited { color: maroon; }
      a:hover { color: yellow; }
      a:active { color: red; }
    </style>
  </head>
  <body>
    <h1>링크의 상태</h1>
    <h2><a href="/html/intro">링크의 상태에 따라 스타일을 다르게 설정합니다!</a></h2>
  </body>
</html>
```

> <h3>페이지 책갈피</h3>

`<a>`태그의 name 속성을 이용하면 간단한 책갈피를 만들 수 있습니다.

우선 책갈피를 통해 가고 싶은 위치에 `<a>`태그를 만들고 name 속성을 작성합니다.

그다음에 작성한 name 속성값을 이용하여 다른 `<a>`태그에서 링크를 걸면 됩니다.

``` html
<a href="#bookmark"><p>제목 3으로 갑시다!!!</p></a>

...

<h2><a name="bookmark"></a>제목 3</h2>
```

## HTML 이미지(Image)

이미지(image)란 2차원 평면 위에 그려진 시각적 요소를 의미합니다.

오늘날 웹 페이지에는 이러한 이미지가 매우 중요한 요소의 하나로 자리 잡고 있습니다.

웹 페이지에서 주로 사용되는 이미지의 종류는 다음과 같습니다.

1. JPEG 이미지
2. GIF 이미지
3. PNG 이미지

> <h3>이미지의 삽입</h3>

HTML 문서에 이미지를 삽입할 때는 `<img>`태그를 사용합니다.

`<img>`태그는 종료 태그가 없는 빈 태그(empty tag)이며, 다음과 같은 문법으로 사용됩니다.

`<img src="이미지주소" alt="대체문자열">`

src 속성은 이미지가 저장된 주소의 URL 주소를 명시합니다.

alt 속성으로 이미지가 로딩될 수 없는 상황에서 이미지 대신 나타날 문자열을 설정할 수 있습니다.

> <h3>이미지의 크기(width, height) 설정</h3>

HTML에서는 style 속성을 사용하여 이미지의 크기를 설정할 수 있습니다.

또한, width 속성과 height 속성을 이용하면, 이미지의 너비와 높이를 각각 픽셀(pixel) 단위로 설정할 수도 있습니다.

위의 두 가지 방법 모두 HTML5 표준에는 적합한 방법이지만, 나중에 배우게 될 CSS를 이용한 내부 스타일 시트나 외부 스타일 시트와 상관없이 이미지의 원래 크기를 유지하려면 style 속성을 사용하는 것이 좋습니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
    <style>
      img {
        width: 100%;
        border: 1px solid black;
      }
    </style>
  </head>
  <body>
    <h1>이미지의 크기 설정</h1>
    <img src="/examples/images/img_flag.png" alt="html size" width="320" height="214">
    <img src="/examples/images/img_flag.png" alt="style size" style="width:320px; height:214px">
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126277306-4eecc29c-8f59-44af-9955-c9d526a8bc1c.png)

> <h3>이미지의 테두리(border) 설정</h3>

border 속성을 사용하여 이미지의 테두리 사용 여부와 굵기를 설정할 수 있습니다.

``` html
<img src="/examples/images/img_flag.png" alt="이미지 테두리" style="width:320px; height:214px; border: 3px solid black">
```

> <h3>이미지에 링크(link) 설정</h3>

이미지에 `<a>`태그를 이용하여 링크를 설정할 수 있습니다.

``` html
<a href="/html/intro" target="_blank">
    <img src="/examples/images/img_flag.png" alt="flag" style="width:320px; height:214px">
</a>
```

> <h3>이미지 맵 만들기</h3>

HTML에서는 `<map>`태그를 이용하여 이미지 맵(image map)을 제작할 수 있습니다.

이미지 맵(image map)이란 이미지의 일부를 클릭할 수 있도록 만들어서 버튼처럼 사용하는 기능을 의미합니다.

`<img>`태그의 usemap 속성을 `<map>`태그의 name 속성과 연결하면 이미지와 맵사이의 관계가 설정됩니다.

`<map>`태그는 하나 이상의 `<area>`태그를 가지며, 이 `<area>`태그가 바로 버튼과 같은 역할을 합니다.

``` html
<h1>이미지 맵 만들기</h1>
<img src="/examples/images/img_imagemap.jpg" alt="진실혹은거짓" usemap="#vending" style="width:320px; height:240px" />
<map name="vending"> 
	<area  shape="rect" coords="90,60,180,130" alt="거짓" href="https://ko.wikipedia.org/wiki/%EA%B1%B0%EC%A7%93%EB%A7%90">
	<area  shape="rect" coords="210,200,70,130" alt="진실" href="https://ko.wikipedia.org/wiki/%EC%A7%84%EC%8B%A4">
</map>
<p>표지판을 눌러보세요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/126277931-57239279-4daf-4233-92da-4e6e829d8077.png)

img를 map으로 만들고 map내의 area를 생성합니다.

area의 모양(shape)은 직사각형(rect)입니다.

좌표의 양끝점을 `<area>`태그의 coords 속성에 "x1, y1, x2, y2" 형식의 px단위로 적습니다(이미지의 좌측 상단이 "0, 0"이 됩니다).

하이퍼링크 URL을 입력하여 좌표 범위를 클릭시 해당 URL로 이동하도록 합니다.

