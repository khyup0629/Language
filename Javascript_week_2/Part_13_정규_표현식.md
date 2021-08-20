# Part 13. 정규 표현식

+ [정규 표현식의 개념](#정규-표현식의-개념)
+ [정규 표현식의 응용](#정규-표현식의-응용)
+ [RegExp 객체](#RegExp-객체)

## 정규 표현식의 개념

> <h3>정규 표현식(regular expression)이란?</h3>

정규 표현식(regular expression)은 문자열에서 특정한 규칙을 가지는 문자열의 집합을 찾아내기 위한 검색 패턴입니다.

이러한 검색 패턴은 모든 종류의 문자열 검색이나 교체 등의 작업에서 사용할 수 있습니다.

> <h3>정규 표현식의 생성</h3>

자바스크립트에서 정규 표현식을 만드는 방법은 다음과 같습니다.

1. 정규 표현식 리터럴을 이용한 생성

2. RegExp 객체를 이용한 생성

 

자바스크립트에서 정규 표현식 리터럴은 다음 문법을 사용하여 표현합니다.

``` javascript
/검색패턴/플래그
```
 

정규 표현식 리터럴은 슬래시(/) 기호로 시작하여, 슬래시(/) 기호로 끝납니다.

또한, 필요에 따라 플래그를 추가하여 기본 검색 설정을 변경할 수도 있습니다.

 

``` javascript
var regStr = /a+bc/;             // 정규 표현식 리터럴을 이용한 생성
var regObj = new RegExp("a+bc"); // RegExp 객체를 이용한 생성
regStr;                          // /a+bc/
regObj;                          // /a+bc/
```

> <h3>단순한 패턴 검색</h3>

정규 표현식을 사용하여 단순한 패턴을 검색하고자 할 때는 찾고자 하는 문자열을 직접 나열하면 됩니다.

예를 들어, 다음과 같은 정규 표현식은 정확히 "abc"라는 문자열만이 일치할 것입니다.

``` javascript
/abc/
```
 
다음 예제는 정규 표현식을 이용한 단순한 패턴 검색 예제입니다.

``` javascript
var targetStr = "간장 공장 공장장은 강 공장장이고, 된장 공장 공장장은 장 공장장이다."
var strReg1 = /공장/;
var strReg2 = /장공/;
 
targetStr.search(strReg1); // 3
targetStr.search(strReg2); // -1
```

위의 예제에서 첫 번째 정규 표현식은 해당 문자열의 부분 문자열인 "공장"과 총 6번 일치합니다.

하지만 search() 메소드는 일치하는 문자열 중에서 첫 번째 문자열의 인덱스만을 반환합니다.

 

위의 예제에서 두 번째 정규 표현식은 해당 문자열이 "장 공"이라는 부분 문자열은 포함하고 있지만, 정확히 "장공"이라는 부분 문자열을 포함하지 않으므로, 아무것도 일치하지 않습니다.

search() 메소드는 해당 문자열에서 인수로 전달받은 정규 표현식과 일치하는 부분 문자열을 찾지 못하면 -1을 반환합니다.

> <h3>플래그(flags)</h3>

정규 표현식을 생성할 때 플래그를 사용하여 기본 검색 설정을 변경할 수 있습니다.

이렇게 설정된 플래그는 나중에 추가되거나 삭제될 수 없습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>
			<p>플래그(flag)</p>
			</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>i</td>
			<td>검색 패턴을 비교할 때 대소문자를 구분하지 않도록 설정함.</td>
		</tr>
		<tr>
			<td>g</td>
			<td>검색 패턴을 비교할 때 일치하는 모든 부분을 선택하도록 설정함.</td>
		</tr>
		<tr>
			<td>m</td>
			<td>검색 패턴을 비교할 때 여러 줄의 입력 문자열을 그 상태 그대로 여러 줄로 비교하도록 설정함.</td>
		</tr>
		<tr>
			<td>y</td>
			<td>대상 문자열의 현재 위치부터 비교를 시작하도록 설정함.</td>
		</tr>
	</tbody>
</table>

``` javascript
var targetStr = "bcabcAB";
var strReg = /AB/;              // 검색 패턴 비교 시 기본 설정으로 대소문자를 구분함.
var strUsingFlag = /AB/i;       // new RegExp("AB", "i")와 동일함.
targetStr.search(strReg);       // 5
targetStr.search(strUsingFlag); // 2 -> 대소문자를 구분하지 않고 검색함.
```

## 정규 표현식의 응용

> <h3>특수 문자(special characters)</h3>

정규 표현식을 사용하여 단순한 패턴을 검색하고자 할 때는 찾고자 하는 문자열을 직접 나열하면 됩니다.

하지만 숫자만을 검색하거나, 띄어쓰기를 찾는 등 정확히 일치하는 패턴보다 더 복잡한 조건을 사용하려면 특수 문자를 사용해야 합니다.

자바스크립트 정규 표현식에서 사용할 수 있는 대표적인 특수 문자는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>특수 문자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>\</td>
			<td>역슬래시(\) 다음에 일반 문자가 나오면 이스케이프 문자로 해석하고, 특수 문자가 나오면 일반 문자로 해석함.</td>
		</tr>
		<tr>
			<td>\d</td>
			<td>숫자를 검색함. /[0-9]/와 같음.</td>
		</tr>
		<tr>
			<td>\D</td>
			<td>숫자가 아닌 문자를 검색함. /[^0-9]/와 같음</td>
		</tr>
		<tr>
			<td>\w</td>
			<td>언더스코어(_)를 포함한 영문자 및 숫자를 검색함. /[A-Za-z0-9_]/와 같음.</td>
		</tr>
		<tr>
			<td>\W</td>
			<td>언더스코어(_), 영문자, 숫자가 아닌 문자를 검색함. /[^A-Za-z0-9_]/와 같음.</td>
		</tr>
		<tr>
			<td>\s</td>
			<td>띄어쓰기, 탭, 줄 바꿈 문자 등의 공백 문자를 검색함.</td>
		</tr>
		<tr>
			<td>\S</td>
			<td>띄어쓰기, 탭, 줄 바꿈 문자 등의 공백 문자가 아닌 문자를 검색함.</td>
		</tr>
		<tr>
			<td>\b</td>
			<td>단어의 맨 앞이나 맨 뒤가 패턴과 일치하는지를 검색함.</td>
		</tr>
		<tr>
			<td>\xhh</td>
			<td>16진수 hh에 해당하는 유니코드 문자를 검색함.</td>
		</tr>
		<tr>
			<td>\uhhhh</td>
			<td>16진수 hhhh에 해당하는 유니코드 문자를 검색함.</td>
		</tr>
	</tbody>
</table>

다음 예제는 특수 문자인 '\d'를 사용한 정규 표현식 예제입니다.

``` javascript
var targetStr = "ab1bc2cd3de";
var reg1 = /\d/;    // 2 -> 0부터 9까지의 숫자를 검색함.
var reg2 = /[3-9]/; // 8 -> 3부터 9까지의 숫자를 검색함.
```

위의 예제에서 첫 번째 정규 표현식은 0부터 9까지의 숫자인지를 검색합니다.

이 정규 표현식은 "/[0-9]/"와 같은 결과를 반환할 것입니다.

두 번째 정규 표현식은 3부터 9까지의 숫자인지를 검색합니다.


다음 예제는 특수 문자인 '\s'와 '\w'를 사용한 정규 표현식 예제입니다.

``` javascript
var text = document.getElementById("text");

var targetStr = "abc 123";
// 공백 문자를 사이에 두는 언더스코어(_)를 포함한 영문자 및 숫자로 이루어진 문자열을 검색함.
var reg = /\w\s\w/;

text.innerHTML = targetStr.match(reg); // c 1
```

`match()` 메소드는 해당 문자열에서 인수로 전달받은 정규 표현식과 일치하는 문자열을 모두 찾아서 하나의 배열로 반환해주는 자바스크립트의 String 메소드입니다.

위의 예제에서 사용된 정규 표현식은 첫 번째 문자로 언더스코어(_)를 포함한 영문자 및 숫자를 검색합니다.

두 번째 문자로는 띄어쓰기를 포함한 탭(tab), 줄 바꿈 문자 등의 공백 문자를 검색합니다.

마지막 세 번째 문자로 다시 언더스코어(_)를 포함한 영문자 및 숫자를 검색합니다.

 

이처럼 특수 문자를 나열하여 각각의 조건에 해당하는 문자로 이루어진 부분 문자열을 검색할 수 있습니다.

다음 예제는 특수 문자인 '\b'를 사용한 정규 표현식 예제입니다.

``` javascript
var targetStr1 = "abc123abc";   // 7
var targetStr2 = "abc 123 abc"; // 1
var targetStr3 = "abc@123!abc"; // 1

// 단어의 맨 앞이나 맨 뒤에 부분 문자열 "bc"가 존재하는지를 검색함.
var reg = /bc\b/;
```

특수 문자 '\b'를 사용한 정규 표현식은 단어의 맨 앞이나 맨 뒤가 패턴과 일치하는지를 검색합니다.

위의 예제에서 첫 번째 정규 표현식은 해당 문자열을 하나의 단어로 인식하고, 양 끝에 위치한 패턴을 검색합니다.

하지만 두 번째와 세 번째 정규 표현식은 해당 문자열을 여러 개의 단어로 인식하고, 모든 단어에 대해 패턴을 검색할 것입니다.

 

자바스크립트에서는 언더스코어(`_`)와 영문자 ,숫자만을 단어에 포함될 수 있는 문자로 인식합니다.

따라서 이 외의 모든 문자는 문자열에서 단어를 구분하는 문자(word break)로 인식될 것입니다.

> <h3>양화사(quantifier)</h3>

정규 표현식에서는 특수 문자로 수량을 나타내는 다양한 양화사를 사용할 수 있습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>괄호</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>n*</td>
			<td>바로 앞의 문자가 0번 이상 나타나는 경우를 검색함. /{0, }/와 같음.</td>
		</tr>
		<tr>
			<td>n+</td>
			<td>바로 앞의 문자가 1번 이상 나타나는 경우를 검색함. /{1, }/과 같음.</td>
		</tr>
		<tr>
			<td>n?</td>
			<td>바로 앞의 문자가 0번 또는 1번만 나타나는 경우를 검색함. /{0,1}/과 같음.</td>
		</tr>
	</tbody>
</table>

``` javascript
var targetStr = "Hello World!";
var zeroReg = /lo*/;          // 문자 'l' 다음에 문자 'o'가 0번 이상 나타나는 경우를 검색함.
var oneReg = /lo+/;           // 문자 'l' 다음에 문자 'o'가 1번 이상 나타나는 경우를 검색함.
var zeroOneReg = /lo?/;       // 문자 'l' 다음에 문자 'o'가 0 또는 1번만 나타나는 경우를 검색함.
 
targetStr.search(zeroReg);    // 2
targetStr.search(oneReg);     // 3
targetStr.search(zeroOneReg); // 2
```

또한, 물음표(?) 기호가 정규 표현식의 양화사(*, +, ?, {}) 바로 다음에 위치하게 되면, 가능한 많은 문자를 가지도록 패턴을 찾는 기본 설정과는 달리 해당 양화사가 가능한 적은 수의 문자만을 가지는 패턴을 찾도록 변경시킵니다.

``` javascript
var targetStr = "123abc";
var oneReg = /\d+/;           // 숫자를 검색함. /[0-9]/와 같음.
var anotherReg = /\d+?/;      // 숫자를 검색하지만, 가능한 적은 수의 문자를 가지는 패턴을 검색함.
 
targetStr.search(oneReg);     // 123
targetStr.search(anotherReg); // 1
```

위의 예제에서 첫 번째 정규 표현식은 하나 이상의 숫자만을 검색하므로, 문자열 "123abc"에서 가능한 많은 문자를 가지도록 "123"을 검색합니다.

하지만 두 번째 정규 표현식처럼 바로 뒤에 물음표(?) 기호를 추가하면, 가능한 적은 문자를 가지도록 변경되므로, "1"만을 검색하게 됩니다.

> <h3>괄호(bracket)</h3>

정규 표현식에서 사용할 수 있는 여러 가지 괄호의 의미는 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>괄호</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>a(b)c</td>
			<td>전체 패턴을 검색한 후에 괄호 안에 명시된 문자열을 저장함. (ex : &quot;abc&quot;를 검색한 후에 b를 저장함.)</td>
		</tr>
		<tr>
			<td>[abc]</td>
			<td>꺾쇠 괄호([]) 안에 명시된 문자를 검색함. (ex : &quot;abc&quot;를 검색함.)</td>
		</tr>
		<tr>
			<td>[0-3]</td>
			<td>꺾쇠 괄호([]) 안에 명시된&nbsp;숫자를 검색함. (ex : 0부터 3까지의 숫자를 검색함.)</td>
		</tr>
		<tr>
			<td>[\b]</td>
			<td>백스페이스 문자를 검색함.</td>
		</tr>
		<tr>
			<td>{n}</td>
			<td>앞의 문자가 정확히 n번 나타나는 경우를 검색함. n은 반드시 양의 정수이어야만 함.</td>
		</tr>
		<tr>
			<td>{m,n}</td>
			<td>앞의 문자가 최소 m번 이상 최대 n번 이하로 나타나는 경우를 검색함. m과 n은 반드시 양의 정수이어야만 함.</td>
		</tr>
	</tbody>
</table>

\b는 단어의 맨 앞이나 맨 뒤가 패턴과 일치하는지를 검색하는 특수 문자이고, [\b]는 백스페이스 문자를 검색하는 정규표현식입니다. 이 둘을 혼동해서는 안 됩니다.

다음 예제는 괄호(())를 사용하여 패턴을 검색하고 해당 패턴을 저장하여, 위치를 변경시키는 예제입니다.

``` javascript
var targetStr = "Hong Gil Dong";
var nameReg = /(\w+)\s(\w+)\s(\w+)/;                  // 공백 문자를 기준으로 각 부분문자열을 저장함.
var engName = targetStr.replace(nameReg, "$2 $3 $1"); // 첫 번째 부분문자열을 맨 마지막으로 위치시킴.
engName;                                              // Gil Dong Hong
```
 

위의 예제에서 괄호로 묶여진 정규 표현식으로 검색되는 세 개의 부분 문자열은 차례대로 저장됩니다.

이때 replace() 메소드에서는 이렇게 저장된 부분 문자열을 $1, $2, ..., $n 표현을 이용하여 사용할 수 있습니다.

이렇게 저장된 부분 문자열은 replace() 메소드에서 사용할 수도 있지만, 정규 표현식 내부에서 바로 사용할 수도 있습니다.

``` javascript
var targetStr = "abc 123 abc 123";
var oneReg = /(\w+) (\d+)/;				// abc 123, abc, 123
var anotherReg = /(\w+) (\d+) \1 \2/;	// abc 123 abc 123, abc, 123
document.getElementById("text").innerHTML =
  targetStr.match(oneReg) + "<br>" + targetStr.match(anotherReg);
```

위의 예제에서 첫 번째 정규 표현식은 언더스코어(_)를 포함한 영문자 및 숫자로 이루어진 한 부분 문자열과 띄어쓰기로 구분되는 숫자로 이루어진 또 다른 부분 문자열을 검색합니다.

따라서 해당 문자열에서는 각각 첫 번째 "abc"와 "123"이 검색되어 저장됩니다. 

하지만 두 번째 정규 표현식에서는 위와 같은 방법으로 저장된 부분 문자열을 정규 표현식 내에서 또다시 사용하고 있습니다.

이때 정규 표현식 내에서는 \1, \2, ..., \n 표현을 이용하여 저장된 부분 문자열을 사용할 수 있습니다.

 

match() 메소드는 정규 표현식과 모두 일치하는 부분 문자열뿐만 아니라, 괄호를 사용하여 저장된 부분 문자열도 함께 반환합니다.

> <h3>위치 문자</h3>

정규 표현식에서는 패턴을 검색할 단어의 위치를 지정할 수 있습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>괄호</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>^a</td>
			<td>단어의 맨 앞에 위치한 해당 패턴만을 검색함. (ex : &#39;a&#39;로 시작하는 단어의 &#39;a&#39;만을 검색함.)</td>
		</tr>
		<tr>
			<td>a$</td>
			<td>단어의 맨 뒤에 위치한 해당 패턴만을 검색함. (ex : &#39;a&#39;로 끝나는 단어의 &#39;a&#39;만을 검색함.)</td>
		</tr>
	</tbody>
</table>

``` javascript
var firstStr = "Php";
var secondStr = "phP";
var strReg = /^p/;       // 'p'로 시작하는 단어의 'p'만을 검색함.
firstStr.match(strReg);  // null
secondStr.match(strReg); // p
```

## RegExp 객체

RegExp 객체는 정규 표현식을 구현한 자바스크립트 표준 내장 객체입니다.

RegExp 객체를 생성하는 문법은 다음과 같습니다.

``` javascript
new RegExp(검색패턴[, 플래그]);
```
 

1. 검색 패턴을 나타내는 정규 표현식은 따옴표나 슬래시(/)로 감싸야 합니다.

2. 기본 검색 설정을 변경할 수 있는 플래그는 필요할 때만 전달할 수 있습니다.

> <h3>exec() 메소드</h3>

exec() 메소드는 인수로 전달된 문자열에서 특정 패턴을 검색하여, `패턴과 일치하는 문자열을 반환`합니다.

만약에 패턴과 일치하는 문자열이 없으면 null을 반환합니다.

``` javascript
var targetStr = "abbcdefabgh";
var firstResult = /ab+/.exec(targetStr);    // 패턴과 일치하는 문자열이 여러 개인 경우
var secondResult = /abbb+/.exec(targetStr); // 패턴과 일치하는 문자열이 하나도 없는 경우
firstResult;  // abb -> 가장 맨 처음으로 일치하는 문자열이 반환됨.
secondResult; // null
```

> <h3>test() 메소드</h3>

test() 메소드는 인수로 전달된 문자열에 특정 패턴과 일치하는 문자열이 있는지를 검색합니다.

만약에 패턴과 일치하는 문자열이 있으면 `true를, 없으면 false를 반환`합니다.

``` javascript
var targetStr = "abbcdefabgh";
var firstResult = /ab+/.test(targetStr);    // 패턴과 일치하는 문자열이 여러 개인 경우
var secondResult = /abbb+/.test(targetStr); // 패턴과 일치하는 문자열이 하나도 없는 경우
firstResult;  // true
secondResult; // false
```

