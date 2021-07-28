# Part 11. HTML5 API

+ [geolocation API](#geolocation-API)
+ [drag and drop API](#drag-and-drop-API)
+ 

## geolocation API

geolocation API는 사용자의 현재 위치 정보를 가져올 때 사용하는 자바스크립트 API입니다.

사용자의 위도 및 경도에 관한 정보는 자바스크립트를 이용해 웹 서버로 전송됩니다.

이것을 이용하면 사용자의 위치를 지도에 표시하거나, 사용자 근처의 상점을 찾아주는 등의 위치기반 서비스를 할 수 있습니다.

하지만 이러한 정보는 사용자의 사생활을 침해할 가능성이 높으므로, 사용자의 동의 없이는 사용할 수 없도록 하고 있습니다.

+ 크롬 50.0 버전부터는 https와 같은 보안 프로토콜에서만 geolocation API가 동작하도록 허용하고 있습니다.

> <h3>getCurrentPosition() 메소드</h3>

getCurrentPosition() 메소드를 이용하면 사용자의 위치에 대한 위도와 경도값을 얻을 수 있습니다.

이 메소드의 첫 번째 인수로는 가져온 사용자의 위치 정보를 출력하는 함수가 들어갑니다.

이 메소드의 두 번째 인수로는 위치 정보에 관한 오류를 처리하는 함수가 들어갑니다.

``` html
<h1>geolocation을 이용한 위도와 경도 찾기</h1>

<button onclick="findLocation()">현재 위치의 위도와 경도</button>
<p id="myLocation"></p>

<script>
  var loc = document.getElementById("myLocation");
  function findLocation() {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(showYourLocation, showErrorMsg);
    } else { 
      loc.innerHTML = "이 문장은 사용자의 웹 브라우저가 Geolocation API를 지원하지 않을 때 나타납니다!";
    }
  }

  function showYourLocation(position) {
    loc.innerHTML = "현재 사용자는 위도 " + position.coords.latitude + ", 경도 " + position.coords.longitude + "에 위치하고 있습니다.";	
  }

      function showErrorMsg(error) {
        switch (error.code){
          case error.PERMISSION_DENIED:
            loc.innerHTML = "이 문장은 사용자가 Geolocation API의 사용 요청을 거부했을 때 나타납니다!"
            break;
          case error.POSITION_UNAVAILABLE:
            loc.innerHTML = "이 문장은 가져온 위치 정보를 사용할 수 없을 때 나타납니다!"
            break;
          case error.TIMEOUT:
            loc.innerHTML = "이 문장은 위치 정보를 가져오기 위한 요청이 허용 시간을 초과했을 때 나타납니다!"
            break;
          case error.UNKNOWN_ERROR:
            loc.innerHTML = "이 문장은 알 수 없는 오류가 발생했을 때 나타납니다!"
            break;
                          }
      }
</script>
```

사용자의 위치 정보를 구글 맵을 통해 표시할 수 있습니다.

``` html
<h1>구글 맵을 통한 사용자의 위치 표시</h1>

<button onclick="findLocation()">사용자의 위치 표시</button>
<p id="myLocation"></p>
<div id="mapLocation"></div>

<script>
  var loc = document.getElementById("myLocation");
  function findLocation() {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(showYourLocation, showErrorMsg);
    } 
        else { 
      loc.innerHTML = "이 문장은 사용자의 웹 브라우저가 Geolocation API를 지원하지 않을 때 나타납니다!";
    }
  }

  function showYourLocation(position) {
    var userLat = position.coords.latitude;
    var userLng = position.coords.longitude;
    var imgUrl = "http://maps.googleapis.com/maps/api/staticmap?center=" + userLat + "," + userLng + "&zoom=15&size=500x400&sensor=false";
    document.getElementById("mapLocation").innerHTML = "<img src='"+imgUrl+"'>";
  }

  function showErrorMsg(error) {
    switch(error.code) {
      case error.PERMISSION_DENIED:
      loc.innerHTML = "이 문장은 사용자가 Geolocation API의 사용 요청을 거부했을 때 나타납니다!"
      break;
      case error.POSITION_UNAVAILABLE:
      loc.innerHTML = "이 문장은 가져온 위치 정보를 사용할 수 없을 때 나타납니다!"
      break;
      case error.TIMEOUT:
      loc.innerHTML = "이 문장은 위치 정보를 가져오기 위한 요청이 허용 시간을 초과했을 때 나타납니다!"
      break;
      case error.UNKNOWN_ERROR:
      loc.innerHTML = "이 문장은 알 수 없는 오류가 발생했을 때 나타납니다!"
      break;
    }
  }
</script>
```

위의 예제처럼 단순한 이미지로 표시하는 것이 아닌 구글 맵 스크립트를 이용한 연동도 가능합니다.

`showYourLocation` 함수를 아래와 같이 작성해줍니다.

``` html
function showYourLocation(position) {
    var userLat = position.coords.latitude;
    var userLng = position.coords.longitude;
    var userLocation = new google.maps.LatLng(userLat, userLng);
    loc = document.getElementById("mapLocation");
    loc.style.width = '500px';
    loc.style.height = '400px';
    var mapOptions = { 
        center: userLocation, 
        zoom: 15, 
        mapTypeId: google.maps.MapTypeId.ROADMAP,
        mapTypeControl: false, 
        navigationControlOptions: {style: google.maps.NavigationControlStyle.SMALL} 
    }
    var map = new google.maps.Map(loc, mapOptions);
    var marker = new google.maps.Marker({position:userLocation,map:map,title:"여기가 현재 위치입니다!"});
}
```

> <h4>Geolocation API 메소드</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>Method</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>getCurrentPosition()</td>
			<td>사용자의 현재 위치를 가져옴.</td>
		</tr>
		<tr>
			<td>watchPosition()</td>
			<td>사용자의 현재 위치를 가져오고 나서, 사용자의 움직임에 따라 지속적으로 위치 정보를 갱신함.</td>
		</tr>
		<tr>
			<td>clearWatch()</td>
			<td>watchPosition() 메소드의 실행을 중지함.</td>
		</tr>
	</tbody>
</table>

> <h4>getCurrentPosition() 메소드의 반환값</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>속성</th>
			<th>반환값</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>coords.latitude</td>
			<td>소수로 표현된 위도 값</td>
		</tr>
		<tr>
			<td>coords.longitude</td>
			<td>소수로 표현된 경도 값</td>
		</tr>
		<tr>
			<td>coords.accuracy</td>
			<td>위도 값과 경도 값의 정확도</td>
		</tr>
		<tr>
			<td>coords.altitude</td>
			<td>평균 해수면을 기준으로 하는 고도 값(해발)</td>
		</tr>
		<tr>
			<td>coords.altitudeAccuracy</td>
			<td>고도 값의 정확도</td>
		</tr>
		<tr>
			<td>coords.heading</td>
			<td>북쪽을 기준으로 현재 진행 방향에 대한 시계방향으로의 각도 값(˚)</td>
		</tr>
		<tr>
			<td>coords.speed</td>
			<td>초당 이동한 미터 수를 나타내는 속도 값(초속)</td>
		</tr>
		<tr>
			<td>timestamp</td>
			<td>위치 정보를 가져온 시간을 나타냄.</td>
		</tr>
	</tbody>
</table>

## drag and drop API

드래그 앤 드롭 API는 웹 페이지 내의 요소를 사용자가 자유롭게 드래그할 수 있도록 설정해줍니다.

HTML5 이전에 이와 같은 기능을 구현하기 위해서는 엄청나게 많고 복잡한 스크립트를 작성해야 했습니다.

하지만 HTML5에서는 드래그 앤 드롭(drag and drop) 기능이 표준 권고안에 포함되어 간단하게 사용할 수 있게 되었습니다.

현재 주요 웹 브라우저들은 모두 이 기능을 지원하며, 따라서 웹 페이지 내의 모든 요소는 드래그될 수 있습니다.

> <h3>드래그 앤 드롭 이벤트</h3>

마우스로 객체(object)를 드래그해서 놓을 때까지 여러 단계의 이벤트가 순차적으로 발생하게 됩니다.

다음 표는 드래그 앤 드롭시 일어나는 이벤트를 순서대로 보여줍니다.

1. dragstart	사용자가 객체(object)를 드래그하려고 시작할 때 발생함.
2. dragenter	마우스가 대상 객체의 위로 처음 진입할 때 발생함.
3. dragover	드래그하면서 마우스가 대상 객체의 위에 자리 잡고 있을 때 발생함.
4. drag	대상 객체를 드래그하면서 마우스를 움직일 때 발생함.
5. drop	드래그가 끝나서 드래그하던 객체를 놓는 장소에 위치한 객체에서 발생함.
6. dragleave	드래그가 끝나서 마우스가 대상 객체의 위에서 벗어날 때 발생함.
7. dragend	대상 객체를 드래그하다가 마우스 버튼을 놓는 순간 발생함.

> <h3>DataTransfer 객체</h3>

드래그 앤 드롭 이벤트를 위한 모든 이벤트 리스너 메소드(event listener method)는 **DataTransfer 객체**를 반환합니다.

이렇게 반환된 **DataTransfer 객체**는 **드래그 앤 드롭 동작에 관한 정보**를 가지고 있게 됩니다.

> <h3>draggable 속성</h3>

웹 페이지 내의 모든 요소는 draggable 속성을 사용하여 드래그될 수 있는 객체(draggable object)로 변환될 수 있습니다.

드래그를 원하는 요소의 속성으로 `draggable="true"`를 작성합니다.

> <h3>ondragstart 속성</h3>

드래그될 수 있는 객체로 만든 후에는 ondragstart 속성을 통해 DataTransfer 객체의 setData() 메소드를 호출합니다.

setData() 메소드는 드래그되는 대상 객체의 **데이터(data)와 타입(data type)** 을 설정합니다.

`dragstart` 이벤트가 발생할 때 `drag` 함수를 호출하고 `event.dataTransfer.setData()` 메소드를 호출합니다.

드래그를 원하는 요소의 속성으로 `ondragstart="drag(event)"`를 적어주고

`drag(event)`라는 함수를 `<script>` 내에 작성해줍니다.

``` html
<script>
	function drag(ev) {
		ev.dataTransfer.setData("text", ev.target.id);
	}
</script>
```

> <h3>ondragover 속성</h3>

ondragover 속성은 드래그되는 대상 객체가 어느 요소 위에 놓일 수 있는지를 설정합니다.

기본적으로 HTML 요소는 다른 요소의 위에 위치할 수 없습니다.

따라서 다른 요소 위에 위치할 수 있도록 만들기 위해서는 놓일 장소에 있는 요소의 기본 동작을 막아야만 합니다.

이 작업을 event.preventDefault() 메소드를 호출하는 것만으로 간단히 설정할 수 있습니다.

`dragover` 이벤트가 발생할 때 `dragEvent` 함수를 호출해서 `event.preventDefault()` 메소드를 호출합니다.

Drop이 가능한 요소의 속성으로 `ondragover="dragEvent(event)"`를 적어주고,

`dragEvent(event)`라는 함수를 `<script>` 내에 작성해줍니다.

``` html
<script>
	function dragEvent(ev){
		ev.preventDefault();
	}
</script>
```

> <h3>ondrop 속성</h3>

드래그하던 객체를 놓으면 drop 이벤트가 발생합니다.

ondrop 속성을 이용하여 drop 이벤트에 대한 동작을 설정할 수 있습니다.

``` html
<h1>드래그 앤 드롭을 이용한 객체의 이동</h1>

<p>모나리자 그림을 드래그해서 옆의 사각형으로 옮겨보세요!</p>

<div ondrop="drop(event)" ondragover="dragEnter(event)">
	<img id="monalisa" width="180" height="280" src="/examples/images/img_monalisa.png" draggable="true" ondragstart="drag(event)">
</div>
<div ondrop="drop(event)" ondragover="dragEnter(event)"></div>

<script>
	function dragEnter(ev) {
		ev.preventDefault();
	}

	function drag(ev) {
		ev.dataTransfer.setData("text", ev.target.id);
	}

	function drop(ev) {
		ev.preventDefault();
		var data = ev.dataTransfer.getData("text");
		ev.target.appendChild(document.getElementById(data));
	}
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127294660-cf0de5b8-ed99-41fd-83fe-e7294eb6b19c.png)

모나리자 그림을 드래그해서 오른쪽으로 드롭하면 그림이 오른쪽으로 옮겨진다.

![image](https://user-images.githubusercontent.com/43658658/127294748-4e727fa4-dbac-41ea-b9a8-f60551b3eb02.png)

