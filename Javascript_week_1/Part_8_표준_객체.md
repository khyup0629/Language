# Part 8. 표준 객체

+ [전역 객체와 래퍼 객체](#전역-객체와-래퍼-객체)
+ [Number 객체](#Number-객체)
+ 

## 전역 객체와 래퍼 객체

> <h3>전역 객체(global object)</h3>

전역 객체란 자바스크립트에 미리 정의된 객체로 전역 프로퍼티나 전역 함수를 담는 공간의 역할을 합니다.

전역 객체 그 자체는 전역 범위(global scope)에서 this 연산자를 통해 접근할 수 있습니다.

 

자바스크립트에서 모든 객체는 전역 객체의 프로퍼티가 됩니다.

웹 브라우저가 새로운 페이지를 로드(load)하면, 자바스크립트는 새로운 전역 개체를 만들고 해당 프로퍼티들을 초기화합니다.

> <h3>래퍼 객체(wrapper object)</h3>

``` html
var str = "문자열";   // 문자열 생성
var len = str.length; // 문자열 프로퍼티인 length 사용
```
 
위의 예제에서 생성한 문자열 리터럴 str은 객체가 아닌데도 length 프로퍼티를 사용할 수 있습니다.

프로그램이 문자열 리터럴 str의 프로퍼티를 참조하려고 하면, 자바스크립트는 new String(str)을 호출한 것처럼 문자열 리터럴을 객체로 자동 변환해주기 때문입니다.


이렇게 생성된 임시 객체는 String 객체의 메소드를 상속받아 프로퍼티를 참조하는 데 사용됩니다.

이후 프로퍼티의 참조가 끝나면 사용된 임시 객체는 자동으로 삭제됩니다.

이렇게 숫자, 문자열, 불리언 등 원시 타입의 프로퍼티에 접근하려고 할 때 생성되는 임시 객체를 래퍼 객체(wrapper object)라고 합니다.

``` html
var str = "문자열";							// 문자열 리터럴 생성
var strObj = new String(str);				// 문자열 객체 생성

// 리터럴 값은 내부적으로 래퍼 객체를 생성한 후에 length 프로퍼티를 참조함.
document.write(str.length + "<br>");

document.write((str == strObj) + "<br>");	// 동등 연산자는 리터럴 값과 해당 래퍼 객체를 동일하게 봄.
document.write((str === strObj) + "<br>");	// 일치 연산자는 리터럴 값과 해당 래퍼 객체를 구별함.

document.write(typeof str + "<br>");		// string 타입
document.write(typeof strObj + "<br>");		// object 타입
```

![image](https://user-images.githubusercontent.com/43658658/129476051-f2e0595a-03c8-414f-b9dd-b584f9c75d0f.png)

> <h3>표준 객체(Standard Object)</h3>

자바스크립트에서 표준 객체(standard object)는 다른 객체의 기초가 되는 핵심적인 객체입니다.

자주 사용되는 대표적인 자바스크립트 표준 객체는 다음과 같습니다.

 

1. Number 객체

2. Math 객체

3. Date 객체

4. String 객체

5. Array 객체

## Number 객체

> <h3>자바스크립트에서의 수 표현</h3>

자바스크립트에서는 정수와 실수를 따로 구분하지 않고, `모든 수를 실수 하나로만 표현`합니다.

자바스크립트에서 모든 숫자는 IEEE 754 국제 표준에서 정의한 64비트 부동 소수점 수로 저장됩니다.

64비트 부동 소수점 수(double precision floating point numbers)는 메모리에 다음과 같은 형태로 저장됩니다.


 

이러한 64비트 부동 소수점 수의 정밀도는 정수부는 15자리까지, 소수부는 17자리까지만 유효합니다.

 

다음 예제는 64비트 부동 소수점 수의 정밀도를 알아보는 예제입니다.

``` html
var x = 999999999999999;	// 15자리의 정수부
var y = 9999999999999999;	// 16자리의 정수부
var z = 0.1 + 0.2

document.write(x + "<br>");		// 999999999999999
document.write(y + "<br>");		// 10000000000000000
document.write(z);				// 0.30000000000000004
```

위의 예제에서 변수 z의 값을 살펴보면 `오차`가 발생했음을 알 수 있습니다.

이렇게 부동 소수점 수를 가지고 수행하는 산술 연산의 결괏값은 언제나 오차가 발생할 가능성을 가지고 있습니다.

이것은 자바스크립트만의 문제가 아닌 부동 소수점 수를 가지고 실수를 표현하는 모든 프로그래밍 언어에서의 문제점입니다.

 

자바스크립트에서는 이러한 오차를 없애기 위해 정수의 형태로 먼저 변환하여 계산을 수행하고, 다시 실수의 형태로 재변환하는 방법을 사용할 수도 있습니다.

``` html
var z = (0.2 * 10 + 0.1 * 10) / 10; // 0.3
```

> <h3>진법 표현</h3>

자바스크립트에서는 기본적으로 `10진법`을 사용하여 수를 표현합니다.

하지만 0x 접두사를 사용하여 `16진법`으로 수를 표현할 수도 있습니다.

``` html
var x = 0xAB;			// 16진법으로 표현된 10진수 171
var y = 29;				// 10진법으로 표현된 10진수 29
document.write(x + "<br>"); // 출력은 10진수로 출력
document.write(x + y);	// 두 수 모두 10진법으로 자동으로 변환되어 계산됨. -> 200
```

또한, 숫자에 toString() 메소드를 사용하여 해당 숫자를 여러 진법의 형태로 변환할 수 있습니다.

``` html
var num = 256;
num.toString(2);       //  2진법으로 변환 : 100000000
num.toString(8);       //  8진법으로 변환 : 400
num.toString(10);      // 10진법으로 변환 : 256
num.toString(16);      // 16진법으로 변환 : 100
// 2진수로 변환한 결괏값을 문자열로 반환함.
num.toString(2);       // 100000000
// 문자열을 숫자로 나눴기 때문에 자동으로 10진수로 변환되어 산술 연산된 결괏값
(num.toString(2) / 2); // 50000000
```
 
toString() 메소드는 해당 숫자의 진법을 실제로 바꿔주는 것이 아닌, 전달된 진법으로 변환된 형태의 문자열을 반환해 주는 것입니다.

> <h3>Infinity</h3>

자바스크립트에서는 양의 무한대를 의미하는 Infinity 값과 음의 무한대를 의미하는 -Infinity 값을 사용할 수 있습니다.

Infinity 값은 사용자가 임의로 수정할 수 없는 읽기 전용 값이며, 자바스크립트의 어떤 수보다도 큰 수로 취급됩니다.

``` html
var x = 10 / 0;         // 숫자를 0으로 나누면 Infinity를 반환함.
var y = Infinity * 1000 // Infinity에 어떠한 수를 산술 연산해도 Infinity를 반환함.
var z = 1 / Infinity    // Infinity의 역수는 0을 반환함.
x;                      // Infinity
y;                      // Infinity
z;                      // 0
```

> <h3>NaN</h3>

NaN(Not A Number)는 숫자가 아니라는 의미로, 정의되지 않은 값이나 표현할 수 없는 값을 가리킵니다.

0을 0으로 나누거나, 숫자로 변환할 수 없는 피연산자로 산술 연산을 시도하는 경우에 반환되는 읽기 전용 값입니다.

``` html
var x = 100 - "10";			// "10"은 자동으로 숫자로 변환되어 계산됨.
var y = 100 - "문자열";		// "문자열"은 숫자로 변환할 수 없기 때문에 NaN을 반환함.
var z = 0 / 0;				// 0을 0으로 나눌 수 없기 때문에 NaN을 반환함.

document.write(x + "<br>");	// 90
document.write(y + "<br>");	// NaN
document.write(z);			// NaN
```

자바스크립트의 전역 함수 중 하나인 isNaN() 함수를 사용하면, 전달받은 값이 숫자인지 아닌지를 판단해 줍니다.

``` html
var x = 100 * "문자열";
if(isNaN(x)) { // 전달된 값이 숫자인지 아닌지를 검사함.
    document.write("변수 x의 값은 숫자가 아닙니다.");
} else {
    document.write("변수 x의 값은 숫자입니다.");
}
```

> <h3>null, undefined, NaN, Infinity에 대한 비교</h3>

자바스크립트에서는 약간은 비슷한 것 같으면서도 전혀 다른 4가지 값을 제공하고 있습니다.

- null은 object 타입이며, 아직 `값`이 정해지지 않은 것을 의미하는 값입니다.

- undefined는 null과는 달리 하나의 타입이며, `타입`이 정해지지 않은 것을 의미하는 값이기도 합니다.

- NaN은 number 타입이며, `숫자가 아님`을 의미하는 숫자입니다.

- Infinity는 number 타입이며, `무한대`를 의미하는 숫자입니다.

 

자바스크립트는 타입 검사가 매우 유연한 언어입니다.

따라서 위의 값들 또한 문맥에 따라 다음과 같이 자동으로 타입 변환이 이루어집니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">값</th>
			<th style="width: 25%;">Boolean 문맥</th>
			<th style="width: 25%;">Number 문맥</th>
			<th style="width: 25%;">String 문맥</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>null</td>
			<td>false</td>
			<td>0</td>
			<td>&quot;null&quot;</td>
		</tr>
		<tr>
			<td>undefined</td>
			<td>false</td>
			<td>NaN</td>
			<td>&quot;undefined&quot;</td>
		</tr>
		<tr>
			<td>NaN</td>
			<td>false</td>
			<td>NaN</td>
			<td>&quot;NaN&quot;</td>
		</tr>
		<tr>
			<td>Infinity</td>
			<td>true</td>
			<td>Infinity</td>
			<td>&quot;Infinity&quot;</td>
		</tr>
	</tbody>
</table>

> <h3>Number 객체</h3>

자바스크립트에서 숫자는 보통 숫자 리터럴을 사용하여 표현합니다.
 
하지만 수를 나타낼 때 new 연산자를 사용하여 명시적으로 Number 객체를 생성할 수도 있습니다.

이러한 Number 객체는 숫자 값을 감싸고 있는 래퍼(wrapper) 객체입니다.

``` html
var x = 100;             // 숫자 리터럴
var y = new Number(100); // Number 객체
x;                       // 100
y;                       // 100
typeof x;                // number 타입
typeof y;                // object 타입
x == y;                  // 값이 같으므로 true
x === y;                 // 서로 다른 객체이므로 false
```

new 연산자를 사용하여 객체를 생성할 때에는 매우 많은 추가 연산을 해야만 합니다.

따라서 가능한 숫자 리터럴을 사용하여 수를 표현하고, Number 객체는 래퍼 객체로만 활용하는 것이 좋습니다.

## Number 메소드

Number 메소드는 Number 객체에 정의되어 있는 숫자와 관련된 작업을 할 때 사용하는 메소드입니다.

가장 많이 사용되는 대표적인 Number 메소드는 다음과 같습니다.

 

1. Number.parseFloat()

2. Number.parseInt()

3. Number.isNaN()

4. Number.isFinite()

5. Number.isInteger()

6. Number.isSafeInteger()

> <h3>Number.parseFloat() 메소드</h3>

Number.parseFloat() 메소드는 문자열을 파싱(parsing)하여, 문자열에 포함된 숫자 부분을 실수 형태로 반환합니다.문자열에 여러 개의 숫자가 존재하면, 그중에서 첫 번째 숫자만을 실수 형태로 반환합니다.

이 메소드는 전역 함수인 parseFloat() 함수와 완전히 같은 동작을 수행합니다.

``` html
Number.parseFloat("12");         // 12
Number.parseFloat("12.34");      // 12.34
Number.parseFloat("12문자열");   // 12
Number.parseFloat("12 34 56");   // 12
Number.parseFloat("문자열 56")); // NaN
```

> <h3>Number.parseInt() 메소드</h3>

Number.parseInt() 메소드는 문자열을 파싱하여, 문자열에 포함된 숫자 부분을 정수 형태로 반환합니다.

문자열에 여러 개의 숫자가 존재하면, 그중에서 첫 번째 숫자만을 정수 형태로 반환합니다.

 

이 메소드는 전역 함수인 parseInt() 함수와 완전히 같은 동작을 수행합니다.

``` html
Number.parseInt("12");         // 12
Number.parseInt("12.34");      // 12
Number.parseInt("12문자열");   // 12
Number.parseInt("12 34 56");   // 12
Number.parseInt("문자열 56")); // NaN
```

> <h3>Number.isNaN() 메소드</h3>

Number.isNaN() 메소드는 전달된 값이 NaN인지 아닌지를 검사합니다.

이 메소드는 전역 함수인 isNaN() 함수가 가지고 있던 `숫자로의 강제 변환에 따라 발생하는 문제를 더는 겪지 않게 해줍니다.`

이 메소드는 `오직 숫자인 값에서만 동작`하며, `그 값이 NaN인 경우에만 true를 반환`합니다.

``` html
document.write(Number.isNaN(NaN) + "<br>");			// true
document.write(Number.isNaN(0 / 0) + "<br><br>");	// true

// 다음은 전역 함수인 isNaN()에서 잘못된 결과를 반환하는 예제임.
document.write(isNaN("NaN") + "<br>");				// true
document.write(isNaN(undefined) + "<br>");			// true
document.write(isNaN("문자열") + "<br><br>");		// true

// Number.isNaN() 메소드에서는 맞는 결과를 반환하고 있음.
document.write(Number.isNaN("NaN") + "<br>");		// false
document.write(Number.isNaN(undefined) + "<br>");	// false
document.write(Number.isNaN("문자열"));				// false
```

> <h3>Number.isFinite() 메소드</h3>

Number.isFinite() 메소드는 전달된 값이 유한한 수인지 아닌지를 검사합니다.

이 메소드는 전역 함수인 isFinite() 함수처럼 전달된 값을 숫자로 강제 변환하지 않습니다.

이 메소드는 오직 셀 수 있는 값(숫자)에서만 동작하며, 그 값이 유한한 경우에만 true를 반환합니다.

``` html
document.write(Number.isFinite(0) + "<br>");		// true
document.write(Number.isFinite(3e45) + "<br><br>");	// true

document.write(Number.isFinite(Infinity) + "<br>");	// false
document.write(Number.isFinite(NaN) + "<br><br>");	// false

// 다음은 전역 함수인 isFinite()에서 잘못된 결과를 반환하는 예제임.
document.write(isFinite("0") + "<br>");				// true
document.write(isFinite(null) + "<br><br>");		// true

// Number.isFinite() 메소드에서는 맞는 결과를 반환하고 있음.
document.write(Number.isFinite("0") + "<br>");		// false
document.write(Number.isFinite(null));				// false
```

> <h3>Number.isInteger() 메소드</h3>

Number.isInteger() 메소드는 전달된 값이 정수인지 아닌지를 검사합니다.

전달된 값이 정수이면 true를 반환하며, 정수가 아니거나 NaN, Infinity와 같은 값은 모두 false를 반환합니다.

``` html
Number.isInteger(0);        // true
Number.isInteger(-100);     // true
Number.isInteger(0.1);      // false
Number.isInteger("문자열"); // false
Number.isInteger(Infinity); // false
Number.isInteger(true);     // false
```

> <h3>Number.isSafeInteger() 메소드</h3>

Number.isSafeInteger() 메소드는 전달된 값이 `안전한 정수(safe integer)인지 아닌지를 검사`합니다.

`안전한 정수(safe integer)`란 IEEE 754 국제 표준에서 정의한 64비트 부동 소수점 수로 정확히 표현되는 정수를 의미합니다.

`-(2^53 - 1)부터 (2^53 - 1)까지`의 모든 정수가 안전한 정수에 포함됩니다.

``` html
document.write(Number.isSafeInteger(10) + "<br>");						// true
document.write(Number.isSafeInteger(Math.pow(2, 53) - 1) + "<br><br>");	// true

document.write(Number.isSafeInteger(Math.pow(2, 53)) + "<br>");			// false
document.write(Number.isSafeInteger(Infinity) + "<br>");				// false
document.write(Number.isSafeInteger(NaN) + "<br>");						// false
document.write(Number.isSafeInteger(3.14));								// false
```

> <h3>Number.prototype 메소드</h3>

모든 Number 인스턴스는 Number.prototype으로부터 메소드와 프로퍼티를 상속받습니다.

가장 많이 사용되는 대표적인 Number.prototype 메소드는 다음과 같습니다.

 

1. Number.prototype.toExponential()

2. Number.prototype.toFixed()

3. Number.prototype.toPrecision()

4. Number.prototype.toString()

5. Number.prototype.valueOf()

> <h3>toExponential() 메소드</h3>

이 메소드는 Number 인스턴스의 값을 지수 표기법으로 변환한 후, 그 값을 문자열로 반환합니다.

이때 전달받은 값은 지수 표기법에서 소수 부분의 자릿수로 사용됩니다.

``` html
numObj.toExponential([소수부분의자릿수])
```
 
``` html
var num = 12.3456;       // Number 인스턴스를 생성함.
num.toExponential();     // 1.23456e+1
num.toExponential(2);    // 1.23e+1
num.toExponential(4);    // 1.2346e+1
12.3456.toExponential(); // 1.23456e+1
```

> <h3>toFixed() 메소드</h3>

이 메소드는 Number 인스턴스의 소수 부분 자릿수를 전달받은 값으로 고정한 후(반올림), 그 값을 문자열로 반환합니다.

``` html
numObj.toFixed([소수부분의자릿수])
```
 

``` html
var num = 3.14159265;  // Number 인스턴스를 생성함.
num.toFixed();         // 3
num.toFixed(2);        // 3.14
num.toFixed(4);        // 3.1416
3.14159265.toFixed(6); // 3.141593
```

> <h3>toPrecision() 메소드</h3>

이 메소드는 Number 인스턴스의 가수와 소수 부분을 합친 자릿수를 전달받은 값으로 고정한 후(반올림), 그 값을 문자열로 반환합니다.

``` html
numObj.toPrecision([전체자릿수])
``` 

``` html
var num = 3.14159265;      // Number 인스턴스를 생성함.
num.toPrecision();         // 3.14159265
num.toPrecision(2);        // 3.1
num.toPrecision(4);        // 3.142
3.14159265.toPrecision(6); // 3.14159
```

> <h3>toString() 메소드</h3>

이 메소드는 Number 인스턴스의 값을 문자열로 반환합니다.

전달받은 값에 해당하는 진법으로 우선 값을 변환한 후, 그 값을 문자열로 반환합니다.

``` html
numObj.toString([진법])
```
 

``` html
var num = 255;       // Number 인스턴스를 생성함.
num.toString();      // 255
(255).toString();    // 255
(3.14).toString();   // 3.14
num.toString(2);     // 11111111
(100).toString(16);  // 64
(-0xff).toString(2); // -11111111
```

숫자 리터럴에 toString() 메소드를 사용할 때에는 반드시 괄호(())를 사용하여 숫자 리터럴을 감싸줘야 합니다.

그렇지 않으면 자바스크립트는 SyntaxError를 발생한 후, 프로그램을 중지시킬 것입니다.

> <h3>valueOf() 메소드</h3>

이 메소드는 Number 인스턴스가 가지고 있는 값을 반환합니다.

``` html
numObj.valueOf()
```
 

``` html
var numObj = new Number(123); // 123의 값을 가지는 Number 인스턴스를 생성함.
typeof numObj;                // object
var num = numObj.valueOf();
num;                          // 123
typeof num;                   // number
```

