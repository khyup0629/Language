# Part 3. 연산자

+ [산술 연산자](#산술-연산자)
+ [대입 연산자](#대입-연산자)
+ [증감 연산자](#증감-연산자)
+ [비교 연산자](#비교-연산자)
+ [논리 연산자](#논리-연산자)
+ [비트 연산자](#비트-연산자)
+ [기타 연산자](#기타-연산자)

## 산술 연산자

산술 연산자는 사칙연산을 다루는 가장 기본적이면서도 많이 사용하는 연산자입니다.

산술 연산자는 모두 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽입니다.

항이란 해당 연산의 실행이 가능하기 위해 필요한 값이나 변수를 의미합니다.

따라서 이항 연산자란 해당 연산의 실행을 위해서 두 개의 값이나 변수가 필요한 연산자를 의미합니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>산술 연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>+</td>
			<td>왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더함.</td>
		</tr>
		<tr>
			<td>-</td>
			<td>왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺌.</td>
		</tr>
		<tr>
			<td>*</td>
			<td>왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱함.</td>
		</tr>
		<tr>
			<td>/</td>
			<td>왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눔.</td>
		</tr>
		<tr>
			<td>%</td>
			<td>왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 반환함.</td>
		</tr>
	</tbody>
</table>

``` html
var x = 10, y = 4;
document.write(x + y + "<br>");
document.write(x - y + "<br>");
document.write(x * y + "<br>");
document.write(x / y + "<br>");
document.write(x % y);
```

> <h3>연산자의 우선순위(operator precedence)와 결합 방향(associativity)</h3>

연산자의 우선순위는 수식 내에 여러 연산자가 함께 등장할 때, 어느 연산자가 먼저 처리될 것인가를 결정합니다.

다음 그림은 가장 높은 우선순위를 가지고 있는 괄호(()) 연산자를 사용하여 연산자의 처리 순서를 변경하는 것을 보여줍니다.

![image](https://user-images.githubusercontent.com/43658658/128822463-195489d1-2fb2-4fd1-b66f-b5e374a77e53.png)
![image](https://user-images.githubusercontent.com/43658658/128822475-e947784e-6938-44dc-b057-255f493f8a06.png)


연산자의 결합 방향은 수식 내에 우선순위가 같은 연산자가 둘 이상 있을 때, 먼저 어느 연산을 수행할 것인가를 결정합니다.

![image](https://user-images.githubusercontent.com/43658658/128822498-7d2d4ec5-bb20-4843-9fa1-ec9a3a1135f6.png)
![image](https://user-images.githubusercontent.com/43658658/128822509-054fd444-f5de-4fc2-b1f3-c31988ef2498.png)

> <h3>자바스크립트 연산자의 우선순위표</h3>

자바스크립트에서 연산자의 우선순위와 결합 방향은 다음과 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 10%;">우선순위</th>
			<th style="width: 10%;">연산자</th>
			<th style="width: 50%;">설명</th>
			<th style="width: 30%;">결합 방향</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><strong>1</strong></td>
			<td>()</td>
			<td>묶음(괄호)</td>
			<td>-</td>
		</tr>
		<tr>
			<td colspan="1"><strong>2</strong></td>
			<td>.</td>
			<td>멤버 접근</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>new</td>
			<td>인수 있는 객체 생성</td>
			<td>-</td>
		</tr>
		<tr>
			<td colspan="1"><strong>3</strong></td>
			<td>()</td>
			<td>함수 호출</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>new</td>
			<td>인수 없는 객체 생성</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td colspan="1"><strong>4</strong></td>
			<td>++</td>
			<td>후위 증가 연산자</td>
			<td>-</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>--</td>
			<td>후위 감소 연산자</td>
			<td>-</td>
		</tr>
		<tr>
			<td colspan="1"><strong>5</strong></td>
			<td>!</td>
			<td>논리 NOT 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>~</td>
			<td>비트 NOT 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>+</td>
			<td>양의 부호 (단항 연산자)</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>-</td>
			<td>음의 부호 (단항 연산자)</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td colspan="1">&nbsp;</td>
			<td>++</td>
			<td>전위 증가 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>--</td>
			<td>전위 감소 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>typeof</td>
			<td>타입 반환</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>void</td>
			<td>undefined 반환</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>delete</td>
			<td>프로퍼티의 제거</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td><strong>6</strong></td>
			<td>**</td>
			<td>거듭제곱 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>*</td>
			<td>곱셈 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>/</td>
			<td>나눗셈 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>%</td>
			<td>나머지 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>7</strong></td>
			<td>+</td>
			<td>덧셈 연산자 (이항 연산자)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>-</td>
			<td>뺄셈 연산자 (이항 연산자)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>8</strong></td>
			<td>&lt;&lt;</td>
			<td>비트 왼쪽 시프트 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&gt;&gt;</td>
			<td>부호 비트를 확장하면서 비트 오른쪽 시프트</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&gt;&gt;&gt;</td>
			<td>부호 비트를 확장하지 않고 비트 오른쪽 시프트</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>9</strong></td>
			<td>&lt;</td>
			<td>관계 연산자(보다 작은)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&lt;=</td>
			<td>관계 연산자(보다 작거나 같은)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&gt;</td>
			<td>관계 연산자(보다 큰)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&gt;=</td>
			<td>관계 연산자(보다 크거나 같은)</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>instanceof</td>
			<td>인스턴스 여부 판단</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>10</strong></td>
			<td>==</td>
			<td>동등 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>===</td>
			<td>일치 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>!=</td>
			<td>부등 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>!==</td>
			<td>불일치 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>11</strong></td>
			<td>&amp;</td>
			<td>비트 AND 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>12</strong></td>
			<td>^</td>
			<td>비트 XOR 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>13</strong></td>
			<td>|</td>
			<td>비트 OR 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>14</strong></td>
			<td>&amp;&amp;</td>
			<td>논리 AND 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>15</strong></td>
			<td>||</td>
			<td>논리 OR 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
		<tr>
			<td><strong>16</strong></td>
			<td>? :</td>
			<td>삼항 연산자</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td><strong>17</strong></td>
			<td>=</td>
			<td>대입 연산자<br />
			(=, +=, -=, *=, /=, %=, &lt;&lt;=, &gt;&gt;=, &gt;&gt;&gt;=, &amp;=, ^=, |=)</td>
			<td>오른쪽에서 왼쪽으로</td>
		</tr>
		<tr>
			<td><strong>18</strong></td>
			<td>...</td>
			<td>전개</td>
			<td>-</td>
		</tr>
		<tr>
			<td><b>19</b></td>
			<td>,</td>
			<td>쉼표 연산자</td>
			<td>왼쪽에서 오른쪽으로</td>
		</tr>
	</tbody>
</table>

위의 표에서 나온 순서대로 우선순위가 빠른 연산자가 가장 먼저 실행됩니다.

또한, 같은 우선순위를 가지는 연산자가 둘 이상 있을 때에는 결합 순서에 따라 실행 순서가 결정됩니다.

위의 표를 모두 외우기보다는 `필요할 때마다 참조하는 것이 좋습니다.`

## 대입 연산자

대입 연산자는 변수에 값을 대입할 때 사용하는 이항 연산자이며, 피연산자들의 결합 방향은 오른쪽에서 왼쪽입니다.

또한, 앞서 살펴본 산술 연산자와 결합한 다양한 복합 대입 연산자가 존재합니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>대입&nbsp;연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>=</td>
			<td>왼쪽 피연산자에 오른쪽 피연산자의 값을 대입함.</td>
		</tr>
		<tr>
			<td>+=</td>
			<td>왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더한 후, 그 결괏값을 왼쪽 피연산자에 대입함.</td>
		</tr>
		<tr>
			<td>-=</td>
			<td>왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺀 후, 그 결괏값을 왼쪽 피연산자에 대입함.</td>
		</tr>
		<tr>
			<td>*=</td>
			<td>왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱한 후, 그 결괏값을 왼쪽 피연산자에 대입함.</td>
		</tr>
		<tr>
			<td>/=</td>
			<td>왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 결괏값을 왼쪽 피연산자에 대입함.</td>
		</tr>
		<tr>
			<td>%=</td>
			<td>왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 왼쪽 피연산자에 대입함.</td>
		</tr>
	</tbody>
</table>

## 증감 연산자

증감 연산자는 피연산자를 1씩 증가 혹은 감소시킬 때 사용하는 연산자입니다.

이 연산자는 피연산자가 단 하나뿐인 단항 연산자입니다.

 

증감 연산자는 해당 연산자가 피연산자의 어느 쪽에 위치하는가에 따라 연산의 순서 및 결과가 달라집니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>증감 연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>++x</td>
			<td>먼저 피연산자의 값을 1 증가시킨 후에 해당 연산을 진행함.</td>
		</tr>
		<tr>
			<td>x++</td>
			<td>먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 증가시킴.</td>
		</tr>
		<tr>
			<td>--x</td>
			<td>먼저 피연산자의 값을 1 감소시킨 후에 해당 연산을 진행함.</td>
		</tr>
		<tr>
			<td>x--</td>
			<td>먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 감소시킴.</td>
		</tr>
	</tbody>
</table>

``` html
var x = 10, y = 10;
document.write((++x - 3) + "<br>"); // 8, x의 값을 우선 1 증가시킨 후에 3을 뺀 값을 출력한다.
document.write(x + "<br>");         // 11
document.write((y++ - 3) + "<br>"); // 7, 먼저 y에서 3을 뺀 값을 출력하고, y의 값을 1 증가시킴.
document.write(y);                  // 11
```

> <h3>증감 연산자의 연산 순서</h3>

증감 연산자는 피연산자의 어느 쪽에 위치하는가에 따라 연산의 순서가 달라집니다.

다음 예제는 증감 연산자의 연산 순서를 살펴보기 위한 예제입니다.
 
``` html
var x = 10;            
var y = x-- + 5 + --x;
// x = 8, y = 23
```

다음 그림은 위의 예제에서 수행되는 연산의 순서를 보여줍니다.

![image](https://user-images.githubusercontent.com/43658658/128824066-0ffd548f-2a1f-4709-b86c-8ce441ada921.png)

① : 첫 번째 감소 연산자(decrement operator)는 피연산자의 뒤쪽에 위치하므로, 덧셈 연산이 먼저 수행됩니다. (15)

② : 덧셈 연산이 수행된 후에 감소 연산이 수행됩니다. (x의 값 : 9)

③ : 두 번째 감소 연산자는 피연산자의 앞쪽에 위치하므로, 덧셈 연산보다 먼저 수행됩니다. (x의 값 : 8)

④ : 감소 연산이 수행된 후에 덧셈 연산이 수행됩니다. (23)

⑤ : 마지막으로 변수 y에 결괏값의 대입 연산이 수행됩니다. (y의 값 : 23)

## 비교 연산자

비교 연산자는 피연산자 사이의 상대적인 크기를 판단하여, 참(true)과 거짓(false)을 반환합니다.

비교 연산자는 모두 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>비교 연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>==</td>
			<td>왼쪽 피연산자와 오른쪽 피연산자의 값이 같으면 참을 반환함.</td>
		</tr>
		<tr>
			<td>===</td>
			<td>왼쪽 피연산자와 오른쪽 피연산자의 값이 같고, 같은 타입이면 참을 반환함.</td>
		</tr>
		<tr>
			<td>!=</td>
			<td>왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않으면 참을 반환함.</td>
		</tr>
		<tr>
			<td>!==</td>
			<td>왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않거나, 타입이 다르면 참을 반환함.</td>
		</tr>
		<tr>
			<td>&gt;</td>
			<td>왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크면 참을 반환함.</td>
		</tr>
		<tr>
			<td>&gt;=</td>
			<td>왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크거나 같으면 참을 반환함.</td>
		</tr>
		<tr>
			<td>&lt;</td>
			<td>왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작으면 참을 반환함.</td>
		</tr>
		<tr>
			<td>&lt;=</td>
			<td>왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작거나 같으면 참을 반환함.</td>
		</tr>
	</tbody>
</table>

자바스크립트에서 비교 연산자는 피연산자의 타입에 따라 두 가지 기준으로 비교를 진행합니다.

 

1. 피연산자가 둘 다 숫자면, 해당 숫자를 서로 비교합니다.

2. 피연산자가 둘 다 문자열이면, 문자열의 첫 번째 문자부터 알파벳 순서대로 비교합니다.


``` html
var x = 3, y = 5;
var a = "abc", b = "bcd";
document.write((x > y) + "<br>");	// y의 값이 x의 값보다 크므로 false
document.write((a <= b) + "<br>");	// 알파벳 순서상 'a'가 'b'보다 먼저 나오므로 'a'가 'b'보다 작음.
document.write(x < a);				// x의 값은 숫자이고 a의 값은 문자열이므로 비교할 수 없음.
```

> <h3>동등 연산자와 일치 연산자</h3>

동등 연산자(==, equal)와 일치 연산자(===, strict equal)는 모두 두 개의 피연산자가 서로 같은지를 비교해 줍니다.

두 연산자 모두 피연산자의 타입을 가리지는 않지만, 그 같음을 정의하는 기준이 조금 다릅니다.

 

동등 연산자(==)는 두 피연산자의 값이 서로 같으면 참(true)을 반환합니다.

이때 두 피연산자의 타입이 서로 다르면, 비교를 위해 강제로 타입을 같게 변환합니다.

하지만 일치 연산자(===)는 타입의 변환 없이 두 피연산자의 값이 같고, 타입도 같아야만 참(true)을 반환합니다.

``` html
var x = 3, y = '3', z = 3;
document.write((x == y) + "<br>");  // x와 y의 타입이 서로 다르므로 타입을 서로 같게 한 후 비교를 하므로 true
document.write((x === y) + "<br>"); // x와 y의 타입이 서로 다르므로 false
document.write(x === z);            // x와 z은 값과 타입이 모두 같으므로 true
```

## 논리 연산자

논리 연산자는 주어진 논리식을 판단하여, 참(true)과 거짓(false)을 반환합니다.

&& 연산자와 || 연산자는 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽입니다.

! 연산자는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>논리 연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&amp;&amp;</td>
			<td>논리식이 모두 참이면 참을 반환함. (논리 AND 연산)</td>
		</tr>
		<tr>
			<td>||</td>
			<td>논리식 중에서 하나라도 참이면 참을 반환함. (논리 OR 연산)</td>
		</tr>
		<tr>
			<td>!</td>
			<td>논리식의 결과가 참이면 거짓을, 거짓이면 참을 반환함. (논리 NOT 연산)</td>
		</tr>
	</tbody>
</table>

``` html
var x = true, y = false;
document.write((x && y) + "<br>"); // false (논리 AND 연산)
document.write((x || y) + "<br>"); // true  (논리 OR  연산)
document.write(!x);                // false (논리 NOT 연산)
```

## 비트 연산자

비트 연산자는 논리 연산자와 비슷하지만, 비트(bit) 단위로 논리 연산을 수행합니다.

또한, 비트 단위로 전체 비트를 왼쪽이나 오른쪽으로 이동시킬 때도 사용합니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>비트 연산자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&amp;</td>
			<td>대응되는 비트가 모두 1이면 1을 반환함. (비트 AND 연산)</td>
		</tr>
		<tr>
			<td>|</td>
			<td>대응되는 비트 중에서 하나라도 1이면 1을 반환함. (비트 OR 연산)</td>
		</tr>
		<tr>
			<td>^</td>
			<td>대응되는 비트가 서로 다르면 1을 반환함. (비트 XOR 연산)</td>
		</tr>
		<tr>
			<td>~</td>
			<td>비트를 1이면 0으로, 0이면 1로 반전시킴. (비트 NOT 연산)</td>
		</tr>
		<tr>
			<td>&lt;&lt;</td>
			<td>지정한 수만큼 비트를 전부 왼쪽으로 이동시킴. (left shift 연산)</td>
		</tr>
		<tr>
			<td>&gt;&gt;</td>
			<td>부호를 유지하면서 지정한 수만큼 비트를 전부 오른쪽으로 이동시킴. (right shift 연산)</td>
		</tr>
		<tr>
			<td>&gt;&gt;&gt;</td>
			<td>지정한 수만큼 비트를 전부 오른쪽으로 이동시키며, 새로운 비트는 전부 0이 됨.</td>
		</tr>
	</tbody>
</table>

## 기타 연산자

> <h3>삼항 연산자(ternary operator)</h3>

삼항 연산자는 유일하게 피연산자를 세 개나 가지는 조건 연산자입니다.

삼항 연산자의 문법은 다음과 같습니다.

`표현식 ? 반환값1 : 반환값2`

물음표(?) 앞의 표현식에 따라 결괏값이 참이면 반환값1을 반환하고, 결괏값이 거짓이면 반환값2를 반환합니다.

``` html
var x = 3, y = 5;
var result = (x > y) ? x : y   // x가 더 크면 x를, 그렇지 않으면 y를 반환함.
document.write("둘 중에 더 큰 수는 " + result + "입니다.");
```

> <h3>쉼표 연산자</h3>

쉼표 연산자를 for 문에서 사용하면, 루프마다 여러 변수를 동시에 갱신할 수 있습니다.

``` html
<script>
  // 루프마다 i의 값은 1씩 증가하고, 동시에 j의 값은 1씩 감소함.
  for (var i = 0, j = 9; i <= j; i++, j--) {
      document.write("i의 값은 " + i + "이고, j의 값은 " + j + "입니다.<br>");
  }
</script>
```

> <h3>delete 연산자</h3>

delete 연산자는 피연산자인 객체, 객체의 프로퍼티(property) 또는 배열의 요소(element) 등을 삭제해 줍니다.

 

피연산자가 성공적으로 삭제되었을 경우에는 참(true)을 반환하고, 삭제하지 못했을 경우에는 거짓(false)을 반환합니다.

이 연산자는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽입니다.

``` html
<script>
  var arr = [1, 2, 3];				// 배열 생성
  delete arr[2];						// 배열의 원소 중 인덱스가 2인 요소를 삭제함.
  document.write(arr + "<br>");		// [1, 2, ]
  // 배열에 빈자리가 생긴 것으로 undefined 값으로 직접 설정된 것은 아님.
  document.write(arr[2] + "<br>");
  // 배열의 요소를 삭제하는 것이지 배열의 크기까지 줄이는 것은 아님.
  document.write(arr.length);
</script>
```

> <h3>instanceof 연산자</h3>

instanceof 연산자는 피연산자인 객체가 특정 객체의 인스턴스인지 아닌지를 확인해 줍니다.

 

피연산자가 특정 객체의 인스턴스이면 참(true)을 반환하고, 특정 객체의 인스턴스가 아니면 거짓(false)을 반환합니다.

이 연산자는 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽입니다.

``` html
var str = new String("이것은 문자열입니다.");
document.write(str + "<br>");

document.write((str instanceof Object) + "<br>");
document.write((str instanceof String) + "<br>");
document.write((str instanceof Array) + "<br>");
document.write((str instanceof Number) + "<br>");
document.write(str instanceof Boolean);
```

> <h3>void 연산자</h3>

void 연산자는 피연산자로 어떤 타입의 값이 오던지 상관없이 언제나 undefined 값만을 반환합니다.

이 연산자는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽입니다.

``` html
<a href="javascript:void(0)">이 링크는 동작하지 않습니다.</a><br><br>
<a href="javascript:void(document.body.style.backgroundColor='yellow')">
  이 링크도 동작하지 않지만, 클릭하면 HTML 문서의 배경색을 바꿔줍니다.
</a>
```

void 연산자는 정의되지 않은 원시 타입의 값을 얻기 위해 void(0)과 같은 형태로 종종 사용됩니다.

