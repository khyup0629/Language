# Part 10. HTML5 그래픽

+ [Canvas](#Canvas)
+ [SVG](#SVG)
+ [Canvas vs SVG](#Canvas-vs-SVG)

## Canvas

> <h3>canvas 요소</h3>

canvas 요소는 웹 페이지에 그래픽을 그려주는 쉽고 강력한 방법을 제공합니다.

이 요소는 그래픽을 위한 컨테이너(container) 역할만을 수행합니다.

따라서 실제로 그래픽을 그리기 위해서는 자바스크립트(JavaScript) 등의 스크립트 언어를 이용해야 합니다.

> <h3>canvas 요소의 속성</h3>

canvas 요소는 테두리(border)도 콘텐츠(content)도 없는 웹 페이지 내의 단순한 사각형의 공간입니다.

그러므로 반드시 style 속성을 이용하여 캔버스의 크기를 설정해 주어야 합니다.

이때, 반드시 속성으로 width와 height를 주어야합니다. style로 묶어선 안됩니다.

canvas 요소를 스크립트(script)에서 접근하기 위해서는 해당 요소의 id 속성을 이용하면 됩니다.

``` html
<h1>canvas 요소에 사각형 그리기</h1>
<canvas id="DrawCanvas" width="300" height = "200" style="border:1px solid #000000">
  이 텍스트는 브라우저가 canvas를 지원하지 않을 때 나타납니다.
</canvas>
```

![image](https://user-images.githubusercontent.com/43658658/127256031-f33f3929-eb95-4cf1-800a-eadbc4dc56ea.png)

> <h3>CSS 좌표 체계</h3>

HTML 그래픽 요소에서 사용하는 x, y, z좌표는 다음 그림과 같은 좌표 체계를 따릅니다.

CSS 좌표계

![image](https://user-images.githubusercontent.com/43658658/127256099-a4abec6f-79c3-4cca-86b6-982fa08e863c.png)

CSS 좌표 체계에서 기준점은 브라우저의 왼쪽 상단이 됩니다.

또한, 각 좌표축의 화살표 방향이 양의 방향이며, 반대쪽이 음의 방향을 가리킵니다.

> <h3>사각형 그리기</h3>

캔버스를 정의한 후에는 스크립트를 이용하여 canvas 요소에 그래픽을 그릴 수 있습니다.

다음 예제는 스크립트를 이용하여 canvas 요소에 사각형을 그리는 예제입니다.

``` html
<h1>canvas 요소에 사각형 그리기</h1>
  
  <canvas id="DrawCanvas" width="300" height="200" style="border:1px solid #993300">
    이 텍스트는 브라우저가 canvas를 지원하지 않을 때 나타납니다.
  </canvas>
  
  <script>
    var paper = document.getElementById("DrawCanvas");
    var context = paper.getContext("2d");
    context.strokeRect(10, 10, 250, 130);
    
    context.fillStyle = "rgba(255, 0, 0, 1)";
    context.fillRect(20, 20, 200, 100);
    
    context.clearRect(30, 30, 150, 50);
  </script>
  
  <p>
    가장 바깥쪽에 strokeRect() 함수를 사용하여 선만으로 이루어진 사각형을 그립니다.<br>
	그 다음에는 fillRect() 함수를 사용하여 빨간색으로 채워진 사각형을 그립니다.<br>
    가장 안쪽에는 clearRect() 함수를 사용하여 사각형 모양으로 안의 내용을 지워줍니다.
  </p>
```

![image](https://user-images.githubusercontent.com/43658658/127257404-2bfdfe82-4533-4c7d-9188-1d25704a4ca7.png)

위의 예제에서 사각형을 그리는 데 사용된 함수들은 다음 순서대로 인수를 전달받습니다.

1. 사각형의 왼쪽 위 꼭짓점의 x좌표
2. 사각형의 왼쪽 위 꼭짓점의 y좌표
3. 사각형의 너비(width)
4. 사각형의 높이(height)

사각형을 그리는데 사용하는 스크립트 함수는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>fillStyle()</td>
			<td>사각형 영역을 채울 색상을 설정함. 색상값만을 사용할 수도 있고, 투명도까지 명시할 수 있음.</td>
		</tr>
		<tr>
			<td>fillRect()</td>
			<td>사각형을 그리기 시작할 시작점의 x, y좌표와 사각형의 너비, 높이 등을 설정함.</td>
		</tr>
		<tr>
			<td>strokeRect()</td>
			<td>사각형 영역에 테두리를 그릴 때 사용함.</td>
		</tr>
		<tr>
			<td>clearRect()</td>
			<td>지정된 사각형 영역을 투명하게 만듦.</td>
		</tr>
	</tbody>
</table>

> <h3>선 그리기</h3>

다음 예제는 스크립트를 이용하여 canvas 요소에 선을 그리는 예제입니다.

``` html
<h1>canvas 요소에 선 그리기</h1>
<canvas id="DrawCanvas" width="300" height="200" style="border:1px solid #993300">
  이 텍스트는 브라우저가 canvas를 지원하지 않을 때 나타납니다!
</canvas>

<script>
  var paper = document.getElementById("DrawCanvas");
  var context = paper.getContext("2d");
  context.moveTo(0,0);
  context.lineTo(300, 100);
  context.lineTo(150, 150);
  context.stroke();
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127261393-6026d5a1-2c52-4646-b7f5-c288f9c8a0e6.png)

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>moveTo()</td>
			<td>선이 시작될 좌표를 설정함.</td>
		</tr>
		<tr>
			<td>lineTo()</td>
			<td>
			<p>선이 끝나는 좌표를 설정함.</p>

			<p>lineTo() 함수를 연속적으로 사용할 때의 시작 위치는 이전 선 그리기가 끝난 위치로 자동 설정됨.</p>
			</td>
		</tr>
		<tr>
			<td>stroke()</td>
			<td>선 그리기 시작함.</td>
		</tr>
	</tbody>
</table>

이러한 선 그리기를 이용하면 도형을 만들 수도 있으며, 만든 도형에 색을 채울 수도 있습니다.

우선 moveTo() 함수와 lineTo() 함수를 이용하여 선 그리기로 도형을 만듭니다.

그 후 fillStyle() 함수로 원하는 색상을 지정하고나서, fill() 함수를 사용하여 만든 도형에 색상을 칠하게 됩니다.

``` html
<h1>선 그리기를 이용한 도형 만들기</h1>
  <canvas id="DrawCanvas" width="300" height="200" style="border:1px solid #993300">
    이 텍스트는 브라우저가 canvas를 지원하지 않을 때 나타납니다!
  </canvas>
  
  <script>
    var paper=document.getElementById("DrawCanvas");
    var context = paper.getContext("2d");
    context.moveTo(0,0);
    context.lineTo(150, 0);
    context.lineTo(300, 200);
    context.lineTo(0,0);
    context.fillStyle = "#0099FF";
    context.fill();
    context.stroke();
  </script>
```

![image](https://user-images.githubusercontent.com/43658658/127261851-1fc08c9c-a095-4478-a321-d5637770174a.png)

> <h3>원 그리기</h3>

다음 예제는 스크립트를 이용하여 canvas 요소에 원을 그리는 예제입니다.

``` html
<h1>canvas 요소에 원 그리기</h1>
<canvas id="DrawCanvas" width="300" height="200" style="border:1px solid #993300">
  브라우저가 canvas를 지원하지 않습니다.
</canvas>

<script>
  var paper=document.getElementById("DrawCanvas");
  var context = paper.getContext("2d");
  context.beginPath();
  context.arc(150, 100, 50, 0, 2 * Math.PI);
  context.stroke();
  context.closePath();
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127266135-2ee758cc-b359-4888-857f-5f33d66bd6ae.png)

위의 예제에서 사용된 arc() 함수는 다음 순서대로 인수를 전달받습니다.

1. 원의 중심 x좌표
2. 원의 중심 y좌표
3. 원의 반지름
4. 원호를 그리기 시작할 각도
5. 원호 그리기를 마칠 각도

원을 그리는데 사용하는 스크립트 함수는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>beginPath()</td>
			<td>도형 그리기를 시작함.</td>
		</tr>
		<tr>
			<td>arc()</td>
			<td>원의 중심 좌표와 반지름, 원을 그리기 시작할 시작 위치와 종료 위치의 좌표, 그리는 방향 등을 설정함.</td>
		</tr>
		<tr>
			<td>closePath()</td>
			<td>닫힌 도형으로 만들면서 도형 그리기 종료.</td>
		</tr>
	</tbody>
</table>

이러한 원 그리기를 이용하면 원호 또한 간단히 만들 수 있습니다.

``` html
<h1>원 그리기를 이용한 원호 그리기</h1>

<canvas id="drawCanvas" width="300px" height="200px" style="border: 1px solid #993300">
  이 문장은 사용자의 웹 브라우저가 canvas 요소를 지원하지 않을 때 나타납니다!
</canvas>

<script>
  var paper = document.getElementById("drawCanvas");
    var context = paper.getContext("2d");
    context.beginPath();
    context.moveTo(100,100);
    context.arc(100,100,100,0,45*Math.PI/180);
    context.closePath();
    context.stroke();
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127266714-9dd33dab-9205-44a4-9183-fbd1f11ba761.png)

> <h3>텍스트(text) 그리기</h3>

다음 예제는 스크립트를 이용하여 canvas 요소에 텍스트를 그리는 예제입니다.

``` html
<h1>canvas 요소에 텍스트 그리기</h1>

<canvas id="drawCanvas" width="300px" height="200px" style="border: 1px solid #993300">
  이 문장은 사용자의 웹 브라우저가 canvas 요소를 지원하지 않을 때 나타납니다!
</canvas>

<script>
  var paper=document.getElementById("drawCanvas");
    var context=paper.getContext("2d");
    context.font="40px Arial";
    context.fillText("CANVAS", 50, 90);
    context.strokeText("HTML5", 80, 150);
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127267150-70ab6de9-e689-4003-b19e-07fe25e4d518.png)

위의 예제에서 텍스트를 그리는 데 사용된 함수들은 다음 순서대로 인수를 전달받습니다.

1. canvas 요소에 그릴 텍스트의 내용
2. 텍스트의 왼쪽 위 꼭짓점의 x좌표
3. 텍스트의 왼쪽 위 꼭짓점의 y좌표

텍스트를 그리는데 사용하는 스크립트 함수는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>font()</td>
			<td>텍스트의 크기, 폰트(font)와 색상 등을 설정함.</td>
		</tr>
		<tr>
			<td>fillText()</td>
			<td>텍스트의 내용과 텍스트를 그리기 시작할 시작 위치의 좌표를 설정함.</td>
		</tr>
		<tr>
			<td>strokeText()</td>
			<td>테두리만 있는 텍스트를 그릴 때 사용함.</td>
		</tr>
	</tbody>
</table>

> <h3>그래디언트(gradient) 그리기</h3>

다음 예제는 스크립트를 이용하여 canvas 요소에 선형 그래디언트를 그리는 예제입니다.

``` html
<h1>canvas 요소에 선형 그래디언트 그리기</h1>

<canvas id="drawCanvas" width="300" height="200" style="border: 1px solid #993300">
  이 문장은 사용자의 웹 브라우저가 canvas 요소를 지원하지 않을 때 나타납니다!
</canvas>

<script>
  var paper = document.getElementById("drawCanvas");
    var context = paper.getContext("2d");
    var gradient = context.createLinearGradient(0, 0, 150, 0);
    gradient.addColorStop(0, "#FFCC00");
    gradient.addColorStop(1, "#FFCCCC");

    context.fillStyle = gradient;
    context.font = "45px Arial black";
    context.fillText("CANVAS", 30, 100);

</script>
```

![image](https://user-images.githubusercontent.com/43658658/127267934-39e34018-4ca8-4e25-89e8-9a1c0af52c00.png)

위의 예제에서 사용된 createLinearGradient() 함수는 다음 순서대로 인수를 전달받습니다.

1. 선형 그래디언트가 시작하는 점의 x좌표
2. 선형 그래디언트가 시작하는 점의 y좌표
3. 선형 그래디언트가 끝나는 점의 x좌표
4. 선형 그래디언트가 끝나는 점의 y좌표

이렇게 createLinearGradient() 함수를 사용하여 선형 그래디언트를 생성합니다.
이때 addColorStop() 함수를 사용하여 그래디언트에 사용될 색상을 명시할 수 있습니다.
또한, 이렇게 생성된 그래디언트는 fillStyle이나 strokeStyle 속성을 이용하여 그릴 수 있습니다.

다음 예제는 스크립트를 이용하여 canvas 요소에 원형 그래디언트를 그리는 예제입니다.

``` html
<h1>canvas 요소에 원형 그래디언트 그리기</h1>

<canvas id="drawCanvas" width="300px" height="200px" style="border: 1px solid #993300">
  이 문장은 사용자의 웹 브라우저가 canvas 요소를 지원하지 않을 때 나타납니다!
</canvas>

<script>
  var paper = document.getElementById("drawCanvas");
    var context = paper.getContext("2d");
    var gradient = context.createRadialGradient(150, 100, 50, 150, 100, 150);
    gradient.addColorStop(0, "white");
    gradient.addColorStop(1, "black");

    context.fillStyle = gradient;
    context.fillRect(0, 0, 300, 200);
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127268438-2d31575c-6bd1-453f-a460-c110419bcebf.png)

위의 예제에서 사용된 createRadialGradient() 함수는 다음 순서대로 인수를 전달받습니다.

1. 원형 그래디언트가 시작하는 원의 중심 x좌표
2. 원형 그래디언트가 시작하는 원의 중심 y좌표
3. 원형 그래디언트가 시작하는 원의 반지름
4. 원형 그래디언트가 끝나는 원의 중심 x좌표
5. 원형 그래디언트가 끝나는 원의 중심 y좌표
6. 원형 그래디언트가 끝나는 원의 반지름

그래디언트(gradient)를 그리는데 사용하는 스크립트 함수는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>createLinearGradient()</td>
			<td>선형 그래디언트를 그리기 시작할 시작 위치와 종료 위치의 좌표를 설정함.</td>
		</tr>
		<tr>
			<td>createRadialGradient()</td>
			<td>원형 그래디언트를 그리기 시작할 큰 원의 중심 좌표, 반지름과&nbsp;그래디언트가 끝날 작은 원의 중심 좌표, 반지름 등을 설정함.</td>
		</tr>
		<tr>
			<td>addColorStop()</td>
			<td>그래디언트의 색을 설정함. 시작점인 0에서부터 종료점인 1까지 다양한 색 지정이 가능함.</td>
		</tr>
	</tbody>
</table>

+ createLinearGradient() 함수와 createRadialGradient() 함수는 익스플로러 8과 그 이전 버전에서 지원하지 않습니다.

> <h3>이미지 그리기</h3>

다음 예제는 스크립트를 이용하여 canvas 요소에 이미지를 그리는 예제입니다.

``` html
<h1>canvas 요소에 이미지 그리기</h1>
<p>원본 이미지</p>
<img id="Monalisa" src="/examples/images/img_monalisa.png" alt="모나리자" width="180" height="280">
<p>사본 이미지</p>
<canvas id="drawCanvas" width="200px" height="300px" style="border: 1px solid #993300">
  이 문장은 사용자의 웹 브라우저가 canvas 요소를 지원하지 않을 때 나타납니다!
</canvas>
<p><button onclick="drawImage()">이미지 그리기</button></p>

<script>
  function drawImage(){
    var paper = document.getElementById("drawCanvas");
    var context = paper.getContext("2d");
    var srcImg = document.getElementById("Monalisa");
    context.drawImage(srcImg, 10, 10);
  }
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127269287-98632a4f-b750-41ec-9829-29095dff52e9.png)

위의 예제에서 사용된 drawImage() 함수는 다음 순서대로 인수를 전달받습니다.

1. canvas 요소에 그릴 이미지의 주소
2. 이미지의 왼쪽 위 꼭짓점의 x좌표
3. 이미지의 왼쪽 위 꼭짓점의 y좌표

이미지를 그리는데 사용하는 스크립트 함수는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>drawImage()</td>
			<td>canvas 요소에 그릴 이미지의 주소와 이미지가 그려질 시작 위치를 설정함.</td>
		</tr>
	</tbody>
</table>

## SVG

svg 요소는 Scalable Vector Graphics를 의미하며, XML 기반의 W3C 그래픽 표준 권고안입니다.

기존에 사용해 왔던 canvas 요소로는 벡터(vector) 이미지를 표현할 수 없었습니다.

하지만 svg 요소는 픽셀 기반인 웹 페이지에서 픽셀의 영향을 받지 않는 벡터 이미지를 표현할 수 있게 해줍니다.

따라서 이 요소는 도표나 그래프 등 벡터 기반의 다이어그램(diagram)를 표현하는 데 매우 효과적입니다.

> <h3>사각형 그리기</h3>

다음 예제는 rect 요소를 사용하여 사각형을 그리는 예제입니다.

``` html
<h1>svg 요소를 이용한 사각형 그리기</h1>
<svg width="200" height="150">
  <rect width="200" height="150" stroke="orange" stroke-width="5" fill="yellow"/>
  이 텍스트는 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127270459-52011b54-e19c-4328-a85c-1cc0e2b962ba.png)

사각형을 그리는데 사용하는 rect 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>width</td>
			<td>도형의 너비를 설정함.</td>
		</tr>
		<tr>
			<td>height</td>
			<td>도형의 높이를 설정함.</td>
		</tr>
		<tr>
			<td>stroke</td>
			<td>도형의 테두리 색상을 설정함.</td>
		</tr>
		<tr>
			<td>stroke-width</td>
			<td>도형의 테두리 굵기를 설정함.</td>
		</tr>
		<tr>
			<td>fill</td>
			<td>도형을 채울 색상을 설정함.</td>
		</tr>
		<tr>
			<td>opacity</td>
			<td>도형의 투명도를 설정함.</td>
		</tr>
	</tbody>
</table>

위와 같이 각각의 속성을 사용하여 설정할 수도 있으며, 다음 예제와 같이 style 속성을 사용하여 한 번에 설정할 수도 있습니다.

``` html
<h1>svg 요소를 이용한 사각형 그리기</h1>
<svg width="200" height="150">
  <rect width="200" height="150" style="stroke:orange; stroke-width:5; fill:yellow"/>
  이 텍스트는 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

rect 요소에 x, y, rx, ry 속성을 추가하여 모서리가 둥근 사각형을 그릴 수 있습니다.

``` html
<h1>svg 요소를 이용한 사각형 그리기</h1>
<svg width="250" height="200">
  <rect width="200" height="150" x="20" y="20" rx="20" ry="20" style="stroke:orange; stroke-width:5; fill:yellow"/>
  이 텍스트는 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127270492-a9a5b8a7-aac3-4339-b5c4-605e4ae2625b.png)

모서리가 둥근 사각형을 그리는데 사용하는 rect 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>x</td>
			<td>사각형의 왼쪽 위 꼭짓점의 x좌표를 설정함.</td>
		</tr>
		<tr>
			<td>y</td>
			<td>사각형의 왼쪽 위 꼭짓점의 y좌표를 설정함.</td>
		</tr>
		<tr>
			<td>rx</td>
			<td>사각형 모서리 굴곡의 x축 반지름을 설정함.</td>
		</tr>
		<tr>
			<td>ry</td>
			<td>사각형 모서리 굴곡의 y축 반지름을 설정함.</td>
		</tr>
	</tbody>
</table>

> <h3>선 그리기</h3>

다음 예제는 line 요소를 사용하여 선을 그리는 예제입니다.

``` html
<h1>svg 요소를 이용한 선 그리기</h1>
<svg width="250" height="200">
  <line x1="10" y1="10" x2="200" y2="150" stroke="orange" stroke-width="5"/>
  이 텍스트는 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127270424-80701582-a267-41ef-9a3c-116701b14fe6.png)

선을 그리는데 사용하는 line 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>x1</td>
			<td>선이 시작될 위치의 x좌표를 설정함.</td>
		</tr>
		<tr>
			<td>y1</td>
			<td>선이 시작될 위치의 y좌표를 설정함.</td>
		</tr>
		<tr>
			<td>x2</td>
			<td>선이 끝나는 위치의 x좌표를 설정함.</td>
		</tr>
		<tr>
			<td>y2</td>
			<td>선이 끝나는 위치의 y좌표를 설정함.</td>
		</tr>
	</tbody>
</table>

> <h3>원 그리기</h3>

다음 예제는 circle 요소를 사용하여 원을 그리는 예제입니다.

``` html
<h1>svg 요소를 이용한 원 그리기</h1>
<svg width="300" height="300">
  <circle cx="150" cy="120" r="100" stroke="blue" stroke-width="5" fill="lightblue"/>
  이 문장은 사용자의 웹 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127270688-8b7a46ea-cced-4519-894c-af9786d526e7.png)

원을 그리는데 사용하는 circle 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>cx</td>
			<td>원의 중심&nbsp;x좌표를 설정함.</td>
		</tr>
		<tr>
			<td>cy</td>
			<td>원의 중심 y좌표를 설정함.</td>
		</tr>
		<tr>
			<td>r</td>
			<td>원의 반지름을 설정함.</td>
		</tr>
	</tbody>
</table>

> <h3>타원 그리기</h3>

다음 예제는 ellipse 요소를 사용하여 타원을 그리는 예제입니다.

``` html
<h1>svg 요소를 이용한 타원 그리기</h1>
<svg width="300" height="300">
  <ellipse cx="150" cy="100" rx="120" ry="70" stroke="blue" stroke-width="5" fill="lightblue"/>
  이 문장은 사용자의 웹 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127270893-0c2bbeff-5a68-4368-ba2d-f967e0a30fae.png)

타원을 그리는데 사용하는 ellipse 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>cx</td>
			<td>타원 중심의 x좌표를 설정함.</td>
		</tr>
		<tr>
			<td>cy</td>
			<td>타원 중심의 y좌표를 설정함.</td>
		</tr>
		<tr>
			<td>rx</td>
			<td>타원의 x축 반지름을 설정함.</td>
		</tr>
		<tr>
			<td>ry</td>
			<td>타원의 y축 반지름을 설정함.</td>
		</tr>
	</tbody>
</table>

> <h3>다각형 그리기</h3>

다음 예제는 polygon 요소를 사용하여 별모양의 다각형을 그리는 예제입니다.

``` html
<h1>svg 요소를 이용한 다각형 그리기</h1>
<svg width="300" height="300">
  <polygon points="10,100 190,100 30,200 100,40 170,200"
    stroke="orange" stroke-width="5" fill="yellow"/>
  이 문장은 사용자의 웹 브라우저가 svg 요소를 지원하지 않을 때 나타납니다!
</svg>
```

![image](https://user-images.githubusercontent.com/43658658/127271044-9328417d-4f16-4c82-a350-5480d4a68f11.png)

다각형을 그리는데 사용하는 polygon 요소의 속성은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 150px;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>points</td>
			<td>다각형의 각 꼭짓점이 표시될 위치의 좌표를 설정함.</td>
		</tr>
	</tbody>
</table>

points 속성은 다각형을 이루는 각 꼭짓점의 x좌표와 y좌표를 명시합니다.

이때 첫 번째 꼭짓점부터 시작하여 마지막 꼭짓점까지 차례대로 선으로 연결되어 다각형을 표현하게 됩니다.

제일 마지막에 찍힌 point와 시작점이 자동으로 이어지면서 완성됩니다.

## Canvas vs SVG

**canvas 요소와 svg 요소**는 거의 같은 결과물을 얻을 수 있는 비슷한 동작을 하는 요소입니다.

어떤 경우에는 **canvas 요소**를 사용하는 것이 더 나으며, 어떤 경우에는 **svg 요소**를 사용하는 것이 더 나은 경우가 있습니다.

> <h3>작업 환경에 따른 선택의 기준</h3>

다음 그림은 화면 크기 및 픽셀 수에 따른 렌더링 시간(rendering time)을 보여줍니다.

렌더링(rendering)이란 프로그램을 사용하여 모델로부터 영상이나 화면을 만들어내는 과정을 가리킵니다.

따라서 렌더링 시간이란 코드를 실행하여 그 결과가 화면에 표시되는 시간을 의미합니다.

![image](https://user-images.githubusercontent.com/43658658/127271600-6950dfcb-e5c6-4548-8333-2cd26d14c6ab.png)

- canvas 요소의 성능은 화면이 작거나, 픽셀 수가 많을 경우(>10k)에 좋습니다.

- svg 요소의 성능은 화면이 크거나, 픽셀 수가 적을 경우(<10k)에 좋습니다.

따라서 각 작업 환경에 맞는 그래픽 요소를 선택하여 사용하는 것이 가장 좋습니다.

> <h3>작업 종류에 따른 선택의 기준</h3>

다음 그림은 canvas 요소와 svg 요소를 사용할 때 선택의 기준을 제시해줍니다.

![image](https://user-images.githubusercontent.com/43658658/127271770-4ebd3b69-ba5b-4acf-abee-18ce90ff790c.png)

- canvas 요소는 복잡하고 고성능의 애니메이션(animation) 작업이나 동영상 조작 등의 작업에 잘 어울립니다.

- svg 요소는 고품질의 문서 작업이나 정적 이미지의 조작 작업 등에 잘 어울립니다.

> <h4>Canvas와 SVG의 차이점</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 50%;">Canvas</th>
			<th style="width: 50%;">SVG</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align: left;">픽셀(pixel) 기반</td>
			<td>모양(shape) 기반</td>
		</tr>
		<tr>
			<td style="text-align: left;">단일 HTML 요소</td>
			<td>DOM의 일부분이 되는 다중 그래픽 요소</td>
		</tr>
		<tr>
			<td style="text-align: left;">스크립트(script)를 통해서만 수정할 수 있음.</td>
			<td>스크립트(script) 및 CSS를 통해서도 수정할 수 있음.</td>
		</tr>
		<tr>
			<td style="text-align: left;">그래픽이 주작업인 게임에 적합함.</td>
			<td>렌더링 영역이 넓은 응용 프로그램(application)에 적합함.</td>
		</tr>
	</tbody>
</table>
