# Part 2. 타입

+ [기본 타입](#기본-타입)
+ [타입 변환](#타입-변환)
+ [변수](#변수)

## 기본 타입

타입(data type)이란 프로그램에서 다룰 수 있는 값의 종류를 의미합니다.

자바스크립트에서는 여러 가지 형태의 타입을 미리 정의하여 제공하고 있으며, 이것을 기본 타입이라고 합니다.

자바스크립트의 기본 타입은 크게 원시 타입과 객체 타입으로 구분할 수 있습니다.

 

원시 타입(primitive type)은 다음과 같습니다.

 

1. 숫자(number)

2. 문자열(string)

3. 불리언(boolean)

4. 심볼(symbol) : ECMAScript 6부터 제공됨

5. undefined

6. 객체(object)

> <h3>숫자(number)</h3>

자바스크립트는 다른 언어와는 달리 정수와 실수를 따로 구분하지 않고, `모든 수를 실수 하나로만 표현`합니다.

또한, 매우 큰 수나 매우 작은 수를 표현할 경우에는 `e 표기법`을 사용할 수 있습니다.

``` html
var firstNum = 10;     // 소수점을 사용하지 않은 표현
var secondNum = 10.00; // 소수점을 사용한 표현
var thirdNum = 10e6;   // 10000000
var fourthNum = 10e-6; // 0.00001
```

> <h3>문자열(string)</h3>

자바스크립트에서 문자열은 큰따옴표("")나 작은따옴표('')로 둘러싸인 문자의 집합을 의미합니다.

큰따옴표는 작은따옴표로 둘러싸인 문자열에만 포함될 수 있으며, 작은따옴표는 큰따옴표로 둘러싸인 문자열에만 포함될 수 있습니다.

``` html
var firstStr = "이것도 문자열입니다.";      // 큰따옴표를 사용한 문자열
var secondStr = '이것도 문자열입니다.';     // 작은따옴표를 사용한 문자열
var thirdStr = "나의 이름은 '홍길동'이야."  // 작은따옴표는 큰따옴표로 둘러싸인 문자열에만 포함될 수 있음.
var fourthStr = '나의 이름은 "홍길동"이야.' // 큰따옴표는 작은따옴표로 둘러싸인 문자열에만 포함될 수 있음.
```

자바스크립트에서는 숫자와 문자열을 더할 수도 있습니다.

이럴 경우에 자바스크립트는 숫자를 문자열로 자동 변환하여, 두 문자열을 연결하는 연산을 수행합니다.

``` html
var num = 10;
var str = "JavaScript";
document.getElementById("result").innerHTML = (num + str); // 10JavaScript
```

> <h3>불리언(boolean)</h3>

불리언 값은 참(true)과 거짓(false)을 표현합니다.

자바스크립트에서 불리언 값은 예약어인 true와 false를 사용하여 나타낼 수 있습니다.

``` html
<p id="result"></p>
<script>
  var firstNum = 10;
  var secondNum = 11;
  document.getElementById("result").innerHTML = (firstNum == secondNum);
</script>
```

결괏값 : false

> <h3>심볼(symbol)</h3>

심볼 타입은 ECMAScript 6부터 새롭게 추가된 타입입니다.

심볼은 유일하고 변경할 수 없는 타입으로, 객체의 프로퍼티를 위한 식별자로 사용할 수 있습니다.

``` html
<p id="result"></p>
  
<script>
  var sym = Symbol("javascript");
  var symObj = Object(sym);

  document.getElementById("result").innerHTML =
    (typeof sym) + "<br>" + (typeof symObj);
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128815054-2a31c997-4bd0-4bc4-bd33-ca3be333933d.png)

> <h3>typeof 연산자</h3>

typeof 연산자는 피연산자의 타입을 반환하는 피연산자가 단 하나뿐인 연산자입니다.

``` html
<p id="result"></p>

<script>
  document.getElementById("result").innerHTML = (typeof 10) + "<br>";
    document.getElementById("result").innerHTML += (typeof "string") + "<br>";
    document.getElementById("result").innerHTML += (typeof true) + "<br>";
    document.getElementById("result").innerHTML += (typeof undefined) + "<br>";
    document.getElementById("result").innerHTML += (typeof null) + "<br>";
</script>
```

![image](https://user-images.githubusercontent.com/43658658/128815590-aa76ae29-efeb-4d23-a9d4-ed50c9b9e0b7.png)

> <h3>null과 undefined</h3>

자바스크립트에서 null이란 `object` 타입이며, 아직 '값'이 있지만, `'값'이 정해지지 않은 것`을 의미합니다.

또한, `undefined`란 null과는 달리 `'타입'이 정해지지 않은 것`을 의미합니다.

따라서 자바스크립트에서 undefined는 `초기화되지 않은 변수`나 `존재하지 않는 값`에 접근할 때 반환됩니다.

``` html
<p id="result"></p>

<script>
  var num;		// 초기화하지 않았으므로 undefined 값을 반환함.
  var str = null;	// object 타입의 null 값

  // 정의되지 않은 변수에 접근하면 undefined 값을 반환함.
  document.getElementById("result").innerHTML = 
    (typeof num) + "<br>" + (typeof str) + "<br>" + (typeof secondNum);
</script>
```

null과 undefined는 동등 연산자(`==`)와 일치 연산자(`===`)로 비교할 때 그 결괏값이 다르므로 주의해야 합니다.

null과 undefined는 타입을 제외하면 같은 의미지만, 타입이 다르므로 일치하지는 않습니다.

``` html
null ==  undefined; // true
null === undefined; // false
```

> <h3>객체(object)</h3>

자바스크립트의 기본 타입은 객체(object)입니다.

객체(object)란 실생활에서 우리가 인식할 수 있는 사물로 이해할 수 있습니다.

객체는 여러 프로퍼티(property)나 메소드(method)를 같은 이름으로 묶어놓은 일종의 집합체입니다.

``` html
<p id="result"></p>

<script>
  var dog = { name: "해피", age: 3 };	// 객체의 생성

  // 객체의 프로퍼티 참조
  document.getElementById("result").innerHTML = 
    "강아지의 이름은 " + dog.name + "이고, 나이는 " + dog.age + "살 입니다.";
</script>
```

## 타입 변환

자바스크립트는 타입 검사가 매우 유연한 언어입니다.

자바스크립트의 변수는 타입이 정해져 있지 않으며, 같은 변수에 다른 타입의 값을 다시 대입할 수도 있습니다.

``` html
<p id="result"></p>
	
<script>
  var num = 20;	// 변수의 선언과 함께 초기화
  document.getElementById("result").innerHTML = num + "<br>";
  num = "이십";	// 문자열 대입
  document.getElementById("result").innerHTML += num + "<br>";
  var num;		// 한 변수를 여러 번 초기화할 수는 있으나, 재선언은 할 수 없습니다.
  document.getElementById("result").innerHTML += num;
</script>
```

> <h3>묵시적 타입 변환(implicit type conversion)</h3>

자바스크립트는 특정 타입의 값을 기대하는 곳에 다른 타입의 값이 오면, 자동으로 타입을 변환하여 사용합니다.

즉, 문자열 값이 오길 기대하는 곳에 숫자가 오더라도 자바스크립트는 알아서 숫자를 문자열로 변환하여 사용합니다.

``` html
10 + "문자열"; // 문자열 연결을 위해 숫자 10이 문자열로 변환됨.

"3" * "5";     // 곱셈 연산을 위해 두 문자열이 모두 숫자로 변환됨.

1 - "문자열";  // NaN
```

위의 세 번째 예제에서 뺄셈 연산을 위해 문자열이 숫자로 변환되어야 하나, 해당 문자열은 두 번째 예제의 문자열과는 달리 숫자로 변환될 수 없는 문자열입니다.

따라서 의미에 맞게 자동으로 타입을 변환할 수 없으므로, 자바스크립트는 `NaN` 값을 반환합니다.

NaN은 Not a Number의 축약형으로, 정의되지 않은 값이나 표현할 수 없는 값이라는 의미를 가집니다.

이러한 NaN은 Number 타입의 값으로 0을 0으로 나누거나, 숫자로 변환할 수 없는 피연산자로 산술 연산을 시도하는 경우에 반환되는 읽기 전용 값입니다.

> <h3>명시적 타입 변환(explicit type conversion)</h3>

자바스크립트에서는 묵시적 타입 변환을 많이 사용하지만, 명시적으로 타입을 변환할 방법도 제공합니다.

명시적 타입 변환을 위해 자바스크립트가 제공하는 전역 함수는 다음과 같습니다.

1. Number()

2. String()

3. Boolean()

4. Object()

5. parseInt()

6. parseFloat()

``` html
document.getElementById("result").innerHTML = Number("10") + "<br>";	// 10
document.getElementById("result").innerHTML += String(true) + "<br>";	// "true"
document.getElementById("result").innerHTML += Boolean(0) + "<br>";		// false
document.getElementById("result").innerHTML += Object(3);				// new Number(3)
```

> <h3>숫자를 문자열로 변환</h3>

숫자를 문자열로 변환하는 가장 간단한 방법은 String() 함수를 사용하는 것입니다.

또한, null과 undefined를 제외한 모든 타입의 값이 가지고 있는 toString() 메소드를 사용할 수도 있습니다.

숫자(Number) 객체는 숫자를 문자열로 변환하는 다음과 같은 메소드를 별도로 제공합니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>메소드</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>toExponential()</td>
			<td>정수 부분은 1자리, 소수 부분은 입력받은 수만큼&nbsp;e 표기법을 사용하여 숫자를 문자열로 변환함.</td>
		</tr>
		<tr>
			<td>toFixed()</td>
			<td>소수 부분을 입력받은 수만큼 사용하여 숫자를 문자열로 변환함.</td>
		</tr>
		<tr>
			<td>toPrecision()</td>
			<td>입력받은 수만큼 유효 자릿수를 사용하여 숫자를 문자열로 변환함.</td>
		</tr>
	</tbody>
</table>

> <h3>불리언 값을 문자열로 변환</h3>

불리언 값을 문자열로 변환하는 방법에는 String() 함수와 toString() 메소드를 사용하는 방법이 있습니다.

``` html
String(true);     // 문자열 "true"
false.toString(); // 문자열 "false"
```

> <h3>날짜를 문자열이나 숫자로 변환</h3>

날짜를 문자열로 변환하는 방법에는 String() 함수와 toString() 메소드를 사용하는 방법이 있습니다.

자바스크립트에서 날짜(Date) 객체는 문자열과 숫자로 모두 변환할 수 있는 유일한 타입입니다.

 

날짜(Date) 객체는 날짜를 숫자로 변환하는 다음과 같은 메소드를 별도로 제공합니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>메소드</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>getDate()</td>
			<td>날짜 중 일자를 숫자로 반환함. (1 ~ 31)</td>
		</tr>
		<tr>
			<td>getDay()</td>
			<td>날짜 중 요일을 숫자로 반환함. (일요일 : 0 ~ 토요일 : 6)</td>
		</tr>
		<tr>
			<td>getFullYear()</td>
			<td>날짜 중 연도를 4자리 숫자로 반환함. (yyyy년)</td>
		</tr>
		<tr>
			<td>getMonth()</td>
			<td>날짜 중 월을 숫자로 반환함. (1월 : 0 ~ 12월 : 11)</td>
		</tr>
		<tr>
			<td>getTime()</td>
			<td>1970년 1월 1일부터 현재까지의 시간을 밀리초(millisecond) 단위의 숫자로 반환함.</td>
		</tr>
		<tr>
			<td>getHours()</td>
			<td>시간 중 시를 숫자로 반환함. (0 ~ 23)</td>
		</tr>
		<tr>
			<td>getMinutes()</td>
			<td>시간 중 분을 숫자로 반환함. (0 ~ 59)</td>
		</tr>
		<tr>
			<td>getSeconds()</td>
			<td>시간 중 초를 숫자로 반환함. (0 ~ 59)</td>
		</tr>
		<tr>
			<td>getMilliseconds()</td>
			<td>시간 중 초를 밀리초(millisecond) 단위의&nbsp;숫자로 반환함. (0 ~ 999)</td>
		</tr>
	</tbody>
</table>

``` html
var result = String(Date());
document.getElementById("result").innerHTML = result + "<br>";
result = Date().toString();
document.getElementById("result").innerHTML += result + "<br>";
result = new Date().getFullYear();
document.getElementById("result").innerHTML += result + "<br>";
result = new Date().getTime();
document.getElementById("result").innerHTML += result + "<br>";
```

![image](https://user-images.githubusercontent.com/43658658/128819270-3a12cf9f-92ad-420c-9cb4-21e3a371219c.png)

> <h3>문자열을 숫자로 변환</h3>

문자열을 숫자로 변환하는 가장 간단한 방법은 Number() 함수를 사용하는 것입니다.

자바스크립트는 문자열을 숫자로 변환해 주는 두 개의 전역 `함수`를 별도로 제공합니다.

 

1. parseInt()

2. parseFloat()

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>함수</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>parseInt()</td>
			<td>문자열을 파싱하여 특정 진법의 정수를 반환함.</td>
		</tr>
		<tr>
			<td>parseFloat()</td>
			<td>문자열을 파싱하여 부동 소수점 수를 반환함.</td>
		</tr>
	</tbody>
</table>

> <h3>불리언 값을 숫자로 변환</h3>

불리언 값을 숫자로 변환하는 방법에는 Number() 함수를 사용하는 방법이 있습니다.

``` html
Number(true);  // 숫자 1
Number(false); // 숫자 0
```

## 변수

> <h3>변수의 선언과 초기화</h3>

변수(variable)란 데이터(data)를 저장할 수 있는 메모리 공간을 의미하며, 그 값이 변경될 수 있습니다.

자바스크립트에서는 var 키워드를 사용하여 변수를 선언합니다.

 

자바스크립트에서는 선언되지 않은 변수를 사용하려고 하거나 접근하려고 하면 오류가 발생합니다.

단, 선언되지 않은 변수를 초기화할 경우에는 자동으로 선언을 먼저 한 후 초기화를 진행합니다.

``` html
var month; // month라는 이름의 변수 선언
date = 25; // date라는 이름의 변수를 묵시적으로 선언
```

선언된 변수는 나중에 초기화할 수도 있고, 선언과 동시에 초기화할 수도 있습니다.

``` html
var month;     // 변수의 선언
var date = 25; // 변수의 선언과 동시에 초기화
month = 12;    // 변수의 초기화
```

쉼표(,) 연산자를 이용하여 여러 변수를 동시에 선언하거나 초기화할 수도 있습니다.

``` html
var month, date;             // 여러 변수를 한 번에 선언
var hours = 7, minutes = 15; // 여러 변수를 선언과 동시에 초기화
month = 10, date = 5;        // 여러 변수를 한 번에 초기화
```

> <h3>변수의 타입과 초깃값</h3>

자바스크립트의 변수는 타입이 정해져 있지 않으며, 같은 변수에 다른 타입의 값을 다시 대입할 수도 있습니다.

이렇게 한 변수에 다른 타입의 값을 여러 번 대입할 수는 있지만, 한 번 선언된 변수를 재선언할 수는 없습니다.

``` html
var num = 10;		// 변수의 선언과 함께 초기화
document.getElementById("result").innerHTML = num + "<br>";
num = [10, 20, 30];	// 배열 할당
document.getElementById("result").innerHTML += num + "<br>";
var num; 			// 이 재선언문은 무시됨.
document.getElementById("result").innerHTML += num;
```

자바스크립트에서 선언만 되고 초기화하지 않은 변수는 undefined 값을 갖습니다.

``` html
var num;  // undefined
num = 10; // 10
```

