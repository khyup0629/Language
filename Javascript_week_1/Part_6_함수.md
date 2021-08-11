# Part 6. 함수

+ [함수의 기초](#함수의-기초)
+ [변수의 유효 범위](#변수의-유효-범위)
+ [함수의 유효 범위](#함수의-유효-범위)
+ [매개변수와 인수](#매개변수와-인수)
+ [미리 정의된 전역 함수](#미리-정의된-전역-함수)

## 함수의 기초

> <h3>자바스크립트 함수</h3>

자바스크립트에서는 함수도 하나의 타입(datatype)입니다.

 

따라서 함수를 변수에 대입하거나, 함수에 프로퍼티를 지정하는 것도 가능합니다.

또한, 자바스크립트 함수는 다른 함수 내에 중첩되어 정의될 수도 있습니다.

> <h3>함수의 정의</h3>

자바스크립트에서 함수의 정의는 function 키워드로 시작되며, 다음과 같은 구성요소를 가집니다.

1. 함수의 이름

2. 괄호 안에 쉼표(,)로 구분되는 함수의 매개변수(parameter)

3. 중괄호({})로 둘러싸인 자바스크립트 실행문


자바스크립트에서 함수를 정의하는 문법은 다음과 같습니다.

``` html
function 함수이름(매개변수1, 매개변수2,...) {
    함수가 호출되었을 때 실행하고자 하는 실행문;
}
```
 

함수 이름(function name)은 함수를 구분하는 식별자(identifier)입니다.

매개변수(parameter)란 함수를 호출할 때 인수(argument)로 전달된 값을 함수 내부에서 사용할 수 있게 해주는 변수입니다.


``` html
function addNum(x, y){
  document.write(x + y);
}

addNum(2, 3);
```
 

위의 예제에서 매개변수 x에는 인수 2가 저장되고, y에는 인수 3이 저장되어 사용됩니다.

이렇게 인수와 매개변수는 개수뿐만 아니라 순서 또한 매우 중요하게 적용됩니다.

 

함수의 인수(argument)란 함수가 호출될 때 함수로 값을 전달해주는 변수나 상수를 의미합니다.

> <h3>반환(return)문</h3>

자바스크립트에서 함수는 반환(return)문을 포함할 수 있습니다.

이러한 반환문을 통해 호출자는 함수에서 실행된 결과를 전달받을 수 있습니다.

 

반환문은 함수의 실행을 중단하고, return 키워드 다음에 명시된 표현식의 값을 호출자에게 반환합니다.

반환문은 배열이나 객체를 포함한 모든 타입의 값을 반환할 수 있습니다.

``` html
function multiNum(x, y) {
    return x * y;         // x와 y를 곱한 결과를 반환함.
}
var num = multiNum(3, 4); // multiNum() 함수가 호출된 후, 그 반환값이 변수 num에 저장됨.
document.write(num);
```

> <h3>값으로서의 함수</h3>

자바스크립트에서 함수는 문법적 구문일뿐만 아니라 값(value)이기도 합니다.

따라서 함수가 변수에 대입될 수도 있으며, 다른 함수의 인수로 전달될 수도 있습니다.

다음 예제는 함수를 변수에 저장하여 사용하는 예제입니다.

``` html
function sqr(x) { 					// 제곱의 값을 구하는 함수 sqr를 정의함.
  return x * x;
}
var sqrNum = sqr; 					// 변수 sqrNum에 함수 sqr을 할당함.

document.write(sqr(4) + "<br>");	// 함수 sqr을 호출함.
document.write(sqrNum(4));			// 변수 sqrNum를 함수처럼 호출함.
```

## 변수의 유효 범위

자바스크립트에서 객체나 함수는 모두 변수(variable)입니다.

변수의 유효 범위(scope)란 해당 변수가 접근할 수 있는 변수, 객체 그리고 함수의 집합을 의미합니다.

자바스크립트에서 변수는 유효 범위에 따라 다음과 같이 구분됩니다.

1. 지역 변수(local variable)

2. 전역 변수(global variable)

> <h3>지역 변수(local variable)</h3>

지역 변수(local variable)란 함수 내에서 선언된 변수를 가리킵니다.

이러한 지역 변수는 변수가 선언된 함수 내에서만 유효하며, 함수가 종료되면 메모리에서 사라집니다.

함수의 매개변수 또한 함수 내에서 정의되는 지역 변수처럼 동작합니다.

> <h3>전역 변수(global variable)</h3>

전역 변수(global variable)란 함수의 외부에서 선언된 변수를 가리킵니다.

이러한 전역 변수는 프로그램의 어느 영역에서나 접근할 수 있으며, 웹 페이지가 닫혀야만 메모리에서 사라집니다.

자바스크립트에서 지역 변수를 선언할 때에는 반드시 `var 키워드`를 사용하여 선언해야 합니다.

함수 내부에서 var 키워드를 사용하지 않고 변수를 선언하면, 해당 변수는 지역 변수가 아닌 전역 변수로 선언됩니다.

``` html
function globalNum() {
    num = 10; // var 키워드를 사용하지 않고 변수 num을 선언함.
    document.write("함수 내부에서 변수 num의 값은 " + num + "입니다.<br>"); // 10
}
globalNum();  // 함수 globalNum()을 호출함.
document.write("함수의 호출이 끝난 뒤 변수 num의 값은 " + num + "입니다."); // 10
```

또한, 전역 변수와 같은 이름의 지역 변수를 선언하면, 해당 블록에서는 해당 이름으로 지역 변수만을 호출할 수 있습니다.

``` html
var num = 10; // 전역 변수 num을 선언함.
function globalNum() {
    var num = 20; // 같은 이름의 지역 변수 num을 선언함.
    document.write("함수 내부에서 변수 num의 값은 " + num + "입니다.<br>"); // 20
}
globalNum(); // 함수 globalNum()을 호출함.
document.write("함수의 호출이 끝난 뒤 변수 num의 값은 " + num + "입니다."); // 10
```

위의 예제와 같은 경우 해당 블록에서 전역 변수를 호출하려면, 전역 변수가 window 객체의 프로퍼티임을 명시하면 됩니다.

``` html
var num = 10; // 전역 변수 num을 선언함.
function globalNum() {
    var num = 20; // 같은 이름의 지역 변수 num을 선언함.
    document.write("함수 내부에서 지역 변수 num의 값은 " + num + "입니다.<br>"); // 20
    document.write("함수 내부에서 전역 변수 num의 값은 " + window.num + "입니다.<br>"); // 10
}
globalNum(); // 함수 globalNum()을 호출함.
```

## 함수의 유효 범위

대부분의 프로그래밍 언어에서는 블록 내에서 정의된 변수를 블록 외부에서는 접근할 수 없습니다.

블록(block)이란 코드 내에서 중괄호({})로 둘러싸인 부분을 가리킵니다.

이러한 블록을 기준으로 하는 유효 범위를 블록 단위의 유효 범위라고 합니다.

 

하지만 자바스크립트는 다른 언어와는 달리 함수를 블록 대신 사용합니다.

자바스크립트에서 함수는 자신이 정의된 범위 안에서 정의된 모든 변수 및 함수에 접근할 수 있습니다.

 

'전역 함수'는 모든 전역 변수와 전역 함수에 접근할 수 있습니다.

반면, 다른 함수 내에 정의된 '내부 함수'는 그 함수의 부모 함수(parent function)에서 정의된 모든 변수 및 부모 함수가 접근할 수 있는 모든 다른 변수까지도 접근할 수 있습니다.

``` html
// x, y를 전역 변수로 선언함.
var x = 10, y = 20;

// sub()를 전역 함수로 선언함.
function sub() {
  return x - y;		// 전역 변수인 x, y에 접근함.
}
document.write("전역 함수에서 x - y의 값은 " + sub() + "입니다.<br>");

// parentFunc()을 전역 함수로 선언함.
function parentFunc() {
  var x = 1, y = 2;	// 전역 변수와 같은 이름으로 선언하여 전역 변수의 범위를 제한함.

  function add() {	// add() 함수는 내부 함수로 선언됨.
    return x + y;	// 전역 변수가 아닌 지역 변수 x, y에 접근함.
  }
  return add();
}
document.write("내부 함수에서 x + y의 값은 " + parentFunc() + "입니다.<br>");
```

> <h3>함수 호이스팅(hoisting)</h3>

자바스크립트에서 함수의 유효 범위라는 것은 함수 안에서 선언된 모든 변수는 함수 전체에 걸쳐 유효하다는 의미입니다.


그런데 이 유효 범위의 적용이 변수가 선언되기 전에도 똑같이 적용됩니다.

이러한 자바스크립트의 특징을 함수 호이스팅(hoisting)이라고 합니다.

즉, 자바스크립트 함수 안에 있는 모든 변수의 선언은 함수의 맨 처음으로 이동된 것처럼 동작합니다.

쉽게 말해, 전역 함수 내에 동일한 변수 이름으로 var 선언이 있을 경우 var 선언 이전까지 나온 전역 변수에 대한 것은 `undefined`로 나타납니다.

``` html
var globalNum = 10;     // globalNum을 전역 변수로 선언함.
function printNum() {
    document.write("지역 변수 globalNum 선언 전의 globalNum의 값은 " + globalNum + "입니다.<br>"); // ①
    var globalNum = 20; // globalNum을 지역 변수로 선언함. // ②
    document.write("지역 변수 globalNum 선언 후의 globalNum의 값은 " + globalNum + "입니다.<br>");
}
printNum();
```

위의 예제 ①의 시점에서는 변수 globalNum가 전역 변수를 가리킨다고 생각하기 쉽습니다.

하지만 자바스크립트 내부에서는 함수 호이스팅에 의해 다음과 같이 코드가 변경되어 처리됩니다.

``` html
var globalNum = 10;
function printNum() {
    var globalNum; // 함수 호이스팅에 의해 변수의 선언 부분이 함수의 맨 처음 부분으로 이동됨.
    document.write("지역 변수 globalNum 선언 전의 globalNum의 값은 " + globalNum + "입니다.<br>"); // undefined
    globalNum = 20;
    document.write("지역 변수 globalNum 선언 후의 globalNum의 값은 " + globalNum + "입니다.<br>"); // 20
}
printNum();
```

위의 예제 ①의 시점에서는 globalNum라는 지역 변수가 선언만 되어 있고, 아직 초기화만 안 된 상태입니다.

따라서 이때 globalNum 변수에 접근하면 아직 초기화되지 않은 변수에 접근했으므로, undefined 값을 반환하게 됩니다.

실제로 변수가 초기화되는 시점은 원래 코드에서 변수가 선언된 ②의 시점입니다.

## 매개변수와 인수

자바스크립트에서는 함수를 정의할 때는 매개변수의 타입을 따로 명시하지 않습니다.

함수를 호출할 때에도 인수(argument)로 전달된 값에 대해 어떠한 타입 검사도 하지 않습니다.

함수를 호출할 때 함수의 정의보다 적은 수의 인수가 전달되더라도, 다른 언어와는 달리 오류를 발생시키지 않습니다.

이 같은 경우 자바스크립트는 전달되지 않은 나머지 매개변수에 자동으로 undefined 값을 설정합니다.

매개변수(parameter)란 함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수를 의미합니다.

인수(argument)란 함수가 호출될 때 함수로 값을 전달해주는 값을 말합니다.

 

다음 예제는 3개의 매개변수를 가지는 함수에 각각 다른 수의 인수를 전달하는 예제입니다.

``` html
function addNum(x, y, z) {	// x, y, z는 매개변수임.
  return x + y + z;
}
document.write("인수가 3개 모두 전달되면 반환값은 " + addNum(1, 2, 3) + "입니다.<br>");	
document.write("인수가 2개만 전달되면 반환값은 " + addNum(1, 2) + "입니다.<br>");
document.write("인수가 1개만 전달되면 반환값은 " + addNum(1) + "입니다.<br>");
document.write("인수가 아무것도 전달되지 않으면 반환값은 " + addNum() + "입니다.");
```

![image](https://user-images.githubusercontent.com/43658658/129020518-54c5e3d4-11d9-4747-b1db-c2a25c324b58.png)

위의 예제에서 addNum() 함수를 호출할 때 인수가 세 개보다 적게 전달되면, 계산할 수 없다는 의미인 NaN을 반환합니다.

그 이유는 전달되지 않은 나머지 값이 자동으로 undefined 값으로 설정되어, 산술 연산을 수행할 수 없기 때문입니다.

 

하지만 다음 예제처럼 하면 NaN을 반환하지 않고 전달된 인수만을 가지고 정상적으로 계산하는 함수를 작성할 수 있습니다.

``` html
function addNum(x, y, z) {	// x, y, z는 매개변수임.
  if (x === undefined)
    x = 0;
  if (y === undefined)
    y = 0;
  if (z === undefined)
    z = 0;
  return x + y + z;
}
document.write("인수가 3개 모두 전달되면 반환값은 " + addNum(1, 2, 3) + "입니다.<br>");	
document.write("인수가 2개만 전달되면 반환값은 " + addNum(1, 2) + "입니다.<br>");
document.write("인수가 1개만 전달되면 반환값은 " + addNum(1) + "입니다.<br>");
document.write("인수가 아무것도 전달되지 않으면 반환값은 " + addNum() + "입니다.");
```

> <h3>arguments 객체</h3>

만약 함수의 정의보다 더 많은 수의 인수가 전달되면, 매개변수에 대입되지 못한 인수들은 참조할 방법이 없게 됩니다.

하지만 arguments 객체를 이용하면, 함수로 전달된 인수의 총 개수를 확인하거나, 각각의 인수에도 바로 접근할 수 있습니다.

arguments 객체는 함수가 호출될 때 전달된 인수를 배열의 형태로 저장하고 있습니다.

첫 번째 인수는 arguments[0]에 저장되며, 다음 인수는 arguments[1]에 저장됩니다.

또한, 인수의 총 개수는 arguments 객체의 length 프로퍼티에 저장됩니다.

arguments 객체는 배열과 비슷할 뿐, 실제로 Array 객체는 아닙니다.

숫자로 된 인덱스와 length 프로퍼티만을 가지고 있을 뿐, 모든 것을 배열처럼 다룰 수는 없습니다. 

다음 예제의 addNum() 함수는 전달받는 인수의 개수에 상관없이 언제나 정상적인 계산을 수행합니다.

``` html
function addNum() {
    var sum = 0;                                // 합을 저장할 변수 sum을 선언함.
    for(var i = 0; i < arguments.length; i++) { // 전달받은 인수의 총 수만큼 반복함.
        sum += arguments[i];                    // 전달받은 각각의 인수를 sum에 더함.
    }
    return sum;
}
addNum(1, 2, 3); // 6
addNum(1, 2);    // 3
addNum(1);       // 1
addNum();        // 0
addNum(1, 2, 3, 4, 5, 6, 7, 8, 9, 10); // 55
```

> <h3>디폴트 매개변수와 나머지 매개변수</h3>

ECMAScript 6부터 새롭게 정의된 매개변수는 다음과 같습니다.

1. 디폴트 매개변수(default parameter)

2. 나머지 매개변수(rest parameter)

> <h3>디폴트 매개변수(default parameter)</h3>

디폴트 매개변수란 함수를 호출할 때 명시된 인수를 전달하지 않았을 경우에 사용하게 될 기본값을 의미합니다.

자바스크립트에서 매개변수의 기본값은 undefined 값으로 설정되어 있습니다.

``` html
function mul(a, b) {
    // 인수가 한 개만 전달되었을 때 나머지 매개변수의 값을 undefined 값이 아닌 1로 설정함.
    b = (typeof b != 'undefined')  ? b : 1;
    return a * b;
}
mul(3, 4); // 12
mul(3);    // 3
```

하지만 디폴트 매개변수를 이용하면 이러한 매개변수의 기본값을 바꿀 수 있습니다.

``` html
function mul(a, b = 1) { // 인수가 한 개만 전달되면 나머지 매개변수의 값을 언제나 1로 설정해 줌.
    return a * b;
}
mul(3, 4); // 12
mul(3);    // 3
```
 
디폴트 매개변수는 익스플로러, 사파리, 오페라에서 지원하지 않습니다.

> <h3>나머지 매개변수(rest parameter)</h3>

나머지 매개변수는 생략 접두사(...)를 사용하여 특정 위치의 인수부터 마지막 인수까지를 한 번에 지정할 수 있습니다.

나머지 매개변수는 익스플로러, 사파리에서 지원하지 않습니다.

다음 예제는 첫 번째 인수에서 두 번째 인수부터 마지막 인수까지를 뺀 후 그 결과를 반환하는 예제입니다.

``` html
function sub() {
  var firstNum = arguments[0];	// 첫 번째 인수에서
  for(var i = 1; i < arguments.length; i++) { // 두 번째부터 마지막 인수까지를
    firstNum -= arguments[i];	// 뺌.
  }
  return firstNum;
}
document.write(sub(10, 2, 3) + "<br>");	// 10 - 2 - 3 = 5
document.write(sub(10, 1, 5, 8));		// 10 - 1 - 5 - 8 = -4
```

하지만 나머지 매개변수를 이용하면 sub() 함수를 좀 더 직관적으로 정의할 수 있습니다.

``` html
// 첫 번째 인수를 변수 firstNum에 저장하고 나머지 인수들은 배열 restArgs에 저장함.
function sub(firstNum, ...restArgs) {
    for(var i = 0; i < restArgs.length; i++) {
        firstNum -= restArgs[i];
    }
    return firstNum;
}
sub(10, 2, 3);    // 10 - 2 - 3 = 5
sub(10, 1, 5, 8); // 10 - 1 - 5 - 8 = -4
```

