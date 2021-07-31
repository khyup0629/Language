# Part 5. CSS 선택자

+ [결합 선택자](#결합-선택자)
+ [동위 선택자(sibling selector)](#동위-선택자sibling-selector)
+ [의사 클래스(pseudo-class)](#의사-클래스pseudoclass)
+ [동적 의사 클래스(dynamic pseudo-class)](#동적-의사-클래스dynamic-pseudoclass)
+ [상태 의사 클래스(UI element states pseudo-class)](#상태-의사-클래스UI-element-states-pseudoclass)
+ [구조 의사 클래스(structural pseudo-class)](#구조-의사-클래스structural-pseudoclass)
+ [의사 요소(pseudo-element)](#의사-요소pseudoelement)
+ [속성 선택자(attribute selectors)](#속성-선택자attribute-selectors)
+ [기타 의사 클래스](#기타-의사-클래스)

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

## 동적 의사 클래스(dynamic pseudo-class)

CSS에서 사용할 수 있는 동적 의사 클래스는 다음과 같습니다.

- :link
- :visited
- :hover
- :active
- :focus
 
동적 의사 클래스를 사용하면 링크의 상태에 따라 각각의 스타일을 별도로 설정할 수 있습니다.

``` html
<style>
    a:link {color: orange;}
    a:visited {color: gray;}
    a:hover {color: blue;}
    a:active {color: red;}
    div:hover { background-color: blue; color: white; }
</style>
```

> <h3>링크(link)의 상태</h3>

링크는 총 5가지의 상태를 가지며, 각 상태마다 별도의 스타일을 적용할 수 있습니다.

 

1. link : 링크의 기본 상태이며, 사용자가 아직 한 번도 이 링크를 통해 연결된 페이지를 방문하지 않은 상태입니다.

2. visited : 사용자가 한 번이라도 이 링크를 통해 연결된 페이지를 방문한 상태입니다.

3. hover : 사용자의 마우스 커서가 링크 위에 올라가 있는 상태입니다.

4. active : 사용자가 마우스로 링크를 클릭하고 있는 상태입니다.

5. focus : 키보드나 마우스의 이벤트(event) 또는 다른 형태로 해당 요소가 포커스(focus)를 가지고 있는 상태입니다.

 

- `:hover`는 반드시 `:link`와 `:visited`가 먼저 정의된 후에 정의되어야 정상적으로 동작합니다.
- `:active`는 반드시 `:hover`가 먼저 정의된 후에 정의되어야 정상적으로 동작합니다.

``` html
<style>
	input {
		border: 3px solid #FFEFD5;
		width: 300px;
		padding: 10px;
		outline: none;
		transition: 0.5s;
	}
	input:focus { border: 3px solid #CD853F; }
</style>
...
<form>
	아래의 입력 양식을 마우스로 클릭해 보세요!<br><br>
	<input type="text" id="email" name="email" value="마우스로 클릭해 보세요!">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127733976-cfc03f0d-628e-4263-994f-031755f62f44.png)

박스 안을 마우스로 클릭해서 포커스를 가지게 되면 아래와 같이 테두리 색이 변합니다.

![image](https://user-images.githubusercontent.com/43658658/127733984-d3cf9e95-e94e-4984-a0fe-3208db611621.png)

## 상태 의사 클래스(UI element states pseudo-class)

상태 의사 클래스를 사용하면 입력 양식의 상태에 따라 각각의 스타일을 별도로 설정할 수 있습니다.

CSS에서 사용할 수 있는 상태 의사 클래스는 다음과 같습니다.

 

- :checked
- :enabled
- :disabled

> <h3>:checked</h3>

:checked는 input 요소 중에서 체크된(checked) 상태의 input 요소를 선택합니다.

``` html
<style>
	span { margin-left: 5px; }
	input:checked + span { color: #CD853F; }
</style>
...
<form>
	<input type="checkbox" name="lecture" value="html" checked="checked"><span>HTML</span><br>
	<input type="checkbox" name="lecture" value="css"><span>CSS</span><br>
	<input type="checkbox" name="lecture" value="java"><span>JAVA</span><br>
	<input type="checkbox" name="lecture" value="cpp"><span>C++</span><br>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127734205-b578d8cb-0dd7-43ba-88d7-c9d95a14483f.png)

> <h3>:enabled와 :disabled</h3>

:enabled는 input 요소 중에서 사용할 수 있는 input 요소를 선택합니다.

또한, :disabled는 input 요소 중에서 사용할 수 없는 input 요소를 선택합니다.

``` html
<style>
	span { margin-left: 5px; }
	input:enabled + span { color: green; }
	input:disabled + span { color: #CD853F; }
</style>
...
<form>
	<input type="checkbox" name="lecture" value="html" checked="checked"><span>HTML</span><br>
	<input type="checkbox" name="lecture" value="css"><span>CSS</span><br>
	<input type="checkbox" name="lecture" value="java"><span>JAVA</span><br>
	<input type="checkbox" name="lecture" value="cpp" disabled="disabled"><span>C++</span>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127734303-35046481-fc69-4f23-9a0d-4c9f49044655.png)

## 구조 의사 클래스(structural pseudo-class)

구조 의사 클래스를 사용하면 HTML 요소의 계층 구조에서 특정 위치에 있는 요소를 선택할 수 있습니다.

CSS에서 사용할 수 있는 구조 의사 클래스는 다음과 같습니다.

 

- :first-child
- :last-child
- :nth-child
- :nth-last-child

- :first-of-type
- :last-of-type
- :nth-of-type
- :nth-last-of-type

> <h3>:first-child</h3>

(선택자):first-child는 어떤 요소의 모든 자식(child) 요소 중에서 맨 앞에 위치하는 선택자 자식(child) 요소를 선택합니다.

첫 번째에 나타나는 요소가 선택자 요소가 아닐 경우 선택하지 않습니다.

``` html
<style>
	div.first{ border: 3px solid #008000; margin:5px; padding: 5px; }
	div.second{ border: 3px solid #FFD700; margin:5px; padding: 5px;}
	p:first-child {
		color: red;
		font-weight: bold;
	}
</style>
...
<p>나는?</p>
<div class="first">
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<div class="second">
		<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
		<p>이 p 태그는 div 태그의 child 입니다!</p>
		<p>이 p 태그는 div 태그의 child 입니다!</p>
	</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734382-8ab7d7e5-f7d1-4dcb-bce5-5e038cc3e64a.png)

> <h3>:last-child</h3>

(선택자):last-child는 어떤 요소의 모든 자식(child) 요소 중에서 맨 마지막에 위치하는 자식 요소가 선택자일 경우 그 자식(child) 요소를 선택합니다.

마지막에 위치한 요소가 선택자 요소가 아닐 경우 선택하지 않습니다.

``` html
<style>
	div.first{ border: 3px solid #008000; margin:5px; padding:5px; }
	div.second{ border: 3px solid #FFD700; margin:5px; padding:5px; }
	p:last-child{ color:red; font-weight:bold; }
</style>
...
<div class="first">
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 마지막 child 입니다!</p>
	<div class="second">
		<p>이 p 태그는 div 태그의 child 입니다!</p>
		<p>이 p 태그는 div 태그의 child 입니다!</p>
		<p>이 p 태그는 div 태그의 마지막 child 입니다!</p>
	</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734462-97b04756-748e-484c-bc82-b2d1b03331ed.png)

> <h3>:nth-child</h3>

(선택자):nth-child는 어떤 요소의 모든 자식(child) 요소 중에서 앞에서부터 n번째에 위치하는 선택자 자식(child) 요소를 모두 선택합니다.

n번째에 위치하는 자식 요소가 선택자 요소가 아닐 경우 선택하지 않습니다.

``` html
<style>
	div{ border: 3px solid #008000; padding:5px; }
	p:nth-child(2n) {
		color: red;
		font-weight: bold;
	}
</style>
...
<div>
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 세 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 네 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 다섯 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 여섯 번째 child 입니다!</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734526-ac540dc4-cde7-4818-9aa0-bf3200df4f7a.png)

``` html
<style>
	div.first{ border: 3px solid #008000; }
	div.second{ border: 3px solid #FFD700; }
	p:nth-child(2n) {
		color: red;
		font-weight: bold;
	}
</style>
...
<div class="first">
	<p>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 두 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 두 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 세 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 세 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 네 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 네 번째로 등장하는 div 태그입니다!</div>
</div>
```

div의 자식 요소 중 2의 배수 번째에 등장하는 요소가 div이고 p가 아니기 때문에 `p:nth-child(2n)`으로 아무것도 선택되지 않았습니다.

![image](https://user-images.githubusercontent.com/43658658/127734895-08e432a2-8be3-4ba1-95df-58b5422f0c07.png)

> <h3>:nth-last-child</h3>

(선택자):nth-last-child는 어떤 요소의 모든 자식(child) 요소 중에서 뒤에서부터 n번째에 위치하는 선택자 요소를 모두 선택합니다.

``` html
<style>
	div { border: 3px solid #008000; padding:5px; }
	p:nth-last-child(3n) { color: red; font-weight:bold; }
</style>
...
<div>
<p>이 p 태그는 div 태그의 뒤에서 여섯 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 뒤에서 다섯 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 뒤에서 네 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 뒤에서 세 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 뒤에서 두번 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 뒤에서 첫 번째 child 입니다!</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734577-3df0d196-0a20-48c8-a06c-0116087dfcfd.png)

> <h3>:first-of-type</h3>

(선택자):first-of-type는 어떤 요소의 선택자 자식(child) 요소 중에서 맨 처음으로 등장하는 선택자의 요소를 모두 선택합니다.

``` html
<style>
	div.first { border:3px solid #008000; margin:5px; padding:5px; }
	div.second { border:3px solid #FFD700; margin:5px; padding:5px; }
	p:first-of-type { color:red; font-weight:bold; }
</style>
...
<div class="first">
	<p>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<div class="second">
		<p>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</p>
		<p>이 p 태그는 div 태그의 child 입니다!</p>
		<p>이 p 태그는 div 태그의 child 입니다!</p>
	</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734730-02a10816-03b8-4109-8e8c-ebfca85f9755.png)

``` html
<div class="first">
	<div>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
<div class="second">
	<p>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
	<p>이 p 태그는 div 태그의 child 입니다!</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734946-f3fbf8d8-f465-4e18-8a9a-237f63958d76.png)

> <h3>:last-of-type</h3>

(선택자):last-of-type는 어떤 요소의 선택자 자식 요소 중에서 맨 마지막으로 등장하는 선택자의 요소를 모두 선택합니다.

``` html
<style>
	div.first { border:3px solid #008000; margin:5px; padding:5px; }
	div.second { border:3px solid #FFD700; margin:5px; padding:5px; }
	p:last-of-type { color:red; font-weight:bold; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127734782-7838c09f-2e67-44a2-8671-201010eafa88.png)

> <h3>:nth-of-type</h3>

(선택자):nth-of-type는 어떤 요소의 선택자 자식(child) 요소 중에서 n번째로 등장하는 선택자의 요소를 모두 선택합니다.

``` html
<style>
	div.first{ border: 3px solid #008000; }
	div.second{ border: 3px solid #FFD700; }
	p:nth-of-type(2n) {
		color: red;
		font-weight: bold;
	}
</style>
...
<div class="first">
	<p>이 p 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 첫 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 두 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 두 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 세 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 세 번째로 등장하는 div 태그입니다!</div>
	<p>이 p 태그는 div 태그의 child 요소 중에서 네 번째로 등장하는 p 태그입니다!</p>
	<div>이 div 태그는 div 태그의 child 요소 중에서 네 번째로 등장하는 div 태그입니다!</div>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734814-2a21c496-63b3-45b1-8315-bd45744baeb6.png)

> <h3>:nth-last-of-type</h3>

(선택자):nth-last-of-type는 어떤 요소의 선택자 자식(child) 요소 중에서 뒤에서부터 n번째로 등장하는 선택자의 요소를 모두 선택합니다.

> <h3>:only-child</h3>

(선택자):only-child는 어떤 요소의 자식 요소 중 선택자에 해당되는 자식 요소 단 하나만 가지고 있을 경우 선택자 자식 요소를 선택합니다.

``` html
<style>
	div{ border: 3px solid #008000; }
	p:only-child {
		color: red;
		font-weight: bold;
	}
</style>
...
<div>
	<p>이 p 태그는 div 태그의 유일한 child 입니다!</p>
</div>
<div>
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
</div>
<div>
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 세 번째 child 입니다!</p>
</div>
<div>
	<p>이 p 태그는 div 태그의 유일한 child 입니다!</p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127734999-c28f97a7-2c8b-407e-8f01-a12fcd4f088a.png)

> <h3>:only-of-type</h3>

(선택자):only-of-type는 어떤 요소의 모든 자식 요소들 중 선택자에 해당되는 자식 요소를 하나만 가지고 있다면 그 선택자 자식 요소를 선택합니다.

``` html
<style>
	div{ border: 3px solid #008000; }
	p:only-of-type {
		color: red;
		font-weight: bold;
	}
</style>
...
<div>
	<div>div 요소 추가</div>
	<p>이 p 태그는 div 태그의 유일한 child 입니다!</p>
</div>
<div>
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
</div>
<div>
	<p>이 p 태그는 div 태그의 첫 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
	<p>이 p 태그는 div 태그의 세 번째 child 입니다!</p>
</div>
<div>
	<span>이 span 태그는 div 태그의 유일한 child 입니다!</span>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127735035-606b9675-26d9-47ae-810f-2aee22fe6430.png)

> <h3>:empty</h3>

(선택자):empty는 선택자에 해당되는 자식(child) 요소 중 값을 가지지 않은 요소를 모두 선택합니다.

``` html
<style>
	div{ border: 3px solid #008000; }
	p:empty { 
		width: 300px;
		height: 20px;
		background: red; 
	}
</style>
...
<div>
	<p></p>
	<p>이 p 태그는 div 태그의 두 번째 child 입니다!</p>
	<p></p>
	<p>이 p 태그는 div 태그의 네 번째 child 입니다!</p>
	<p></p>
</div>
```

![image](https://user-images.githubusercontent.com/43658658/127735071-b707ce41-2e7e-40d4-8b44-47b8156ad742.png)

> <h3>:root</h3>

:root는 해당 문서의 root 요소를 선택합니다.

HTML 문서에서 root 요소는 언제나 html 요소입니다.

``` html
<style>
    :root { background: red; }
</style>
...
<h1>:root를 이용한 선택</h1>
```

![image](https://user-images.githubusercontent.com/43658658/127735127-ec2764d2-7b33-4714-b3ec-6177c6a36027.png)

## 의사 요소(pseudo-element)

의사 요소(pseudo-element)는 해당 HTML 요소의 특정 부분만을 선택할 때 사용합니다.

CSS1과 CSS2에서는 의사 클래스와 의사 요소를 나타낼 때 하나의 콜론(:)으로 함께 표기하였습니다.

하지만 CSS3에서는 의사 클래스의 표현과 의사 요소의 표현을 구분하기로 합니다.

따라서 CSS3에서는 `의사 클래스`는 하나의 콜론(`:`)을, `의사 요소`에는 두 개의 콜론(`::`)을 사용하고 있습니다.

> <h3>대표적인 CSS 의사 요소</h3>

CSS에서 자주 사용하는 대표적인 의사 요소는 다음과 같습니다.

 

- ::first-letter
- ::first-line
- ::before
- ::after
- ::selection

> <h3>::first-letter</h3>

이 의사 요소(pseudo-element)는 텍스트의 첫 글자만을 선택합니다.

단, 블록(block) 타입의 요소에만 사용할 수 있습니다.

이 의사 요소를 통해 사용할 수 있는 속성은 다음과 같습니다.

 

- font 속성
- color 속성 
- background 속성
- margin 속성
- padding 속성
- border 속성
- text-decoration 속성
- text-transform 속성
- line-height 속성
- float 속성
- clear 속성
- vertical-align 속성 (단, float 속성값이 none일 경우에만)

``` html
<style>
	p::first-letter {
		color: #FF4500;
		font-size: 2em;
	}
</style>
...
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent at tellus et neque luctus tincidunt at vitae ligula. Donec a accumsan magna. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed dolor nunc, facilisis in felis efficitur, sodales maximus nunc. Integer congue lectus vitae velit aliquam vehicula. Nunc mauris massa, sodales vitae augue ut, pulvinar mollis erat. Sed feugiat, mauris vitae convallis iaculis, nibh magna pretium diam, a sagittis quam urna quis augue. Nam feugiat accumsan ante id porttitor. Morbi tempus accumsan sem vitae venenatis. Duis mattis consequat ipsum nec interdum. Curabitur placerat vulputate faucibus. Cras consectetur elit ut metus consectetur tristique.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127735753-8d125ce5-d213-431f-9da3-5589aed2fc7e.png)

> <h3>::first-line</h3>

이 의사 요소는 텍스트의 첫 라인만을 선택합니다.

단, 블록(block) 타입의 요소에만 사용할 수 있습니다.

 

이 의사 요소를 통해 사용할 수 있는 속성은 다음과 같습니다.

 

- font 속성
- color 속성 
- background 속성
- word-spacing 속성
- letter-spacing 속성
- text-decoration 속성
- text-transform 속성
- line-height 속성
- clear 속성
- vertical-align 속성

``` html
<style>
	p::first-line {
		color: #FF4500;
		font-size: 2em;
	}
</style>
...
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent at tellus et neque luctus tincidunt at vitae ligula. Donec a accumsan magna. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed dolor nunc, facilisis in felis efficitur, sodales maximus nunc. Integer congue lectus vitae velit aliquam vehicula. Nunc mauris massa, sodales vitae augue ut, pulvinar mollis erat. Sed feugiat, mauris vitae convallis iaculis, nibh magna pretium diam, a sagittis quam urna quis augue. Nam feugiat accumsan ante id porttitor. Morbi tempus accumsan sem vitae venenatis. Duis mattis consequat ipsum nec interdum. Curabitur placerat vulputate faucibus. Cras consectetur elit ut metus consectetur tristique.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127735771-c1dba70f-b5d0-4daf-ad5f-c8ba7a38015a.png)

> <h3>::before</h3>

이 의사 요소는 특정 요소의 내용(content) 부분 바로 앞에 다른 요소를 삽입할 때 사용합니다.

``` html
<style>
	p::before { content: url("/examples/images/img_penguin.png"); }
</style>
...
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent at tellus et neque luctus tincidunt at vitae ligula. Donec a accumsan magna. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Sed dolor nunc, facilisis in felis efficitur, sodales maximus nunc. Integer congue lectus vitae velit aliquam vehicula. Nunc mauris massa, sodales vitae augue ut, pulvinar mollis erat. Sed feugiat, mauris vitae convallis iaculis, nibh magna pretium diam, a sagittis quam urna quis augue. Nam feugiat accumsan ante id porttitor. Morbi tempus accumsan sem vitae venenatis. Duis mattis consequat ipsum nec interdum. Curabitur placerat vulputate faucibus. Cras consectetur elit ut metus consectetur tristique.</p>
```

> <h3>::after</h3>

이 의사 요소는 특정 요소의 내용(content) 부분 바로 뒤에 다른 요소를 삽입할 때 사용합니다.

``` html
<style>
	p::after { content: url("/examples/images/img_penguin.png"); }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127735814-298d26c8-bdae-4309-9eff-aebafac9845b.png)

> <h3>::selection</h3>

이 의사 요소는 해당 요소에서 사용자가 선택한 부분만을 선택할 때 사용합니다.

``` html
<style>
	p::selection {
		color: #FF4500;

	}
</style>
```

마우스를 통해 본문을 드래그하면 글씨색이 변하는 것을 볼 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127735838-839f73bb-5ced-4714-b825-d4353b08aa56.png)

> <h3>의사 요소의 동시 적용</h3>

하나의 HTML 요소에 여러 개의 의사 요소를 동시에 적용할 수 있습니다.

``` html
<style>
	p::first-letter {
		color: #FFD700;
		font-size: 2em;
		font-weight: bold;
	}
	p::first-line { color: #FF4500; }
</style>
```

![image](https://user-images.githubusercontent.com/43658658/127735870-82716f4e-de1e-448d-abdc-3b48d891a69b.png)

## 속성 선택자(attribute selectors)

속성 선택자를 사용하면 특정 속성이나 특정 속성값을 가지고 있는 HTML 요소를 선택할 수 있습니다.

> <h3>기본 속성 선택자</h3>

CSS에서 사용할 수 있는 기본 속성 선택자는 다음과 같습니다.

 

- [속성이름] 선택자

- [속성이름="속성값"] 선택자

> <h3>[속성이름] 선택자</h3>

[속성이름] 선택자는 특정 속성을 가지고 있는 요소를 모두 선택합니다.

``` html
<style>
	[title] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성을 가지고 있습니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="first p">이 단락은 title 속성을 가지고 있습니다!</p>
<p title="second p">이 단락은 title 속성을 가지고 있습니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127735920-fd7d0032-f83c-4817-bfff-d2d6418a3533.png)

> <h3>[속성이름="속성값"] 선택자</h3>

[속성이름="속성값"] 선택자는 특정 속성을 가지고 있으며, 해당 속성의 속성값까지 일치하는 요소를 모두 선택합니다.

``` html
<style>
	[title="first h2"] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="first p">이 단락은 title 속성값이 "first p"입니다!</p>
<p title="second p">이 단락은 title 속성값이 "second p"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127735941-301320e4-d95d-4aee-9c76-2aaf133543a5.png)

> <h3>문자열 속성 선택자</h3>

CSS에서는 기본 속성 선택자 이외에도 문자열 속성 선택자를 제공합니다.

문자열 속성 선택자는 HTML 요소가 가지고 있는 특정 속성의 속성값 내에 특정 문자열을 확인하여 선택해 줍니다.

CSS에서 사용할 수 있는 문자열 속성 선택자는 다음과 같습니다.


- [속성이름~="속성값"] 선택자

- [속성이름|="속성값"] 선택자

- [속성이름^="속성값"] 선택자

- [속성이름$="속성값"] 선택자

- [속성이름*="속성값"] 선택자

익스플로러 8과 그 이전 버전에서는 HTML 문서에 `<!DOCTYPE html>`태그가 삽입되어 있어야만 문자열 속성 선택자를 제대로 인식합니다.

> <h3>[속성이름~="속성값"] 선택자</h3>

[속성이름~="속성값"] 선택자는 특정 속성의 속성값에 특정 문자열로 이루어진 하나의 단어를 포함하는 요소를 모두 선택합니다.

[속성이름~="속성값"] 선택자는 띄어쓰기(whitespace)를 기준으로 단어를 인식합니다.

따라서 예제처럼 하이픈(-)으로 연결된 단어는 전부 하나의 단어로 인식하며, 각각 별도의 단어로 인식하지 않습니다.

``` html
<style>
	[title~="first"] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="first p">이 단락은 title 속성값이 "first p"입니다!</p>
<p title="first-p">이 단락은 title 속성값이 "first-p"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736117-b8b2ecc7-b8b5-46a0-b2c7-b0f50e7457fa.png)

> <h3>[속성이름|="속성값"] 선택자</h3>

[속성이름|="속성값"] 선택자는 특정 속성의 속성값이 특정 문자열로 이루어진 하나의 단어로 시작하는 요소를 모두 선택합니다.

[속성이름|="속성값"] 선택자는 title 속성값이 정확히 "first"인 요소나 "first" 바로 다음에 하이픈(-)으로 시작하는 요소만을 선택합니다.

``` html
<style>
	[title|="first"] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="first p">이 단락은 title 속성값이 "first p"입니다!</p>
<p title="first-p">이 단락은 title 속성값이 "first-p"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736181-c9219efa-084b-42cb-a05d-3e18dd7766e0.png)

> <h3>[속성이름^="속성값"] 선택자</h3>

[속성이름^="속성값"] 선택자는 특정 속성의 속성값이 특정 문자열로 시작하는 요소를 모두 선택합니다.

이 선택자는 [속성이름|="속성값"] 선택자와는 달리 속성값이 특정 문자열로 시작하면 모두 선택해 줍니다.

따라서 위의 예제에서는 title 속성값이 "first"로 시작되는 요소가 모두 선택됩니다.

``` html
<style>
	[title^="first"] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="first p">이 단락은 title 속성값이 "first p"입니다!</p>
<p title="first-p">이 단락은 title 속성값이 "first-p"입니다!</p>
<p title="p first">이 단락은 title 속성값이 "p first"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736209-056b0750-c82e-4380-ac89-2a1fef510d0a.png)

> <h3>[속성이름$="속성값"] 선택자</h3>

[속성이름$="속성값"] 선택자는 특정 속성의 속성값이 특정 문자열로 끝나는 요소를 모두 선택합니다.

이 선택자는 특정 속성의 속성값이 특정 문자열로 끝나기만 하면 모두 선택해 줍니다.

``` html
<style>
	[title$="first"] {
		background: black;
		color: yellow;
	}
</style>
...
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="p first">이 단락은 title 속성값이 "p first"입니다!</p>
<p title="p-first">이 단락은 title 속성값이 "p-first"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736240-0f9e884d-e7f3-404e-b463-68dad8da8d42.png)

> <h3>[속성이름*="속성값"] 선택자</h3>

[속성이름*="속성값"] 선택자는 특정 속성의 속성값에 특정 문자열를 포함하는 요소를 모두 선택합니다.

이 선택자는 특정 속성의 속성값이 특정 문자열를 포함하기만 하면 모두 선택해 줍니다.

(-)이 붙었다고 해서 한 문자로 인식하지 않습니다. ('~'와의 차이점입니다)

``` html
<style>
	[title*="first"] {
		background: black;
		color: yellow;
	}
</style>
...
<h1>[속성*="속성값"] 선택자를 이용한 선택</h1>
<h2 title="first h2">이 제목은 title 속성값이 "first h2"입니다!</h2>
<h3>이 제목은 title 속성을 가지고 있지 않습니다!</h3>
<p title="my-first-p">이 단락은 title 속성값이 "my-first-p"입니다!</p>
<p title="p-first">이 단락은 title 속성값이 "p-first"입니다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736336-b0421f8b-04bc-46ab-9007-1da55cf5a1ad.png)

``` html
<style>
	input[type="text"] {
		width: 150px;
		display: block;
		background-color: #FFEFD5;
		margin-bottom: 10px;
	}
	input[type="password"] {
		width: 130px;
		display: block;
		background-color: #90EE90;
		border: 2px solid red;
	}
	input[type="password"]:focus { background-color: #FFC0CB; }
</style>
...
<form>
	사용자 : <br>
	<input type="text" name="username">
	비밀번호 : <br>
	<input type="password" name="password">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127736381-2ba20b1f-0871-4383-bb96-3e48389fa97d.png)

## 기타 의사 클래스

> <h3>:not</h3>

:not 선택자는 모든 선택자와 함께 사용할 수 있으며, 해당 선택자를 반대로 적용하여 선택합니다.

``` html
<style>
	span { margin-left: 5px; }
	input { color: #FFEFD5; }
	input:not([type="password"]) { background-color: #CD853F; }
</style>
...
<form>
	사용자 : <br>
	<input type="text" name="username"><br>
	비밀번호 : <br>
	<input type="password" name="password"><br>
	주소 : <br>
	<input type="text" name="address">
</form>
```

위의 예제에서 `input:not([type="password"])`는 password 타입을 제외한 나머지 타입의 input들에게 CSS를 적용한다는 뜻입니다.

![image](https://user-images.githubusercontent.com/43658658/127736439-25db0880-65e8-4ece-9be1-375e033837ba.png)

> <h3>:lang</h3>

:lang 선택자는 특정 HTML 요소를 사용자 컴퓨터의 언어 설정에 따라 다르게 표현할 때 사용합니다.

예를 들면, 영어에서는 인용의 표현으로 따옴표("")를 사용하나, 프랑스어에서는 부등호(<>)를 사용합니다.

이렇게 언어에 따라 달라지는 태그의 모양을 사용자 컴퓨터의 언어 설정에 따라 다르게 표현할 수 있게 해줍니다.

`:lang(언어의 약자)` 로 선택자를 선언합니다.

``` html
<style>
	q { font-weight: bold; }
	:lang(en) { quotes: '"' '"'  "'"  "'"; }
	:lang(fr) { quotes: "<<" ">>" "<" ">"; }
</style>
...
<p>영어에서는 <q lang="en">인용의 표현</q>을 이렇게 사용합니다.</p>
<p>프랑스어에서는 <q lang="fr">인용의 표현</q>을 이렇게 사용합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127736560-cf154921-19b1-429e-8365-c62de75a3f24.png)

