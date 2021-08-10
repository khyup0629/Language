# Part 4. 제어문

+ [조건문](#조건문)

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

