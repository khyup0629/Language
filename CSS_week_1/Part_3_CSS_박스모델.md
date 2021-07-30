# Part 3. CSS 박스 모델

+ [크기 단위](#크기-단위)
+ [크기](#크기)
+ [박스 모델](#박스-모델)
+ [패딩](#패딩)
+ [테두리](#테두리)
+ [마진](#마진)
+ [아웃라인](#아웃라인)

## 크기 단위

CSS에서 사용하는 크기의 단위에는 %, em, px, cm, mm, inch 등이 있습니다.


그 중에서도 가장 많이 쓰이는 크기 단위는 다음과 같습니다.

 

1. 백분율 단위(%)

2. 배수 단위(em)

3. 픽셀 단위(px)

 

백분율 단위(%)는 기본 크기를 100%로 놓고, 그에 대한 상대적인 크기를 설정합니다.

배수 단위(em)는 해당 글꼴(font)의 `<body>` 크기를 1em으로 놓고, 그에 대한 상대적인 크기를 설정합니다.

픽셀 단위(px)는 스크린의 픽셀(pixel)을 기준으로 하는 절대적인 크기를 설정합니다.

``` html
<style>
    #large { font-size: 200%; }
    #small { font-size: 0.7em; }
    #fixed { font-size: 20px; }
</style>
```

하지만, 인터넷 익스플로러의 이전 버전에서는 글씨 크기를 늘리거나 줄였을 때, 기대한 것보다 더 커지거나 더 작아지는 경우가 생깁니다.

이럴 때는 `<body>`의 글꼴 크기를 100%로 설정한 뒤에 원하는 글꼴들의 크기를 조정하면 됩니다.

``` html
<style>
  body { font-size: 100%; }

  h1 { font-size: 2.5em; }

  h2 { font-size: 1.875em; }

  p { font-size: 0.875em; }
</style>
```

## 크기

CSS를 이용하면 HTML 요소의 크기를 마음대로 설정할 수 있습니다.

CSS에서 크기 조절을 위해 사용할 수 있는 속성은 다음과 같습니다.

 

1. height

2. width

3. max-width

4. min-width

5. max-height

6. min-height

> <h3>max-width 속성</h3>

max-width 속성은 해당 HTML 요소가 가질 수 있는 최대 너비(width)를 설정합니다.

이 속성의 기본 설정값은 none이며, 해당 HTML 요소의 너비에 제한을 두지 않겠다는 의미입니다.

 

width 속성으로 너비를 설정하면, 설정된 너비 이하로 브라우저의 크기가 줄어들 때 해당 요소에 스크롤 바를 생성하게 됩니다.

하지만 max-width 속성으로 너비를 설정하면 다음과 같이 좀 더 유연한 결과를 얻을 수 있습니다.

max-width 속성으로 너비를 설정하면 줄어드는 웹 브라우저의 크기에 맞춰 해당 HTML 요소의 너비도 자동으로 줄어듭니다.

``` html
<style>
  div.width {
    width: 500px;
    border: 2px solid #DAA520;
  }
  div.maxWidth {
    max-width: 500px;
    border: 2px solid #CD5C5C;
  }
</style>
...
<div class="width">이 div 요소는 width 속성을 500px로 설정했습니다.</div><br>
<div class="maxWidth">이 div 요소는 max-width 속성을 500px로 설정했습니다.</div>
<p>웹 브라우저의 크기를 줄여서 두 div 요소의 차이를 알아보세요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127586389-c11d4c02-9f25-460b-9918-e3a888089f2f.png)

위와 같이 브라우저 창의 크기를 줄였을 때 `max-width`로 설정한 박스는 창의 크기에 맞게 줄어드는 것을 확인할 수 있습니다.

> <h3>min-width 속성</h3>

min-width 속성은 해당 HTML 요소가 가질 수 있는 최소 너비(width)를 설정합니다.

이 속성의 기본 설정값은 0이며, 해당 HTML 요소의 너비에 제한을 두지 않겠다는 의미입니다.

 

min-width 속성이 설정된 요소에 width 속성값을 따로 설정하지 않으면 `초기 너비(width)`는 `100%`를 가지게 됩니다.

이때 웹 브라우저의 크기가 줄어들면 거기에 맞춰 HTML 요소의 너비도 자동으로 줄어듭니다.

하지만 웹 브라우저가 min-width 속성으로 설정된 너비 이하로 줄어들면, HTML 요소의 너비는 더는 줄어들지 않고 수평 스크롤 바를 생성하게 됩니다.

``` html
<style>
		div.width {
			width: 500px;
			border: 2px solid #DAA520;
		}
		div.minWidth {
			min-width: 500px;
			border: 2px solid #CD5C5C;
		}
</style>
...
<div class="width">이 div 요소는 width 속성을 500px로 설정했습니다.</div><br>
<div class="minWidth">이 div 요소는 min-width 속성을 500px로 설정했습니다.</div>
<p>웹 브라우저의 크기를 줄여서 두 div 요소의 차이를 알아보세요!</p>
```

`width`에 대한 속성이 따로 설정되어 있지 않기 때문에 초기 너비는 `100%`로 설정됩니다.

![image](https://user-images.githubusercontent.com/43658658/127586557-933013de-dc65-488a-83c2-754f930c54c3.png)

`500px 이하`로 창을 줄이게 되면 너비는 더 줄어들지 않습니다.

![image](https://user-images.githubusercontent.com/43658658/127586609-4ab991b3-e86e-4efc-8a7b-4ec3da82eacf.png)

> <h3>max-height 속성</h3>

max-height 속성은 해당 HTML 요소가 가질 수 있는 최대 높이(height)를 설정합니다.

이 속성의 기본 설정값은 none이며, 해당 HTML 요소의 크기에 따라 높이가 자동으로 설정됩니다.

 

max-height 속성으로 최대 높이를 설정하면, 해당 HTML 요소의 높이를 설정된 높이 이하로 제한합니다.

만약 해당 요소의 높이가 설정된 최대 높이보다 클 경우에는 수직 스크롤 바를 생성하게 됩니다.

``` html
<style>
  p {
    max-height: 50px;
    background-color: greenyellow;
    overflow: auto;
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127586836-b7e27f21-3733-43bf-96d5-9e1b40b83934.png)

> <h3>min-height 속성</h3>

min-height 속성은 지정된 HTML 요소가 가질 수 있는 최소 높이(height)를 설정합니다.

이 속성의 기본 설정값은 0이며, 해당 HTML 요소의 높이에 제한을 두지 않겠다는 의미입니다.

 

min-height 속성을 설정하면 해당 HTML 요소의 높이를 설정된 높이 이하로 제한합니다.

즉 height 속성값이 min-height 속성값 이하로 낮아지지 않도록 합니다.

이러한 min-height 속성값은 max-height 속성값과 height 속성값보다 먼저 적용됩니다.

``` html
<style>
  p {
    min-height: 50px;
    background-color: greenyellow;
  }
</style>
```

최소 높이를 50px로 적용한 모습입니다.

![image](https://user-images.githubusercontent.com/43658658/127587045-e50a568b-8969-4a75-a7b9-f53db3f68e46.png)

입력 문자열이 길어질 수록 그에 맞게 크기가 커지는 모습을 볼 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127587101-8933fee7-87fa-47e3-a1f9-98186101bb97.png)

## 박스 모델

모든 HTML 요소는 박스(box) 모양으로 구성되며, 이것을 박스 모델(box model)이라고 부릅니다.

박스 모델은 HTML 요소를 패딩(padding), 테두리(border), 마진(margin), 그리고 내용(content)으로 구분합니다.

![image](https://user-images.githubusercontent.com/43658658/127590997-684cc796-0082-40e4-984d-443151769c69.png)

1. 내용(content) : 텍스트나 이미지가 들어있는 박스의 실질적인 내용 부분입니다.

2. 패딩(padding) : 내용과 테두리 사이의 간격입니다. 패딩은 눈에 보이지 않습니다.

3. 테두리(border) : 내용와 패딩 주변을 감싸는 테두리입니다.

4. 마진(margin) : 테두리와 이웃하는 요소 사이의 간격입니다. 마진은 눈에 보이지 않습니다.

``` html
<style>
  div {
        background-color: red;
        width: 400px;
        color: white;
        padding: 50px;
        border:20px solid maroon;
        margin: 50px
    }
</style>
```

> <h3>height와 width 속성의 이해</h3>

모든 웹 브라우저에서 정확하게 HTML 요소들을 표현하려면 이러한 박스 모델이 어떻게 동작하는지 정확히 알아야만 합니다.

CSS에서 height와 width 속성을 설정할 때 그 크기가 가르키는 부분은 내용(content) 부분만을 대상으로 합니다.

HTML 요소의 height와 width 속성으로 설정된 높이와 너비에 패딩(padding), 테두리(border), 마진(margin)의 크기는 포함되지 않습니다.

``` html
<style>
  div {
    width: 320px;
    padding: 10px;
    border: 5px solid maroon;
    margin: 0;
  }
</style>
...
<h1>CSS 박스 모델의 전체 크기 계산법</h1>
<img src="/examples/images/img_flower.png" width="350" height="263" alt="flower">
<div>
  위 이미지의 너비는 350px입니다.<br>
  이 div 요소의 width 속성값은 320px입니다.<br>
  하지만 좌우 패딩(padding)이 10px로 설정되어 있습니다.<br>
  또한, 좌우 테두리(border)의 너비가 5px로 설정되어 있습니다.<br>
  따라서 이 div 요소의 전체 너비는 320px + 10px + 10px + 5px + 5px = 350px이 됩니다.
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127591341-5cd6c946-f72d-4247-9578-26fce776544e.png)

> <h3>HTML 요소의 높이와 너비 구하기</h3>
 
![image](https://user-images.githubusercontent.com/43658658/127591381-80c9a7f6-b415-4a82-9d26-375aa567f5d6.png)

위의 그림에서 전체 너비(width)를 계산해 보면,

width(70px) + left margin(10px) + left padding(5px) + right padding(5px) + right margin(10px) = 100px 이 됩니다.

 

즉, HTML 요소의 전체 너비(`width`)를 계산하는 공식은

width + left padding + right padding + left border + right border + left margin + right margin 입니다.

 

또한, HTML 요소의 전체 높이(`height`)를 계산하는 공식은

height + top padding + bottom padding + top border + bottom border + top margin + bottom margin 입니다.

 

이때 마진(margin) 영역의 크기는 눈으로 바로 확인할 수는 없을 것입니다.

왜냐하면 마진이란 테두리(border)와 이웃하는 요소 사이의 간격이면서, 배경색의 영향을 받지 않기 때문입니다.

하지만 HTML 요소가 차지하는 크기에는 포함됩니다.

 
+ 익스플로러 8과 그 이전 버전에서는 width나 height 속성으로 설정한 너비나 높이에 패딩과 테두리의 크기까지 포함됩니다.
+ 이러한 차이점을 없애기 위해서는 반드시 HTML 문서에 `<!DOCTYPE html>`태그를 삽입해야만 합니다.

## 패딩

padding 속성은 내용(content)과 테두리(border) 사이의 간격인 패딩 영역의 크기를 설정합니다.

이러한 패딩 영역은 `background-color` 속성으로 설정하는 배경색의 영향을 함께 받습니다.

CSS를 사용하면 패딩 영역의 크기를 방향별로 따로 설정할 수 있습니다.

> <h3>패딩(padding) 속성</h3>

CSS에서는 HTML 요소의 패딩 영역을 설정하기 위해 다음과 같은 속성을 제공합니다.

 

1. padding-top

2. padding-right

3. padding-bottom

4. padding-left

``` html
<style>
  div {
    background-color: #7FFFD4;
    border: 2px solid teal;
  }
  div.pad {
    padding-top: 50px;
        padding-bottom: 20px;
        padding-left:50px;
        padding-right:30px;
  }
</style>
```

> <h3>패딩 축약 표현(padding shorthand)</h3>

모든 padding 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

4개의 padding 속성값을 가질 때는 `top, right, bottom, left` 순(`top부터 시계방향`)으로 설정합니다.

ex) padding: 10px 20px 30px 40px;

(위의 예제는 아래 4줄의 코드와 같은 의미를 가지고 있습니다.)

padding-top: 10px;

padding-right: 20px;

padding-bottom: 30px;

padding-left: 40px;

 

3개의 padding 속성값을 가질 때는 `top`, `right와 left`, `bottom` 순으로 설정합니다.

ex) padding: 10px 20px 30px;

(위의 예제는 아래 4줄의 코드와 같은 의미를 가지고 있습니다.)

padding-top: 10px;

padding-right: 20px;

padding-bottom: 30px;

padding-left: 20px;

 

2개의 padding 속성값을 가질 때는 `top과 bottom`, `right와 left` 순으로 설정합니다.

ex) padding: 10px 20px;

(위의 예제는 아래 4줄의 코드와 같은 의미를 가지고 있습니다.)

padding-top: 10px;

padding-right: 20px;

padding-bottom: 10px;

padding-left: 20px;

 

1개의 padding 속성값을 가질 때는 `모든 패딩값을 같게 설정`합니다.

ex) padding: 10px;

(위의 예제는 아래 4줄의 코드와 같은 의미를 가지고 있습니다.)

padding-top: 10px;

padding-right: 10px;

padding-bottom: 10px;

padding-left: 10px;

## 테두리

border 속성은 내용(content)과 패딩(padding) 영역을 둘러싸는 테두리의 스타일을 설정합니다.

> <h3>border-style 속성</h3>

border-style 속성을 이용하면 테두리(border)를 다양한 모양으로 설정할 수 있습니다.
 

- dotted : 테두리를 점선으로 설정함.

- dashed : 테두리를 약간 긴 점선으로 설정함.

- solid : 테두리를 실선으로 설정함.

- double : 테두리를 이중 실선으로 설정함.

- groove : 테두리를 3차원인 입체적인 선으로 설정하며, border-color 속성값에 영향을 받음.

- ridge : 테두리를 3차원인 능선효과가 있는 선으로 설정하며, border-color 속성값에 영향을 받음.

- inset : 테두리를 3차원인 내지로 끼운 선으로 설정하며, border-color 속성값에 영향을 받음.

- outset : 테두리를 3차원인 외지로 끼운 선으로 설정하며, border-color 속성값에 영향을 받음.

- none : 테두리를 없앰.

- hidden : 테두리가 존재하기는 하지만 표현되지는 않음.

``` html
<style>
  .dotted {border-style: dotted;}
  .dashed {border-style: dashed;}
  .solid {border-style: solid;}
  .double {border-style: double;}
  .groove {border-style: groove;}
  .ridge {border-style: ridge;}
  .inset {border-style: inset;}
  .outset {border-style: outset;}
  .none {border-style: none;}
  .hidden {border-style: hidden;}
  .mix {border-style: solid dashed dotted double;}
</style>
...
<p class="dotted">border-style 속성값을 dotted로 한 단락입니다.</p>
<p class="dashed">border-style 속성값을 dashed로 한 단락입니다.</p>
<p class="solid">border-style 속성값을 solid로 한 단락입니다.</p>
<p class="double">border-style 속성값을 double로 한 단락입니다.</p>
<p class="groove">border-style 속성값을 groove로 한 단락입니다.</p>
<p class="ridge">border-style 속성값을 ridge로 한 단락입니다.</p>
<p class="inset">border-style 속성값을 inset으로 한 단락입니다.</p>
<p class="outset">border-style 속성값을 outset으로 한 단락입니다.</p>
<p class="none">border-style 속성값을 none으로 한 단락입니다.</p>
<p class="hidden">border-style 속성값을 hidden으로 한 단락입니다.</p>
<p class="mix">border마다 각각의 border-style 속성값을 적용한 단락입니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127592226-9e1f44a3-a2a1-4e12-a6ab-a7e798d4aee7.png)

> <h3>border-width 속성</h3>

border-width 속성은 테두리(border)의 두께를 설정합니다.

px, em, cm 등과 같은 CSS 크기 단위를 이용하여 두께를 직접 설정할 수 있습니다.

또한, 미리 설정해 놓은 예약어인 thin, medium, thick을 사용하여 설정할 수도 있습니다.

``` html
<style>
  .dottedA {
    border-style: dotted;
    border-width: 2px;
  }
  .dottedB {
    border-style: dotted;
    border-width: 5px;
  }
  .dashedA {
    border-style: dashed;
    border-width: thin;
  }
  .dashedB {
    border-style: dashed;
    border-width: thick;
  }
  .doubleA {
    border-style: double;
    border-width: 5px;
  }
  .doubleB {
    border-style: double;
    border-width: thick;
  }
  .mix {
    border-style: solid;
    border-width: 1px 2px 10px thick;
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127592402-f176e8a5-bcee-4159-9956-534e254bae11.png)

> <h3>border-color 속성</h3>

border-color 속성은 테두리(border)의 색상을 설정합니다.

기본적인 color 속성값들뿐만 아니라 투명한 선을 나타내는 transparent 속성값을 사용할 수도 있습니다.

border-color 속성값이 설정되지 않으면 해당 요소의 color 속성값을 그대로 물려받습니다.

``` html
<style>
  p {
    border-style: solid;
    border-width: 3px;
  }
  .red { border-color: red; }
  .green { border-color: rgb(0,255,0); }
  .blue { border-color: #0000FF; }
  .mix { border-color: red green blue maroon; }
  .color { color: teal; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127592468-cd0606fd-a3e7-4d6a-aaf6-a61c4e496b7c.png)

> <h3>테두리(border)의 개별 설정</h3>

CSS를 사용하면 테두리의 위쪽, 오른쪽, 아래쪽, 왼쪽 부분에 대하여 개별적으로 스타일을 적용할 수 있습니다.

속성 부여 방법 : `border-(top or right or bottom or left)-(style or width or color)`

원리는 `padding`과 같습니다. 4개, 3개, 2개, 1개의 속성값을 줄 수 있습니다.

top부터 시계방향 순으로 top, right, bottom, left 순입니다.

``` html
<style>
  .mixA, .mixB {
    border-style: solid;
    border-width: 3px;
  }
  .mixA {
    border-top-style: dotted;
    border-right-style: double;
    border-bottom-style: dotted;
    border-left-style: double;
  }
  .mixB { border-style: dotted double; }
</style>
```

> <h3>테두리 축약 표현(border shorthand)</h3>

모든 border 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

순서대로 적어주어야 합니다.

1. border-width
2. border-style
3. border-color

``` html
<style>
  div { border: 1px solid red; }
</style>
```

## 마진

margin 속성은 테두리(border)와 이웃하는 요소 사이의 간격인 마진 영역의 크기를 설정합니다.

이러한 마진 영역은 패딩 영역과는 달리 background-color 속성으로 설정하는 배경색의 영향을 받지 않습니다.

CSS를 사용하면 마진 영역의 크기를 방향별로 따로 설정할 수 있습니다.

> <h3>마진(margin) 속성</h3>

CSS에서는 HTML 요소의 마진 영역을 설정하기 위해 다음과 같은 속성을 제공합니다.


1. margin-top

2. margin-right

3. margin-bottom

4. margin-left

 

margin 속성값을 음수로 설정하여 해당 요소를 다른 요소의 위에 겹치게 할 수도 있습니다.

``` html
<style>
  div {
    background-color: #7FFFD4;
    border: 2px solid teal;
  }
  div.mar {
    margin-top: -25px;
    margin-right: 10px;
    margin-bottom: 30px;
    margin-left: 100px;
  }
</style>
...
<div>아무런 margin 속성값도 설정하지 않은 요소입니다.</div><br>
<div class="mar">margin 속성값을 각 측면마다 별도로 지정한 요소입니다.</div>
```

![image](https://user-images.githubusercontent.com/43658658/127593583-00c2bd8a-adb6-4d99-b0c7-d1f2dd635415.png)

margin 속성값을 inherit로 설정하면, 부모(parent) 요소의 margin 속성값을 그대로 물려받습니다.

``` html
<style>
  div {
    background-color: #7FFFD4;
    border: 2px solid teal;
  }
  div.A {
    height: 100px;
    margin-left: 100px;
  }
  div.B {
    background-color: #FFF8DC;
    margin-left: inherit;
  }
</style>
...
<div>아무런 margin 속성값도 설정하지 않은 요소입니다.</div><br>
<div class="A">left-margin 속성값을 100px로 설정한 요소입니다.
  <div class="B">left-margin 속성값을 inherit로 설정한 요소입니다.</div>
</div>
```

`class="A"` 내에 `class="B"`가 속해있으므로 A는 부모 요소 B는 자식 요소입니다.

![image](https://user-images.githubusercontent.com/43658658/127594252-35624ac3-5b0e-4794-bccb-1a92e1a06727.png)

> <h3>마진 축약 표현(margin shorthand)</h3>

모든 margin 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

`padding`의 원리와 같습니다. 4개, 3개, 2개, 1개를 설정할 수 있습니다.

top부터 시계방향 순으로 top, right, bottom, left 순입니다.

> <h3>margin 속성값에 auto를 사용하는 이유</h3>

margin 속성값을 auto로 설정하면, 웹 브라우저가 수평 방향 마진(margin) 값을 자동으로 설정합니다.

즉, 해당 HTML 요소의 왼쪽과 오른쪽 마진을 자동으로 설정하게 됩니다.

그 결과 해당 요소는 그 요소를 포함하고 있는 부모(parent) 요소의 정중앙에 위치하게 됩니다.

``` html
<style>
  div {
    border: 2px solid teal;
    width: 350px;
        height:100px;
    margin: auto;
  }
    div.A {
      width: 150px;
      height:20px;
      text-align: center;
    }
</style>
...
<div>margin 속성값을 auto로 설정한 요소입니다.
  <div class="A">가운데</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127594756-9700a65f-3af1-4b99-83ea-72b285a99f4b.png)

첫 번째 `<div>`요소는 부모 요소가 `<body>`이므로 페이지의 좌우 중앙에 놓입니다.

두 번째 `<div class="A">`요소는 부모 요소가 `<div>`이므로 `<div>`요소의 좌우 중앙에 놓입니다.

## 아웃라인

outline 속성은 HTML 요소의 가장 바깥 부분을 둘러싸고 있는 아웃라인 부분의 스타일을 설정합니다.

즉, border(테두리)의 바로 바깥이자 margin(마진)의 안쪽에 위치합니다.

이 속성은 border 속성과 마찬가지로 style, width, color 속성을 가집니다.

 

하지만 outline 속성은 border 속성과는 달리 HTML 요소의 전체 크기에는 포함되지 않습니다.

HTML 요소의 높이나 너비는 outline의 두께에 전혀 영향을 받지 않습니다.

> <h3>outline-style 속성</h3>

outline-style 속성을 이용하면 아웃라인(outline)을 다양한 모양으로 설정할 수 있습니다.

익스플로러 8과 그 이전 버전에서는 HTML 문서에 `<!DOCTYPE html>`태그가 삽입되어 있어야 outline 속성이 제대로 표현됩니다. 

1. dotted : 아웃라인을 점선으로 설정함.

2. dashed : 아웃라인을 약간 긴 점선으로 설정함.

3. solid : 아웃라인을 실선으로 설정함.

4. double : 아웃라인을 이중 실선으로 설정함.

5. groove : 아웃라인을 3차원인 입체적인 선으로 설정하며, outline-color 속성값에 영향을 받음.

6. ridge : 아웃라인을 3차원인 능선효과가 있는 선으로 설정하며, outline-color 속성값에 영향을 받음.

7. inset : 3차원인 내지로 끼운 선으로 설정하며, outline-color 속성값에 영향을 받음.

8. outset : 3차원인 외지로 끼운 선으로 설정하며, outline-color 속성값에 영향을 받음.

9. none : 아웃라인(outline)을 없앰.

10. hidden : 아웃라인(outline)이 존재하기는 하지만 표현되지는 않음.

``` html
<style>
  p {
    border: 1px solid black;
    outline-color: red;
  }
  p.dotted {outline-style: dotted;}
  p.dashed {outline-style: dashed;}
  p.solid {outline-style: solid;}
  p.double {outline-style: double;}
  p.groove {outline-style: groove;}
  p.ridge {outline-style: ridge;}
  p.inset {outline-style: inset;}
  p.outset {outline-style: outset;}
  p.none {outline-style: none;}
  p.hidden {outline-style: hidden;}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127595166-7fce4845-f734-4ae2-ab58-14d4074a44c1.png)

> <h3>outline-width 속성</h3>

outline-width 속성은 아웃라인(outline)의 두께를 설정합니다.

px, em, cm 등과 같은 CSS 크기 단위를 이용하여 두께를 직접 설정할 수 있습니다.

또한, 미리 설정해 놓은 예약어인 thin, medium, thick을 사용하여 설정할 수도 있습니다.

``` html
<style>
    p.solidA { outline-style: solid; outline-color: violet; outline-width: 2px; }
    p.solidB { outline-style: solid; outline-color: coral; outline-width: 7px; }
    p.dashedA { outline-style: dashed; outline-color: violet; outline-width: thin; }
    p.dashedB { outline-style: dashed; outline-color: coral; outline-width: thick; }
</style>
```

> <h3>outline-color 속성</h3>

outline-color 속성은 아웃라인(outline)의 색상을 설정합니다.

기본적인 color 속성값들뿐만 아니라 색반전을 나타내는 invert 속성값을 사용할 수 있습니다.

또한, invert 속성값은 배경색과 상관없이 아웃라인을 보여주기 위한 색반전을 설정합니다.

``` html
<style>
  p {
    border: 1px solid black;
    outline-style: dashed;
  }
  p.red { outline-color: red; }
  p.green { outline-color: rgb(0,255,0); }
  p.blue { outline-color: #0000FF; }
  p.invert { outline-color: invert; }
</style>
```

> <h3>아웃라인 축약 표현(outline shorthand)</h3>

모든 outline 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

border와 마찬가지의 형식으로 지정된 순서에 맞게 작성해야 합니다.

1. outline-width
2. outline-style
3. outline-color

``` html
<style>
    p { border: 1px solid black; }
    p.none { border-style: none; }
    p.good { outline: 3px solid teal; }
    p.wrong { outline: 5px teal; }
</style>
```

+ outline은 개별 설정을 할 수 없습니다.
