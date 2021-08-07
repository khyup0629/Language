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

