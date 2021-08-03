# Part 7. CSS3 모듈

+ [CSS3 개요](#CSS3-개요)
+ [CSS3 선택자](#CSS3-선택자)
+ [벤더 프리픽스(Vendor Prefix)](#벤더-프리픽스Vendor-Prefix)
+ [CSS3 선형 그래디언트](#CSS3-선형-그래디언트)
+ [CSS3 원형 그래디언트](#CSS3-원형-그래디언트)
+ [CSS3 그림자 효과](#CSS3-그림자-효과)
+ [CSS3 배경](#CSS3-배경)
+ [CSS3 테두리](#CSS3-테두리)
+ [CSS3 텍스트](#CSS3-텍스트)
+ [CSS3 웹 글꼴](#CSS3-웹-글꼴)

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

> <h3>원형 그래디언트의 크기 설정</h3>

CSS를 이용하면 원형 그래디언트의 크기를 설정할 수 있습니다.

이때 크기를 나타내기 위해 사용할 수 있는 매개변수는 다음과 같습니다.

 

- closest-side : 원형 그래디언트의 크기가 가장 가까운 면에 닿을 만큼의 크기로 설정됩니다.

- farthest-side : 원형 그래디언트의 크기가 가장 먼 면에 닿을 만큼의 크기로 설정됩니다. 

따라서 가까운 면에서는 그래디언트의 일부분이 화면을 넘을 것입니다.

- closest-corner : 원형 그래디언트의 크기가 가장 가까운 모서리에 닿을 만큼의 크기로 설정됩니다.

- farthest-corner : 원형 그래디언트의 크기가 가장 먼 모서리에 닿을 만큼의 크기로 설정됩니다.

이 크기가 기본 설정이며, 가까운 모서리에서는 그래디언트의 일부분이 화면을 넘을 것입니다.

 

다음 예제는 다양하게 크기를 조절한 원형 그래디언트 예제입니다.

``` html
<style>
	div {
		height: 300px;
		width: 300px;
	}
	#grad_01 {
		background: red;
		background: -webkit-radial-gradient(35% 35%, closet-side, red, yellow, orange);
		background: -moz-radial-gradient(35% 35%, closet-side, red, yellow, orange);
		background: -o-radial-gradient(35% 35%, closet-side, red, yellow, orange);
		background: radial-gradient(closest-side at 35% 35%, red, yellow, orange);
	}
	#grad_02 {
		background: red;
		background: -webkit-radial-gradient(35% 35%, farthest-side, red, yellow, orange);
		background: -moz-radial-gradient(35% 35%, farthest-side, red, yellow, orange);
		background: -o-radial-gradient(35% 35%, farthest-side, red, yellow, orange);
		background: radial-gradient(farthest-side at 35% 35%, red, yellow, orange);
	}
	#grad_03 {
		background: red;
		background: -webkit-radial-gradient(35% 35%, closet-corner, red, yellow, orange);
		background: -moz-radial-gradient(35% 35%, closet-corner, red, yellow, orange);
		background: -o-radial-gradient(35% 35%, closet-corner, red, yellow, orange);
		background: radial-gradient(closest-corner at 35% 35%, red, yellow, orange);
	}
	#grad_04 {
		background: red;
		background: -webkit-radial-gradient(35% 35%, farthest-corner, red, yellow, orange);
		background: -moz-radial-gradient(35% 35%, farthest-corner, red, yellow, orange);
		background: -o-radial-gradient(35% 35%, farthest-corner, red, yellow, orange);
		background: radial-gradient(farthest-corner at 35% 35%, red, yellow, orange);
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127969841-1aa5f7f3-7968-4d3e-ad01-abca1ce5d272.png)

![image](https://user-images.githubusercontent.com/43658658/127969866-9b48cea7-ea9f-47d6-962c-3637ad0e69f9.png)

> <h3>repeating-radial-gradient() 메소드</h3>

repeating-radial-gradient() 메소드는 원형 그래디언트 효과가 계속 반복되도록 설정합니다.

다음 예제는 반복되는 원형 그래디언트 예제입니다.

``` html
<style>
	#grad {
		height: 300px;
		width: 300px;
		background: red;
		background: -webkit-repeating-radial-gradient(red, white 10%, blue 20%);
		background: -moz-repeating-radial-gradient(red, white 10%, blue 20%);
		background: -o-repeating-radial-gradient(red, white 10%, blue 20%);
		background: repeating-radial-gradient(red, white 10%, blue 20%);
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127970297-c55f61f6-5784-4278-9958-26b5738d4762.png)

## CSS3 그림자 효과
 
CSS3에서는 텍스트나 HTML 요소에 간단히 그림자 효과를 적용할 수 있습니다.
 
CSS3에서 사용할 수 있는 shadow 속성은 다음과 같습니다.

1. text-shadow

2. box-shadow

> <h3>text-shadow 속성</h3>

text-shadow 속성은 해당 텍스트에 간단히 그림자 효과를 적용해 줍니다.

text-shadow 속성의 문법은 다음과 같습니다.

``` html
text-shadow: 그림자의x축값 그림자의y축값 blur값 색상값;
```
 
그림자가 시작할 `x축`과 `y축`의 상대 위치를 명시하고, 그림자의 흐린 정도를 나타내는 `blur` 값을 명시합니다.

쉼표(,)를 통해 여러 그림자 효과를 중첩시킬 수도 있습니다.

다음 예제는 CSS3에서 텍스트에 적용할 수 있는 다양한 그림자 효과를 보여주는 예제입니다.

``` html
<style>
	#shadow_01 { text-shadow: 2px 2px; }
	#shadow_02 { text-shadow: 2px 2px orange; }
	#shadow_03 { text-shadow: 2px 2px 5px; }
	#shadow_04 { text-shadow: 0 0 3px red; }
	#shadow_05 { color: white; text-shadow: 1px 1px 2px black, 0 0 20px purple, 0 0 5px maroon; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127973479-704e66a7-1e87-4e75-8dde-008a9fa864a6.png)

> <h3>box-shadow 속성</h3>

box-shadow 속성은 해당 HTML 요소에 간단히 그림자 효과를 적용해 줍니다.

box-shadow 속성의 문법은 text-shadow 속성을 사용하는 문법과 같습니다.

``` html
box-shadow: 그림자의x축값 그림자의y축값 blur값 색상값;
```

그림자가 시작할 `x축`과 `y축`의 상대 위치를 명시하고, 그림자의 흐린 정도를 나타내는 `blur` 값을 명시합니다.
 

다음 예제는 CSS3에서 HTML 요소에 적용할 수 있는 다양한 그림자 효과를 보여주는 예제입니다.

``` html
<style>
	div {
		background-color: lightgray;
		height: 50px;
		width: 200px;
		margin: 30px;
	}
	#shadow_01 { box-shadow: 5px 5px; }
	#shadow_02 { box-shadow: 5px 5px orange; }
	#shadow_03 { box-shadow: 5px 5px 10px; }
	#shadow_04 { box-shadow: 0 0 15px red; }
	#shadow_05 { box-shadow: 5px 5px 10px black, 0 0 15px purple, 0 0 30px maroon; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127973577-69dc2184-e709-4df0-8535-1dc23557cb4b.png)

## CSS3 배경
 

CSS3에서는 배경의 크기뿐만 아니라 위치까지도 마음대로 설정할 수 있습니다.
  
또한, 하나의 HTML 요소에 여러 개의 배경 이미지를 적용할 수도 있습니다.
 

 
CSS3에서 새롭게 추가된 background 속성은 다음과 같습니다.

 

1. background-size

2. background-origin

3. background-clip

> <h3>background-size 속성</h3>

background-size 속성은 배경 이미지의 크기를 설정합니다.

CSS2에서 배경 이미지의 크기란 배경 이미지로 사용되는 이미지의 실제 크기와 같았습니다.

하지만 CSS3에서는 배경 이미지의 크기를 마음대로 설정할 수 있습니다.

background-size 속성의 문법은 다음과 같습니다.

``` html
background-size: 너비 높이 contain|cover ;
```

배경 이미지의 너비와 높이를 명시할 때는 CSS 크기 단위를 사용합니다.

CSS 크기 단위에는 픽셀 단위(px), 배수 단위(em), 백분율 단위(%) 등이 있습니다.

``` html
<style>
    #origin { background: url(/examples/images/img_monitor.png); background-repeat: no-repeat; }
    #resize {
        background: url(/examples/images/img_monitor.png);
        background-size: 200px 110px;
        background-repeat: no-repeat;
    }
</style>
```

background-size 속성값은 contain과 cover 중에서 선택할 수 있습니다.

 

속성값을 contain으로 설정하면 이미지의 비율은 유지하면서, 크기를 가능한 한 크게 조절합니다. 

단, 배경 이미지의 크기가 해당 요소의 내용(content) 영역을 넘지는 않습니다.

따라서 배경 이미지의 크기가 해당 요소의 크기보다 `항상 작거나 같게` 되며, 배경 이미지가 요소의 일부분은 가리지 못할 수도 있습니다.

 

속성값을 cover로 설정하면 이미지의 비율은 유지하면서, 요소의 모든 영역을 가리도록 크기를 조절합니다.

따라서 배경 이미지의 크기가 해당 요소의 크기보다 `항상 크거나 같게` 되며, 배경 이미지의 일부분이 잘릴 수도 있습니다.

``` html
<style>
	div { height:180px; width:220px; border:3px solid black; }
	#origin { background-image:url("/examples/images/img_monalisa.png");
	background-repeat:no-repeat; }
	#contain { background-image: url("/examples/images/img_monalisa.png");
	background-repeat:no-repeat; background-size:contain; }
	#cover { background-image: url("/examples/images/img_monalisa.png");
	background-repeat:no-repeat; background-size:cover; }
</style>
...
<h3>원래 크기</h3>
<div id="origin">
</div>

<h3>contain</h3>
<div id="contain">
</div>

<h3>cover</h3>
<div id="cover">
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127989309-38fba686-b83d-41d1-9994-48561a9dbcca.png)

![image](https://user-images.githubusercontent.com/43658658/127989342-9644cb9d-9ec7-4029-8516-88f55c91cd3e.png)

> <h3>background-origin 속성</h3>
 
background-origin 속성은 배경 이미지의 위치를 결정할 기준을 설정합니다.

이 속성은 다음과 같이 세 가지 속성값을 사용할 수 있습니다.

 

1. border-box : 배경 이미지를 테두리(border) 영역의 왼쪽 위에 맞춥니다.

2. padding-box : 기본 설정이며, 배경 이미지를 패딩(padding) 영역의 왼쪽 위에 맞춥니다.

3. content-box : 배경 이미지를 내용(content) 영역의 왼쪽 위에 맞춥니다.

 

다음 예제는 background-origin 속성값에 따른 차이점을 보여주는 예제입니다.

``` html
<style>
	div {
		border: 10px dotted orange;
		padding: 20px;
		margin-bottom: 20px;
	}
	h2{ color: red; }
	#origin {
		background: url(/examples/images/img_penguin.png);
		background-repeat: no-repeat;
  background-origin:padding-box; /* default */
	}
	#border {
		background: url(/examples/images/img_penguin.png);
		background-repeat: no-repeat;
		background-origin: border-box;
	}
	#content {
		background: url(/examples/images/img_penguin.png);
		background-repeat: no-repeat;
		background-origin: content-box;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127990246-a032e527-900a-489c-bff4-34cdf9bc8e02.png)

![image](https://user-images.githubusercontent.com/43658658/127990270-77fcb18b-3574-452e-a1b0-3442a94a3d83.png)

![image](https://user-images.githubusercontent.com/43658658/127990305-da379a61-d2a7-4f4e-abe2-90075c9f9ff1.png)

> <h3>background-clip 속성</h3>

background-clip 속성은 해당 요소의 배경을 어느 영역까지 설정할지를 결정합니다.

이 속성은 다음과 같이 세 가지 속성값을 사용할 수 있습니다.

 

1. border-box : 기본 설정이며, 배경을 테두리(border) 영역의 끝부분까지 설정합니다.

2. padding-box : 배경을 패딩(padding) 영역의 끝부분까지 설정합니다.

3. content-box : 배경을 내용(content) 영역까지만 설정합니다.

 

다음 예제는 background-clip 속성값에 따른 차이점을 보여주는 예제입니다.

``` html
<style>
	div { background-color:yellow; padding:20px; margin-bottom:20px;
          border:10px dashed black; height:250px; }
      h2 { color:deeppink; }
      #origin { background-clip:border-box; }
      #padding { background-clip:padding-box; }
      #content { background-clip:content-box; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127990821-3b4e4d96-c187-418e-bd12-8af0b94068e9.png)

![image](https://user-images.githubusercontent.com/43658658/127990846-e8868523-25db-4a6c-81de-1182090afb09.png)

![image](https://user-images.githubusercontent.com/43658658/127990869-7120ed89-5184-48e6-ad5c-cf7d2cd186de.png)

> <h3>여러 개의 배경 이미지 설정</h3>

background-image 속성을 사용하면 하나의 요소에 여러 개의 배경 이미지를 설정할 수 있습니다.

 

각각의 배경 이미지는 쉼표(,)로 구분되며, 스택(stack)처럼 차례대로 쌓이게 됩니다.

배경 이미지들 간의 순서는 가장 처음 명시된 이미지가 가장 위에 나타납니다.

즉 가장 나중에 명시된 이미지가 가장 아래쪽에 위치하게 됩니다.

 

다음 예제는 background-image 속성을 이용하여 여러 개의 배경 이미지를 설정하는 예제입니다.

``` html
<style>
	div {
		height: 200px;
		padding: 10px;
		margin-bottom: 20px;
	}
	#origin {
		background-image: url(/examples/images/img_man.png), url(/examples/images/img_background_good.png);
		background-position: top right, left;
  background-size:100px 233px, auto;
  background-repeat:no-repeat, repeat;
	}
</style>
...
<h1>background-image 속성을 이용한 여러 개의 배경 이미지 설정</h1>

<div id="origin">
	<h2>여러 개의 배경 이미지 설정</h2>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut quam tellus, pellentesque posuere urna sit amet, pellentesque tempus risus. Vivamus interdum dolor nec diam lacinia, luctus semper erat laoreet. Proin enim eros, pulvinar a tellus ac, porttitor pharetra turpis. Maecenas eros ex, venenatis a varius in, vestibulum vel tortor. Phasellus imperdiet imperdiet ex, nec accumsan leo tristique at. Praesent eget nisl posuere sem aliquet feugiat nec nec eros. Mauris commodo magna dictum, pretium diam non, interdum eros. Cras vitae mauris sit amet tortor cursus accumsan eget vel neque.</p>
</div>
```

## CSS3 테두리
 

CSS3에서는 테두리의 모서리를 둥글게 만들거나, 테두리에 이미지를 사용할 수 있습니다.

CSS3에서 새롭게 추가된 border 속성은 다음과 같습니다.

 

1. border-radius

2. border-top-left-radius

3. border-top-right-radius

4. border-bottom-right-radius

5. border-bottom-left-radius

6. border-image

7. border-image-source

8. border-image-slice

9. border-image-width

10. border-image-outset

11. border-image-repeat

> <h3>border-radius 속성</h3>

CSS3에서는 모든 HTML 요소에 border-radius 속성을 설정하여 모서리를 둥글게 만들 수 있습니다.

`border-radius: 10px;`

border-radius 속성은 실제로 다음 네 가지 속성의 스타일을 한 줄에 설정한 것입니다.

따라서 다음 속성들을 각각 사용하면 모서리별로 따로 스타일을 설정할 수 있습니다.

 

1. border-top-left-radius

2. border-top-right-radius

3. border-bottom-right-radius

4. border-bottom-left-radius

 

다음 예제는 모서리별로 다른 크기의 둥근 모서리를 설정하는 예제입니다.

``` html
<style>
    #p_01 {
        border-top-left-radius: 20px;
        border-top-right-radius: 40px;
        border-bottom-right-radius: 60px;
        border-bottom-left-radius: 80px;
    }
</style>
```

4개의 border-radius 속성값을 가질 때는 top-left, top-right, bottom-right, bottom-left 순으로 설정됩니다.

3개의 border-radius 속성값을 가질 때는 top-left, top-right와 bottom-left, bottom-right 순으로 설정됩니다.

2개의 border-radius 속성값을 가질 때는 top-left와 bottom-right, top-right와 bottom-left 순으로 설정됩니다.

1개의 border-radius 속성값을 가질 때는 border-radius 속성값이 모두 같은 값으로 설정됩니다.

> <h3>border-image 속성</h3>

CSS3에서는 요소를 둘러싸는 테두리(border)에 이미지를 사용할 수 있습니다.

 

border-image 속성은 다음과 같은 순서로 동작합니다.

 

1. 테두리(border)로 사용할 이미지를 결정합니다.

2. 이미지의 어느 부분을 자를 것인지 결정합니다.

3. 테두리 중간 부분의 이미지 처리를 반복되게 할지 아니면 그냥 늘릴지를 결정합니다.

 

우선 테두리로 사용할 이미지를 결정합니다.

![image](https://user-images.githubusercontent.com/43658658/127995040-6705def5-f7ce-41c0-a694-79db7747fc5e.png)

border-image 속성은 설정된 이미지를 바둑판처럼 9조각으로 나눕니다.

![image](https://user-images.githubusercontent.com/43658658/127995059-8a035a47-18a9-4401-8064-c71321e43fbf.png)

그 후에 top, right, bottom, left에 해당하는 영역의 처리를 반복되게 할지 아니면 그냥 늘릴지를 결정하게 됩니다.

border-image 속성을 설정하기 위해서는 반드시 border 속성이 먼저 설정되어 있어야 합니다.

border의 color 속성을 transparent로 설정합니다.

``` html
<style>
	#p_01 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 34 round;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 34 round;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 34 round;
		border-image: url(/examples/images/img_css3_pattern.png) 34 round;
	}
	#p_02 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 22 round;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 22 round;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 22 round;
		border-image: url(/examples/images/img_css3_pattern.png) 22 round;
	}
	#p_03 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 10 round;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 10 round;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 10 round;
		border-image: url(/examples/images/img_css3_pattern.png) 10 round;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127995888-84371e47-7c1f-40d4-b031-faa83f89832f.png)

다음 예제는 stretch 속성값을 사용하여 테두리 중간 부분의 처리를 늘리는 것으로 설정한 예제입니다.

``` html
style>
	#p_01 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 34% stretch;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 34% stretch;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 34% stretch;
		border-image: url(/examples/images/img_css3_pattern.png) 34% stretch;
	}
	#p_02 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 46% stretch;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 46% stretch;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 46% stretch;
		border-image: url(/examples/images/img_css3_pattern.png) 46% stretch;
	}
	#p_03 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 80% stretch;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 80% stretch;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 80% stretch;
		border-image: url(/examples/images/img_css3_pattern.png) 80% stretch;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127996189-1a064991-b4d5-421b-9fe5-297d89016bc5.png)

``` html
<style>
	#p_01 {
		padding: 20px;
		border: 20px solid transparent;
		-webkit-border-image: url(/examples/images/img_css3_pattern.png) 34 round stretch;
		-moz-border-image: url(/examples/images/img_css3_pattern.png) 34 round stretch;
		-o-border-image: url(/examples/images/img_css3_pattern.png) 34 round stretch;
		border-image: url(/examples/images/img_css3_pattern.png) 34 round stretch;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127997390-485a0bec-b408-467f-bf1b-5a019a99a6cf.png)

border-image 속성은 실제로 다음 5가지 속성의 스타일을 한 줄에 설정한 것입니다.

1. border-image-source	: 테두리로 사용할 이미지를 설정함.
2. border-image-slice	: 테두리로 사용할 이미지를 자르는 방법을 설정함.
3. border-image-width	: 테두리로 사용할 이미지의 너비를 설정함.
4. border-image-outset	: 테두리 영역 너머로 테두리로 사용할 이미지가 얼마만큼 넘어갈지를 설정함.
5. border-image-repeat	: 테두리로 사용할 이미지의 중간 부분의 처리를 반복으로 할지 늘릴지를 설정함.

## CSS3 텍스트
 

CSS3에서는 HTML 문서 내에 존재하는 텍스트를 더욱 다양한 방법으로 조작할 수 있게 되었습니다.

 
CSS3에서 새롭게 추가된 텍스트에 관한 속성은 다음과 같습니다.

1. text-overflow
2. word-wrap
3. word-break

> <h3>text-overflow 속성</h3>

text-overflow 속성은 콘텐츠(content) 영역을 벗어난 텍스트를 어떻게 표현할지를 설정합니다.

영역을 벗어난 텍스트 부분을 `자를 수`도 있으며, `생략 부호(…)`를 사용하여 표현할 수도 있습니다.

``` html
<style>
	p {
		border: 1px solid black;
		white-space: nowrap; 
		width: 250px;
		overflow: hidden;
	}
	#p_01 { text-overflow: clip; } /* 영역을 벗어나면 가린다. */
	#p_02 { text-overflow: ellipsis; } /* 영역을 벗어나면 ... 으로 표시 */
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127998250-f8a1edab-7b6e-432d-82d2-b6710135741a.png)

overflow 속성값을 `visible`로 설정하면, 사용자에게 콘텐츠 영역을 벗어나 생략된 텍스트까지 보여줄 수 있습니다.

``` html
<style>
	#p_01, #p_02 {
		border: 1px solid black;
		white-space: nowrap; 
		width: 200px;
		overflow: hidden;
	}
	#p_01 { text-overflow: clip; }
	#p_02 { text-overflow: ellipsis; }
	#p_01:hover, #p_02:hover { overflow: visible; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127998360-98879843-63a9-426a-8272-daa65042f3c3.png)

> <h3>word-wrap 속성</h3>

word-wrap 속성은 콘텐츠 영역을 벗어난 길이가 긴 단어를 다음 줄에 나누어 표현할 수 있도록 해줍니다.

``` html
<style>
	p {
		border: 1px solid black;
		width: 130px;
	}
	#p_01, #p_03 { word-wrap: break-word; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127998662-bf26109e-3530-4998-88f0-a6bafdd84610.png)

> <h3>word-break 속성</h3>

word-break 속성은 길이가 긴 단어를 나누어 표현해야 할 때 단어가 나뉘는 기준을 설정합니다.

단어를 `문자별`로 나눌 수도 있으며, `하이폰(-)`을 기준(`keep-all`)으로 나눌 수도 있습니다.

``` html
<style>
	p {
		border: 1px solid black;
		width: 130px;
	}
	#p_02 { word-wrap: break-word; }
	#p_03 { word-break: break-all; }
	#p_04 { word-break: keep-all; }
</style>
...
<p id="p_01">콘텐츠 영역을 벗어난 긴 단어단어단어단어단어단어가 어떻게 될까요?</p>
<p id="p_02">콘텐츠 영역을 벗어난 긴 wordwordwordwordwordword를 다음 줄에 나누어 표현합니다.</p>
<p id="p_03">콘텐츠 영역을 벗어난 긴 wordwordwordwordwordword를 다음 줄에 나누어 표현합니다.</p>
<p id="p_04">콘텐츠 영역을 벗어난 긴 word-word-word-word-word-word를 다음 줄에 나누어 표현합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127999662-016ca7e0-69a0-47f4-92d8-485ab49cc344.png)

![image](https://user-images.githubusercontent.com/43658658/127999697-caff7775-69f8-4795-8f4f-a101e0040c45.png)

> <h4>CSS3 text 속성</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>text-overflow</td>
			<td>콘텐츠(content) 영역을 벗어난 텍스트를 어떻게&nbsp;표현할지를 설정함.</td>
		</tr>
		<tr>
			<td>word-wrap</td>
			<td>길이가 긴 단어가 콘텐츠(content) 영역을 벗어나면 그 단어를 다음 줄에 나누어 표현할 수 있도록&nbsp;함.</td>
		</tr>
		<tr>
			<td>word-break</td>
			<td>긴 단어를 나누어 표현해야 할 때 해당 단어가 나뉘는 기준을 설정함.</td>
		</tr>
		<tr>
			<td>text-emphasis</td>
			<td>사용자가 강조 표현을 설정할 수 있도록 함.</td>
		</tr>
		<tr>
			<td>text-align-last</td>
			<td>텍스트의 마지막 줄의 정렬 방법을 설정함.</td>
		</tr>
		<tr>
			<td>text-justify</td>
			<td>텍스트의 정렬이 양끝 맞춤으로 되어 있을 때 그 정렬 방법을 설정함.</td>
		</tr>
	</tbody>
</table>

## CSS3 웹 글꼴
 

CSS3에서는 웹 글꼴을 사용하여 사용자의 컴퓨터에 설치되어 있지 않은 글꼴까지 사용할 수 있게 해줍니다.

 

 
CSS3에서는 웹 글꼴을 위해 다음 규칙이 추가되었습니다.

 

- @font-face 규칙

> <h3>웹 글꼴의 형식</h3>

웹 글꼴의 형식에는 다양한 종류가 있으며, 현재 가장 많이 사용하는 웹 글꼴 형식은 다음과 같습니다.

 

1. 트루 타입 글꼴(TrueType Fonts, TTF)

2. 오픈 타입 글꼴(OpenType Fonts, OTF)

3. 웹 오픈 글꼴(The Web Open Font Format, WOFF)

4. 웹 오픈 글꼴 2.0(The Web Open Font Format 2.0, WOFF 2.0)

5. SVG 글꼴(SVG Fonts/Shapes)

6. 임베디드 오픈 타입 글꼴(Embedded OpenType Fonts, EOT)

> <h3>@font-face 규칙</h3>

`@font-face` 규칙은 웹 폰트(web font)를 정의할 때 사용하는 규칙입니다.

웹 폰트(web font)는 사용자의 컴퓨터에 설치되어 있지 않은 글꼴(font)을 웹 브라우저가 사용할 수 있게 해줍니다.

 

우선 웹 폰트를 서버에 올려놓고, CSS 파일에 @font-face 규칙을 사용하여 `웹 폰트를 정의하고 추가`합니다.

그러면 해당 웹 페이지에 접속하는 모든 웹 브라우저는 자동으로 서버에서 웹 폰트를 내려받아 해당 글꼴을 표시하게 됩니다.

 

CSS3에서 @font-face 규칙을 사용하려면, 우선 font-family 속성을 이용하여 새로운 웹 글꼴을 위한 이름을 정의해야 합니다.

그 후에 해당 웹 글꼴이 사용할 글꼴 파일의 주소를 지정해 주면 됩니다.

``` html
<style>
	@font-face {
		font-family: myGothicFont; /* font-family 이름 정의 */
		src: url(/examples/media/NanumGothic.woff); /* font 추가 */
	}
	@font-face {
		font-family: myMyeongjoFont;
		src: url(/examples/media/NanumMyeongjo.woff);
	}
	#nGothic { font-family: myGothicFont; }
	#nMyeongjo { font-family: myMyeongjoFont; }
</style>
...
<p id="nGothic">웹 글꼴을 사용하여 나눔고딕 글꼴을 적용해 보았어요!</p>
<p id="nMyeongjo">웹 글꼴을 사용하여 나눔명조 글꼴을 적용해 보았어요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/128000836-9f1dbc36-8321-41b4-9845-8af300e30408.png)

> <h3>CSS3 @font-face 규칙 속성</h3>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>font-family</td>
			<td>필수적이며, 글꼴의 이름을 설정함.</td>
		</tr>
		<tr>
			<td>src</td>
			<td>필수적이며, 글꼴 파일의 주소를 설정함.</td>
		</tr>
		<tr>
			<td>font-weight</td>
			<td>선택적이며, 글꼴의 굵기를 설정함. 기본값은 &quot;normal&quot;임.</td>
		</tr>
		<tr>
			<td>font-stretch</td>
			<td>선택적이며, 글꼴의 크기가 늘어나는 방법을 설정함. 기본값은 &quot;normal&quot;임.</td>
		</tr>
		<tr>
			<td>font-style</td>
			<td>선택적이며, 글꼴의 스타일을 설정함. 기본값은 &quot;normal&quot;임.</td>
		</tr>
		<tr>
			<td>unicode-range</td>
			<td>선택적이며, 글꼴이 지원하는 유니코드 문자의 범위를 설정함. 기본값은 &quot;U+0-10FFFF&quot;임.</td>
		</tr>
	</tbody>
</table>
