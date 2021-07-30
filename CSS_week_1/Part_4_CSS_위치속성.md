# Part 4. CSS 위치 속성

+ [디스플레이](#디스플레이)
+ [포지션](#포지션)
+ [Float](#Float)
+ [정렬](#정렬)

## 디스플레이

> <h3>display 속성</h3>

display 속성은 웹 페이지의 레이아웃(layout)을 결정하는 CSS의 중요한 속성 중 하나입니다.

이 속성은 해당 HTML 요소가 웹 브라우저에 언제 어떻게 보이는가를 결정합니다.


대부분의 HTML 요소는 display 속성의 기본값으로 다음 두 가지 값 중 하나의 값을 가집니다.

 

1. 블록(block)

2. 인라인(inline)

> <h3>display 속성의 기본 설정값의 변경</h3>

HTML의 모든 요소는 각각의 기본 display 속성값을 가지고 있습니다.

하지만 display 속성값이 블록인 요소의 속성값을 인라인으로 바꿀 수 있습니다.

또한, 반대로 display 속성값이 인라인인 요소의 속성값을 블록으로 바꿀 수도 있습니다.


이렇게 HTML 요소의 display 속성값을 변경함으로써 웹 페이지를 개발자가 원하는 모양으로 변경할 수 있습니다.

``` html
<style>
  li { display: inline; }
</style>
...
<ul class="circle">
  <li><a href="/html/intro">HTML</a></li>
  <li><a href="/css/intro">CSS</a></li>
  <li><a href="/javascript/intro">자바스크립트</a></li>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/127608573-3bb8704e-6633-4502-bb2c-b6f32732320d.png)

위의 예제에서 블록 요소인 `<li>`요소의 display 속성값을 인라인으로 변경하고 있습니다.

display 속성값이 인라인으로 변경된 `<li>`요소는 해당 라인의 모든 너비를 차지하는 블록 요소의 특징을 잃어버리게 됩니다.

 

display 속성값을 변경해도, 실제로 해당 요소가 완전히 다른 타입의 요소로 바뀌는 것은 아닙니다.

즉, display 속성값을 인라인에서 블록으로 변경했더라도, 변경된 요소는 내부에 다른 요소를 포함할 수 없습니다.

왜냐하면, 처음부터 display 속성값이 블록인 요소만이 내부에 다른 요소를 포함할 수 있기 때문입니다.

> <h3>인라인-블록(inline-block)</h3>

인라인과 블록 이외에도 display 속성에 자주 사용되는 속성값에는 인라인-블록(inline-block)이 있습니다.

display 속성값이 인라인-블록으로 설정된 요소는 해당 요소 자체는 인라인(inline) 요소처럼 동작합니다.

하지만 해당 요소 내부에서는 블록(block) 요소처럼 동작합니다.

 

이처럼 인라인-블록 요소는 인라인 요소와 비슷하지만, 너비와 높이를 설정할 수 있습니다.

또한, 블록 요소처럼 margin을 이용하여 여백을 지정할 수도 있게 됩니다.

 

다음 예제는 다양한 display 속성값의 동작을 보여주는 예제입니다.

``` html
<style>
    div { width:100px; height:50px; }
  
    .first { background-color:aqua; }
    .second { background-color:green; }
    .third { background-color:yellow; }

    .inline { display:inline; }
    .inlineBlock { display:inline-block; }
</style>
...
<p>아래에 나오는 div 요소는 모두 display 속성값이 블록입니다.</p>
<div class="first">블록</div>
<div class="second">블록</div>
<div class="third">블록</div>
<br>
<p>아래에 나오는 div 요소는 모두 display 속성값이 인라인입니다.</p>
<div class="first inline">인라인</div>
<div class="second inline">인라인</div>
<div class="third inline">인라인</div>
<br><br>
<p>아래에 나오는 div 요소는 모두 display 속성값이 인라인-블록입니다.</p>
<div class="first inlineBlock">인라인-블록</div>
<div class="second inlineBlock">인라인-블록</div>
<div class="third inlineBlock">인라인-블록</div>
```

![image](https://user-images.githubusercontent.com/43658658/127609335-fc96b69b-1807-4c14-a57d-33978ebbe55c.png)

위의 예제처럼 display 속성값이 인라인-블록으로 설정된 요소들은 인라인 요소처럼 한 줄로 늘어서게 됩니다.

하지만 블록 요소처럼 너비와 높이를 설정할 수 있게 됩니다.

따라서 웹 사이트의 `메뉴`나 `내비게이션 바`를 만들 때 자주 사용됩니다.

> <h3>visibility 속성</h3>

visibility 속성은 HTML 요소가 웹 페이지에 표현될지 아닐지만을 결정합니다.

따라서 웹 페이지에는 나타나지 않더라도 레이아웃 내에는 여전히 존재하게 되며, 코드 내에도 당연히 존재하게 됩니다.

visibility 속성을 자바스크립트와 함께 사용하면 매우 복잡한 메뉴나 레이아웃을 손쉽게 만들 수 있습니다.

 

visibility 속성에 사용할 수 있는 속성값은 다음과 같습니다.

 

1. visible : 해당 HTML 요소를 웹 페이지에 나타냅니다.

2. hidden : HTML 요소를 웹 페이지에 나타내지 않습니다. 하지만 여전히 웹 페이지의 레이아웃에는 존재합니다.

3. collapse : 이 속성값은 동적인 테이블에서만 사용할 수 있으며, 테이블의 테두리를 한 줄만 보여줍니다.

따라서 민감하거나 귀중한 데이터를 visibility 속성을 이용하여 감추는 것은 바람직하지 못합니다.

``` html
<style>
  div {
    background-color: ivory;
    border: 2px solid black;
  }
  p.none { display: none; }
  p.hidden { visibility: hidden; }
</style>
...
<div>
  <p>이 아래의 단락은 display 속성값을 none으로 설정했습니다</p>
  <p class="none">이 단락은 display 속성값을 none으로 설정했습니다.</p>
</div><br>
<div>
  <p>이 아래의 단락은 visibility 속성값을 hidden으로 설정했습니다.</p>
  <p class="hidden">이 단락은 visibility 속성값을 hidden으로 설정했습니다.</p>
</div>
<p>visibility 속성값을 hidden으로 설정하면 눈에 보이지만 않을 뿐 여전히 웹 페이지 내에 존재하게 됩니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127609635-61620fd3-3960-4318-8fac-b357598eaa25.png)

> <h3>opacity 속성</h3>

opacity 속성을 이용하면 HTML 요소의 투명도를 간단히 조절할 수 있습니다.

opacity 속성값은 0.0부터 1.0까지 설정할 수 있으며, 속성값이 0에 가까울수록 투명한 상태가 됩니다.

익스플로러 8과 그 이전 버전에서는 투명도를 표현하기 위해 다음과 같은 문법을 사용합니다.

`filter:alpha(opacity=x)`

여기서 x값은 0부터 100까지 설정할 수 있으며, x값이 0에 가까울수록 투명한 상태가 됩니다.

 

다음 예제는 대부분의 웹 브라우저뿐만 아니라 익스플로러 8과 그 이전 버전에서도 투명도를 정확하게 표현하는 예제입니다.

``` html
<style>
    img {
      opacity: 0.4;
      filter:alpha(opacity=40);
    }
    img:hover{
      opacity: 1.0;
      filter:alpha(opacity=100);
    }
</style>
...
<img src="/examples/images/img_flower.png" width="350" height="263" alt="flower">
<p>opacity 속성값을 조절하면 간단히 이미지를 투명하게 만들 수 있어요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127611221-23a2693d-490a-4ee4-969c-6b3c9e426b8d.png)

## 포지션

> <h3>position 속성</h3>

position 속성은 HTML 요소가 위치를 결정하는 방식을 설정합니다.

CSS에서 요소의 위치를 결정하는 방식에는 다음과 같이 4가지 방식이 있습니다.

 

1. 정적 위치(static position) 지정 방식

2. 상대 위치(relative position) 지정 방식

3. 고정 위치(fixed position) 지정 방식

4. 절대 위치(absolute position) 지정 방식

> <h3>정적 위치(static position) 지정 방식</h3>

HTML 요소의 위치를 결정하는 가장 기본적인 방식은 정적 위치(static position) 지정 방식입니다.

position 속성값이 static으로 설정된 요소는 top, right, bottom, left 속성값에 영향을 받지 않습니다.

정적 위치(static position) 지정 방식은 단순히 웹 페이지의 흐름에 따라 차례대로 요소들을 위치시키는 방식입니다.

``` html
<style>
  div {
    border: 2px solid #CD5C5C;
    position: static;
  }
</style>
...
<div>이 요소는 정적 위치 지정 방식으로 위치를 설정하였습니다.</div>
<p>정적 위치는 단순히 웹 페이지의 흐름에 따라 차례대로 요소들을 위치시키는 방식입니다!</p>
```

모든 HTML 요소의 position 속성의 기본 설정값은 static입니다.

> <h3>상대 위치(relative position) 지정 방식</h3>

상대 위치(relative position) 지정 방식은 해당 HTML 요소의 기본 위치를 기준으로 위치를 설정하는 방식입니다.

HTML 요소의 기본 위치란 해당 요소가 정적 위치(static position) 지정 방식일 때 결정되는 위치를 의미합니다.

``` html
<style>
  div.static {
    border: 2px solid #B8860B;
    position: static;
  }
  div.relative {
    border: 2px solid #CD5C5C;
    position: relative;
    left: 30px;
  }
</style>
...
<div class="static">이 요소는 정적 위치 지정 방식으로 위치를 설정하였습니다.</div><br>
<div class="relative">이 요소는 상대 위치 지정 방식으로 위치를 설정한 후, left 속성값을 30px로 설정하였습니다.</div><br>
<p>상대 위치는 해당 HTML 요소의 정적 위치(static position)에 따라 위치를 재조정하는 방식입니다!</p>
```

> <h3>고정 위치(fixed position) 지정 방식</h3>

고정 위치(fixed position) 지정 방식은 뷰포트(viewport)를 기준으로 위치를 설정하는 방식입니다. 

 

즉, 웹 페이지가 스크롤 되어도 고정 위치로 지정된 요소는 항상 같은 곳에 위치하게 됩니다.

``` html
<style>
  div.fixed {
    border: 2px solid #B8860B;
    width: 450px;
    position: fixed;
    top: 0;
    right: 0;
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127612869-5111e2bd-3e7c-47da-b35c-55137084ada1.png)

스크롤을 내려도 황토색 박스 문구는 고정되어있는 것을 확인할 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127612913-c834eba5-6db7-4c16-a39e-cb2e63dea63e.png)

> <h3>절대 위치(absolute position) 지정 방식</h3>

절대 위치(absolute position) 지정 방식은 고정 위치가 뷰포트를 기준으로 위치를 결정하는 것과 비슷하게 동작합니다.

단지 뷰포트(viewport)를 기준으로 하는 것이 아닌 위치가 설정된 조상(ancestor) 요소를 기준으로 위치를 설정하게 됩니다.

하지만 위치가 설정된 조상(ancestor) 요소를 가지지 않는다면, HTML 문서의 body 요소를 기준으로 위치를 설정하게 됩니다.

위치가 설정된 요소라는 것은 정적 위치(static position) 지정 방식을 제외한 다른 방식(`relative, fixed, absolute`)으로 위치가 설정된 요소를 의미합니다.

``` html
<style>
  div.relative {
    border: 2px solid #B8860B;
    width: 500px;
    height: 200px;
    position: relative;
  } 
  div.absolute {
    border: 2px solid #006400;
    width: 200px;
    height: 100px;
    position: absolute;
    top: 50px;
    right: 0;
  }
</style>
...
<div class="relative">이 요소는 상대 위치 지정 방식으로 위치를 설정하였습니다.
  <div class="absolute">이 요소는 절대 위치 지정 방식으로 위치를 설정한 후, top 속성값을 50px로 설정하였습니다.</div>
</div>
<div class="absolute">이 요소는 절대 위치 지정 방식으로 위치를 설정한 후, top 속성값을 50px로 설정하였습니다.</div>
<p>절대 위치는 해당 요소의 바로 상위의 위치가 설정된 조상(ancestor) 요소에 따라 위치를 재조정하는 방식입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127613163-01a8ed6a-cffd-400e-8839-d1c90b436697.png)

위의 결과를 보면 `relative` 클래스 내에 들어있는 `absolute` 클래스 요소는 `relative`를 기준으로 위에서 50px 떨어져있습니다.

반면, 그냥 `absolute` 클래스 요소는 `<body>`에 속해있게 되는 것이므로 전체 페이지를 기준으로 위에서 50px 떨어져있습니다.

> <h3>정적 위치(static position) 지정 방식과 다른 방식들과의 차이점</h3>

정적 위치(static position) 지정 방식을 제외한 나머지 다른 방식(relative, fixed, absolute)들은 전부 어떤 기준에 대해 해당 요소의 상대적인 위치를 설정하는 방식입니다.

- 상대 위치(relative position) : 해당 요소가 정적 위치 지정 방식일 때의 위치에 상대적으로 위치함.

- 고정 위치(fixed position) : 뷰포트(viewport)에 상대적으로 위치함.

- 절대 위치(absolute position) : 위치가 설정된 바로 상위의 조상(ancestor) 요소에 상대적으로 위치함.

``` html
<style>
  .container {
    border: 3px solid red;
    width: 100%;
    height: 1000px;
    position: relative;
  }
  .position {
    width: 150px;
    height: 50px;
    top: 100px;
    left: 120px;
  }
  .static {
    border: 3px solid black;
    position: static;
  }
  .relative {
    border: 3px solid green;
    position: relative;
  }
  .fixed {
    border: 3px solid orange;
    position: fixed;
  }
  .absolute {
    border: 3px solid blue;
    position: absolute;
  }
</style>
...
<h1>정적 위치(static position) 지정 방식의 특징</h1>
<div class="container">
  <div class="static position">정적 위치(static position)</div>
  <div class="relative position">상대 위치(relative position)</div>
  <div class="fixed position">고정 위치(fixed position)</div>
  <div class="absolute position">절대 위치(absolute position)</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127614290-c1f9fc1e-ead3-4d9b-b222-6ea38ad288a7.png)

> <h3>position: sticky</h3>

sticky 역시 fixed와 마찬가지로 스크롤을 움직이면 해당 자리에 고정됩니다.

단, fixed와의 가장 큰 차이점은 sticky는 스크롤을 움직여서 sticky가 적용된 요소가 화면을 벗어나기 전까지는

해당 위치에 계속 있다가 화면을 벗어나는 순간 고정이 된다는 것입니다.

fixed는 뷰포트를 기준으로 하기 때문에 처음부터 그 위치에 고정되어 있습니다.

``` html
<style>
div.sticky {
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
  padding: 5px;
  background-color: #cae8ca;
  border: 2px solid #4CAF50;
}
</style>
...
<p>Try to <b>scroll</b> inside this frame to understand how sticky positioning works.</p>

<div class="sticky">I am sticky!</div>

<div style="padding-bottom:2000px">
  <p>In this example, the sticky element sticks to the top of the page (top: 0), when you reach its scroll position.</p>
  <p>Scroll back up to remove the stickyness.</p>
  <p>Some text to enable scrolling.. Lorem ipsum dolor sit amet, illum definitiones no quo, maluisset concludaturque et eum, altera fabulas ut quo. Atqui causae gloriatur ius te, id agam omnis evertitur eum. Affert laboramus repudiandae nec et. Inciderint efficiantur his ad. Eum no molestiae voluptatibus.</p>
  <p>Some text to enable scrolling.. Lorem ipsum dolor sit amet, illum definitiones no quo, maluisset concludaturque et eum, altera fabulas ut quo. Atqui causae gloriatur ius te, id agam omnis evertitur eum. Affert laboramus repudiandae nec et. Inciderint efficiantur his ad. Eum no molestiae voluptatibus.</p>
</div>
```

처음에는 정적 위치에 존재하다가

![image](https://user-images.githubusercontent.com/43658658/127616463-665dd37d-c11b-482b-94a1-032181fcfc9a.png)

스크롤을 내려서 화면 밖으로 벗어나는 순간 상단에 고정됩니다.

![image](https://user-images.githubusercontent.com/43658658/127616499-980bdfff-c722-41af-9217-23bb77c49e6f.png)


> <h3>z-index 속성</h3>

HTML 요소의 위치를 설정하게 되면 어떤 요소들은 설정된 위치 및 방식에 따라 서로 겹칠 수도 있습니다.

z-index 속성은 이렇게 겹쳐지는 요소들이 쌓이는 스택(stack)의 순서를 설정합니다.

스택(stack)의 순서는 양수나 음수 모두 설정할 수 있으며, 크기가 클수록 앞쪽에 위치하고 작을수록 뒤쪽에 위치하게 됩니다.

``` html
<style>
  .position {
    width: 180px;
    height: 50px;
  }
  .static {
    background-color: lightblue;
    position: static;
  }
  .first {
          background-color: orange;
    position: fixed;
    top: 90px;
    left: 120px;
  }
  .last {
          background-color: orange;
    position: fixed;
    top: 180px;
    left: 120px;
    z-index: -1;
  }
</style>
...
<h1>z-index 속성을 이용한 노출 순서 변경</h1>
<div>
  <div class="static position">정적 위치(static position)</div>
  <div class="first position">고정 위치(fixed position)</div>
</div>
<br><br>
<div>
  <div class="static position">정적 위치(static position)</div>
  <div class="last position">고정 위치(fixed position)</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127614862-17c7ea23-071a-4f6a-ae55-2332f152c914.png)

## float

> <h3>float 속성</h3>

float 속성은 해당 HTML 요소가 주변의 다른 요소들과 자연스럽게 어울리도록 만들어 줍니다.

이 속성은 본래 위와 같은 목적으로 만들어졌지만, 현재는 웹 페이지의 레이아웃(layout)을 작성할 때 자주 사용됩니다.


다음 예제는 이미지와 글자를 함께 출력하는 예제입니다.

``` html
<style>
 img {
  float: left;
  margin-right: 20px;
 }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127625769-70a489a9-1b40-41c8-9afa-e27e425de898.png)

> <h3>clear 속성</h3>

clear 속성은 float 속성이 적용된 이후 나타나는 요소들의 동작을 조절해 줍니다.

컨테이너 요소에 float 속성이 적용되면 그 이후에 등장하는 모든 요소들은 정확한 위치를 설정하기가 매우 힘들어집니다.

``` html
<style>
 .left {
  background-color: #FF8C00;
  width: 150px;
  height: 50px; 
  float: left;
 }
 .right {
  background-color: #9932CC;
  width: 150px;
  height: 50px; 
  float: right;
 }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127625880-39120d0e-45af-4382-9d88-af747ce50320.png)

따라서 float 속성을 적용하고자 하는 요소가 모두 등장한 이후에는 clear 속성을 사용하여, 이후에 등장하는 요소들이 더는 flaot 속성에 영향을 받지 않도록 설정해줘야 합니다.

``` html
<style>
 .left {
  background-color: #FF8C00;
  width: 150px;
  height: 50px; 
  float: left;
 }
 .right {
  background-color: #9932CC;
  width: 150px;
  height: 50px; 
  float: right;
 }
 p { clear: both; }
</style>
...
<h1>clear 속성을 이용한 위치 조정</h1>
<div>
 <div class="left">왼쪽 끝에 위치하고 싶은 요소</div>
 <div class="right">오른쪽 끝에 위치하고 싶은 요소</div>
</div>
<p>이 글자를 아래쪽에 제대로 출력하고 싶어요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127625991-446ac576-d541-4676-a950-c0b18292726e.png)

> <h3>overflow 속성</h3>

float 속성이 적용된 HTML 요소가 자신을 감싸고 있는 컨테이너 요소보다 크면, 해당 요소의 일부가 밖으로 흘러넘치게 됩니다.

이때 overflow 속성값을 auto로 설정하면, 컨테이너 요소의 크기가 자동으로 내부의 요소를 감쌀 수 있을 만큼 커지게 됩니다.

``` html
<style>
     div {
       border:3px solid green;
       padding: 5px;
     }
     p { clear: both; }
     img { float:left; margin-right: 5px; }
     .good { overflow:auto; }
 </style>
...
<h1>overflow 속성을 이용한 크기 조정</h1>
<div>이미지와 함께 하고 싶은 내용
 <img src="/examples/images/img_flower.png" alt="flower" width="245" height="185">
</div>
<p id="second"><br>overflow 속성값을 auto로 주면 자동으로 컨테이너 요소의 크기도 함께 늘어납니다!</p>
<div class="good">이미지와 함께 하고 싶은 내용
 <img src="/examples/images/img_flower.png" alt="flower" width="245" height="185">
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127626683-ba3340a1-4878-4557-934b-9cbdc020dee5.png)

> <h3>float 속성을 이용한 레이아웃</h3>

현재 웹 페이지의 레이아웃은 대부분 float 속성을 이용하여 작성되고 있습니다.

다음 예제는 float 속성을 이용해 작성된 레이아웃을 보여줍니다.

``` html
<style>
 div.page {
  border: 3px solid #CD5C5C;
  overflow: auto;
 }
 h2 { text-align: center; }
 header{ border: 3px solid #FFD700; }
 nav {
  border: 3px solid #FF1493;
  width: 150px;
  float: left;
 }
 section {
  border: 3px solid #00BFFF;
  margin-left: 156px;
 }
 footer{ border: 3px solid #00FA9A; }
</style>
...
<div class="page">

 <header>
  <h2>header 영역</h2>
 </header>
 <nav>
  <h2>nav 영역</h2>
  <p>여기에는 보통 메뉴가 들어갑니다.</p>
 </nav>
 <section>
  <h2>section 영역</h2>
  <p>여기에는 페이지에 해당하는 내용이 들어갑니다.<br>
   Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ornare sapien suscipit tincidunt ullamcorper. Cras ac sem sed mauris maximus rhoncus vel in metus. Nam pharetra arcu sit amet dolor interdum, eget scelerisque libero finibus. Phasellus quis vulputate ante. Fusce sit amet viverra justo. Donec id elementum mauris. Nam id porttitor nisl, et suscipit nunc. Vestibulum sit amet volutpat quam. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Duis placerat sem eu facilisis ultricies.
  </p>
 </section>
 <footer>
  <h2>footer 영역</h2>
 </footer>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127627176-343bd4dc-edbe-4a95-bbaa-389d5485553f.png)

## 정렬

> <h3>정렬(align)</h3>

블록(block) 타입의 요소를 정렬하기 위해서는 다음과 같은 방법을 사용할 수 있습니다.

 

1. margin 속성을 이용한 가운데 정렬

2. position 속성을 이용한 좌우 정렬

3. float 속성을 이용한 좌우 정렬

> <h3>margin 속성을 이용한 가운데 정렬</h3>

margin 속성값을 auto로 설정하면, 해당 요소를 감싸고 있는 컨테이너 요소를 기준으로 수평 방향 가운데 정렬이 됩니다.

 

이때 해당 요소는 특정한 너비를 가져야 하며, 너비를 제외한 나머지 공간은 좌우로 균등하게 나뉘어 여백으로 만들어집니다.

따라서 이 방법을 사용하기 위해서는 반드시 해당 요소의 width 속성값을 먼저 설정해야만 합니다.

익스플로러 8과 그 이전 버전에서는 HTML 문서에 `<!DOCTYPE html>`태그가 삽입되어 있어야 margin 속성이 제대로 표현됩니다.

``` html
<style>
    div { width: 300px; margin: auto; }
</style>
```

> <h3>position 속성을 이용한 좌우 정렬</h3>

절대 위치 지정 방식으로 위치한 요소는 정상적인 레이아웃에서 벗어나 다른 요소와 겹칠 수 있게 됩니다.

따라서 이 특성을 이용하면 HTML 요소를 수평 방향으로 좌우 정렬할 수 있습니다.

 

position 속성을 이용하여 정렬할 경우에는 `<body>`요소에 margin과 padding 속성값을 설정하는 것이 좋습니다.

이렇게 함으로써 웹 브라우저마다 레이아웃이 다르게 보이는 것을 미리 방지할 수 있습니다.

익스플로러 8과 그 이전 버전에서는 HTML 문서에 `<!DOCTYPE html>`태그가 삽입되어 있어야 position 속성이 제대로 표현됩니다.

``` html
<style>
 body {  /* 웹 브라우저마다 레이아웃이 다르게 보이는 것을 방지 */
  padding: 0;
  margin: 0;
 }
 div {
  border: 3px solid #4B0082;
  width: 300px;
  padding: 10px;
  margin: 0;
  position: absolute;
  right: 0;
 }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127627826-53cd65c0-7abb-4e3f-953e-7e6f8191da2b.png)

> <h3>float 속성을 이용한 좌우 정렬</h3>

float 속성을 이용하면 수평 방향으로 좌우 정렬할 수 있습니다.

 

float 속성을 이용하여 정렬할 경우에는 `<body>`요소에 margin과 padding 속성값을 설정하는 것이 좋습니다.

이렇게 함으로써 웹 브라우저마다 레이아웃이 다르게 보이는 것을 미리 방지할 수 있습니다.

익스플로러 8과 그 이전 버전에서는 HTML 문서에 <!DOCTYPE html>태그가 삽입되어 있어야 float 속성이 제대로 표현됩니다.

``` html
<style>
 body { /* 웹 브라우저마다 레이아웃이 다르게 보이는 것을 방지 */
  padding: 0;
  margin: 0;
 }
 div {
  border: 3px solid #4B0082;
  width: 350px;
  padding: 10px;
  margin: 0;
 }
 div.left { float: left }
 div.right { float: right }
</style>
...
<h1>float 속성을 이용한 좌우 정렬</h1>
<div class="left">float 속성값으로 left 또는 right를 사용하면,<br>
수평으로 좌우 정렬을 할 수 있어요!
</div>
<div class="right">float 속성값으로 left 또는 right를 사용하면,<br>
수평으로 좌우 정렬을 할 수 있어요!
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127628068-491ab19e-4325-4543-ad18-52d5bc5e815e.png)
