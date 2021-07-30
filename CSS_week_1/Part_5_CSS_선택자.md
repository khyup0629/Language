# Part 5. CSS 선택자

+ [결합 선택자](#결합-선택자)
+ 

## 결합 선택자

CSS 선택자는 하나 이상의 선택자를 포함할 수 있습니다.

결합 선택자는 연관된 선택자들 간의 관계를 설정해 줍니다.

> <h3>자손 선택자(descendant selector)</h3>

자손 선택자는 해당 요소의 하위 요소 중에서 특정 타입의 요소를 모두 선택합니다.

다음 예제는 모든 `<div>`태그의 하위 요소 중에서 `<p>`태그를 모두 선택하는 예제입니다.

자손 선택자는 div와 p 사이에 한 칸의 띄어쓰기를 반드시 명시해야 합니다.

``` html
<style>
  div{ border: 3px solid #CD853F; }
  div p { background-color: #FFEFD5; }
</style>
...
<h1>자식 선택자를 이용한 선택</h1>
<p>div 태그 외부의 p 태그는 선택되지 않습니다.</p>
<div>
  <p>div 태그 바로 밑에 존재하는 p 태그만 선택됩니다!</p>
  <p>div 태그 바로 밑에 존재하는 p 태그만 선택됩니다!</p>
  <span>
    <p>이 p 태그는 span 태그로 둘러 쌓여 있습니다.<br>
      따라서 div 태그 바로 밑에 존재하는 p 태그가 아니므로 선택되지 않습니다!
    </p>
  </span>
</div>
<p>div 태그 외부의 p 태그는 선택되지 않습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127660985-db98d0ed-90fa-4c89-a263-22566fba28de.png)

> <h3>자식 선택자(child selector)</h3>

자식 선택자는 해당 요소의 바로 밑에 존재하는 하위 요소 중에서 특정 타입의 요소를 모두 선택합니다.

다음 예제는 모든 `<div>`태그의 바로 밑에 존재하는 하위 요소 중에서 `<p>`태그를 모두 선택하는 예제입니다.

``` html
<style>
  div{ border: 3px solid #CD853F; }
  div > p { background-color: #FFEFD5; }
</style>
...
<p>div 태그 외부의 p 태그는 선택되지 않습니다.</p>
<div>
  <p>div 태그 바로 밑에 존재하는 p 태그만 선택됩니다!</p>
  <p>div 태그 바로 밑에 존재하는 p 태그만 선택됩니다!</p>
  <span>
    <p>이 p 태그는 span 태그로 둘러 쌓여 있습니다.<br>
      따라서 div 태그 바로 밑에 존재하는 p 태그가 아니므로 선택되지 않습니다!
    </p>
  </span>
</div>
<p>div 태그 외부의 p 태그는 선택되지 않습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127660775-346ac1c8-b2f3-48f8-9c29-64c238bad1c6.png)

## 동위 선택자(sibling selector)

동위 선택자는 동위 관계에 있는 요소 중에서 해당 요소보다 뒤에 존재하는 특정 타입의 요소를 모두 선택합니다.

 

동위 관계란 HTML 요소의 계층 구조에서 같은 부모(parent) 요소를 가지고 있는 요소들을 의미합니다.

이러한 동위 관계에 있는 요소들을 ***형제(sibling) 요소***라고 합니다.

 
![image](https://user-images.githubusercontent.com/43658658/127661130-53b90884-5187-4a9f-a557-5b980fdff5c8.png)


위의 그림에서 초록색으로 표시된 세 요소는 모두 `<body>`요소를 부모 요소로 가집니다.

따라서 이 세 요소는 동위 관계에 있는 형제 요소라고 할 수 있습니다.

> <h3>일반 동위 선택자(general sibling selector)</h3>

일반 동위 선택자는 해당 요소와 동위 관계에 있으며, 해당 요소보다 뒤에 존재하는 특정 타입의 요소를 모두 선택합니다.

 

다음 예제는 모든 `<div>`태그와 동위 관계에 있는 요소 중에서 `<div>`태그보다 뒤에 존재하는 `<p>`태그를 모두 선택하는 예제입니다.

``` html
<style>
  div{ border: 3px solid #F08080; }
  div ~ p { background-color: #FFE4E1; }
</style>
...
<h1>일반 동위 선택자를 이용한 선택</h1>
<p>이 p 태그는 div 태그의 sibling 이지만 div 태그보다 앞에 나옵니다!</p>
<div>
  <p>이 p 태그는 div 태그의 child 입니다!</p>
  <p>이 p 태그는 div 태그의 child 입니다!</p>
  <p>이 p 태그는 div 태그의 child 입니다!</p>
</div>
<p>이 p 태그는 div 태그의 sibling 입니다!</p>
<p>이 p 태그는 div 태그의 sibling 입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127661352-98786df1-4692-42e0-80cb-018f402e4fab.png)

> <h3>인접 동위 선택자(adjacent sibling selector)</h3>

영어로 adjacent는 인접한, 가까운 이라는 의미가 있습니다.

인접 동위 선택자는 해당 요소와 동위 관계에 있으며, 해당 요소의 바로 뒤에 존재하는 특정 타입의 요소를 모두 선택합니다..

 

다음 예제는 모든 `<div>`태그와 동위 관계에 있는 요소 중에서 `<div>`태그의 바로 뒤에 존재하는 `<p>`태그를 모두 선택하는 예제입니다.

``` html
<style>
  div { border: 3px solid #F08080; }
  div ~ p { background-color: #FFE4E1; }
</style>
...
<h1>인접 동위 선택자를 이용한 선택</h1>
<div>
  <p>이 p 태그는 div 태그의 sibling 입니다!</p>
  <div>
    <p>이 p 태그는 div 태그의 child 입니다!</p>
  </div>
  <p>이 p 태그는 div 태그 바로 뒤에 나오는 sibling 입니다!</p>
  <p>이 p 태그는 div 태그의 sibling 입니다!</p>
</div>
<p>이 p 태그는 div 태그 바로 뒤에 나오는 sibling 입니다!</p>
<p>이 p 태그는 div 태그의 sibling 입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127661610-cea19bb8-a35b-4f35-b0c2-77fb9281578e.png)

## 의사 클래스(pseudo-class)
CSS에서 의사 클래스(pseudo-class)는 선택하고자 하는 HTML 요소의 특별한 '상태(state)'를 명시할 때 사용합니다.

> <h3>의사 클래스의 문법</h3>

의사 클래스(pseudo-class)를 사용하기 위한 문법은 다음과 같습니다.

`선택자:의사클래스이름 {속성: 속성값;} `

클래스(class)나 아이디(id)에도 의사 클래스(pseudo-class)를 사용할 수 있습니다.

```
선택자.클래스이름:의사클래스이름 {속성: 속성값;} 
선택자#아이디이름:의사클래스이름 {속성: 속성값;}
```
 
의사 클래스(pseudo-class)의 이름은 대소문자를 구분하지 않습니다.

> <h3>대표적인 CSS 의사 클래스</h3>

CSS에서 자주 사용하는 대표적인 의사 클래스는 다음과 같습니다.


1. 동적 의사 클래스(dynamic pseudo-classes)
- :link
- :visited
- :hover
- :active
- :focus


2. 상태 의사 클래스(UI element states pseudo-classes)
- :checked
- :enabled
- :disabled

 
3. 구조 의사 클래스(structural pseudo-classes)
- :first-child
- :nth-child
- :first-of-type
- :nth-of-type

 
4. 기타 의사 클래스
- :not
- :lang

> <h4>CSS 의사 클래스(pseudo classes)</h4>

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">의사 클래스</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>:link</td>
			<td>사용자가 아직 한 번도 해당 링크를 통해서&nbsp;연결된 페이지를 방문하지 않은 상태를 모두 선택함. (기본 상태)</td>
		</tr>
		<tr>
			<td>:visited</td>
			<td>사용자가 한 번이라도 해당 링크를 통해서 연결된 페이지를 방문한 상태를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:hover</td>
			<td>사용자의 마우스 커서가 링크&nbsp;위에 올라가 있는 상태를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:active</td>
			<td>사용자가 마우스로 링크를 클릭하고 있는 상태를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:focus</td>
			<td>초점이 맞춰진 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:checked</td>
			<td>체크된(checked) 상태의 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:enabled</td>
			<td>사용할 수 있는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:disabled</td>
			<td>사용할 수 없는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:target</td>
			<td>현재 활성화된 target 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:in-range</td>
			<td>특정 범위 내의 값을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:out-of-range</td>
			<td>특정 범위를 벗어나는 값을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:read-only</td>
			<td>readonly 속성을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:read-write</td>
			<td>readonly 속성을 가지지 않는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:required</td>
			<td>required 속성을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:optional</td>
			<td>required 속성을 가지지 않는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:valid</td>
			<td>유효한 값을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:invalid</td>
			<td>유효하지 않은 값을 가지는 input 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:first-child</td>
			<td>모든 자식(child) 요소 중에서 첫 번째에 위치하는 자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:last-child</td>
			<td>모든 자식(child) 요소 중에서 마지막에 위치하는 자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-child</td>
			<td>모든 자식(child) 요소 중에서 앞에서부터 n번째에 위치하는 자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-last-child</td>
			<td>모든 자식(child) 요소 중에서 뒤에서부터 n번째에 위치하는 자식(child) 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:first-of-type</td>
			<td>모든 자식(child) 요소 중에서 첫 번째로 등장하는 특정 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:last-of-type</td>
			<td>모든 자식(child)&nbsp;요소 중에서 마지막으로 등장하는 특정 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-of-type</td>
			<td>모든 자식(child)&nbsp;요소 중에서 n번째로 등장하는 특정 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:nth-last-of-type</td>
			<td>모든 자식(child)&nbsp;요소 중에서 뒤에서부터 n번째로 등장하는 특정 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:only-child</td>
			<td>자식(child)&nbsp;요소를 단 하나만 가지는 모든 요소의 자식(child) 요소를 선택함.</td>
		</tr>
		<tr>
			<td>:only-of-type</td>
			<td>자식(child)&nbsp; 요소를 특정 요소 단 하나만 가지는 모든 요소의 자식(child)&nbsp;요소를 선택함.</td>
		</tr>
		<tr>
			<td>:empty</td>
			<td>아무런 자식(child)&nbsp;요소도 가지지 않는 요소를 모두 선택함.</td>
		</tr>
		<tr>
			<td>:root</td>
			<td>문서의 root 요소를 선택함.</td>
		</tr>
		<tr>
			<td>:not(선택자)</td>
			<td>모든 선택자와 함께 사용할 수 있으며, 해당 선택자를 반대로 적용함.</td>
		</tr>
		<tr>
			<td>:lang(언어)</td>
			<td>특정 요소를 언어 설정에 따라 다르게 표현할 때에 사용함.</td>
		</tr>
	</tbody>
</table>
