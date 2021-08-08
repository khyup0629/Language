# Part 9. CSS3 확장

+ [CSS3 버튼](#CSS3-버튼)
+ [사용자 인터페이스](#사용자-인터페이스)
+ [다중 칼럼 레이아웃](#다중-칼럼-레이아웃)
+ [플렉서블 박스 레이아웃](#플렉서블-박스-레이아웃)
+ [미디어 쿼리](#미디어-쿼리)

## CSS3 버튼

CSS를 이용하면 다양한 모양의 버튼을 여러 방식으로 만들 수 있습니다.

CSS에서 버튼은 `<button>`태그 뿐만 아니라 `<a>`태그와 `<input>`태그로도 만들 수 있습니다.

``` html
.btn {
    background-color:#87CEEB;
    font-size:16px;
    color:black;
    border:none;
    text-decoration:none;
    display:inline-block;
    padding:15px 30px;
    cursor:pointer;
    margin:2px;
}
...
<h3>기본 버튼</h3>
<button>button 태그</button>
<a href="#">a 태그</a>
<input type="button" value="input 태그">

<h3>CSS로 버튼 스타일 설정</h3>
<button class="btn">button 태그</button>
<a class="btn" herf="#">a 태그</a>
<input type="button" value="input 태그" class="btn">
```

![image](https://user-images.githubusercontent.com/43658658/128597320-ba5a6f42-58a6-4bb5-9ada-fc4f32b66f1b.png)

다음 예제는 그림자 효과를 설정한 버튼 예제입니다.

``` html
<style>
  .btn {
    background-color: #87CEEB;
    padding: 15px 30px;
    margin: 10px;
    border: none;
    color: black;
    text-align: center;
    text-decoration: none;
    font-size: 16px;
    display: inline-block;
    cursor: pointer;
    -webkit-transition: box-shadow 0.4s;
    transition: box-shadow 0.4s;
  }
  .btn1, .btn2:hover { box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19); }
</style>
...
<button class="btn btn1">그림자 효과 버튼</button>
<button class="btn btn2">마우스를 올려 보세요!</button>

![image](https://user-images.githubusercontent.com/43658658/128597492-0f202f85-057b-4668-8238-bde6010cfd1b.png)

다음 예제는 버튼을 사용하지 못하도록 설정하는 예제입니다.

``` html
.btn2 {
  opacity:0.4;
  cursor:not-allowed;
}
```

![image](https://user-images.githubusercontent.com/43658658/128597599-d3cfc09a-bd9d-4c75-9960-706620fff9d4.png)

float 속성을 이용하여 버튼으로 메뉴를 만들 수도 있습니다.

``` html
<style>
		.btn {
          background-color: #87CEEB;
          border:1px solid white;
          padding:15px 30px;
          float:left;
          display:inline-block;
          font-size:16px;
          -webkit-transition:0.4s;
		      transition:0.4s;
          cursor:pointer;
          box-sizing:border-box;
		}
		.btn1:hover, .btn2:hover, .btn3:hover, .btn4:hover {
			    background-color:#4169E1;
          color:white;
          border:1px solid black;
		}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128597777-c94dc5d7-3fde-4f04-87f5-96957ba40039.png)

> <h3>다양한 형태의 버튼 예제</h3>

CSS의 애니메이션(animation) 효과를 이용하면, 버튼에 더욱 다양한 효과를 적용할 수 있습니다.

다음 예제는 마우스를 올리면 버튼의 표시 내용이 바뀌는 예제입니다.

'▶'기호는 ::after 선택자를 이용하여 '버튼'이라는 문자열 바로 뒤에 삽입됩니다.

이때 opacity 속성값을 0으로 설정하여 처음에는 보이지 않습니다.

하지만 마우스를 버튼 위로 올리면, opacity 속성값이 1로 변경되어 눈에 보이게 됩니다.

이때 transition 효과가 실행되며 0.5초 동안 천천히 opacity 속성값이 변경됩니다.

`<span>`내의 opacity를 1로 설정하고 위치를 조정한 다음 0으로 바꾸면 작업이 쉬워집니다.

``` html
<style>
  .btn{
        background-color:orange;
        width:150px;
        height:75px;
        font-size:22px;
        border:none;
        padding:15px 30px;
        margin:10px;
        cursor:pointer;
        display:inline-block;
        position:relative;
    }
    .btn span{
      position:relative;
      display:inline-block;
      -webkit-transition:0.5s;
      transition:0.5s;

    }
    .btn span::after{
      content:'▶';
      color:white;
      opacity:0;
      position:absolute;
      top:-7px;
      right:-50px;
      font-size:30px;
      -webkit-transition:0.5s;
      transition:0.5s;
    }
    .btn:hover span{
      transform:translateX(-15px); /* padding-right:30px; 도 가능하다.*/
    }
    .btn:hover span::after{
      opacity:1;
      right:-32px; /* padding-right:30px;일 경우 right:0px */
    }
</style>
...
<button class="btn"><span>버튼</span></button>
```

`버튼`에 마우스를 올리기 전 :

![image](https://user-images.githubusercontent.com/43658658/128599145-bf74497c-9820-47b4-949c-b2c391003188.png)

`버튼`에 마우스를 올린 후 :

![image](https://user-images.githubusercontent.com/43658658/128599156-3a3ecb90-aa98-4760-9502-9a25e0f5efc0.png)

다음 예제는 버튼을 누르면 버튼 위로 다른 색상이 물결처럼 퍼지는 예제입니다.

``` html
<style>
      .btn {
        width:150px;
        height:70px;
        background-color:orange;
        border:none;
        font-size:22px;
        color:black;
        position:relative;
        padding:15px 30px;
        margin:10px;
        cursor:pointer;
        overflow:hidden; /* 이 항목을 없애고 .btn::after에 opacity:1로 해서 
	.btn::after와 .btn:active::after사이의 변화양상을 확인할 수 있다.*/
      }
      /* .btn:active::after와 .btn::after 사이를 왔다갔다 함 */
      /* 평상시에 .btn::after 서식이 있지만, opacity로 인해 보이지 않음. */
      .btn::after { 
        content:"";
        background-color: #FFD700;
        position:absolute;
        top:70px;
        left:0;
        padding-top:200%;
        padding-left:300%;
        margin-top:-120%;
        margin-left:0;
        opacity:0;
        -webkit-transition: 0.4s;
        transition: 0.4s;
      }
      .btn:active::after {
        padding:0;
        margin:0;
        opacity:1;
        /* 이 항목이 없으면 클릭을 하는 순간
        .btn::after -> .btn:active::after 과정이 눈에 보인다. */
        -webkit-transition:0s; 
        transition:0s;
      }
</style>
```

다음 예제는 진짜 버튼처럼 누르는 효과를 적용한 버튼 예제입니다.

우선 `box-shadow` 속성을 이용하여 버튼에 그림자 효과를 설정합니다.

그 후에 사용자가 버튼을 누르면 :active 선택자와 transform 효과를 이용하여 버튼의 위치를 아래로 살짝 이동시킵니다.

이렇게 함으로써 버튼이 진짜로 눌리는 듯한 효과를 줄 수 있게 됩니다.

``` html
<style>
	.btn {
          width:150px;
          height:70px;
          font-size:22px;
          background-color:orange;
          border:none;
          border-radius:15px;
          box-shadow:0 5px #B0B0B0;
          position:relative;
          display:inline-block;
          box-sizing:border-box;
          margin:10px;
	  cursor:pointer;
      }
      .btn:hover { background-color: #FF8C00; }
      .btn:active {
        background-color:#FF8C00;
        box-shadow:0 1px #808080; /* translate한 만큼 y값을 빼주면 버튼이 아래로 내려가는 것처럼 보인다. */
        transform:translateY(4px);
      }
</style>
```

버튼 누르기 전

![image](https://user-images.githubusercontent.com/43658658/128626176-9f99fe07-b132-464c-b634-a4787b880e61.png)

버튼 누른 후

![image](https://user-images.githubusercontent.com/43658658/128626186-f3ea5157-c731-4413-85e3-36db20c7ee0d.png)

## 사용자 인터페이스

CSS3에서는 새로운 사용자 인터페이스를 이용하여, 사용자가 요소의 크기나 아웃라인 등을 마음대로 변경할 수 있게 해줍니다.

사용자 인터페이스(user interface)를 위해 제공되는 속성은 다음과 같습니다.

1. resize

2. outline-offset

3. box-sizing

4. nav-index

5. nav-left

6. nav-right

7. nav-up

8. nav-down

+ nav- 속성은 Opera 12 이상에서만 지원합니다.

> <h3>resize 속성</h3>

resize 속성은 사용자가 해당 요소의 높이나 너비를 변경할 수 있게 해줍니다.

resize 속성이 설정된 요소에는 오른쪽 하단에 크기 조절 핸들이 생깁니다.

이 핸들을 마우스로 드래그해서 사용자가 직접 요소의 크기를 조절할 수 있습니다.

``` html
<style>
	div {
		border:3px solid orange;
		width:300px;
		padding:20px;
		overflow:auto;
		margin:10px;
	}
	#width { resize:horizontal; }
	#height { resize:vertical; }
	#both { resize:both; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128627592-67d56fda-dff3-4631-ab2e-759f13bb4975.png)

> <h3>outline-offset 속성</h3>

outline-offset 속성은 해당 요소의 테두리(border)와 아웃라인(outline) 사이에 공간(offset)을 추가해 줍니다.

아웃라인(outline)과 테두리(border)의 차이는 다음과 같습니다.

 

1. 아웃라인은 테두리의 바깥쪽에서 요소를 둘러싸고 있는 라인입니다.

2. 아웃라인은 HTML 요소의 크기에 포함되지 않습니다.

3. 아웃라인은 사각형이 아닐 수도 있습니다.

 

다음 예제는 outline-offset 속성을 이용하여 아웃라인과 테두리를 확인하는 예제입니다.

``` html
<style>
	div {
		height: 100px;
		width: 300px;
		padding: 20px;
		margin: 50px;
		border:1px solid black;
		outline:1px solid red;
		outline-offset:20px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128627785-c2696474-3108-4a8d-b9db-2c01212863ba.png)

> <h3>box-sizing 속성</h3>

box-sizing 속성의 속성값을 border-box로 설정하면, 해당 요소의 총 너비와 높이에 패딩과 테두리의 크기까지 포함해서 설정합니다.

``` html
<style>
	div {
		width: 350px;
		height: 100px;
		margin: 10px;
	}
	#origin { border: 1px solid orange; }
	#no_border_box {
		border: 10px solid green; 
		padding: 20px; 
	}
	#border_box { 
		border: 10px solid yellow; 
		padding: 20px; 
		box-sizing: border-box; 
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128627824-4b312400-14e1-48e2-9ce2-fb1a5c90e4d3.png)

## 다중 칼럼 레이아웃

CSS에서는 신문과 같이 여러 개의 칼럼(column)으로 구성되는 구조를 column 속성을 이용하여 손쉽게 만들 수 있습니다.

다중 칼럼(multi-column)을 위해 제공되는 속성은 다음과 같습니다.

1. columns

2. column-count

3. column-gap

4. column-width

5. column-span

6. column-fill

7. column-rule

8. column-rule-style

9. column-rule-width

10. column-rule-color

> <h3>column-count 속성</h3>

column-count 속성은 해당 요소를 몇 개의 칼럼(column)으로 나눌지를 설정합니다.

``` html
<style>
	#origin {
		-webkit-column-count: 3;
		-moz-column-count: 3;
		column-count: 3;
	}
</style>
<div id="origin">
	<h4>칼럼을 3개로 나누겠어요!</h4>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean dignissim magna et iaculis molestie. Vivamus semper gravida magna, non imperdiet nisl viverra vitae. Interdum et malesuada fames ac ante ipsum primis in faucibus. Nunc tristique cursus dui at facilisis. Maecenas mollis dui tortor, non elementum libero condimentum vulputate. Phasellus eget sagittis felis. Quisque ornare et risus ac sodales. Phasellus malesuada efficitur mattis. In hac habitasse platea dictumst. Ut enim sem, placerat id sagittis tristique, posuere ac mi. Cras et efficitur magna. Vestibulum in nulla feugiat, sodales libero quis, molestie urna. Praesent laoreet at augue in interdum. Duis et mauris at lacus tempus fringilla.</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128628057-05372c10-31f5-4626-a740-99965a25d838.png)

> <h3>column-gap 속성</h3>

column-gap 속성은 칼럼(column) 사이의 간격을 설정합니다.

``` html
div {
	margin: 30px 0;
	-webkit-column-count: 3;
	-moz-column-count: 3;
	column-count: 3;
}
#gap {
	-webkit-column-gap: 70px;
	-moz-column-gap: 70px;
	column-gap: 70px;
}
```

![image](https://user-images.githubusercontent.com/43658658/128628076-f69fcc36-742b-4b8f-8b98-482a345aafec.png)

> <h3>column-width 속성</h3>

column-width 속성은 칼럼의 너비를 설정합니다.

웹 브라우저는 설정한 너비의 칼럼을 만든 후, 나머지 영역을 동일하게 나누어 칼럼 사이의 간격으로 자동 설정합니다.

``` html
div { margin: 30px 0; }
#origin {
	-webkit-column-count: 5;
	-moz-column-count: 5;
	column-count: 5;
}
#gap {
	-webkit-column-width: 150px;
	-moz-column-width: 150px;
	column-width: 150px;
}
```

![image](https://user-images.githubusercontent.com/43658658/128628181-a7b9188c-18b7-45e5-a990-660999c5664f.png)

> <h3>column-span 속성</h3>

column-span 속성은 해당 요소가 몇 개의 칼럼을 병합하여 표현할지를 설정합니다.

``` html
<style>
	div {
		margin: 30px 0;
		-webkit-column-count: 4;
		-moz-column-count: 4;
		column-count: 4;
	}
	#merge { /* 4개의 칼럼을 병합합니다. */
		-webkit-column-span: all;
		column-span: all;
	}
</style>
...
<div>
	<h4>칼럼 레이아웃의 원래 모습이에요!</h4>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean dignissim magna et iaculis molestie. Vivamus semper gravida magna, non imperdiet nisl viverra vitae. Interdum et malesuada fames ac ante ipsum primis in faucibus. Nunc tristique cursus dui at facilisis. Maecenas mollis dui tortor, non elementum libero condimentum vulputate. Phasellus eget sagittis felis. Quisque ornare et risus ac sodales. Phasellus malesuada efficitur mattis. In hac habitasse platea dictumst. Ut enim sem, placerat id sagittis tristique, posuere ac mi. Cras et efficitur magna. Vestibulum in nulla feugiat, sodales libero quis, molestie urna. Praesent laoreet at augue in interdum. Duis et mauris at lacus tempus fringilla.</p>
</div>
<div>
	<h4 id="merge">column-span 속성으로 h4 요소의 모든 칼럼을 병합했어요!</h4>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean dignissim magna et iaculis molestie. Vivamus semper gravida magna, non imperdiet nisl viverra vitae. Interdum et malesuada fames ac ante ipsum primis in faucibus. Nunc tristique cursus dui at facilisis. Maecenas mollis dui tortor, non elementum libero condimentum vulputate. Phasellus eget sagittis felis. Quisque ornare et risus ac sodales. Phasellus malesuada efficitur mattis. In hac habitasse platea dictumst. Ut enim sem, placerat id sagittis tristique, posuere ac mi. Cras et efficitur magna. Vestibulum in nulla feugiat, sodales libero quis, molestie urna. Praesent laoreet at augue in interdum. Duis et mauris at lacus tempus fringilla.</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128628256-29f9b7f7-7c80-498e-b507-b60871c5a252.png)

> <h3>column-rule-style 속성</h3>

column-rule-style 속성은 칼럼 사이에 들어갈 라인의 스타일을 설정합니다.

``` html
<style>
	div {
		margin:30px 0;
		-webkit-column-count:4;
		-moz-column-count:4;
		column-count:4;
	}
	#line {
		-webkit-column-rule-style:solid;
		-moz-column-rule-style:solid;
		column-rule-style:solid;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128628300-d40992b7-4969-4f6d-8e8f-9df57ed42c1c.png)

> <h3>column-rule-width 속성</h3>

column-rule-width 속성은 칼럼 사이에 들어갈 라인의 두께를 설정합니다.

``` html
<style>
	div {
		margin:30px 0;
		-webkit-column-count:4;
		-moz-column-count:4;
		column-count:4;
	}
	#line {
		-webkit-column-rule-style:solid;
		-moz-column-rule-style:solid;
		column-rule-style:solid;
		-webkit-column-rule-width:5px;
		-moz-column-rule-width:5px;
		column-rule-width:5px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128628384-f3fad132-49dc-4c0d-b53d-6f072f36924b.png)

> <h3>column-rule-color 속성</h3>

column-rule-color 속성은 칼럼 사이에 들어갈 라인의 색상을 설정합니다.

``` html
<style>
	div {
		margin: 30px 0;
		-webkit-column-count: 4;
		-moz-column-count: 4;
		column-count: 4;
	}
	#line {
		-webkit-column-rule-style: solid;
		-moz-column-rule-style: solid;
		column-rule-style: solid;
		-webkit-column-rule-width: 5px;
		-moz-column-rule-width: 5px;
		column-rule-width: 5px;
		-webkit-column-rule-color: #6495ED;
		-moz-column-rule-color: #6495ED;
		column-rule-color: #6495ED;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128628421-ba6d3cf9-5e9e-4e0f-b7d6-3cb8b3263888.png)

> <h3>column-rule 속성</h3>

모든 columns-rule 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

``` html
<style>
	div {
		margin: 30px 0;
		-webkit-column-count: 4;
		-moz-column-count: 4;
		column-count: 4;
	}
	#line {
		-webkit-column-rule: 5px solid #6495ED;
		-moz-column-rule: 5px solid #6495ED;
		column-rule: 5px solid #6495ED;
	}
</style>
```

## 플렉서블 박스 레이아웃

플렉서블 박스(flexible box)는 플렉스 박스(flex box)라고도 불리며, CSS3에서 처음 소개된 레이아웃 모델입니다.

이 레이아웃은 서로 다른 크기의 화면과 기기에서도 HTML 요소들이 자동으로 재정렬되어, 웹 페이지의 레이아웃을 언제나 똑같이 유지할 수 있게 해줍니다.

 

플렉스 박스(flex box)을 위해 제공되는 속성은 다음과 같습니다.

 

1. display

2. flex-direction

3. justify-content

4. align-items

5. flex-wrap

6. flex-flow

7. align-content

 

또한, 플렉스 요소(flex item)를 위해 제공되는 속성은 다음과 같습니다.

 

8. order

9. align-self

10. flex

> <h3>플렉스 박스(flex box)의 개념</h3>

플렉스 박스(flex box)는 플렉스 컨테이너(flex container)와 플렉스 요소(flex item)로 구성됩니다.

 

플렉스 컨테이너(flex container)는 해당 HTML 요소의 display 속성을 설정하는 것으로 정의할 수 있습니다.

해당 요소를 블록 타입으로 정의하려면 display 속성값을 flex로, 인라인 타입으로 정의하려면 inline-flex로 설정합니다.

플렉스 컨테이너는 언제나 하나 이상의 플렉스 요소를 포함해야 합니다.

 

플렉스 컨테이너의 외부와 플렉스 요소의 내부의 모든 것들은 평소처럼 동작합니다.

플렉스 박스(flex box)는 오직 플렉스 요소가 플렉스 컨테이너의 내부에서 어떻게 위치하는가만을 정의합니다.

 

플렉스 요소는 플렉스 컨테이너 안에서 플렉스 라인(flex line)이라는 가상의 선을 따라 위치하게 됩니다.

기본적으로 하나의 플렉스 컨테이너는 오직 단 하나의 플렉스 라인만을 가지고 있습니다.

``` html
<style>
	#flex {
		background-color: dimgray;
		width: 400px;
		height: 150px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
...
<div id="flex"> <!--flex container-->
	<div class="item">1</div> <!-- flex item -->
	<div class="item">2</div>
	<div class="item">3</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128628717-f9b104b4-8572-4058-bdf0-616eec42bbb2.png)

direction 속성을 이용하면 이러한 플렉스 라인(flex line)의 방향을 바꿀 수도 있습니다.

direction 속성값이 rtl(right-to-left)로 설정되면, 페이지 내의 모든 텍스트 요소는 오른쪽에서 왼쪽 방향으로 써집니다.

그와 동시에 플렉스 라인(flex line)의 방향도 바뀌게 되어, 플렉스 요소의 정렬도 오른쪽에서 왼쪽으로 바뀌게 됩니다.

``` html
<style>
	body { direction: rtl; }
	#flex {
		background-color: dimgray;
		width: 400px;
		height: 150px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128628731-736633f2-df52-4d3b-a375-0b5321be7dae.png)

> <h3>flex-direction 속성</h3>

flex-direction 속성은 플렉스 컨테이너 안에서 플렉스 요소가 배치될 방향을 설정합니다.

이 속성은 다음과 같은 속성값을 가질 수 있습니다.

 

1. row : 기본 설정으로, 플렉스 요소는 왼쪽에서 오른쪽으로, 그리고 위쪽에서 아래쪽으로 배치됩니다.

2. row-reverse : 만약에 direction 속성값이 ltr(left-to-right)이면, 플렉스 요소는 반대로 오른쪽에서 왼쪽으로 배치됩니다.

3. column : 만약에 쓰기 방식이 수평이면, 플렉스 요소는 수직 방향으로 위쪽에서 아래쪽으로 배치됩니다.

4. column-reverse : 만약에 쓰기 방식이 수평이면, 플렉스 요소는 수직 방향으로 아래쪽에서 위쪽으로 배치됩니다.

`flex container` 요소에 속성으로 `flex-direction`을 적용해야 합니다.

다음 예제는 flex-direction 속성의 row와 row-reverse 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 400px;
		height: 150px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#row_reverse {
	        -webkit-flex-direction:row-reverse;
	        flex-direction:row-reverse;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
...
<h3>flex-direction의 속성값이 row입니다.</h3>
<div id="row" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
<h3>flex-direction의 속성값이 row-reverse입니다.</h3>
<div id="row_reverse" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128628891-d327be7a-05bd-442d-995b-ae419bbfc08e.png)

다음 예제는 flex-direction 속성의 column과 column-reverse 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 400px;
		height: 250px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#column {
		-webkit-flex-direction: column;
		flex-direction: column;
	}
	#column_reverse {
		-webkit-flex-direction: column-reverse;
		flex-direction: column-reverse;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
...
<h3>flex-direction의 속성값이 column입니다.</h3>
<div id="column" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
<div id="column_reverse" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128629004-92431ab2-8289-4330-a320-3631c0c22893.png)

> <h3>justify-content 속성</h3>

justify-content 속성은 플렉스 요소의 수평 방향 정렬 방식을 설정합니다.

이 속성은 다음과 같은 속성값을 가질 수 있습니다.

1. flex-start : 기본 설정으로, 플렉스 요소는 플렉스 컨테이너의 앞쪽에서부터 배치됩니다. (왼쪽 정렬)

2. flex-end : 플렉스 요소는 플렉스 컨테이너의 뒤쪽에서부터 배치됩니다. (오른쪽 정렬)

3. center : 플렉스 요소는 플렉스 컨테이너의 가운데에서부터 배치됩니다. (가운데 정렬)

4. space-between : 플렉스 요소는 요소들 사이에만 여유 공간을 두고 배치됩니다. (양쪽 정렬)

5. space-around : 플렉스 요소는 앞, 뒤, 그리고 요소들 사이에도 모두 여유 공간을 두고 배치됩니다. (모두 정렬)

`flex container` 요소에 id 또는 class로 속성을 적용합니다.

다음 예제는 justify-content 속성의 flex-start와 flex-end 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {width:400px;
		  height:250px;
		  margin:10px;
		  -webkit-display:flex;
		  display:flex;
		  background-color:dimgray;
		  border-radius:15px;
	}
	#end {
		-webkit-justify-content:flex-end;
		justify-content:flex-end;
	}
	.item {
		width:80px;
		height:50px;
		text-align:center;
		line-height:50px;
		margin:10px;
		color:white;
		background-color:darkgray;
		font-size:22px;
		border-radius:10px;
	}
</style>
...
<h3>justify-content의 속성값이 flex-start입니다.</h3>
<div id="start" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
<h3>justify-content의 속성값이 flex-end입니다.</h3>
<div id="end" class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128629291-219e5e1f-26d6-45d0-99a4-9c618a63d7fa.png)

한편, justify-content:flex-start 에서 줄에 `flex item`이 더 추가되면

기존에 설정된 width, margin 등은 무시되고 적절히 조절됩니다.

다음 줄로 넘기고 싶다면 후에 배울 flex-wrap을 적용하면 됩니다.

![image](https://user-images.githubusercontent.com/43658658/128629439-ab861dba-9dab-44e5-a239-58594ca05bf4.png)

다음 예제는 justify-content 속성의 center, space-between과 space-around 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 400px;
		height: 250px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#center {
		-webkit-justify-content: center;
		justify-content: center;
	}
	#between {
		-webkit-justify-content: space-between;
		justify-content: space-between;
	}
	#around {
		-webkit-justify-content: space-around;
		justify-content: space-around;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128629453-1290098a-5dc1-4bcf-97f3-3cfa01cb2ece.png)

![image](https://user-images.githubusercontent.com/43658658/128629458-8d29a1e7-4970-412b-90df-aa72fe238487.png)

> <h3>align-items 속성</h3>

align-items 속성은 플렉스 요소의 수직 방향 정렬 방식을 설정합니다.

이 속성은 한 줄만을 가지는 플렉스 박스에서는 align-content와 차이가 없습니다.

두 줄 이상을 가지는 플렉스 박스에서 align-content와 차이가 있습니다.

이 속성은 다음과 같은 속성값을 가질 수 있습니다.

1. stretch : 기본 설정으로, 플렉스 요소의 높이가 플렉스 컨테이너의 높이와 같게 변경된 뒤 연이어 배치됩니다.

2. flex-start : 플렉스 요소는 플렉스 컨테이너의 위쪽에 배치됩니다.

3. flex-end : 플렉스 요소는 플렉스 컨테이너의 아래쪽에 배치됩니다.

4. center : 플렉스 요소는 플렉스 컨테이너의 가운데에 배치됩니다.

5. baseline : 플렉스 요소는 플렉스 컨테이너의 기준선(baseline)에 배치됩니다.

 

다음 예제는 align-items 속성의 flex-start, center와 flex-end 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 400px;
		height: 100px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#start { -webkit-align-items:flex-start;
		align-items:flex-start;
	}
	#center { -webkit-align-items:center;
		align-items:center;
	}
	#end { -webkit-align-items:flex-end;
		align-items:flex-end;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128631003-010afa97-c854-40b4-9534-d59274cb5df8.png)

![image](https://user-images.githubusercontent.com/43658658/128630105-bf2a2cbb-6f36-488e-9614-9f95282596f8.png)

다음 예제는 align-items 속성의 stretch와 baseline 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 400px;
		height: 100px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#stretch {
		-webkit-align-items: stretch;
		align-items: stretch;
	}
	#base {
		-webkit-align-items: baseline;
		align-items: baseline;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128630134-26e11fb5-7806-49b6-bf78-8d5ff9277b69.png)

> <h3>flex-wrap 속성</h3>

flex-wrap 속성은 플렉스 라인에 더 이상의 여유 공간이 없을 때, 플렉스 요소의 위치를 다음 줄로 넘길지를 설정합니다.

이 속성은 다음과 같은 속성값을 가질 수 있습니다.

1. nowrap : 기본 설정으로, 플렉스 요소가 다음 줄로 넘어가지 않습니다. 대신에 플렉스 요소의 너비를 줄여서 한 줄에 모두 배치시킵니다.

2. wrap : 플렉스 요소가 여유 공간이 없으면 다음 줄로 넘어가서 배치됩니다.

3. wrap-reverse : 플렉스 요소가 여유 공간이 없으면 다음 줄로 넘어가서 배치됩니다. 단, 아래쪽이 아닌 위쪽으로 넘어갑니다. (기본 아래쪽 정렬)

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 250px;
		height: 150px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
	}
	#wrap {
		-webkit-flex-wrap: wrap;
		flex-wrap: wrap;
	}
	#wrap_reverse {
		-webkit-flex-wrap: wrap-reverse;
		flex-wrap: wrap-reverse;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		height: 50px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128630564-2ab7c1fc-6bec-4774-ac44-cbee5a66f25b.png)

![image](https://user-images.githubusercontent.com/43658658/128630568-1caf47f1-eb49-4c71-9ff7-4ac9eee147b3.png)

> <h3>align-content 속성</h3>

align-content 속성은 flex-wrap 속성의 동작을 변경할 수 있습니다.

이 속성은 align-items 속성과 비슷한 동작을 하지만, 플렉스 요소를 정렬하는 대신에 플렉스 라인을 정렬합니다.

이 속성은 다음과 같은 속성값을 가질 수 있습니다.

 

1. stretch : 기본 설정으로, 플렉스 라인의 높이가 남는 공간을 전부 차지하게 됩니다.

2. flex-start : 플렉스 라인은 플렉스 컨테이너의 앞쪽에 뭉치게 됩니다.

3. flex-end : 플렉스 라인은 플렉스 컨테이너의 뒤쪽에 뭉치게 됩니다.

4. center : 플렉스 라인은 플렉스 컨테이너의 가운데에 뭉치게 됩니다.

5. space-between : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다.

6. space-around : 플렉스 라인은 플렉스 컨테이너에 고르게 분포됩니다. 단, 양쪽 끝에 약간의 공간을 남겨둡니다.

 

다음 예제는 align-content 속성의 stretch, space-between과 space-around 속성값을 이용한 예제입니다.

``` html
<style>
	.flexbox {
		background-color: dimgray;
		width: 200px;
		height: 300px;
		border-radius: 15px;
		display: -webkit-flex;
		display: flex;
		-webkit-flex-wrap: wrap;
		flex-wrap: wrap;
	}
	#space_between {
		-webkit-align-content: space-between;
		align-content: space-between;
	}
	#space_around {
		-webkit-align-content: space-around;
		align-content: space-around;
	}
	.item {
		background-color: darkgray;
		border-radius: 10px;
		width: 80px;
		margin: 10px;
		color: white;
		font-size: 26px;
		text-align: center;
		line-height: 50px;
	}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128631046-d72e737c-f1e6-4ca8-81a7-21cd36f58fda.png)

![image](https://user-images.githubusercontent.com/43658658/128631056-cd60258d-2a5a-4831-becd-f61960d1b18b.png)

다음 예제는 align-content 속성의 flex-start, center와 flex-end 속성값을 이용한 예제입니다.

``` html
#flex_start {
	-webkit-align-content: flex-start;
	align-content: flex-start;
}
#center {
	-webkit-align-content: center;
	align-content: center;
}
#flex_end {
	-webkit-align-content: flex-end;
	align-content: flex-end;
}
```

![image](https://user-images.githubusercontent.com/43658658/128631082-e4ad8b3d-f70b-409f-9c5d-d78db520254c.png)

![image](https://user-images.githubusercontent.com/43658658/128631086-102ec8ec-e745-4a31-b49f-45b69c74e2a5.png)

center를 보면 align-items와의 차이점을 알 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/128631113-1fd44d54-eac4-4e0d-b961-1ae2f258a03b.png)
![image](https://user-images.githubusercontent.com/43658658/128631124-d0a6609e-cf25-4572-bcd7-551a12c27f47.png)

> <h3>플렉스 요소(flex item)의 order 속성</h3>

order 속성은 플렉스 컨테이너 안에 있는 플렉스 요소들의 순서를 설정합니다.

기본값은 `0`이며 음수일 경우 0보다 앞에 위치, 양수일 경우 0보다 뒤에 위치합니다.

``` html
#first {
	-webkit-order: -2;
	order: -2;
}
#second {
	-webkit-order:-1;
	order:-1;
}
...
<div class="flexbox">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item" id="second">3</div>
	<div class="item" id="first">4</div>
	<div class="item">5</div>
	<div class="item">6</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128631208-68c9b93f-491e-4d65-9298-1bfa314eb585.png)

> <h3>플렉스 요소(flex item)의 margin 속성</h3>

margin 속성값을 auto로 설정하면, 수평 방향의 여유 공간을 없앨 수 있습니다. 

이 속성을 이용하면 플렉스 요소들을 서로 반대 방향으로 밀어내 위치시킬 수 있습니다.

``` html
<style>
      #first .item:nth-child(1) { margin-right:auto; }
      #second .item:nth-child(2) { margin-right:auto; }
</style>
...
<div class="flexbox" id="first">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
<div class="flexbox" id="second">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128631324-0354248b-b319-41b6-8b41-6dc734984934.png)

또한, margin 속성을 이용하여 수직과 수평 방향의 가운데 정렬을 손쉽게 설정할 수도 있습니다.

``` html
.item {
	background-color: darkgray;
	border-radius: 10px;
	width: 80px;
	height: 50px;
	color: white;
	font-size: 20px;
	text-align: center;
	line-height: 50px;
	margin: auto;
}
...
<div class="flexbox">
	<div class="item">Center</div>
	<div class="item">Center</div>
	<div class="item">Center</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/128631383-4184e607-d134-4aff-ae49-928069e412e4.png)

> <h3>플렉스 요소(flex item)의 align-self 속성</h3>

align-self 속성은 플렉스 컨테이너의 align-items 속성보다 우선 적용됩니다.

이 속성을 이용하면 플렉스 요소마다 서로 다른 align 속성값을 설정할 수 있습니다.

``` html
.item:nth-child(2) {
	-webkit-align-self: flex-start;
	align-self: flex-start;
}
.item:nth-child(3) {
	-webkit-align-self: flex-end;
	align-self: flex-end;
}
.item:nth-child(4) {
	-webkit-align-self: center;
	align-self: center;
}
.item:nth-child(5) {
	-webkit-align-self: baseline;
	align-self: baseline;
}
```

![image](https://user-images.githubusercontent.com/43658658/128631440-2e7a917d-65d5-415e-872f-858cadf480f1.png)

> <h3>플렉스 요소(flex item)의 flex 속성</h3>

flex 속성을 이용하면 같은 플렉스 컨테이너 안에 있는 플렉스 요소의 너비를 상대적으로 설정할 수 있습니다.

다음 예제에서 첫 번째 플렉스 요소는 전체 너비의 3/5을 차지하며, 나머지 두 요소는 각각 전체 너비의 1/5씩을 차지하게 됩니다.

``` html
.item:nth-child(1) { /* 3/5 */
	-webkit-flex: 3;
	flex: 3;
}
.item:nth-child(2) { /* 1/5 */
	-webkit-flex: 1;
	flex: 1;
}
.item:nth-child(3) { /* 1/5 */
	-webkit-flex: 1;
	flex: 1;
}
```

![image](https://user-images.githubusercontent.com/43658658/128631495-d0ece3d6-776f-475e-a79f-e1a899fd749d.png)

## 미디어 쿼리

CSS2에서는 @media 규칙을 통해 서로 다른 매체 유형(media type)을 위한 맞춤식 스타일 시트(style sheet)를 지원합니다.

예를 들면, HTML 문서가 스크린에 표현될 때와 프린트할 때 서로 다른 스타일을 적용할 수 있습니다.

 

CSS3에서는 @media 규칙을 더욱 발전시켜 매체 유형(media type)과 하나 이상의 표현식(expression)으로 구성된 미디어 쿼리(media query)를 사용할 수 있습니다.

미디어 쿼리(media query)는 width, height, color 속성과 같은 미디어 관련 속성을 이용한 표현식을 통해 스타일이 적용되는 범위를 조절할 수 있습니다.

미디어 쿼리를 사용하면 콘텐츠(content)를 별도로 변경하지 않아도 웹 페이지에 접속하고 있는 기기에 알맞은 형태로 스타일이 조정됩니다.

> <h3>미디어 쿼리 문법</h3>

다음은 같은 파일 내의 `<style>`태그 안에 미디어 쿼리가 위치할 경우의 문법입니다.

`@media only|not 매체유형 and (표현식) { CSS스타일코드; }`

또 다른 방법으로는 외부 CSS 파일에 미디어 쿼리를 따로 저장할 수도 있습니다.

`<link rel="stylesheet" media="매체유형 and|only|not (표현식)" href="CSS파일URL"/>`

만약 웹 페이지에 접속하고 있는 기기의 매체 유형과 명시된 매체 유형이 일치하고, 모든 표현식이 참(true)이면, 미디어 쿼리는 참(true)을 반환합니다.

이렇게 미디어 쿼리의 반환값이 참이면, 해당 블록 안에 명시된 CSS 스타일 코드가 실행됩니다.

여기에 and, only, not 등과 같은 키워드를 사용하여 더욱 복잡한 조건을 명시할 수도 있습니다.

> <h3>CSS3 매체 유형(media type)</h3>

CSS3의 매체 유형은 이전 CSS2에서 정의된 것을 그대로 사용하고 있습니다.

다음은 자주 사용되는 매체 유형(media type)입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">매체 유형</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>all</td>
			<td>모든 매체에 사용함.</td>
		</tr>
		<tr>
			<td>print</td>
			<td>프린터 기기에 사용함.</td>
		</tr>
		<tr>
			<td>screen</td>
			<td>컴퓨터나 태블릿, 스마트폰 등 스크린(screen)이 있는 매체에 사용함.</td>
		</tr>
		<tr>
			<td>speech</td>
			<td>웹 페이지를 읽어주는 스크린 리더(screenreader)에 사용함.</td>
		</tr>
	</tbody>
</table>

> <h3>CSS3 미디어 쿼리(media query) 속성</h3>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>width</td>
			<td>화면의 너비</td>
		</tr>
		<tr>
			<td>height</td>
			<td>화면의 높이</td>
		</tr>
		<tr>
			<td>device-width</td>
			<td>매체 화면의 너비</td>
		</tr>
		<tr>
			<td>device-height</td>
			<td>매체&nbsp;화면의&nbsp;높이</td>
		</tr>
		<tr>
			<td>devie-aspect-ratio</td>
			<td>매체 화면의 비율</td>
		</tr>
		<tr>
			<td>orientation</td>
			<td>매체 화면의 방향</td>
		</tr>
		<tr>
			<td>color</td>
			<td>매체의 색상 비트 수</td>
		</tr>
		<tr>
			<td>color-index</td>
			<td>매체에서 표현 가능한 색상의 개수</td>
		</tr>
		<tr>
			<td>monochrome</td>
			<td>흑백 매체에서의 픽셀당 비트 수</td>
		</tr>
		<tr>
			<td>resolution</td>
			<td>매체의 해상도</td>
		</tr>
	</tbody>
</table>

> <h3>CSS3 미디어 쿼리(media query) 예제</h3>

다음 예제는 뷰포트의 너비가 480픽셀이거나 그 이하일 경우에는 배경색을 darkorange로 표현해 줍니다.

하지만 뷰포트의 너비가 그 초과일 경우에는 배경색을 lightblue로 바꿔서 표현해 줍니다.

``` html
<style>
	body { background-color: darkorange; }
	@media screen and (min-width: 480px) {
		body {
			background-color: lightblue;
		}
	}
</style>
```

브라우저 창의 너비가 480px보다 크다면,

![image](https://user-images.githubusercontent.com/43658658/128631935-a59737e1-ffeb-4447-abf1-8bba61e4f64b.png)

브라우저 창의 너비가 480px보다 작다면,

![image](https://user-images.githubusercontent.com/43658658/128631945-9463e866-e5f7-4382-8211-3230c54d05bc.png)

다음 예제를 웹 브라우저에서 실행하면 배경색을 검정색으로, 텍스트의 색상은 흰색으로 표현합니다.

하지만 웹 페이지를 프린트하게 되면 배경색을 흰색으로, 텍스트의 색상을 검정색으로 바꿔서 프린트합니다.

``` html
<style>
	@media screen {
		body {
			background-color: black;
			color: white;
		}
	}
	@media print {
		body {
			background-color: white;
			color: black;
		}
	}
</style>
```

