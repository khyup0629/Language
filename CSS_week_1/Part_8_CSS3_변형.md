# Part 8. CSS3 변형

+ [2D Transform](#2D-Transform)

## 2D Transform

> <h3>변형(Transform)</h3>

CSS3에서는 transform 속성을 사용하여 HTML 요소의 모양, 크기, 위치 등을 자유롭게 바꿀 수 있습니다.


transform 속성은 HTML 요소에 대해 다음과 같은 동작을 제공합니다.

 

- 해당 요소를 움직입니다.

- 해당 요소를 회전시킵니다.

- 해당 요소의 크기를 변경합니다.

- 해당 요소를 기울입니다.

- 해당 요소에 위의 네 가지 동작 중 원하는 동작들을 한 번에 적용시킵니다.

 

CSS3에서는 transform 속성을 사용하여 2D 변형(transform)과 3D 변형(transform)을 모두 제공합니다.

2D 변형(transform)을 위해 제공되는 메소드(method)는 다음과 같습니다.

1. translate()

2. rotate()

3. scale()

4. skew()

5. matrix()

> <h3>translate() 메소드</h3>

`translate()` 메소드는 현재 위치에서 해당 요소를 주어진 x축과 y축의 거리만큼 이동시킵니다.

주어진 거리가 양수이면 해당 축의 양의 방향으로, 음수이면 해당 축의 음의 방향으로 이동시킵니다.

`translateX()`, `translateY()`를 통해 x, y를 따로 설정할 수 있습니다.

``` html
<style>
  div { width:200px; height:150px; position:absolute; }
  #origin { border:3px solid black; }
  #trans { border:3px solid red; background-color:lightblue;
    -webkit-transform: translate(100px, 50px);
    -ms-transform: translate(100px, 50px);
    transform: translate(100px, 50px);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588427-788d5b3f-9d8f-443a-b19f-75e4245a61ae.png)

> <h3>rotate() 메소드</h3>

`rotate()` 메소드는 해당 요소를 주어진 각도만큼 시계 방향이나 반시계 방향으로 회전시킵니다.

주어진 각도가 양수이면 시계 방향으로, 음수이면 반시계 방향으로 회전시킵니다.

``` html
<style>
  div {
    height: 150px;
    width: 200px;
    position: absolute;
    margin: 30px
  }
  #origin { border: 3px solid black; }
  #rotate {
    background-color: #87CEFA;
    border: 3px solid red;
        -webkit-transform: rotate(30deg);
        -ms-transform: rotate(30deg);
        transform : rotate(30deg);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588422-f5e3e07d-93f9-427e-9000-0319f9ff0532.png)

> <h3>scale() 메소드</h3>

`scale()` 메소드는 해당 요소의 크기를 주어진 배율만큼 늘리거나 줄입니다.

주어진 배율이 `1보다 크면` 크기를 늘리고, `0보다 크고 1보다 작으면` 크기를 줄입니다.

`scaleX()`, `scaleY()`를 통해 x, y를 따로 설정할 수 있습니다.

``` html
<style>
    div { width:200px; height:150px; margin:100px; position:absolute; }
    #origin { border:3px solid black; }
    #scale_in { 
      -webkit-transform: scale(1.5, 2);
      -ms-transform: scale(1.5, 2);
      transform: scale(1.5, 2);
      border:3px solid red;
    }
    #scale_de {
      -webkit-transform: scale(0.7, 0.7);
      -ms-transform: scale(0.7, 0.7);
      transform: scale(0.7, 0.7);
      border:3px solid orange;
    }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588417-37f5653a-a34e-42e2-8f29-19a93280d32c.png)

> <h3>skewX() 메소드</h3>

`skewX()` 메소드는 해당 요소를 주어진 각도만큼 x축 방향으로 기울입니다.

주어진 각도가 양수이면 x축의 양의 방향으로, 음수이면 x축의 음의 방향으로 기울입니다.

``` html
<style>
    div { width:200px; height: 150px; margin:50px; position:absolute; }
    #origin { border:3px solid black; }
    #skew_x { border:3px solid red; background-color:lightblue;
      -webkit-transform: skewX(20deg);
      -ms-transform: skewX(20deg);
      transform: skewX(20deg);
    }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588387-a12eb216-699b-4f81-9d6e-9417d9ec7385.png)

> <h3>skewY() 메소드</h3>

`skewY()` 메소드는 해당 요소를 주어진 각도만큼 y축 방향으로 기울입니다.

주어진 각도가 양수이면 y축의 양의 방향으로, 음수이면 y축의 음의 방향으로 기울입니다.

``` html
<style>
  div {
    height: 150px;
    width: 200px;
    position: absolute;
    margin: 30px
  }
  #origin { border: 3px solid black; }
  #skew_y {
    background-color: #87CEFA;
    border: 3px solid red;
    -webkit-transform: skewY(20deg);
    -ms-transform: skewY(20deg);
    transform: skewY(20deg);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588404-9f989886-fa6c-4400-a797-6c4c98fc5045.png)

> <h3>skew() 메소드</h3>

`skew()` 메소드는 해당 요소를 주어진 각도만큼 각각 x축과 y축 방향으로 기울입니다.

``` html
<style>
  div {
    height: 150px;
    width: 200px;
    position: absolute;
    margin: 50px
  }
  #origin { border: 3px solid black; }
  #skew {
    background-color: #87CEFA;
    border: 3px solid red;
    -webkit-transform: skew(20deg, 30deg);
    -ms-transform: skew(20deg, 30deg);
    transform: skew(20deg, 30deg);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588511-1100dd2f-1997-425e-abfd-32bbec18fb15.png)

> <h3>matrix() 메소드</h3>

`matrix()` 메소드는 모든 2D transform 메소드를 한 줄에 설정할 수 있도록 해줍니다.

이 메소드는 2D 변형(transform)과 관련된 6개의 매개변수를 가집니다.

matrix() 메소드의 매개변수 순서는 다음과 같습니다.

`matrix(scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY());`

+ 주의: matrix로 skew를 지정해 줄 땐 `deg`로 하면 안되고, 소숫점으로 표기해야한다.
  + 예를 들어, 20deg라면 0.2, 30deg라면 0.3으로 표기한다.

``` html
<style>
  div {
    height: 150px;
    width: 200px;
    position: absolute;
    margin: 30px
  }
  #origin { border: 3px solid black; }
  #matrix {
    background-color: #87CEFA;
    border: 3px solid red;
    -webkit-transform: matrix(2, 0.3, 0.2, 1.3, 150, 100);
        -ms-transform: matrix(2, 0.3, 0.2, 1.3, 150, 100);
        transform: matrix(2, 0.3, 0.2, 1.3, 150, 100);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128588763-166793e9-3585-4c23-a921-f84f102897c9.png)

## 3D Transform

CSS3에서는 transform 속성을 사용하여 HTML 요소의 모양, 크기 위치 등을 입체적으로 변형시킬 수 있습니다.

3D 변형(transform)을 위해 제공되는 메소드(method)는 다음과 같습니다.

 

1. rotate()

2. translate()

3. scale()

4. matrix()

5. perspective()


> <h3>rotateX() 메소드</h3>

`rotateX()` 메소드는 해당 요소를 주어진 각도만큼 x축을 중심으로 회전시킵니다.

주어진 각도가 양수이면 x축 양의 방향으로, 음수이면 x축 음의 방향으로 회전시킵니다.

``` html
<style>
		div {
			height: 150px;
			width: 200px;
			margin: 10px;
		}
      #origin { border:3px solid black; }
      .rotate {
        border:3px solid red;
        background-color:#87CEFA;
		}
      #rotate_01 {
        -webkit-transform: rotateX(20deg);
        transform: rotateX(20deg);
      }
		#rotate_02 {
			-webkit-transform: rotateX(40deg);
			transform: rotateX(40deg);
		}
		#rotate_03 {
			-webkit-transform: rotateX(60deg);
			transform: rotateX(60deg);
		}
		#rotate_04 {
			-webkit-transform: rotateX(80deg);
			transform: rotateX(80deg);
		}
		#rotate_05 {
			-webkit-transform: rotateX(100deg);
			transform: rotateX(100deg);
		}
		#rotate_06 {
			-webkit-transform: rotateX(120deg);
			transform: rotateX(120deg);
		}
		#rotate_07 {
			-webkit-transform: rotateX(140deg);
			transform: rotateX(140deg);
		}
		#rotate_08 {
			-webkit-transform: rotateX(160deg);
			transform: rotateX(160deg);
		}
		#rotate_09 {
			-webkit-transform: rotateX(180deg);
			transform: rotateX(180deg);
		}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128589144-b7ae3307-ce2c-4cff-9cbf-ba368664ad35.png)

![image](https://user-images.githubusercontent.com/43658658/128589153-18f80cf9-73c3-4b03-b45a-feaac5527dc1.png)

![image](https://user-images.githubusercontent.com/43658658/128589158-31c15e6f-053b-4858-b68c-47f0fee08a20.png)

![image](https://user-images.githubusercontent.com/43658658/128589164-9dd6f7b5-6bef-4b81-a037-1830c6a0e28e.png)

> <h3>rotateY() 메소드</h3>

`rotateY()` 메소드는 해당 요소를 주어진 각도만큼 y축을 중심으로 회전시킵니다.

주어진 각도가 양수이면 y축 양의 방향으로, 음수이면 y축 음의 방향으로 회전시킵니다.

``` html
<style>
		div {
			height: 150px;
			width: 200px;
			margin: 10px;
		}
		#origin { border: 3px solid black; }
		.rotate {
			background-color: #87CEFA;
			border: 3px solid red;
		}
		#rotate_09 {
			-webkit-transform: rotateY(180deg);
			transform: rotateY(180deg);
		}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128589220-6ad0db01-e42b-4593-a4b1-f9974e23d5bd.png)

> <h3>rotateZ() 메소드</h3>

`rotateZ()` 메소드는 해당 요소를 주어진 각도만큼 z축을 기준으로 회전시킵니다.

주어진 각도가 양수이면 z축 양의 방향으로, 음수이면 z축 음의 방향으로 회전시킵니다.

``` html
<style>
		div {
			height: 150px;
			width: 200px;
			margin: 50px;
		}
		#origin { border: 3px solid black; }
		.rotate {
			background-color: #87CEFA;
			border: 3px solid red;
		}
		#rotate_01 {
			-webkit-transform: rotateZ(20deg);
			transform: rotateZ(20deg);
		}
		#rotate_02 {
			-webkit-transform: rotateZ(40deg);
			transform: rotateZ(40deg);
		}
		#rotate_03 {
			-webkit-transform: rotateZ(60deg);
			transform: rotateZ(60deg);
		}
		#rotate_04 {
			-webkit-transform: rotateZ(80deg);
			transform: rotateZ(80deg);
		}
		#rotate_05 {
			-webkit-transform: rotateZ(100deg);
			transform: rotateZ(100deg);
		}
		#rotate_06 {
			-webkit-transform: rotateZ(120deg);
			transform: rotateZ(120deg);
		}
		#rotate_07 {
			-webkit-transform: rotateZ(140deg);
			transform: rotateZ(140deg);
		}
		#rotate_08 {
			-webkit-transform: rotateZ(160deg);
			transform: rotateZ(160deg);
		}
		#rotate_09 {
			-webkit-transform: rotateZ(180deg);
			transform: rotateZ(180deg);
		}
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128589282-ead18f22-51a3-47d2-a400-8515d2aa63a6.png)

> <h3>translate3d() 메소드</h3>

`translate3d()` 메소드는 현재 위치에서 해당 요소를 주어진 x축과 y축, z축의 거리만큼 이동시킵니다.

주어진 거리가 양수이면 해당 축의 양의 방향으로, 음수이면 해당 축의 음의 방향으로 이동시킵니다.

rotate3d(), translate3d(), scale3d() 메소드와 같이 입체적으로 보여지는 3D 변형에 관련된 메소드는 원근감을 표현할 기준을 명시해야 합니다.

``` html
<style>
		div {
    height: 150px;
    width: 200px;
            box-sizing: border-box;
    margin: 10px;
		}
		#origin { border: 3px solid black; }
		.trans {
    background-color: #87CEFA;
    border: 3px solid red;
		}
		#trans_01 {
    -webkit-transform: translate(100px, 50px);
    -ms-transform: translate(100px, 50px);
    transform: translate(100px, 50px);	
		}
  #trans_02 {
    -webkit-transform: perspective(500px) translate3d(100px, 50px, -150px);
    -ms-transform: perspective(500px) translate3d(100px, 50px, -150px);
    transform: perspective(500px) translate3d(100px, 50px, -150px);
  }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/128589435-e7445439-237a-417d-ab79-222f9eac671f.png)

위의 예제에서는 perspective() 메소드를 사용하여 원근감을 표현하기 위해 사용할 픽셀 수를 500px로 설정하고 있습니다.

> <h4>CSS3 3D transform 속성</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>transform</td>
			<td>요소에 2D 또는 3D 변형(transform)을 적용함.</td>
		</tr>
		<tr>
			<td>transform-origin</td>
			<td>요소에 변형(transform)을 적용하는 변환 중심을 설정함.</td>
		</tr>
		<tr>
			<td>transform-style</td>
			<td>요소에 변형을 적용할 때 그 변환이 자식(child) 요소들에게도 적용될지 안 될지를 설정함.</td>
		</tr>
		<tr>
			<td>perspective</td>
			<td>3D 요소에 원근감을 표현할 때 사용할 픽셀 수를 설정함.</td>
		</tr>
		<tr>
			<td>perspective-origin</td>
			<td>3D 요소에 원근감을 표현할 때 사용할 기준 축을 설정함.</td>
		</tr>
		<tr>
			<td>backface-visibility</td>
			<td>요소의 앞면만을 표현하고, 뒷면을 표현할지 안 할지를 설정함.</td>
		</tr>
	</tbody>
</table>

> <h4>CSS3 3D transform 메소드</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">메소드</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>matrix3d(n&times;16)</td>
			<td>4x4 행렬을 이용한 16개의 매개변수로 모든 3D 변형 메소드를 한 번에 설정함.</td>
		</tr>
		<tr>
			<td>rotate3d(x,y,z,angle)</td>
			<td>해당 요소를 주어진 각도만큼 x축, y축과 z축을 기준으로 회전시킴.</td>
		</tr>
		<tr>
			<td>rotateX(angle)</td>
			<td>해당 요소를 주어진 각도만큼 x축을 기준으로 회전시킴.</td>
		</tr>
		<tr>
			<td>rotateY(angle)</td>
			<td>해당 요소를 주어진 각도만큼 y축을 기준으로 회전시킴.</td>
		</tr>
		<tr>
			<td>rotateZ(angle)</td>
			<td>해당 요소를 주어진 각도만큼 z축을 기준으로 회전시킴.</td>
		</tr>
		<tr>
			<td>translate3d(x,y,z)</td>
			<td>현재의 위치에서 해당 요소를 주어진 x축, y축과 z축의 거리만큼 이동시킴.</td>
		</tr>
		<tr>
			<td>translateX(x)</td>
			<td>현재의 위치에서 해당 요소를 주어진 x축의 거리만큼 이동시킴.</td>
		</tr>
		<tr>
			<td>translateY(y)</td>
			<td>현재의 위치에서 해당 요소를 주어진 y축의 거리만큼 이동시킴.</td>
		</tr>
		<tr>
			<td>translateZ(z)</td>
			<td>현재의 위치에서 해당 요소를 주어진 z축의 거리만큼 이동시킴.</td>
		</tr>
		<tr>
			<td>scale3d(x,y,z)</td>
			<td>해당 요소의 크기를 주어진 배율만큼 x축, y축과 z축 방향으로 늘리거나 줄임.</td>
		</tr>
		<tr>
			<td>scaleX(x)</td>
			<td>해당 요소의 x축 크기를 주어진 배율만큼 늘리거나 줄임.</td>
		</tr>
		<tr>
			<td>scaleY(y)</td>
			<td>해당 요소의 y축 크기를 주어진 배율만큼 늘리거나 줄임.</td>
		</tr>
		<tr>
			<td>scaleZ(z)</td>
			<td>해당 요소의 z축 크기를 주어진 배율만큼 늘리거나 줄임.</td>
		</tr>
		<tr>
			<td>perspective(n)</td>
			<td>3D 요소에 원근감을 표현할 때 사용할 픽셀 수를 설정함.</td>
		</tr>
	</tbody>
</table>
