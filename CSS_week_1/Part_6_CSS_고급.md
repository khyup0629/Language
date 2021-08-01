# Part 6. CSS 고급

+ [내비게이션 바(navigation bar)](#내비게이션-바navigation-bar)
+ [드롭다운](#드롭다운)
+ [툴팁](#툴팁)
+ [Form 요소](#Form-요소)
+ [@규칙](#규칙)

## 내비게이션 바(navigation bar)

사용자가 웹 사이트에서 가장 많이 클릭하는 영역 중 하나가 바로 내비게이션 바입니다.

내비게이션 바(navigation bar)는 우리가 흔히 사용하는 웹 사이트의 메뉴를 의미합니다.

HTML 요소만으로 만든 단순한 메뉴에 CSS를 이용하면, 보기에도 이쁘고 쓰기도 편리한 메뉴로 손쉽게 바꿀 수 있습니다.

> <h3>링크를 사용한 리스트 메뉴</h3>

내비게이션 바 중에서도 가장 기본적인 것이 바로 링크(link)를 사용한 리스트 메뉴입니다.

HTML에서 링크는 `<a>`태그로 표현합니다.

 

다음 예제는 링크를 사용하여 구현한 간단한 메뉴 예제입니다.

``` html
<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
</style>
...
<ul>
  <li><a href="/index.php">Home</a></li>
  <li><a href="/html/intro">HTML</a></li>
  <li><a href="/css/intro">CSS</a></li>
  <li><a href="/javascript/intro">자바스크립트</a></li>
</ul>
```

> <h3>수직 내비게이션 바</h3>

링크를 사용한 리스트 메뉴에 display 속성값을 block으로 설정하면, 간단히 수직 내비게이션 바를 만들 수 있습니다.

예제에서 인라인 요소인 `<a>`요소의 display 속성값을 블록(block)으로 변경하면, 메뉴의 어느 곳을 클릭하더라도 바로 연결된 페이지로 넘어가게 설정됩니다.
  
``` html
<style>
  ul {
    background-color: #FFDAB9;
    width: 150px;
    list-style-type: none;
    margin: 0;
    padding: 0;
        border: 3px solid #CD853F;
  }
  li a {
    display: block;
    color: #CD853F;
    padding: 8px;
    text-decoration: none;
    font-weight: bold;

  }
  li a:hover {
    background-color: #CD853F;
    color: white;
  }
</style>
...
<ul>
  <li><a href="/index.php">Home</a></li>
  <li><a href="/html/intro">HTML</a></li>
  <li><a href="/css/intro">CSS</a></li>
  <li><a href="/javascript/intro">자바스크립트</a></li>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/127739612-c70a75c7-d53b-4caf-b8fa-d9a91637d24d.png)

클래스(class)를 이용하면 내비게이션 바에서 현재 메뉴의 위치도 표현할 수 있습니다.

``` html
<style>
  ul {
    background-color: #FFDAB9;
    width: 150px;
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  li a {
    display: block;
    color: #000000;
    padding: 8px;
    text-align: center;
    text-decoration: none;
    font-weight: bold;
  }
  li a.current {
    background-color: #FF6347;
    color: white;
  }
  li a:hover:not(.current) {
    background-color: #CD853F;
    color: white;
  }
</style>
...
<ul>
  <li><a href="/index.php">Home</a></li>
  <li><a class="current" href="/html/intro">HTML</a></li>
  <li><a href="/css/intro">CSS</a></li>
  <li><a href="/javascript/intro">자바스크립트</a></li>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/127739757-a75d9aa1-418f-4671-ac07-d71097507da0.png)

위의 예제에서는 `:not` 선택자를 이용하여 현재 메뉴를 나타내는 current 클래스와 그 외의 메뉴의 배경색을 구분하고 있습니다.


border 속성을 이용하면 내비게이션 바에 경계선을 표현할 수 있습니다.

``` html
<style>
  ul {
    background-color: #FFDAB9;
    width: 150px;
    list-style-type: none;
    margin: 0;
    padding: 0;
    border: 1px solid black;
  }
    li { border-bottom: 1px solid black; }
    li:last-child { border-bottom: none; }
  li a {
    display: block;
    color: #000000;
    padding: 8px;
    text-align: center;
    text-decoration: none;
    font-weight: bold;
  }
  li a.current {
    background-color: #FF6347;
    color: white;
  }
  li a:hover:not(.current) {
    background-color: #CD853F;
    color: white;
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127739820-5926bc79-5e0e-4b20-bd74-2586e86b9e84.png)

> <h3>수평 내비게이션 바</h3>

수평 내비게이션 바는 다음과 같은 속성을 이용해 만들 수 있습니다.

1. display 속성의 inline 속성값을 이용한 방법

2. floating 속성을 이용한 방법

> <h3>display 속성의 inline 속성값을 이용한 방법</h3>

링크를 사용한 리스트 메뉴에서 `<li>`요소의 display 속성값을 inline으로 설정합니다.

그러면 블록 요소였던 `<li>`요소가 인라인 요소의 성질을 갖도록 변경됩니다.

 

인라인 요소로 변경된 `<li>`요소는 너비가 자신의 내용만큼만을 차지하도록 변경됩니다.

따라서 모든 `<li>`요소가 수평으로 늘어서게 되며, 이것을 이용하여 수평 내비게이션 바를 만들게 됩니다.

``` html
<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  li { display: inline; }
</style>
```

> <h3>floating 속성을 이용한 방법</h3>

링크를 사용한 리스트 메뉴의 `<li>`요소에 float 속성을 설정합니다.

 

이때 float 속성값을 left로 설정하면, 모든 메뉴가 왼쪽으로 정렬됩니다.

또한, float 속성값을 right로 설정하면, 모든 메뉴가 오른쪽으로 정렬됩니다.

``` html
<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  li { float: left; border: 1px solid black; border-right: none;}
    li:last-child {border-right:1px solid black;}
  li a {
    display: block;
    background-color: #FFDAB9;
    padding: 8px;
  }
</style>
...
<ul>
  <li><a href="/index.php">Home</a></li>
  <li><a href="/html/intro">HTML</a></li>
  <li><a href="/css/intro">CSS</a></li>
  <li><a href="/bbs/login.php">로그인</a></li>
  <li><a href="/bbs/register_form.php">회원가입</a></li>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/127740194-984b78f8-ff79-4269-b9f5-ac3be569e7e4.png)

CSS를 이용하면 수평 내비게이션 바에 여러 가지 스타일을 설정할 수 있습니다.

``` html
<style>
  ul {
    background-color: #FFDAB9;
    list-style-type: none;
    margin: 0;
    padding: 0;
        overflow: hidden; /* 내비게이션 바의 배경을 가로로 꽉 채워주는 역할 */
  }
  li { float: left;  }
  li a {
    display: block;
    background-color: #FFDAB9;
    color: #000000;
    padding: 8px 50px;
    text-decoration: none;
    text-align: center;
    font-weight: bold;

  }
  li a:hover {
    background-color: #CD853F;
    color: white;
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127740386-fcb2742b-8b1f-42c5-bfbc-8e4741095b09.png)

클래스(class)를 이용하면 내비게이션 바에서 현재 메뉴의 위치도 표현할 수 있습니다.

``` html
<style>
    ul { background-color: #FFDAB9; margin:0; padding:0; overflow:hidden; list-style-type: none; }
    li { float: left; }
    li a { display: block; padding:8px 50px; text-align:center; text-decoration:none; font-weight:bold; color:black; }
    li a.current { background-color:#FF6347; color:white; }
    li a:hover:not(.current) { background-color: #CD853F; color:white; transition:0.3s; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127740742-6da93b02-17a5-4e22-8a86-a75c55ab46a9.png)

위의 예제에서는 :not 선택자를 이용하여 현재 메뉴를 나타내는 current 클래스와 그 외의 메뉴의 배경색을 구분하고 있습니다.

`<ul>`요소나 `<ol>`요소의 float 속성값을 조절하면, 왼쪽 메뉴뿐만 아니라 오른쪽 메뉴도 같이 설정할 수 있습니다.

``` html
<style>
    ul { background-color: #FFDAB9; margin:0; padding:0; overflow:hidden; list-style-type: none; }
    ul.right { float: right; }
    li { float: left; }
    li a { display: block; padding:8px 50px; text-align:center; text-decoration:none; font-weight:bold; color:black; }
    li a.current { background-color:#FF6347; color:white; }
    li a:hover:not(.current) { background-color: #CD853F; color:white; transition:0.3s; }
</style>
...
<h1>오른쪽 메뉴 설정</h1>
<ul>
  <li><a href="/index.php">Home</a></li>
  <li><a href="/html/intro">HTML</a></li>
  <li><a class="current" href="/css/intro">CSS</a></li>
  <ul class="right">
    <li><a href="/bbs/login.php">로그인</a></li>
    <li><a href="/bbs/register_form.php">회원가입</a></li>
  </ul>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/127740819-0bfe2c05-7b57-44fc-8ed0-2f66bac2ac7d.png)

border 속성을 이용하면 내비게이션 바에 경계선을 표현할 수 있습니다.

``` html
<style>
    ul { background-color: #FFDAB9; margin:0; padding:0; overflow:hidden; list-style-type: none; }
    ul.right { float: right; }
    li { float: left; border-right: 2px solid gray; }
    li:last-child { border-right: none; }
    li a { display: block; padding:8px 50px; text-align:center; text-decoration:none; font-weight:bold; color:black; }
    li a.current { background-color:#FF6347; color:white; }
    li a:hover:not(.current) { background-color: #CD853F; color:white; transition:0.3s; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127740869-1b504a95-6328-4f71-945d-44d903b3a930.png)

## 드롭다운

> <h3>드롭다운(dropdown) 효과</h3>

해당 요소에 마우스를 올려서 다른 요소나 텍스트가 나타나게 하는 효과를 드롭다운(dropdown) 효과라고 합니다.

CSS를 이용하면 이러한 드롭다운 효과를 간단히 설정할 수 있습니다.

다음 예제는 display 속성을 이용하여 드롭다운 효과를 구현하는 예제입니다.

``` html
<style>
 .dropdown {
  position: relative;
  display: inline-block; /* inline-block으로 설정하면 자식요소로 나타나는 숨겨진 박스의 너비가 dropdown에 맞춰진다. */
 }
 .dropdown-content {
  display: none;
  position: absolute;
  background-color: #F9F9F9;
  min-width: 160px;
  padding: 8px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
 }
 .dropdown:hover .dropdown-content { display: block; }
</style>
...
<div class="dropdown">
 <span>여기에 마우스를 올려보세요!</span>
 <div class="dropdown-content">
  <p>마우스를 올려야 나타나는 div 요소입니다!</p>
 </div>
</div>
 <p> 나는 무엇을 하는가 </p>
```

![image](https://user-images.githubusercontent.com/43658658/127741428-2805e683-20c3-4fe2-81e1-fc9f78126ad7.png)

마우스를 올리면 "나는 무엇을 하는가"라는 문구가 가려지면서 숨겨진 요소가 나타납니다.

![image](https://user-images.githubusercontent.com/43658658/127741439-0f3d60e2-6468-41d9-b676-d5011b44e092.png)

위의 예제에서 사용자가 마우스를 올리면 나타날 `<div>`요소의 display 속성값을 none으로 설정합니다.

이렇게 설정하면 처음에는 눈에 보이지 않게 됩니다.

 

하지만 특정 요소에 마우스를 올리면 해당 `<div>`요소의 display 속성값이 블록(block)으로 변경됩니다.

따라서 이때에는 이 `<div>`요소가 눈에 보이게 됩니다.

> <h3>드롭다운(Dropdown) 메뉴</h3>

메뉴에 마우스를 올리면 하위 메뉴가 나타나게 하는 메뉴를 드롭다운(dropdown) 메뉴라고 합니다.

드롭다운 효과를 이용하면 이러한 드롭다운 메뉴도 간단히 구현할 수 있습니다.

``` html
<style>
      ul { list-style-type: none; margin:0; padding:0; }
     .dropdown-menu { background-color:#FFDAB9; text-align:center; font-weight:bold; padding:8px; min-width:100px; }
     .dropdown { position:relative; display:inline-block; } /* relative와 absolute가 없다면 드롭다운의 메뉴의 width가 상위 메뉴와 똑같이 맞춰진다. */
     .dropdown-content { box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2); position: absolute; min-width: 200px; }
     .dropdown-content a{ background-color:#FFDAB9; display:none; text-decoration:none; color:black; padding: 8px;}

     .dropdown:hover .dropdown-content a { display: block; }
     .dropdown:hover .dropdown-menu { background-color: #CD853F; }
     .dropdown .dropdown-content a:hover { background-color: #CD853F; }
     .dropdown-content:hover { background-color: #CD853F; }
</style>
...
<div class="dropdown">
 <ul>
   <li class="dropdown-menu">Dropdown</li>
 </ul>
 <div class="dropdown-content">
  <a href="#">HTML</a>
  <a href="#">CSS</a>
  <a href="#">JAVA</a>
  <a href="#">C++</a>
 </div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127742225-7e82c117-e33b-40f2-a7f5-e3684be95613.png)

위의 예제에서도 앞선 예제와 마찬가지로 해당 요소의 display 속성을 이용하여 드롭다운 메뉴를 구현하고 있습니다.

## 툴팁

> <h3>툴팁(tooltip) 효과</h3>

해당 요소에 마우스를 올리면 추가적인 정보가 나타나게 하는 효과를 툴팁(tooltip) 효과라고 합니다.

CSS를 이용하면 이러한 툴팁 효과를 간단히 설정할 수 있습니다.

다음 예제는 visiblility 속성을 이용하여 툴팁 효과를 구현하는 예제입니다.

``` html
<style>
     .tooltip { position: relative; }
     .tooltip .tooltip-content { visibility: hidden; margin-top: 10px; padding:0; width:300px; background-color: orange; text-align:center; color:white; position:absolute; z-index:1; }
     .tooltip:hover .tooltip-content { visibility: visible; }
</style>
...
<div class="tooltip">
 <span>여기에 마우스를 올려보세요!</span>
 <div class="tooltip-content">
  <p>마우스를 올려야 나타나는 툴팁입니다!</p>
 </div>
     <p>으히히히히히히힣</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127758513-e00faaa7-4561-4c13-97b9-3399f176663c.png)

CSS를 이용하면 툴팁(tooltip)이 나타나는 위치도 간단히 설정할 수 있습니다.

CSS의 상대적 위치를 나타내는 `top, right, bottom, left` 속성을 이용하여 툴팁의 상대 위치를 설정할 수 있습니다.

- top : relative 요소가 absolute 요소보다 border-top을 기준으로 얼마만큼 위에 있는지.
- bottom : relative 요소가 absolute 요소보다 border-bottom을 기준으로 얼마만큼 아래에 있는지.
- right : relative 요소가 absolute 요소보다 border-right를 기준으로 얼마만큼 오른쪽에 있는지.
- left : relative 요소가 absolute 요소보다 border-left를 기준으로 얼마만큼 왼쪽에 있는지.

다음 예제는 툴팁이 해당 요소의 아래 쪽이 아닌 왼쪽에 나타나도록 구현한 예제입니다.

``` html
<style>
     body { text-align:center; }
     .tooltip { display:inline-block; position:relative; margin:auto; }
     .tooltip .tooltip-content {
       visibility:hidden; background-color: orange; color:white; text-align:center;
       top:-15px; right:105%; position:absolute; width:220px; padding:0;
     }
     .tooltip:hover .tooltip-content { visibility: visible; }
</style>
...
<div class="tooltip">
 <span>여기에 마우스를 올려보세요!</span>
 <div class="tooltip-content">
  <p>왼쪽에 나타나는 툴팁입니다!</p>
 </div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127759513-614b25ca-dc62-4b17-ab7e-acefcfa52220.png)

다음 예제는 해당 요소에 마우스를 올리면 툴팁이 위쪽에 나타나도록 구현한 예제입니다.

``` html
<style>
     body { text-align:center; }
     .tooltip { position:relative; display:inline-block; margin:auto; }
     .tooltip .tooltip-content { position:absolute; padding:0; background-color:orange; color: white;
       bottom:180%; left:-3%; visibility:hidden; text-align: center; min-width:220px; }
     .tooltip:hover .tooltip-content { visibility:visible; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127759837-f62da73f-1bfc-4976-b203-019f93e0ef17.png)

`.tooltip`에 `display:inline-block`을 설정해주어야 `.tooltip`크기 만큼의 인라인 블록으로 바뀌고,

`position:absolute`의 `top, right, bottom, left`를 통해 위치 조정이 가능해집니다.

또한, 다음 예제처럼 툴팁(tooltip)의 모양을 말풍선 모양처럼 설정할 수도 있습니다.

``` html
<style>
 body { text-align:center; }
    .tooltip { position:relative; display:inline-block; margin:auto; }
    .tooltip .tooltip-content { position:absolute; padding:0; background-color:orange; color: white;
      bottom:180%; left:-3%; visibility:hidden; text-align: center; min-width:220px; border-radius: 5px; }
    .tooltip:hover .tooltip-content { visibility:visible; }
 .tooltip .tooltip-content::after {content:" "; position:absolute; top:100%; left:50%; margin-left:-10px;
         border-width:10px; border-style:solid; border-color:orange transparent transparent transparent;
     }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127759903-a145184d-21b6-4236-a392-3889defc9832.png)

`.tooltip .tooltip-content::after` 의사 요소가 바로 아래쪽 역삼각형을 구현하는 부분입니다.

툴팁의 말풍선 모양은 border-color 속성값을 transparent로 설정하여 구현할 수 있습니다.

border과 관련된 속성은 반드시 widht, style, color 따로 지정해주어야 transparent 효과가 나타납니다.

transparent 속성값은 투명함을 의미합니다.

## Form 요소

CSS를 이용하면 사용자의 입력을 받는 input 요소에도 다양한 스타일을 설정할 수 있습니다.

> <h3>input 요소의 크기 설정</h3>

width 속성을 이용하여 input 요소의 크기를 설정할 수 있습니다.

``` html
<style>
		input {
			width: 100%;
			padding: 10px 20px;
			margin: 5px 0;
			box-sizing: border-box; /* 요소의 총 너비와 높이에 패딩과 테두리 두께까지 고려합니다. */
		}
	</style>
```

![image](https://user-images.githubusercontent.com/43658658/127761089-3dec425b-974b-47e5-b550-0825a23620ec.png)

> <h3>input 요소의 테두리 설정</h3>

border 속성을 이용하여 input 요소의 테두리(border) 색상과 두께를 바꿀 수 있습니다.

또한, border-radius 속성을 이용하여 input 요소의 모서리를 둥글게 만들 수도 있습니다.

``` html
<style>
     input { width:100%; padding: 10px 20px; margin: 5px 0; box-sizing:border-box;}
     input[type="text"] { border: 2px solid #D2691E; border-radius: 10px; }
     input[type="password"] { border: none; border-bottom:2px solid #D2691E; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127761184-06ec9f15-de3d-442a-ab20-ed77d672fc92.png)

> <h3>input 요소에 배경색 적용</h3>

background-color 속성을 이용하여 input 요소의 배경색을 설정할 수 있습니다.

또한, color 속성을 이용하여 input 요소의 텍스트 색상를 변경할 수도 있습니다.

``` html
<style>
 input { width:100%; box-sizing:border-box; padding:10px 20px; margin: 5px 0; border:none;
         background-color:#FFF8DC; color:olive; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127761364-3e39611a-5a15-4cb0-b541-a777ee7ddd31.png)

> <h3>포커스를 가지고 있는 input 요소의 스타일 적용</h3>

`:focus` 선택자를 이용하여 해당 input 요소가 포커스(focus)를 가지고 있을 때의 스타일을 별도로 설정할 수 있습니다.

``` html
<style>
 input { width:100%; box-sizing:border-box; border:2px solid #FFE4B5; border-radius: 5px; outline:none;
         margin:5px 0; padding:10px 20px; -webkit-transition:0.5s; }
     input[type="text"]:focus, input[type="password"]:focus { border:2px solid #D2691E; }
</style>
...
<form>
 사용자 : <br>
 <input type="text" name="username" placeholder="아이디를 입력하세요."><br>
 비밀번호 : <br>
 <input type="password" name="password" placeholder="비밀번호를 입력하세요.">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127761601-65981eb8-e494-4a8e-a1b7-cd9f4c5ddde9.png)

> <h3>input 요소에 아이콘(icon)이나 이미지 삽입</h3>

background-image 속성을 이용하여 input 요소에 아이콘(icon)이나 이미지를 삽입할 수 있습니다.

또한, background-position 속성을 이용하여 삽입한 아이콘이나 이미지가 나타날 위치를 설정할 수도 있습니다.

``` html
<style>
 input { width:100%; box-sizing:border-box; border:2px solid gray; border-radius: 5px;
         background-image: url("/examples/images/img_search_icon.png"); background-position:5px 4px; background-repeat:no-repeat;
         padding:10px 40px; margin:5px 0; -webkit-transition:0.3s; outline:none; font-size:14px; }
     input[type="text"]:focus { border:2px solid black; }
</style>
...
<form>
 <input type="text" name="search" placeholder="검색할 키워드를 입력하세요."><br>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127761952-a2da5d84-432c-47f9-b429-319a747eb598.png)

> <h3>textarea 요소의 크기 조절</h3>

resize 속성을 이용하여 textarea 요소의 크기를 조절할 수 있습니다.

resize 속성을 설정하면 해당 textarea 요소의 오른쪽 아래 부분에 마우스로 잡을 수 있는 핸들이 생깁니다.

사용자가 그 핸들을 마우스로 클릭하여 조절하면 textarea 요소의 크기를 마음대로 조절할 수 있게 됩니다.

CSS에서 사용할 수 있는 resize 속성값은 다음과 같습니다.

- none :	해당 요소의 크기를 조절할 수 없음. (기본 설정)
- both : 사용자가 해당 요소의 높이와 너비를 모두 조절할 수 있음.
- horizontal :	사용자가 해당 요소의 너비만을 조절할 수 있음.
- vertical :	사용자가 해당 요소의 높이만을 조절할 수 있음.

resize 속성은 익스플로러에서 지원하지 않습니다.

``` html
<style>
     textarea { border:2px solid #1E90FF; width:100%; height:200px; box-sizing:border-box; 
       border-radius:5px; resize:both; padding: 10px 20px; font-size:16px; }
</style>
...
<form>
 <textarea placeholder="여기에 텍스트를 입력합니다!"></textarea>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127762071-12a8b766-6b19-4e53-abc8-a574195d48db.png)

> <h3>select 요소에 스타일 적용</h3>

CSS를 이용하면 select 요소에도 여러 가지 스타일을 적용할 수 있습니다.

``` html
<style>
 select {
  width: 100%;
  padding: 10px;
  border: solid 1px #EEEEEE;
  border-radius: 5px;
  background-color: #FFFFE0;
         box-sizing:border-box;
         font-size:14px;
         outline:none;
         -webkit-transition: 0.5s;
 }
     select:hover { border: 1px solid black; }
     select:focus { box-shadow: 0 0 3px 2px #777; border: 1px solid black; }
     select option {font-size:14px;}
</style>
...
<form>
 <select name="fruit">
  <option value="apple" selected> 사과
  <option value="orange"> 귤
  <option value="strawberry"> 딸기
  <option value="peach"> 복숭아
 </select>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127765445-d44f6d77-16c6-4b8b-918e-d0dcf69ba29c.png)

## @규칙

CSS에서는 W3C에서 규정하고 있는 몇몇 규칙들을 사용할 수 있습니다.

그 중에서도 많이 사용되는 대표적인 규칙은 다음과 같습니다.

1. @import

2. @font-face

3. @media

> <h3>@import 규칙</h3>

`@import` 규칙은 다른 스타일 시트에서 스타일 규칙을 가져올 수 있는 규칙입니다.

이 규칙은 스타일 시트에 사용되는 문자 인코딩을 지정하는 @charset 규칙을 제외하고 모든 다른 규칙보다 앞서 명시되어야 합니다.

 

보통 HTML 문서에는 다음과 같이 여러 개의 `<link>`태그를 사용하여 스타일 시트를 추가합니다.

``` html
<head>
    <title>@import 규칙</title>
    <link rel="stylesheet" href="firstStyleSheet.css">
    <link rel="stylesheet" href="secondStyleSheet.css">
    ...
    <link rel="stylesheet" href="hundredStyleSheet.css">
</head>
```
 
하지만 이렇게 추가하는 CSS 파일의 개수가 늘어날수록 웹 서버의 부하도 같이 커지게 됩니다.

따라서 HTML 문서에는 일정 개수의 CSS 파일만을 추가하고, 추가된 CSS 파일에서 `@import` 규칙을 이용해 또 다른 CSS 파일을 추가하는 방법을 사용합니다.

HTML 문서

``` html
<head>
    <title>@import 규칙</title>
    <link rel="stylesheet" href="firstStyleSheet.css">
    <link rel="stylesheet" href="secondStyleSheet.css">
</head>
```

firstStyleSheet.css

``` html
@import url("thirdStyleSheet.css");
@import "fourthStyleSheet.css";
...
```

@import 규칙을 사용해도 추가하는 CSS 파일의 개수가 늘어나면 여전히 웹 서버의 부하는 커질 수밖에 없습니다.

따라서 웹 서버의 부하를 줄이기 위해 작성한 CSS 파일들을 적절히 분산해서 추가하는 방법이 필요해집니다.

 

@import 규칙을 이용하면 `미디어 쿼리(media query)`의 조건에 따라 필요한 CSS 파일만을 선별적으로 불러올 수 있습니다.

 

다음 예제는 `프린트`할 때에는 firstStyleSheet.css 파일을 불러오고, `스크린이 가로 방향`으로 설정되어 있을 때는 secondStyleSheet.css 파일을 불러오는 예제입니다.

``` html
<head>
    <title>@import 규칙</title>
    @import url("firstStyleSheet.css") print;
    @import "secondStyleSheet.css" screen and (orientation:landscape);
</head>
```

> <h3>@font-face 규칙</h3>

@font-face 규칙은 웹 폰트(web font)를 정의할 때 사용하는 규칙입니다.

웹 폰트(web font)는 사용자의 컴퓨터에 설치되어 있지 않은 글꼴(font)을 웹 브라우저가 사용할 수 있게 해줍니다.

우선 웹 폰트를 서버에 올려놓고, CSS 파일에 @font-face 규칙을 사용하여 웹 폰트를 정의하고 추가합니다.

그러면 해당 웹 페이지에 접속하는 모든 웹 브라우저는 자동으로 서버에서 웹 폰트를 내려받아 해당 글꼴을 표시하게 됩니다.

``` html
<style>
    @font-face {
        font-family: "myWebFont";
        src: local("NanumGothic"), url("NanumGothic.eot"), url("NanumGothic.ttf"), url("NanumGothic.woff");
    }
    * { font-family: "myWebFont"; }
</style>
```

> <h3>@media 규칙</h3>

CSS2에서는 @media 규칙을 통해 서로 다른 미디어 타입(media type)을 위한 맞춤식 스타일 시트를 지원합니다.

다음 예제는 HTML 문서가 스크린에 표현될 때와 프린트할 때 서로 다른 스타일을 적용해 주는 예제입니다.

``` html
<style>
    body { background-color: darkorange; }
    @media screen {
        body { background-color: black; color: white; }
    }
    @media print {
        body { background-color: white; color: black; }
    }
</style>
```

