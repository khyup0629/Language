# Part 3. HTML 기본 요소

+ [HTML 스타일(Style)](#HTML-스타일Style)
+ [HTML 색](#HTML-색)
+ 

## HTML 스타일(Style)

HTML 요소의 style 속성(attribute)을 이용하면 CSS 스타일을 HTML 요소에 직접 설정할 수 있습니다.

하지만 이러한 style 속성을 이용한 방법은 오직 단 하나의 HTML 요소에만 스타일을 적용할 수 있습니다

`<태그이름 style="속성이름:속성값">`

> 배경색 변경(background-color)

다음 예제는 style 속성을 이용하여 배경색을 변경하는 예제입니다.

```
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

> 글자색 변경(color)

다음 예제는 style 속성을 이용하여 글자색을 변경하는 예제입니다.

```
<h1 style="color:maroon">
  style 속성을 이용한 글자색 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269516-cee40c4c-0326-47cd-87b2-dc7c7159124c.png)

> 글자 크기 변경(font-size)

다음 예제는 style 속성을 이용하여 글자 크기를 변경하는 예제입니다.

```
<h1 style="font-size:250%">
  style 속성을 이용한 글자 크기 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269643-a8f38de0-56b6-4b2e-bb53-81274a3cd936.png)

> 문단 정렬 변경(text-align)

다음 예제는 style 속성을 이용하여 문단 정렬을 변경하는 예제입니다.

속성값은 'left', 'center', 'right', 'justify'를 사용할 수 있습니다.

+ justify : 신문이나 잡지와 같이 길이를 유동적으로 조절해서 각 줄의 너비를 똑같이 맞추는 정렬법(양쪽 정렬)

```
<h1 style="text-align:center">
  style 속성을 이용한 문단 정렬 변경
</h1>
```

![image](https://user-images.githubusercontent.com/43658658/126269845-c6e7ee47-deb3-43fd-be67-a728ee05abba.png)

> 여러 스타일의 설정

style 속성을 이용하여 여러 CSS 스타일을 한 번에 적용할 수 있습니다.

style 속성값에 사용되는 CSS 속성(property)과 속성값들은 세미콜론(;)을 이용하여 구분합니다.

CSS 속성을 하나만 사용할 때나, 여러 개의 CSS 속성 중 맨 마지막 CSS 속성은 세미콜론(;)을 생략할 수 있습니다.

```
<body style="background-color:#33CCFF">
	<h1 style="background-color:white; color:maroon; text-align:center; font-size:150%">
		style 속성을 이용하여 한 번에 스타일링 하기!
	</h1>
</body>
```

## HTML 색

> HTML 색(Color) 표현

HTML에서 색을 표현하는 방법은 다음과 같이 세 가지 방법이 있습니다. 

1. 색상 이름으로 표현
2. RGB 색상값으로 표현
3. 16진수 색상값으로 표현

> 색상 이름으로 표현

W3C에서 정의한 16개의 HTML4 표준 색상 이름은 아래와 같습니다.

```
<table class="tb-2" summary="">
	<thead>
	</thead>
	<tbody>
		<tr>
			<td style="width: 50%; background-color: aqua;"><span style="color:#000000;">aqua</span></td>
			<td style="text-align: center; background-color: black;"><span style="color:#FFFFFF;">black</span></td>
		</tr>
		<tr>
			<td style="background-color: blue;"><span style="color:#FFFFFF;">blue</span></td>
			<td style="text-align: center; background-color: fuchsia;"><span style="color:#FFFFFF;">fuchsia</span></td>
		</tr>
		<tr>
			<td style="background-color: gray;"><span style="color:#FFFFFF;">gray</span></td>
			<td style="text-align: center; background-color: green;"><span style="color:#FFFFFF;">green</span></td>
		</tr>
		<tr>
			<td style="background-color: lime;"><span style="color:#FFFFFF;">lime</span></td>
			<td style="text-align: center; background-color: maroon;"><span style="color:#FFFFFF;">maroon</span></td>
		</tr>
		<tr>
			<td style="background-color: navy;"><span style="color:#FFFFFF;">navy</span></td>
			<td style="text-align: center; background-color: olive;"><span style="color:#FFFFFF;">olive</span></td>
		</tr>
		<tr>
			<td style="background-color: purple;"><span style="color:#FFFFFF;">purple</span></td>
			<td style="text-align: center; background-color: red;"><span style="color:#FFFFFF;">red</span></td>
		</tr>
		<tr>
			<td style="background-color: silver;"><span style="color:#FFFFFF;">silver</span></td>
			<td style="text-align: center; background-color: teal;"><span style="color:#FFFFFF;">teal</span></td>
		</tr>
		<tr>
			<td style="background-color: white;">white</td>
			<td style="text-align: center; background-color: yellow;">yellow</td>
		</tr>
	</tbody>
</table>
```

현재는 주요 브라우저가 140개의 색상 이름을 모두 지원하고 있습니다.

색상 이름은 대소문자를 구분하지 않습니다.

```
<h1 style="color:blue">색상 이름으로 표현된 파란색</h1>
<h1 style="color:green">색상 이름으로 표현된 녹색</h1>
<h1 style="color:silver">색상 이름으로 표현된 은색</h1>
<h1 style="color:teal">색상 이름으로 표현된 청록색</h1>
<h1 style="color:red">색상 이름으로 표현된 빨간색</h1>
```

> <h3 style="color:black">RGB 색상값으로 표현</h3>

모니터나 스크린은 빨간색(Red), 녹색(Green), 파란색(Blue)을 혼합하여 색을 표현합니다.

HTML에서도 위와 같이 세 가지 색을 가지고 색을 표현하는 RGB 색상을 사용합니다.

RGB 색상의 기본색(Red, Green, Blue)은 각각 0부터 255까지의 범위를 가집니다.

```
<h1 style="color:rgb(0,0,255)">RGB 색상값으로 표현된 파란색</h1>
<h1 style="color:rgb(0,128,0)">RGB 색상값으로 표현된 녹색</h1>
<h1 style="color:rgb(192,192,192)">RGB 색상값으로 표현된 은색</h1>
<h1 style="color:rgb(0,128,128)">RGB 색상값으로 표현된 청록색</h1>
<h1 style="color:rgb(255,0,0)">RGB 색상값으로 표현된 빨간색</h1>
```

> 16진수 색상값으로 표현

16진수 색상값은 RGB 색상값을 각각 16진수로 변환한 것입니다.

따라서 각각의 기본색(Red, Green, Blue)은 각각 00부터 FF까지의 범위를 가집니다.

예를 들면, 빨간색을 나타내는 RGB 색상값인 rgb(255,0,0)은 16진수 색상값으로는 #FF0000이 되는 것입니다.

```
<h1 style="color:#0000FF">16진수 색상값으로 표현된 파란색</h1>
<h1 style="color:#008000">16진수 색상값으로 표현된 녹색</h1>
<h1 style="color:#C0C0C0">16진수 색상값으로 표현된 은색</h1>
<h1 style="color:#008080">16진수 색상값으로 표현된 청록색</h1>
<h1 style="color:#FF0000">16진수 색상값으로 표현된 빨간색</h1>
```

