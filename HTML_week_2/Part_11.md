# Part 11. HTML5 API

+ [geolocation API](#geolocation-API)
+ [drag and drop API](#drag-and-drop-API)
+ [web storage API](#web-storage-API)
+ [application cache API](#application-cache-API)
+ [web worker API](#web-worker-API)
+ [Server Sent Events API](#Server-Sent-Events-API)

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

## web storage API

웹 스토리지 API는 기존 쿠키(cookie)의 문제점을 극복하기 위해 웹 브라우저가 직접 데이터(data)를 저장할 수 있게 해줍니다.


HTML5 이전에는 응용 프로그램이 데이터를 서버에게 요청할 때마다 매번 쿠키(cookie)라는 곳에 그 정보를 저장합니다.

하지만 웹 스토리지는 사용자 측에서 좀 더 많은 양의 정보를 안전하게 저장할 수 있도록 해줍니다.

웹 스토리지는 최소 5MB 이상의 많은 공간을 가지고 있으며, 이 정보는 절대 서버로 전송되지 않습니다.
 

이러한 웹 스토리지는 오리진(origin)마다 단 하나씩만 존재합니다.

오리진(origin)이란 도메인(domain)과 프로토콜(protocol)의 한 쌍으로 이루어진 식별자입니다.

따라서 하나의 오리진에 속하는 모든 웹 페이지는 같은 데이터(data)를 저장하며 또한 같은 데이터에 접근할 수 있습니다.
 
> <h3>웹 스토리지 지원 여부 확인</h3>

웹 스토리지를 사용하기 전에, 우선 사용자의 웹 브라우저가 이를 지원하는지 안 하는지 확인해야 합니다.

```
if (typeof(Storage) !== "undefined") {
    // web storage를 위한 코드 부분
} else {
    // web storage를 지원하지 않는 브라우저를 위한 안내 부분
}
```

> <h3>웹 스토리지 객체</h3>

웹 스토리지 API는 사용자가 데이터를 저장할 수 있도록 두 가지 객체를 제공합니다.

- sessionStorage 객체 : 하나의 세션(session)만을 위한 데이터를 저장하는 객체
- localStorage 객체 : 보관 기한이 없는 데이터를 저장할 수 있는 객체

> <h3>sessionStorage 객체</h3>

sessionStorage 객체는 하나의 세션(session)만을 위한 데이터를 저장합니다.

따라서 사용자가 브라우저 탭이나 창을 닫으면 이 객체에 저장된 데이터는 사라집니다.

``` html
<h1>sessionStorage 객체를 이용한 데이터의 저장</h1>
<p id="counter"></p>
<button onclick="clickCounter()">카운터 증가!!</button>
<p>브라우저 탭이나 창을 <mark>닫으면</mark> 카운터의 횟수는 초기화될 것입니다.</p>
<p>하지만 <mark>결과보기</mark>를 누르거나 <mark>F5</mark>를 누르면 초기화되지 않을 것입니다.</p>

<script>
var loc = document.getElementById("counter"); // 카운트 출력 메세지

function clickCounter(){
if (typeof(Storage) !== "undefined"){
if (sessionStorage.click){  // sessionStorage.변수
  sessionStorage.click = Number(sessionStorage.click) + 1;
}
else{
  sessionStorage.click = 1;
}
loc.innerHTML = "카운터의 현재 횟수는 " + sessionStorage.click + "입니다!";
}
else{
loc.innerHTML = "이 문장은 사용자의 웹 브라우저가 Web Storage API를 지원하지 않을 때 나타납니다!";
}
}
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127301779-ba39952f-8737-4298-b021-546f29675d92.png)

> <h3>localStorage 객체</h3>
	
localStorage 객체는 보관 기한이 없는 데이터를 저장합니다.
	
따라서 브라우저 탭이나 창이 닫히거나, 컴퓨터를 재부팅 해도 저장된 데이터는 없어지지 않습니다.
	
``` html
<h1>localStorage 객체를 이용한 데이터의 저장</h1>
  
<p id="counter"></p>
<button onclick="clickCounter()">카운터 증가!!</button>
<p>브라우저 탭이나 창을 닫아도 카운터의 횟수는 초기화되지 않을 것입니다.<p>

<script>
	loc = document.getElementById("counter");

	function clickCounter(){
		if ( typeof(Storage) !== "undefined" ) {
			if ( localStorage.click ) {
			  localStorage.click = Number(localStorage.click) + 1;
			}
			else{
			  localStorage.click = 1;
			}
			loc.innerHTML = "카운터의 현재 횟수는 " + localStorage.click + "입니다!";
		}
		else{
		loc.innerHTML = "이 문장은 사용자의 웹 브라우저가 Web Storage API를 지원하지 않을 때 나타납니다!";
		}
	}
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127303529-871bcccb-5bab-41ff-95aa-a448730847eb.png)

## application cache API

application cache API는 웹 응용 프로그램을 캐시(cache) 하여, 인터넷 접속 없이 사용자가 접근할 수 있게 해줍니다.

따라서 application cache를 사용하면 웹 응용 프로그램의 오프라인 버전을 쉽게 만들 수 있습니다.

application cache를 사용해서 생기는 장점은 다음과 같습니다.

- 오프라인 접속 : 사용자가 웹 응용 프로그램을 오프라인(off-line)으로도 사용할 수 있습니다.
- 속도 : 캐시(cache)된 자원은 빠르게 로드(load)할 수 있습니다.
- 서버의 부하 감소 : 웹 브라우저는 서버의 자원에 변동이 있을 때만 자원을 갱신하면 됩니다.

> <h3>cache manifest 파일</h3>

application cache를 사용하기 위해서는 먼저 cache manifest 파일을 작성해야 합니다.

cache manifest 파일은 웹 브라우저에 캐시(cache) 해야 할 파일과 캐시하지 말아야 할 파일을 알려줍니다.

이러한 mainfest 파일은 다음과 같이 세 개의 세션(session)으로 이루어집니다.

- CACHE MANIFEST : 처음 다운로드한 이후에 계속 캐시할 파일들을 기록합니다.
- NETWORK : 서버와의 접속이 필요한 파일들을 기록하며, 이 파일들은 절대로 캐시되지 않습니다.
- FALLBACK : 파일에 접속할 수 없을 때에 대체할 파일들을 기록합니다.

> <h3>캐시(cache)의 갱신</h3>

웹 브라우저는 다음과 같은 경우가 발생하면 캐시(cache)의 정보를 갱신하게 됩니다.

- 사용자가 웹 브라우저의 캐시를 강제로 지웠을 경우
- application cache가 프로그램 때문에 갱신됐을 경우
- cache manifest 파일이 수정됐을 경우

```
<!--cache manifest 파일-->
CACHE MANIFEST
# 2021-07-28 v1.0.1
test.html
test.css
test.js

NETWORK:
test.jpg

FALLBACK:
/ offline.html
```

한 번 캐시 되면 서버상의 파일을 수정해도, 웹 브라우저는 사용자 측에 캐시 되어 있는 버전의 파일만을 보여줍니다.

따라서 서버상의 파일을 수정한 후에는 반드시 웹 브라우저가 캐시를 갱신하도록 만들어야 합니다.

이때 가장 많이 사용되는 방법이 cache manifest 파일 내의 **주석 부분을 수정**하는 것입니다.

일반적으로 **갱신 날짜 및 버전 정보**를 주석으로 표시하고, 이 부분을 수정하여 웹 브라우저가 캐시를 갱신하도록 유도합니다.

## web worker API

웹 페이지에서 스크립트가 실행되면, 해당 웹 페이지는 실행 중인 스크립트가 종료될 때까지 응답 불가 상태가 됩니다.

web worker는 스크립트가 웹 페이지의 성능에 영향을 미치지 않도록 백그라운드에서 동작하게 해주는 자바스크립트입니다.

즉, web worker는 스크립트의 다중 스레드(multi-thread)를 지원합니다.

따라서 사용자가 웹 페이지를 이용하면서도, 동시에 시간이 오래 걸리는 자바스크립트 작업도 병행할 수 있도록 해줍니다.

> <h3>web worker 지원 여부 확인</h3>

web worker를 사용하기 전에, 우선 사용자의 웹 브라우저가 이를 지원하는지 안 하는지 확인해야 합니다.

```
if (typeof(Worker) !== "undefined") {
    // web worker를 위한 코드 부분 
}
else {
    // web worker를 지원하지 않는 브라우저를 위한 안내 부분
}
```

> <h3>web worker 파일 생성</h3>

web worker의 동작을 확인하기 위해 소수를 찾는 외부 자바스크립트 파일을 만듭니다.

> <h3>web worker 파일 생성</h3>

web worker의 동작을 확인하기 위해 소수를 찾는 외부 자바스크립트 파일을 만듭니다.

```
var n = 1;
search: while (true) {
    n += 1;
    for (var i = 2; i <= Math.sqrt(n); i += 1)
        if (n % i == 0)
            continue search;
        postMessage(n);
}
``` 

위의 예제에서 postMessage() 메소드는 HTML 문서에 결과를 전달하기 위해 사용합니다.

> <h3>web worker 객체 생성</h3>

위에서 만든 web worker 파일을 불러올 HTML 파일을 만듭니다.

``` html
if(typeof(webworker) == "undefined") {
    webworker = new Worker("/examples/web_worker.js");
}
``` 

위의 예제는 web worker 파일이 존재하지 않으면, 새로운 web worker 객체를 만들어 줍니다.

> <h3>worker 객체와의 연결</h3>

onmessage 이벤트 리스너(event listener)를 통해 web worker 파일과 메시지를 주고받을 수 있습니다.

```
webworker.onmessage = function(event) {
    document.getElementById("result").innerHTML = event.data;
};
```

위의 예제에서 web worker 파일이 메시지를 보내면 해당 이벤트 리스너(event listener)가 실행됩니다.

이 때 web worker 파일이 보낸 정보는 event.data에 저장됩니다.

> <h3>web worker 객체의 실행 종료</h3>

web worker 객체는 생성되고 나서 종료될 때까지 계속해서 메시지를 받을 준비를 합니다.

따라서 웹 브라우저나 컴퓨터의 자원을 돌려주기 위해서는 terminate() 메소드를 사용하여 web worker를 반드시 종료해줘야 합니다.

```
webworker.terminate();
```

> <h3>web worker 객체의 재사용</h3>

web worker 객체가 종료된 후에는 web worker의 값을 undefined로 설정해야만 web worker 객체를 재사용할 수 있습니다.

```
webworker = undefined;
```

> <h3>web worker 예제</h3>

다음 예제는 앞에서 살펴본 web worker의 동작을 하나의 예제로 보여주는 예제입니다.

``` html
<h1>web worker를 이용한 동시 작업</h1>

<p>현재까지 발견한 소수의 개수는 <output id="result"></output>입니다.</p>
<button onclick="startWorker()">Web Worker 시작</button> 
<button onclick="stopWorker()">Web Worker 종료</button>
<p>위의 스크립트가 실행되는 동안에도 텍스트 필드에 글을 쓰는 작업을 동시에 할 수 있습니다!</p>
<textarea rows="10" cols="50"></textarea>

<script>
	var webworker;

	function startWorker() {
		if(typeof(Worker) !== "undefined") {		// web worker 지원 여부 확인
			if(typeof(webworker) == "undefined") {	// web worker 객체 생성
				webworker = new Worker("/examples/media/web_worker.js");
			}
			webworker.onmessage = function(event) {	// web worker 객체와의 연결
				document.getElementById("result").innerHTML = event.data;
			};
		} else {
			document.getElementById("result").innerHTML = "이 문장은 사용자의 웹 브라우저가 Web Worker API를 지원하지 않을 때 나타납니다!";
		}
	}

	function stopWorker() { 
		webworker.terminate();	// web worker 객체의 실행 종료
		webworker = undefined;	// web worker 객체의 재사용
	}
</script>
```

![image](https://user-images.githubusercontent.com/43658658/127317610-508b6a34-8aee-41ab-94f0-ae2895a3d057.png)

## Server Sent Events API

server sent events API는 웹 페이지가 서버로부터 갱신된 정보를 자동으로 받을 수 있도록 설정합니다.

> <h3>server sent events 지원 여부 확인</h3>

server sent events를 사용하기 전에, 우선 사용자의 웹 브라우저가 이를 지원하는지 안 하는지 확인해야 합니다.

```
if (typeof(EventSource) !== "undefined") {
    // server sent events를 위한 코드 부분
} else {
    // server sent events를 지원하지 않는 브라우저를 위한 안내 부분
}
```

> <h3>server sent events 예제</h3>

다음 예제는 server sent events를 이용해 3초마다 웹 페이지를 갱신하는 예제입니다.

``` html
<h1>server sent events를 이용한 자동 갱신</h1>
  
  <p id="time"></p>
  
  <script>
    var loc = document.getElementById("time");
    var source;
    
    
    if ( typeof(EventSource) !== "undefined" ){
      source = new EventSource("/examples/media/sse.php");
      source.onmessage = function(event){
        loc.innerHTML += event.data + "<br>";
      }
    }
    else{
      loc.innerHTML = "이 문장은 사용자의 웹 브라우저가 Server Sent Events를 지원하지 않을 때 나타납니다!";
    }
    
  </script>
```

`EventSource`를 따로 계속 호출하지 않아도 반복적으로 계속 갱신됩니다.

자동으로 갱신이 되고 갱신이 된 날짜와 시간이 3초마다 출력되는 것을 확인할 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127318004-95375abe-be2e-4372-80ae-80abb27036a9.png)

위의 예제에서 사용한 서버 측 PHP 파일인 sse.php 파일은 다음과 같습니다.

```
<!--sse.php-->
<?php
header('Content-Type: text/event-stream');
header('Cache-Control: no-cache');

$time = date('r');
echo "data: The server time is: {$time}\n\n";
flush();
?>
```
