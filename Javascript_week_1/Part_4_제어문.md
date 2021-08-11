# Part 4. 제어문

+ [조건문](#조건문)
+ [반복문](#반복문)
+ [기타 제어문](#기타-제어문)

## 조건문

조건문이란 프로그램 내에서 주어진 표현식의 결과에 따라 별도의 명령을 수행하도록 제어하는 실행문입니다.

조건문 중에서 가장 기본이 되는 실행문은 if 문입니다.

자바스크립트에서 사용할 수 있는 조건문의 형태는 다음과 같습니다.

1. if 문
2. if / else 문
3. if / else if / else 문
4. switch 문

> <h3>if 문</h3>

if 문은 표현식의 결과가 참(true)이면 주어진 실행문을 실행하며, 거짓(false)이면 아무것도 실행하지 않습니다.

if 문의 문법은 다음과 같습니다.

``` html
if (표현식) {
    표현식의 결과가 참일 때 실행하고자 하는 실행문;
}
```

if 문에서 실행될 실행문이 한 줄 뿐이라면 `중괄호({})`를 생략할 수 있습니다.

``` html
<script>
  var x = 10, y = 20;
  if (x == y) {
    document.write("x와 y는 같습니다.");
  }
  if (x < y) {
    document.write("x가 y보다 작습니다.");
  }
  if (x > y) // 실행될 실행문이 한 줄뿐이라면 중괄호({})를 생략할 수 있음.
    document.write("x가 y보다 큽니다.");
</script>
```

> <h3>else 문</h3>

if 문과 같이 사용할 수 있는 else 문은 if 문의 표현식 결과가 거짓(false)일 때 주어진 실행문을 실행합니다.

else 문의 문법은 다음과 같습니다.

``` html
if (표현식) {
    표현식의 결과가 참일 때 실행하고자 하는 실행문;
} else {
    표현식의 결과가 거짓일 때 실행하고자 하는 실행문;
}
```
 
else 문에서도 실행될 실행문이 한 줄뿐이라면 `중괄호({})`를 생략할 수 있습니다.
 
else 문을 사용하면 앞의 예제를 좀 더 직관적으로 표현할 수 있습니다.

``` html
<script>
  var x = 10, y = 20;
  if (x == y) {
    document.write("x와 y는 같습니다.");
  } else {
  if (x < y)
    document.write("x가 y보다 작습니다.");
  else // 실행될 실행문이 한 줄뿐이라면 중괄호({})를 생략할 수 있음.
    document.write("x가 y보다 큽니다.");
  }
</script>
```

> <h3>else if 문</h3>

else if 문은 if 문처럼 표현식을 설정할 수 있으므로, 중첩된 if 문을 좀 더 간결하게 표현할 수 있습니다.

하나의 조건문 안에서 if 문과 else 문은 단 한 번만 사용될 수 있습니다.

하지만 else if 문은 여러 번 사용되어 다양한 조건을 설정할 수 있습니다.

else if 문의 문법은 다음과 같습니다.

``` html
if (표현식1) {
    표현식1의 결과가 참일 때 실행하고자 하는 실행문;
} else if (표현식2) {
    표현식2의 결과가 참일 때 실행하고자 하는 실행문;
} else {
    표현식1의 결과도 거짓이고, 표현식2의 결과도 거짓일 때 실행하고자 하는 실행문;
}
```
  
else if 문에서도 실행될 실행문이 한 줄뿐이라면 `중괄호({})`를 생략할 수 있습니다.
  
else if 문을 사용하면 앞선 예제를 더욱 간결하게 표현할 수 있습니다.

``` html
var x = 10, y = 20;
if (x == y) {
    document.write("x와 y는 같습니다.");
} else if (x < y) {
    document.write("x가 y보다 작습니다.");
} else { // x > y인 경우
    document.write("x가 y보다 큽니다.");
}
```
 
> <h3>삼항 연산자에 의한 조건문</h3>

자바스크립트에서는 간단한 if / else 문을 삼항 연산자를 이용하여 간단히 표현할 수 있습니다.

`표현식 ? 반환값1 : 반환값2`

``` html
<script>
  var x = 30, y = 20;
  document.write((x >= y) ? "x는 y보다 크거나 같습니다.": "x가 y보다 작습니다.");
</script>
```

> <h3>switch 문</h3>

switch 문은 if / else 문과 마찬가지로 주어진 조건 값에 따라 프로그램이 다른 명령을 수행하도록 하는 조건문입니다.

이러한 switch 문은 if / else 문보다 가독성 측면에서 더 좋습니다.

``` html
switch (조건 값) {
    case 값1:
        조건 값이 값1일 때 실행하고자 하는 실행문;
        break;
    case 값2:
        조건 값이 값2일 때 실행하고자 하는 실행문;
        break;
    ...
    default:
        조건 값이 어떠한 case 절에도 해당하지 않을 때 실행하고자 하는 실행문;
        break;
}
```

`default` 절은 조건 값이 위에 나열된 어떠한 case 절에도 해당하지 않을 때 실행됩니다.

이 구문은 반드시 존재해야 하는 것은 아니며, 필요할 때만 선언할 수 있습니다.

 

각 case 절 및 default 절은 반드시 `break` 키워드를 포함하고 있어야 합니다.

break 키워드는 조건 값에 해당하는 case 절이나 default 절이 실행된 뒤에 전체 switch 문을 빠져나가게 해줍니다.

 

default 절의 위치가 반드시 switch 문의 맨 마지막일 필요는 없습니다.

``` html
<script>
		var x = 10;

		switch (typeof x) {
          case "Number": document.write("변수 x의 타입은 숫자입니다.");
            break; 
          case "String": document.write("변수 x의 타입은 문자열입니다.");
            break; 
          case "Object": document.write("변수 x의 타입은 객체입니다.");
            break; 
          default: document.write("변수 x의 타입을 잘 모르겠어요.");
            break; 
                        }
</script>
```

다음 예제는 case 절과 default 절에 break 키워드가 없을 때 어떤 현상이 벌어지는가를 보여주는 예제입니다.

``` html
<script>
		var x = "문자열";

		switch (typeof x) {
		case "number":
			document.write("변수 x의 타입은 숫자입니다.<br>");
		case "string":
			document.write("변수 x의 타입은 문자열입니다.<br>");
		case "object":
			document.write("변수 x의 타입은 객체입니다.<br>");
		default:
			document.write("변수 x의 타입을 잘 모르겠네요...<br>");
		}
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128884790-fae19d30-d874-4aa6-bbfb-7bb3e6e0e01b.png)

다음 예제와 같이 여러 개의 case 절을 사용하여 여러 개의 조건을 한 번에 표현할 수도 있습니다.

``` html
<script>
		var day = new Date().getDay(); // 오늘의 요일을 반환함. (일요일: 0 ~ 토요일: 6)

		switch (day) {
			case 1: // 월요일인 경우
			case 2: // 화요일인 경우
			case 3: // 수요일인 경우
			case 4: // 목요일인 경우
			default: // 0부터 6까지의 값이 아닌 경우
				document.write("아직도 주말은 멀었네요... 힘내자구요!!");
				break; 
			case 5: // 금요일인 경우
				document.write("오늘은 불금이네요!!");
				break; 
			case 6: // 토요일인 경우
			case 0: // 일요일인 경우
				document.write("즐거운 주말에도 열심히 공부하는 당신~ 최고에요!!");
				break;
		}
</script>
```

## 반복문

반복문이란 프로그램 내에서 똑같은 명령을 일정 횟수만큼 반복하여 수행하도록 제어하는 실행문입니다.

프로그램이 처리하는 대부분의 코드는 반복적인 형태가 많으므로, 가장 많이 사용되는 실행문 중 하나입니다.

 

자바스크립트에서 사용할 수 있는 반복문의 형태는 다음과 같습니다.

 

1. while 문

2. do / while 문

3. for 문

4. for / in 문

5. for / of 문

> <h3>while 문</h3>

while 문은 특정 조건을 만족할 때까지 계속해서 주어진 실행문을 반복 실행합니다.

while 문의 문법은 다음과 같습니다.

``` html
while (표현식) {
    표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
}
```

while 문은 우선 표현식이 참(true)인지를 판단하여 참이면 내부의 실행문을 실행합니다.

내부의 실행문을 전부 실행하고 나면, 다시 표현식으로 돌아와 또 한 번 표현식이 참인지를 판단하게 됩니다.

이렇게 표현식의 검사를 통해 반복해서 실행되는 반복문을 루프(loop)라고 합니다.

``` html
<script>
      var i=1;
      
      while (i < 10){
        document.write(i+"<br>");
        i++;
      }
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128984390-551b47eb-bea0-4a3c-8052-5faaec7abe4e.png)

while 문에서 실행될 실행문이 한 줄 뿐이라면 중괄호({})를 생략할 수 있습니다

> <h3>do / while 문</h3>

while 문은 루프에 진입하기 전에 먼저 표현식부터 검사합니다.

하지만 do / while 문은 먼저 루프를 한 번 실행한 후에 표현식을 검사합니다.

즉, do / while 문은 표현식의 결과와 상관없이 무조건 한 번은 루프를 실행합니다.

do / while 문의 문법은 다음과 같습니다.

``` html
do {
    표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
} while (표현식);
```

``` html
var i = 1, j = 1;
		
while (i > 3) { // 변수 i의 초기값은 1이기 때문에 이 while 문은 한 번도 실행되지 않음.
	document.write("i : " + (i++) + "<br>");
}

do { // 변수 j의 초기값은 1이기 때문에 이 do / while 문은 단 한 번만 실행됨.
	document.write("j : " + (j++) + "<br>");
} while (j > 3);
```

![image](https://user-images.githubusercontent.com/43658658/128984852-31240ef9-5be5-4e75-8c3a-1c7ed302ef74.png)

> <h3>for 문</h3>

for 문은 while 문과는 달리 자체적으로 초기식, 표현식, 증감식을 모두 포함하고 있는 반복문입니다.

따라서 while 문보다는 좀 더 간결하게 반복문을 표현할 수 있습니다.

for 문의 문법은 다음과 같습니다.

``` html
for (초기식; 표현식; 증감식) {
    표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
}
```
 

for 문을 구성하는 초기식, 표현식, 증감식은 각각 생략될 수 있습니다.

또한, 쉼표 연산자(,)를 사용하면 여러 개의 초기식이나 증감식을 동시에 사용할 수도 있습니다.

 

for 문을 사용하면 앞선 예제의 while 문을 더욱 더 간결하게 표현할 수 있습니다.

``` html
for (var i = 1; i < 10; i++){
  document.write(i+"<br>");
}
```

> <h3>for / in 문</h3>

for / in 문은 일반적인 for 문과는 전혀 다른 형태의 반복문입니다.

for / in 문은 해당 객체의 모든 열거할 수 있는 프로퍼티(enumerable properties)를 순회할 수 있도록 해줍니다.

열거할 수 있는 프로퍼티란 내부적으로 enumerable 플래그가 true로 설정된 프로퍼티를 의미합니다.

이러한 프로퍼티들은 for / in 문으로 접근할 수 있게 됩니다.
 

이 반복문은 루프마다 객체의 열거할 수 있는 프로퍼티의 이름을 지정된 변수에 대입합니다.

이렇게 대입받은 변수를 이용하면 루프 안에서 객체의 열거할 수 있는 프로퍼티에 순차적으로 접근할 수 있습니다.

for / in 문의 문법은 다음과 같습니다.

``` html
for (변수 in 객체) {
    객체의 모든 열거할 수 있는 프로퍼티의 개수만큼 반복적으로 실행하고자 하는 실행문;
}
```
 

다음 예제는 for / in 문을 사용하여 배열의 요소에 접근하는 예제입니다.

``` html
var arr = [3, 4, 5];

for (var i = 0; i < arr.length; i++) { // 배열 arr의 모든 요소의 인덱스(index)를 출력함.
	document.write(i + " ");
}
document.write("<br>");

for (var i in arr) { // 위와 같은 동작을 하는 for / in 문
	document.write(i + " ");
}
```

``` html
var obj = {
	name : "이순신",
	age : 20
};

for (var i in obj) {
	document.write(i + "<br>");
}
```

> <h3>for / of 문</h3>

for / of 문은 반복할 수 있는 객체(iterable objects)를 순회할 수 있도록 해주는 반복문입니다.

자바스크립트에서 반복할 수 있는 객체에는 Array, Map, Set, arguments 객체 등이 있습니다.

이 반복문은 루프마다 객체의 열거할 수 있는 프로퍼티의 값을 지정된 변수에 대입합니다.

for / of 문의 문법은 다음과 같습니다.

``` html
for (변수 of 객체) {
    객체의 모든 열거할 수 있는 프로퍼티의 개수만큼 반복적으로 실행하고자 하는 실행문;
}
```
 

다음 예제는 for / of 문을 사용하여 배열의 요소에 접근하는 예제입니다.

``` html
var arr = [3, 4, 5];

for (var i = 0; i < arr.length; i++) { // 배열 arr의 모든 요소의 인덱스(index)를 출력함.
	document.write(arr[i] + " ");
}
document.write("<br>");

for (var value of arr) { // 위와 같은 동작을 하는 for / of 문
	document.write(value + " ");
}
```

``` html
var arr = new Set([1, 1, 2, 2, 3, 3]);

for (var value of arr) {
	document.write(value + " ");
}
```

## 기타 제어문

> <h3>루프의 제어</h3>

일반적으로 표현식의 검사를 통해 루프로 진입하면, 다음 표현식을 검사하기 전까지 루프 안에 있는 모든 실행문을 실행합니다.

하지만 continue 문과 break 문은 이러한 일반적인 루프의 흐름을 사용자가 직접 제어할 수 있게 해줍니다.

label 문을 사용하면 continue 문과 break 문의 동작이 프로그램의 흐름을 특정 영역으로 이동시킬 수 있습니다.

> <h3>label 문</h3>

label 문은 프로그램 내의 특정 영역을 식별할 수 있도록 해주는 식별자입니다.

label 문을 사용하면 continue 문과 break 문의 동작이 프로그램의 흐름을 특정 영역으로 이동시킬 수 있습니다.

label 문의 문법은 다음과 같습니다.

``` html
label:
식별하고자 하는 특정 영역
```
 

다음 예제에서 라벨인 arrIndex는 그 이후에 나오는 for 문 전체를 가리키는 식별자로 사용되고 있습니다.

``` html
arrIndex:
for (var i in arr) {
    document.write(i);
}
```

> <h3>continue 문</h3>

continue 문은 루프 내에서 사용하여 해당 루프의 나머지 부분을 건너뛰고, 바로 다음 표현식의 판단으로 넘어가게 합니다.

보통 반복문 내에서 특정 조건에 대한 처리를 제외하고자 할 때 자주 사용됩니다.

자바스크립트에서 continue 문은 다음과 같이 두 가지 형태로 사용할 수 있습니다.

``` html
1. continue;
2. continue 라벨이름;
```

다음 예제는 1부터 100까지의 정수 중에서 3의 배수를 제외하고 출력하는 예제입니다.

``` html
var exceptNum = 3;

for (var i = 0; i <= 100; i++) {
	if (i % exceptNum == 0) // exceptNum의 배수는 출력하지 않음.
		continue;
	document.write(i + " ");
}
```

다음 예제는 라벨을 이용하여 구구단의 값이 홀수인 경우에만 출력하는 예제입니다.

``` html
gugudan: 
for (var i = 2; i <= 9; i++) {
	dan: 
	for (var j = 1; j <= 9; j++) {
		if ((i*j) % 2 == 0)
			continue dan;
		document.write(i + " * " + j + " = " + (i*j) + "<br>");
	}
}
```

![image](https://user-images.githubusercontent.com/43658658/128989508-ed436fdc-e127-4d09-85c9-aa9e73ffd516.png)

`continue gugudan;`으로 바꿀 경우 바깥 for문으로 이동합니다.

``` html
gugudan: 
for (var i = 2; i <= 9; i++) {
	dan: 
	for (var j = 1; j <= 9; j++) {
		if ((i*j) % 2 == 0)
			continue gugudan;
		document.write(i + " * " + j + " = " + (i*j) + "<br>");
	}
}
```

![image](https://user-images.githubusercontent.com/43658658/128989658-0cef11c0-e7df-49e2-9fc3-b7deac5163de.png)

> <h3>break 문</h3>

break 문은 루프 내에서 사용하여 해당 반복문을 완전히 종료시키고, 반복문 바로 다음에 위치한 실행문으로 프로그램의 흐름을 이동시킵니다.

즉, 루프 내에서 표현식의 판단 결과에 상관없이 반복문을 완전히 빠져나가고 싶을 때 사용합니다.

자바스크립트에서 break 문은 다음과 같이 두 가지 형태로 사용할 수 있습니다.

``` html
1. break;
2. break 라벨이름;
```
 
다음 예제는 배열에서 특정값을 가지고 있는 인덱스를 출력하는 예제입니다.

``` html
var lectures = ["html", "css", "자바스크립트", "php"];
var topic = "자바스크립트";

for (var i = 0; i < lectures.length; i++) {
	if (lectures[i] == topic) {
		document.write(topic + " 과목은 " + (i + 1) + "번째 과목입니다.");
		break; // 원하는 값을 찾은 후에는 더 이상 for 문을 반복하지 않고 빠져나감.
	}
}
```

다음 예제는 라벨을 이용하여 구구단을 3단까지만 출력하는 예제입니다.

``` html
gugudan: 
for (var i = 2; i <= 9; i++) {
	dan: 
	for (var j = 1; j <= 9; j++) {
		if (i > 3)
			break gugudan;
		document.write(i + " * " + j + " = " + (i*j) + "<br>");
	}
}
```

바깥 for문을 종료하는 것을 확인할 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/128990073-a2a30e85-faa1-46d7-ae0a-19fdc675d5a4.png)
