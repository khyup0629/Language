# Part 6. CSS 고급

+ [내비게이션 바(navigation bar)](#내비게이션-바navigation-bar)
+ 

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
