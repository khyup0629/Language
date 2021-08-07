# Part 9. CSS3 확장

+ [CSS3 버튼(#CSS3-버튼)
+ 

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
