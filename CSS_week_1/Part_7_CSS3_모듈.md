# Part 7. CSS3 모듈

+ [CSS3 개요](#CSS3 개요)
+ [CSS3 선택자](#CSS3 선택자)
+ [벤더 프리픽스(Vendor Prefix)](#벤더-프리픽스Vendor-Prefix)
+ [CSS3 원형 그래디언트](#CSS3-원형-그래디언트)
+ 

## CSS3 개요

CSS3는 이전 버전 CSS와 완전히 호환되는 CSS의 최신 표준 권고안입니다.

> <h3>CSS3 변경사항</h3>

CSS3에서 새롭게 추가되거나 변경된 대표적인 기능은 다음과 같습니다.

- 선택자(Selectors) Level 3

- 미디어 쿼리(Media Queries) Level 3

- 색(Color) Level 3

- 네임스페이스(Namespaces)

> <h3>CSS3 모듈(module)</h3>

CSS3는 새롭게 정의된 기능과 함께 이전 버전의 CSS 기능까지도 함께 포함하고 있는 모듈(module)이라는 것으로 구성됩니다.

CSS3를 구성하고 있는 주요 모듈은 다음과 같습니다.

 

- 선택자(Selectors)

- 박스 모델(Box Model)

- 배경(Backgrounds)

- 이미지(Image Values and Replaced Content)

- 텍스트 효과(Text Effects)

- 2D 변형(Transformations)

- 3D 변형(Transformations)

- 애니메이션(Animations)

- 다중 칼럼(Multiple Column) 레이아웃

- 사용자 인터페이스(User Interface)

## CSS3 선택자

> <h4>선택자(selectors) Level 3</h4>

CSS3에서 새롭게 정의된 선택자는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">선택자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>일반 동위 선택자</td>
			<td>해당&nbsp;요소와 동위 관계에 있으며, 문서의 위치에서 해당 요소보다&nbsp;뒤에 위치한 모든 특정 요소를&nbsp;선택함.</td>
		</tr>
		<tr>
			<td>[속성이름^=&quot;속성값&quot;] 선택자</td>
			<td>특정 속성의 속성값이 특정 문자열로 시작하는 요소를 선택함.</td>
		</tr>
		<tr>
			<td>[속성이름$=&quot;속성값&quot;] 선택자</td>
			<td>특정 속성의 속성값이 특정 문자열로 끝나는 요소를 선택함.</td>
		</tr>
		<tr>
			<td>[속성이름*=&quot;속성값&quot;] 선택자</td>
			<td>특정 속성의 속성값이 특정 문자열로 시작하는 하나의 단어로 된 요소를 선택함.</td>
		</tr>
		<tr>
			<td>:root</td>
			<td>문서의 루트(root) 요소를 선택함.</td>
		</tr>
		<tr>
			<td>:nth-child</td>
			<td>모든 자식(child) 요소들 중에서 앞에서부터 n번째에 위치한&nbsp;자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-last-child</td>
			<td>모든 자식(child) 요소들 중에서 뒤에서부터 n번째에 위치한&nbsp;자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-of-type</td>
			<td>모든 자식(child)&nbsp;요소들 중에서 n번째로&nbsp;등장하는 특정 타입의 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-last-of-type</td>
			<td>모든 자식(child)&nbsp;요소들 중에서 뒤에서부터&nbsp;n번째로 등장하는 특정 타입의 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:last-child</td>
			<td>모든 자식(child) 요소들 중에서 맨 마지막에 위치한&nbsp;자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:first-of-type</td>
			<td>모든 자식(child) 요소들 중에서 맨 처음으로 등장하는 특정&nbsp;타입의&nbsp;요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:last-of-type</td>
			<td>모든 자식(child)&nbsp;요소들 중에서 맨 마지막으로 등장하는 특정 타입의 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:only-child</td>
			<td>자식(child)&nbsp;요소를 단 하나만 가지는 모든 요소의 자식(child) 요소를 선택함.</td>
		</tr>
		<tr>
			<td>:only-of-type</td>
			<td>자식(child)&nbsp; 요소로 특정 타입의 요소를 단 하나만 가지는 모든 요소의 자식(child)&nbsp;요소를 선택함.</td>
		</tr>
		<tr>
			<td>:empty</td>
			<td>자식(child)&nbsp;요소를 전혀 가지고 있지 않은 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:target</td>
			<td>현재 활성화된 target 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:checked</td>
			<td>체크된(checked) 상태의 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:enabled</td>
			<td>사용할 수 있는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:disabled</td>
			<td>사용할 수 없는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:not(선택자)</td>
			<td>모든 선택자와 함께 사용할 수 있으며, 해당 선택자의 의미를 반대로 적용함.</td>
		</tr>
	</tbody>
</table>

## 벤더 프리픽스(Vendor Prefix)

세계적으로 가장 많이 사용되는 웹 브라우저에는 익스플로러, 크롬, 파이어폭스, 사파리, 오페라 등이 있습니다.

 

벤더 프리픽스(vendor prefix)란 이러한 주요 웹 브라우저 공급자가 새로운 실험적인 기능을 제공할 때 이전 버전의 웹 브라우저에 그 사실을 알려주기 위해 사용하는 접두사(prefix)를 의미합니다.

즉 아직 CSS 권고안에 포함되지 못한 기능이나, CSS 권고안에는 포함되어 있지만 아직 완벽하게 제정된 상태가 아닌 기능을 사용하고자 할 때 벤더 프리픽스를 사용하게 됩니다.

그렇게 하면 해당 기능이 포함되어 있지 않은 이전 버전의 웹 브라우저에서도 그 기능을 사용할 수 있게 됩니다.

> <h3>주요 웹 브라우저의 벤더 프리픽스(vendor prefix)</h3>

주요 웹 브라우저가 사용하고 있는 벤더 프리픽스는 다음과 같습니다.

- ie : -ms-
- chrome : -webkit-
- safari : -webkit-
- firefox : -moz-
- opera : -o-

## CSS3 색

> <h3>RGBA 색상값으로 표현</h3>

RGBA 색상값은 RGB 색상값에 알파 채널 값을 더한 색상값입니다.

 

알파 채널(alpha channel)이란 색상의 투명도를 나타내는 채널입니다.

알파 채널 값은 완전한 투명 상태인 0.0부터 투명도가 전혀 없는 1.0 사이의 값을 가집니다.

``` html
<style>
  body { 
    background-image: url("/examples/images/img_check_pattern.png");
    color: white;
  }
  #header_01 {background-color: rgba(0,255,0,0);}
  #header_02 {background-color: rgba(0,255,0,0.2);}
  #header_03 {background-color: rgba(0,255,0,0.4);}
  #header_04 {background-color: rgba(0,255,0,0.6);}
  #header_05 {background-color: rgba(0,255,0,0.8);}
  #header_06 {background-color: rgba(0,255,0,1);}
</style>
...
<h1 id="header_01">RGBA 색상값으로 표현된 녹색 : 알파 값 0.0</h1>
<h1 id="header_02">RGBA 색상값으로 표현된 녹색 : 알파 값 0.2</h1>
<h1 id="header_03">RGBA 색상값으로 표현된 녹색 : 알파 값 0.4</h1>
<h1 id="header_04">RGBA 색상값으로 표현된 녹색 : 알파 값 0.6</h1>
<h1 id="header_05">RGBA 색상값으로 표현된 녹색 : 알파 값 0.8</h1>
<h1 id="header_06">RGBA 색상값으로 표현된 녹색 : 알파 값 1.0</h1>
```

![image](https://user-images.githubusercontent.com/43658658/127942715-51bfa6d6-8da8-4d47-88b4-64a85f7d3ca4.png)

> <h3>HSL 색상값으로 표현</h3>

HSL 색상값은 빛의 삼원색으로 색을 표현하는 RGB 색상값과는 달리 색상, 채도, 명도를 사용해서 색을 표현합니다.

HSL 색상값에서 HSL은 각각 색상(Hue), 채도(Saturation), 명도(Lightness)를 의미합니다.

 

색상은 `0`부터 `360` 사이의 값을 가지며, 색상환(color wheel)의 각도를 나타냅니다.

색상 값이 `0 또는 360`이면 빨간색(red)이 되며, `120`이면 녹색(green), `240`이면 파란색(blue)이 됩니다.

채도는 `0%`부터 `100%` 사이의 값을 가지며, 색상의 연하고 짙은 정도를 나타냅니다.

채도 값이 `0%`면 회색이 되고, `100%`면 원래 색상이 됩니다.

명도는 `0%`부터 `100%` 사이의 값을 가지며, 색상의 밝고 어두운 정도를 나타냅니다.

명도 값이 `0%`면 검정색이 되고, `50%`면 원래 색상, `100%`면 흰색이 됩니다.

HSLA 색상값으로 표현이 가능합니다.

RGBA와 마찬가지로 알파 채널을 더한 색상값입니다.

`hsl(120, 100%, 50%, 0.2)`

> <h3>opacity 속성과 알파 채널과의 차이점</h3>

위에서 살펴본 opacity 속성과 알파 채널 모두 투명도를 조절한다는 공통점을 가지고 있습니다.

 

opacity 속성은 투명도를 설정했을 때 설정한 요소의 모든 자식(child) 요소까지 전부 같은 투명도로 설정합니다.

하지만 알파 채널은 투명도를 설정한 요소에만 투명도를 설정하는 차이점이 존재합니다.


![image](https://user-images.githubusercontent.com/43658658/127943018-fcb6aee5-277e-4b96-9a14-94858a5e2458.png)

## CSS3 선형 그래디언트
 

그래디언트(gradient)란 둘 이상의 색 사이의 색상 표현을 부드럽게 전환해주는 효과를 의미합니다.

CSS3 이전에는 그래디언트 효과를 나타내기 위해서 별도의 여러 이미지 파일을 사용해야만 했습니다.

하지만 CSS3에서는 웹 브라우저가 간단히 그래디언트 효과를 나타낼 수 있게 해줍니다.

> <h3>선형 그래디언트(linear gradient)</h3>

선형 그래디언트(linear gradient)는 적용된 HTML 요소에 선형으로 그래디언트(gradient) 효과를 적용시켜 줍니다.

선형 그래디언트를 만들기 위해서는 최소한 두 개 이상의 색상 지정점이 필요합니다.

선형 그래디언트(linear gradient)의 문법은 다음과 같습니다.

`background: linear-gradient(진행방향, 색상지정점1, 색상지정점2, ...);`

진행방향은 기본적으로 시작점을 의미합니다. right라고 적었다면 오른쪽에서 시작해 왼쪽 방향으로 가는 것을 의미합니다.

색상 지정점에는 그래디언트 효과로 그 사이의 색상 표현을 부드럽게 전환해주고 싶은 색상을 명시합니다.

가장 먼저 정의된 색상 지정점이 시작점이 되며, 그 후로는 마지막 지정점까지 차례대로 그래디언트 효과가 적용됩니다.

``` html
<style>
		#grad {
			height: 200px;
			background: red;
			background: -webkit-linear-gradient(left, red, orange, yellow, green, blue, indigo, purple);
			background: -moz-linear-gradient(left, red, orange, yellow, green, blue, indigo, purple);
			background: -o-linear-gradient(left, red, orange, yellow, green, blue, indigo, purple);
			background: linear-gradient(to right, red, orange, yellow, green, blue, indigo, purple);
		}
	</style>
```

![image](https://user-images.githubusercontent.com/43658658/127943269-3babd06a-f879-4485-b561-e491da85396e.png)

위의 예제에서 가장 먼저 나오는 background 속성은 linear-gradient 속성을 지원하지 않는 모든 브라우저를 위한 것입니다.

맨 마지막에 나오는 background 속성은 CSS 표준 문법으로 작성된 코드입니다.

이러한 CSS 표준 문법 코드는 벤더 프리픽스(vendor prefix)로 작성된 코드가 모두 나오고 난 후에 나와야만, 벤더 프리픽스가 포함된 코드가 정상적으로 동작할 수 있습니다.

> <h3>선형 그래디언트의 진행 방향 설정</h3>

CSS를 이용하면 선형 그래디언트 효과가 진행될 방향을 설정할 수 있습니다.

 

그래디언트의 진행 방향은 top, right, bottom, left 뿐만 아니라 대각선으로도 설정할 수 있습니다.

선형 그래디언트(linear gradient) 효과의 기본 진행 방향은 위쪽에서 아래쪽으로 진행됩니다.

 

다음 예제는 위쪽에서 아래쪽으로 진행되는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-linear-gradient(green, yellow);
        background: -moz-linear-gradient(green, yellow);
        background: -o-linear-gradient(green, yellow);
        background: linear-gradient(green, yellow);
    }
</style>
```

다음 예제는 오른쪽에서 왼쪽으로 진행되는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-linear-gradient(right, green, yellow);
        background: -moz-linear-gradient(right, green, yellow);
        background: -o-linear-gradient(right, green, yellow);
        background: linear-gradient(to left, green, yellow);
    }
</style>
```

다음 예제는 왼쪽 아래에서 오른쪽 위로 진행되는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-linear-gradient(left bottom, green, yellow);
        background: -moz-linear-gradient(left bottom, green, yellow);
        background: -o-linear-gradient(left bottom, green, yellow);
        background: linear-gradient(to top right, green, yellow);
    }
</style>
```

선형 그래디언트 효과의 진행 방향을 각도로 명시하여 설정할 수도 있습니다.

 

기준 각도인 0도는 아래쪽에서 위쪽으로의 진행을 의미합니다.

각도가 양수일 때는 기준 각도를 중심으로 시계방향으로 회전하며, 음수일 때는 반시계방향으로 회전합니다.

 

다음 예제는 225도의 진행 방향을 가지는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-linear-gradient(225deg, green, yellow);
        background: -moz-linear-gradient(225deg, green, yellow);
        background: -o-linear-gradient(225deg, green, yellow);
        background: linear-gradient(225deg, green, yellow);
    }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127943760-48ab356d-862f-4426-80e7-2f1f0f6778bf.png)

> <h3>선형 그래디언트의 투명도 설정</h3>

CSS3에서는 그래디언트의 투명도를 지원하며, 지정된 색상이 서서히 사라지는 효과를 사용할 수 있습니다.

 

그래디언트에 투명도를 추가할 때에는 RGBA 색상값을 사용하면 됩니다.

RGBA 색상값의 알파 채널 값은 완전한 투명 상태인 0.0부터 투명도가 전혀 없는 1.0 사이의 값을 가집니다.

 

다음 예제는 왼쪽에서 오른쪽으로 서서히 사라지는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-linear-gradient(left, rgba(0,255,0,1), rgba(0,255,0,0));
        background: -moz-linear-gradient(left, rgba(0,255,0,1), rgba(0,255,0,0));
        background: -o-linear-gradient(left, rgba(0,255,0,1), rgba(0,255,0,0));
        background: linear-gradient(to right, rgba(0,255,0,1), rgba(0,255,0,0));
    }
</style>
```

> <h3>repeating-linear-gradient 메소드</h3>

repeating-linear-gradient 메소드는 선형 그래디언트 효과가 계속 반복되도록 설정합니다.


다음 예제는 150도의 진행 방향을 가지고 반복되는 선형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: green;
        background: -webkit-repeating-linear-gradient(150deg, red, white 10%, blue 20%);
        background: -moz-repeating-linear-gradient(150deg, red, white 10%, blue 20%);
        background: -o-repeating-linear-gradient(150deg, red, white 10%, blue 20%);
        background: repeating-linear-gradient(150deg, red, white 10%, blue 20%);
    }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127944086-03187574-645e-40e9-bf6a-3c90d31cfa8b.png)

## CSS3 원형 그래디언트
 
CSS3에서는 그래디언트 효과를 선형뿐만 아니라 원형으로도 나타낼 수 있습니다.

> <h3>원형 그래디언트(radial gradient)</h3>

원형 그래디언트(radial gradient)는 적용된 HTML 요소에 원형으로 그래디언트(gradient) 효과를 적용시켜 줍니다.

원형 그래디언트를 만들기 위해서는 최소한 두 개 이상의 색상 지정점이 필요합니다.

원형 그래디언트(radial gradient)의 문법은 다음과 같습니다.

``` html
background: radial-gradient(모양 크기 at 중심점, 색상지정점1, 색상지정점2, ...);
```

원형 그래디언트는 기본적으로 모양은 ellipse(타원), 크기는 farthest-corner, 중심좌표는 center로 설정됩니다.

``` html
<style>
    #grad {
        background: red;
        background: -webkit-radial-gradient(red, orange, yellow, green, blue, indigo, purple);
        background: -moz-radial-gradient(red, orange, yellow, green, blue, indigo, purple);
        background: -o-radial-gradient(red, orange, yellow, green, blue, indigo, purple);
        background: radial-gradient(red, orange, yellow, green, blue, indigo, purple);
    }
</style>
```

> <h3>색상 지정점 사이의 간격 조절</h3>

CSS를 이용하면 원형 그래디언트에서 색상 지정점 사이의 간격을 조절할 수 있습니다.


다음 예제는 색상 지정점 사이의 간격을 다르게 설정한 원형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: red;
        background: -webkit-radial-gradient(red 5%, yellow 20%, orange 50%);
        background: -moz-radial-gradient(red 5%, yellow 20%, orange 50%);
        background: -o-radial-gradient(red 5%, yellow 20%, orange 50%);
        background: radial-gradient(red 5%, yellow 20%, orange 50%);
    }
</style>
```

> <h3>원형 그래디언트의 모양 설정</h3>

CSS를 이용하면 원형 그래디언트의 모양을 타원이 아닌 원으로도 설정할 수 있습니다.

다음 예제는 원 모양을 가지는 원형 그래디언트 예제입니다.

``` html
<style>
    #grad {
        background: red;
        background: -webkit-radial-gradient(circle, red, yellow, orange);
        background: -moz-radial-gradient(circle, red, yellow, orange);
        background: -o-radial-gradient(circle, red, yellow, orange);
        background: radial-gradient(circle, red, yellow, orange);
    }
</style>
```

