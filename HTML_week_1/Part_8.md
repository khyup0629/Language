# Part 8. HTML5 의미 요소

+ [의미 요소(semantic element)](#의미-요소semantic-element)
+ [Input 요소](#Input-요소)
+ [input 요소의 타입](#input-요소의-타입)
+ 

## 의미 요소(semantic element)

의미 요소(semantic element)란 그 자체로 의미를 가지고 있는 요소를 가리킵니다.

즉, 요소가 자기 스스로 브라우저와 개발자 모두에게 자신이 사용된 의미를 명확히 전달해 주는 요소를 의미합니다.
 
의미 요소가 아닌 div 요소나 span 요소 등은 해당 요소가 무슨 목적으로 사용되었는지 코드를 살펴봐야 알 수 있습니다.

하지만 의미 요소인 table 요소는 코드를 보지 않아도 해당 요소가 표를 만드는 데 사용되었다는 것을 이름만 살펴봐도 바로 알 수 있습니다.

> <h3>HTML5에서 추가된 의미 요소</h3>

HTML5에서 새롭게 추가된 대표적인 의미 요소는 다음과 같습니다.

1. header 요소
2. nav 요소
3. main 요소
4. section 요소
5. article 요소
6. figure와 figcaption 요소
7. footer 요소

![image](https://user-images.githubusercontent.com/43658658/126896055-1e27f410-59d3-47be-81fb-845340672cf8.png)

> <h3>header 요소</h3>

header 요소는 HTML 문서나 섹션(section) 부분에 대한 헤더(header)를 정의합니다.

헤더(header)란 도입부에 해당하는 콘텐츠(content)를 가지고 있는 부분을 의미합니다.

또한, 한 문서 내에 여러 개의 header 요소가 존재할 수 있습니다.

``` html
<header>
  <h1>전체 문서에 대한 헤더(header)입니다.</h1>
</header>
<section>
  <header>
    <h2>섹션 부분에 대한 헤더(header)입니다.</h2>
    <p>헤더 부분에 들어간 단락입니다.</p>
  </header>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed iaculis sapien ut felis lacinia eleifend. Aliquam est lectus, iaculis ultrices fringilla et, sollicitudin nec risus. In pretium metus in risus elementum, sit amet lobortis velit vulputate. Sed non ipsum suscipit, condimentum augue eu, cursus lacus. Nulla mattis metus et sapien consequat euismod. Nunc luctus nibh at dapibus rhoncus. In hac habitasse platea dictumst.</p>
</section>
```

![image](https://user-images.githubusercontent.com/43658658/126896228-29b50f3b-e11c-417b-9614-b1fe5bde5ebe.png)

> <h3>nav 요소</h3>

nav 요소는 HTML 문서 사이를 탐색할 수 있는 링크(link)의 집합을 정의합니다.

nav 요소는 링크의 커다란 집합을 의미하지만, 문서 내의 모든 링크가 nav 요소에 포함되는 것은 아닙니다.

``` html
<nav>
    <a href="/html/html5_element_semantic">의미 요소</a> | 
    <a href="/html/html5_element_form">Forms 요소</a> | 
    <a href="/html/html5_element_inputtype">Input 요소</a>
</nav>

<p>문서 내의 링크가 모두 nav 요소에 포함되는 것은 아니에요!</p>
<p>이 링크는 nav 요소에 포함되지 않는 <a href="/html/html5_element_inputattr">Input 요소의 속성</a>에 관한 링크에요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/126896323-3705715b-03ec-4792-abe6-55c7743fc220.png)

> <h3>section 요소</h3>

section 요소는 HTML 문서에서 섹션(section) 부분을 정의합니다.

섹션(section)이란 제목을 가지고 있으며, HTML 문서의 전체적인 내용과 관련이 있는 콘텐츠들의 집합을 의미합니다.

``` html
<section>
  <h2>섹션(section) 영역입니다.</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed iaculis sapien ut felis lacinia eleifend. Aliquam est lectus, iaculis ultrices fringilla et, sollicitudin nec risus. In pretium metus in risus elementum, sit amet lobortis velit vulputate. Sed non ipsum suscipit, condimentum augue eu, cursus lacus. Nulla mattis metus et sapien consequat euismod. Nunc luctus nibh at dapibus rhoncus. In hac habitasse platea dictumst.
  </p>
</section>

<section>
  <h2>또 다른 섹션(section) 영역입니다.</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed iaculis sapien ut felis lacinia eleifend. Aliquam est lectus, iaculis ultrices fringilla et, sollicitudin nec risus. In pretium metus in risus elementum, sit amet lobortis velit vulputate. Sed non ipsum suscipit, condimentum augue eu, cursus lacus. Nulla mattis metus et sapien consequat euismod. Nunc luctus nibh at dapibus rhoncus. In hac habitasse platea dictumst.
  </p>
</section>
```

![image](https://user-images.githubusercontent.com/43658658/126896365-46b3bd6b-28ff-46c1-868a-f9b497d1749f.png)

> <h3>article 요소</h3>

article 요소는 HTML 문서에서 독립적인 하나의 기사(article) 부분을 정의합니다.

article 요소의 내용은 그 자체만으로도 이해가 되어야 하며, 웹 사이트의 나머지 부분과는 별도로 읽을 수 있어야 합니다.

``` html
<article>
  <h2>기사(article) 영역입니다.</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed iaculis sapien ut felis lacinia eleifend. Aliquam est lectus, iaculis ultrices fringilla et, sollicitudin nec risus. In pretium metus in risus elementum, sit amet lobortis velit vulputate. Sed non ipsum suscipit, condimentum augue eu, cursus lacus. Nulla mattis metus et sapien consequat euismod. Nunc luctus nibh at dapibus rhoncus. In hac habitasse platea dictumst.
  </p>
</article>

<article>
  <h2>또 다른 기사(article) 영역입니다.</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed iaculis sapien ut felis lacinia eleifend. Aliquam est lectus, iaculis ultrices fringilla et, sollicitudin nec risus. In pretium metus in risus elementum, sit amet lobortis velit vulputate. Sed non ipsum suscipit, condimentum augue eu, cursus lacus. Nulla mattis metus et sapien consequat euismod. Nunc luctus nibh at dapibus rhoncus. In hac habitasse platea dictumst.
  </p>
</article>
```

![image](https://user-images.githubusercontent.com/43658658/126896391-871ccc4c-b118-452e-8238-d2c917e23801.png)

위의 두 예제를 살펴보면 section 요소와 article 요소 간의 별다른 차이점을 발견할 수 없을 것입니다.

실제로도 두 요소 간의 쓰임에 있어 큰 차이를 보이지는 않습니다.

대체로 ***section 요소***는 HTML **문서의 전체적인 내용**에 포함되며, ***article 요소***는 문서의 전체적인 내용과는 **별도의 독립적인 내용**이 들어갈 때 사용하면 됩니다.

> <h3>figure 요소와 figcaption 요소</h3>

책이나 신문 등에 포함되는 이미지 바로 아래에는 해당 이미지를 설명하는 캡션(caption)이 위치하게 됩니다.

HTML5에서는 위와 같은 목적을 위해 figure 요소와 figcaption 요소를 제공하고 있습니다. 

***figure 요소***는 **HTML 문서에서 그래픽과 비디오 등의 독립적인 콘텐츠(content)를 정의**할 때 사용합니다.

figcaption 요소는 위와 같은 figure 요소를 위한 캡션을 정의할 때 사용합니다.

``` html
<h1>figure 요소와 figcaption 요소</h1>
<figure>
  <img src="/examples/images/img_flower.png" alt="flower" width="350" height="263" />
  <figcaption>[ 그림 1. 위의 그림은 예쁜 꽃이네요! ]</figcaption>
</figure>
```

![image](https://user-images.githubusercontent.com/43658658/126896495-03f593b6-ab87-4377-8d62-5286739feaa7.png)

> <h3>footer 요소</h3>

footer 요소는 HTML 문서나 섹션(section) 부분에 대한 푸터(footer)을 정의합니다.

HTML 문서의 푸터(footer)에는 일반적으로 사이트의 작성자나 그에 따른 저작권 정보, 연락처 등을 명시합니다.

또한, 한 문서 내에 여러 개의 footer 요소가 존재할 수 있습니다.

``` html
<footer>
  <p>전체 문서에 대한 푸터(footer)입니다.</p>
  <p>Copyright 2016. 지은이 all rights reserved.</p>
  <p>연락처 : 02-1234-5678</p>
</footer>
```

![image](https://user-images.githubusercontent.com/43658658/126896545-0843cfda-f8a2-4598-8776-6687c0178a72.png)

> <h3>details와 summary</h3>

***details 요소***는 사용자가 보거나 숨길 수 있는 추가적인 설명문을 정의합니다.

***summary 태그***를 details 요소 내에 작성하여 내용을 숨겼을 때 나타날 내용을 정의할 수 있습니다.

``` html
<details>
    <summary>화살표를 누르면 세부정보가 보여요!</summary>
    <p>이젠 보이지?</p>
</details>
```

![image](https://user-images.githubusercontent.com/43658658/126896680-6315e8f4-271c-4696-b4c0-9e0bf7080229.png)

> <h3>mark 요소</h3>

mark 요소를 이용해 형광펜을 칠한 것 같은 효과를 줄 수 있습니다.

``` html
<p>문장에 형광펜을 치고 싶다면 <mark style="background-color:lightyellow">&lt;mark&gt; 요소</mark>를 이용합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126896769-3aad6103-eb33-4279-a733-7bc058139b59.png)

> <h3>dialog 요소</h3>

dialog 요소는 대화박스나 대화창 같은 효과로 나타낼 수 있습니다.

``` html
<h1>The dialog element</h1>

<p>This is some text.</p>

<p>This is some text.</p>

<dialog open style="border:2px solid blue">This is an open <b>dialog window</b></dialog>

<p>This is some text.</p>

<p>This is some text.</p>

<p><b>Note:</b> The dialog tag is not supported in Safari and Edge (prior version 79).</p>
```

![image](https://user-images.githubusercontent.com/43658658/126896867-796566e3-d19f-47bc-971f-2fbd36b162b0.png)

> <h3>bdi 요소</h3>

bdi 요소는 아랍어와 같이 한국어나 영어와 출력 알고리즘이 다를 경우 올바르게 출력되게 하기 위해 사용합니다.

``` html
<ul>
 <li>User hrefs: 60 points</li>
 <li>User <bdi>jdoe</bdi>: 80 points</li>
 <li>User <bdi>إيان</bdi>: 90 points</li>
</ul>
```

![image](https://user-images.githubusercontent.com/43658658/126897050-aaf150b2-388c-434c-8bb3-b38ac19fffe0.png)

위에서 아랍어에 `<bdi>` 요소를 씌우지 않는다면 `<li>User <bdi>إيان<: 90 points</li>` 자동으로 이런식으로 이상하게 변합니다.

> <h3>meter 요소</h3>

meter 요소는 게이지를 나타낼 때 이용합니다.

``` html
<label>디스크 사용량 C:</label>
<meter value="2" min="0" max="10"></meter><br>
<label>디스크 사용량 D:</label>
<meter value="0.6"></meter>
```

![image](https://user-images.githubusercontent.com/43658658/126897308-a199ba3a-62b0-482d-bc0f-fe20c27d43e6.png)

> <h3>menuitem 요소</h3>

우클릭을 했을 때 나타나는 팝업창의 요소들을 정의할 수 있습니다.

하지만 현재는 Firefox 브라우저에서만 지원됩니다.

> <h3>progress 요소</h3>

meter 요소와 마찬가지로 게이지를 나타낼 때 이용합니다.

``` html
<label for="file">Downloading progress:</label>
<progress id="file" value="32" max="100"> 32% </progress>
```

![image](https://user-images.githubusercontent.com/43658658/126897459-fff3febe-f3a7-44af-ab87-9fe0440c7bd3.png)

> <h3>ruby 요소</h3>

ruby 문자를 쓰기 위한 요소입니다.

ruby 문자란 일반적인 문자 위에 작게 올라가는 문자를 의미합니다.

본문을 먼저 쓰고 `<rt>` 태그를 이용해 본문 위에 올라갈 루비 문자를 쓸 수 있습니다.

``` html
<ruby>
 루비다. <rt> 이 글자가 </rt>
</ruby>
```

![image](https://user-images.githubusercontent.com/43658658/126897573-514b5dd8-d1f3-4df9-a5cb-db2cbf45dbf9.png)

> <h3>wbr 요소</h3>

wbr 요소는 페이지 창을 확대하거나 축소했을 때 상황에 따라 한 줄을 띄울 곳을 미리 지정하는 용도로 이용합니다.

``` html
<p>This is a veryveryveryveryveryveryveryveryveryveryveryveryveryveryveryveryveryvery<wbr>longwordthatwillbreakatspecific<wbr>placeswhenthebrowserwindowisresized.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126897632-e9984471-06dd-4ec4-8587-5e02c34529e2.png)

페이지 창을 축소하면 아래와 같이 됩니다.

![image](https://user-images.githubusercontent.com/43658658/126897640-86f26964-5ec5-4187-989b-3784162bc532.png)

## Input 요소

> <h3>다양한 타입의 input 요소</h3>

HTML에서는 다양한 타입의 input 요소를 이용하여 사용자로부터 입력을 받을 수 있습니다.

대표적인 HTML input 요소는 다음과 같습니다.

1. 텍스트 입력
2. 비밀번호 입력
3. 라디오 버튼
4. 체크박스(check box)
5. 파일 선택 박스
6. 선택(select) 입력(drop-down 리스트)
7. 문장 입력
8. 버튼(button) 입력
9. 전송 버튼(submit)
10. 필드셋(fieldset)

HTML5에서 새롭게 추가된 다양한 타입의 input 요소는 다음과 같습니다.

1. datalist 요소
2. keygen 요소
3. output 요소

> <h3>datalist 요소</h3>

datalist 요소는 input 요소에 대해 미리 정의된 옵션 리스트를 명시해 주는 요소입니다.

사용자는 텍스트를 바로 입력해도 되고, 드롭다운 메뉴에서 미리 정의한 옵션 중의 하나를 골라도 됩니다.

단, input 요소의 **list 속성값**이 datalist 요소의 **id 속성값**과 **반드시 일치**해야 연결됩니다.

datalist 요소는 사파리, 익스플로러 9와 그 이전 버전에서 지원하지 않습니다.

``` html
<form action="/examples/media/request.php">
  <input list="lectures" name="lecture">
  <datalist id="lectures">
    <option value="HTML"></option>
    <option value="CSS"></option>
    <option value="Java"></option>
    <option value="C++"></option>
  </datalist>
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126898034-4cb2ca69-d479-4174-b370-82eda1abaeb6.png)

> <h3>keygen 요소</h3>

keygen 요소의 목적은 사용자가 인증할 수 있는 안전한 방법을 제공하는 것입니다.

keygen 요소는 사용자가 입력한 데이터를 암호화하여 서버로 전송합니다.

이때 생성된 키(key)를 가지고 서버는 해당 사용자의 인증을 수행합니다.

(keygen 요소는 익스플로러에서 지원하지 않습니다)

``` html
<h1>keygen 요소를 이용한 key 생성</h1>

<form action="/examples/media/request.php">
    사용자 : <br>
    <input type="text" name="username">
    암호화방법 : <br>
    <keygen name="security">
    <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126898131-2cb924e8-24f1-467b-a3aa-96b0da78f5e8.png)

"전송" 버튼을 누르면 username에 대한 정보가 keygen으로 암호화되어 전송됩니다.

암호화된 데이터는 해독되어 정상적인 데이터의 모습으로 출력됩니다.

![image](https://user-images.githubusercontent.com/43658658/126898159-cb69e2f9-2543-4d20-b3f2-d2c84b3a1086.png)

> <h3>output 요소</h3>

output 요소는 스크립트(script) 등으로 실행된 계산의 결과를 바로 표시해주는 요소입니다.

form 요소의 oninput 속성을 사용해서 output의 계산식을 적어줄 수 있습니다. output의name.value=...

***for 속성***을 사용하여 해당 결과에 영향을 줄 수 있는 HTML 문서 내의 요소를 명시할 수 있습니다.

이때 for 속성의 속성값에는 해당 요소의 id 속성값을 공백으로 나열해야 합니다.

(output 요소는 익스플로러에서 지원하지 않습니다)

``` html
<h1>output 요소를 이용한 계산 결과 표현</h1>
<form action="/examples/media/request.php" oninput="total.value=parseInt(value01.value)/parseInt(value02.value)">
  <input type="number" id="value01" value="20"> / ( 0 <input type="range" id="value02" value="50" min="0" max="100"> 100 ) = 
  <output name="total" for="value01 value02"></output>
  <br><br>
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126898430-55c0a6fa-6a4b-417e-aaaf-3c7b4acc3ded.png)

## input 요소의 타입

form 요소는 다양한 타입의 input 요소를 포함할 수 있습니다.

HTML에서 자주 사용되는 input 요소의 대표적인 타입은 다음과 같습니다.

1. text

2. password

3. submit

4. radio button

5. checkbox

6. button

HTML5에서 새롭게 추가된 input 요소의 타입은 다음과 같습니다.

1. 숫자 입력(number)

2. 입력 범위 지정(range)

3. 색상 입력(color)

4. 날짜 입력(date)

5. 시간 입력(time)

6. 날짜와 시간 입력(datetime-local)

7. 연도와 월 입력(month)

8. 연도와 주 입력(week)

9. 이메일 입력(email)

10. URL 주소 입력(url)

11. 전화번호 입력(tel)

12. 검색어 입력(search)

새롭게 추가된 `<input>`태그의 type 속성값은 익스플로러에서는 대부분 동작하지 않습니다.

> <h3>숫자 입력(number)</h3>

`<input>`태그의 type 속성값을 "number"로 설정하면, input 요소는 사용자가 숫자를 입력할 수 있도록 해줍니다.

number 타입이 일반 text 타입과 다른 점은 입력 필드 우측에 숫자의 크기를 조절할 수 있는 상하 버튼이 생기는 점입니다.

브라우저의 지원 여부에 따라 min 속성과 max 속성을 이용하여 숫자 선택에 제한값을 설정할 수도 있습니다.

``` html
<h1>number 타입을 이용한 숫자 입력</h1>

<p>여러분이 가장 좋아하는 숫자는 몇인가요?<br>
  (단, 1부터 9까지에서 골라주세요!)</p>

<form action="/examples/media/request.php">
  <input type="number" name="number" min="1" max="9">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126898867-ac4e4962-dbc0-43b8-ae48-e61b656885ad.png)

> <h3>입력 범위 지정(range)</h3>

`<input>`태그의 type 속성값을 "range"로 설정하면, input 요소는 사용자가 일정 범위 안의 값만을 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 값을 선택하기 위한 수평 조절바를 보여줍니다.

``` html
<form action="/examples/media/request.php">
    여러분이 가장 좋아하는 숫자는 몇인가요?<br>
    이번에는 수평바를 조절해서 골라주세요!<br>
    <br>
    <b>0</b> <input type="range" name="range" min="1" max="9"> <b>9</b>
    <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126898960-05be75c5-d8e5-4938-8130-73ddda2e60a0.png)

> <h3>색상 입력(color)</h3>

`<input>`태그의 type 속성값을 "color"로 설정하면, input 요소는 사용자가 색상을 입력할 수 있도록 해줍니다.

선택된 색상은 #을 제외한 6자리의 16진수 색상값으로 전송됩니다.

``` html
<form action="/examples/media/request.php">
      가장 좋아하는 색을 골라주세요 : <br>
      <br>
		<input type="color" name="color" value="#FFFFFF">
      <input type="submit" value="전송">
  </form>
```

![image](https://user-images.githubusercontent.com/43658658/126899731-5d1c5f52-9116-4c7c-bc53-f9f383558eb6.png)

> <h3>날짜 입력(date)</h3>

`<input>`태그의 type 속성값을 "date"로 설정하면, input 요소는 사용자가 날짜를 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 날짜를 선택하기 위한 캘린더를 보여줍니다.

또한, min과 max 속성을 사용하여 날짜 선택에 제한값을 설정할 수도 있습니다.

``` html
<h1>date 타입을 이용한 날짜 선택 제한</h1>
<form action="/examples/media/request.php">
  맘에 드는 날짜를 하나 골라주세요 :<br>
  (단, 1977년 1월 1일부터 2021년 12월 31일까지만 선택이 가능해요!)<br><br>
  <input type="date" name="theday" min="1977-01-01" max="2021-12-31">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126899868-eaafa7c9-5be6-4ff9-b82c-9e97c0e571ec.png)

> <h3>시간 입력(time)</h3>

`<input>`태그의 type 속성값을 "time"로 설정하면, input 요소는 사용자가 시간을 입력할 수 있도록 해줍니다.
 
브라우저 지원 여부에 따라 시간을 선택하기 위한 도구를 보여줍니다.

``` html
<h1>time 타입을 이용한 시간 선택</h1>
<form action="/examples/media/request.php">
  여러분이 태어난 시간은 몇 시인가요?<br><br>
  <input type="time" name="birthday">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126899917-c67a6d3d-c293-428d-88a6-573d606dd381.png)

> <h3>날짜와 시간 입력(datetime-local)</h3>

`<input>`태그의 type 속성값을 "datetime-local"로 설정하면, input 요소는 사용자가 날짜와 시간을 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 날짜를 선택하기 위한 캘린더와 시간을 선택하기 위한 도구를 보여줍니다.

``` html
<h1>datetime-local 타입을 이용한 날짜와 시간 선택</h1>
<form action="/examples/media/request.php">
  이 수업을 처음 들은 날을 골라주세요!<br>
  그렇다면 혹시 그 시간도 기억하시나요?<br>
  <br>
  <input type="datetime-local" name="firsttime">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900022-c611d8c8-0f87-4fb1-b270-63355fdfaf54.png)

> <h3>연도와 월 입력(month)</h3>

`<input>`태그의 type 속성값을 "month"로 설정하면, input 요소는 사용자가 연도와 월을 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 연도와 월을 선택하기 위한 캘린더를 보여줍니다.

``` html
<form action="/examples/media/request.php">
  여러분이 태어난 연월을 선택해 보세요!<br><br>
  <input type="month" name="birthmonth">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900074-78af9aa2-a3d3-46dd-8d0b-864d0d3b1300.png)

> <h3>연도와 주 입력(week)</h3>

`<input>`태그의 type 속성값을 "week"로 설정하면, input 요소는 사용자가 연도와 몇 번째 주인지를 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 연도와 주를 선택하기 위한 캘린더를 보여줍니다.

``` html
<h1>week 타입을 이용한 연도와 주 선택</h1>

<form action="/examples/media/request.php">
  오늘이 올해의 몇 번째 주인지 선택해주세요!<br>
  <br>
  <input type="week" name="week">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900178-e84893f1-6cea-41e2-a4cc-c7b1273d1661.png)

> <h3>이메일 입력(email)</h3>

`<input>`태그의 type 속성값을 "email"로 설정하면, input 요소는 사용자가 email 주소를 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 전송할 때 입력한 email 주소가 유효한 email 주소인지 자동으로 검사합니다.

올바른 이메일 주소를 입력하지 않으면 알림창이 뜹니다.

``` html
<form action="/examples/media/request.php">
  여러분의 이메일 주소를 입력해 주세요 :<br><br>
  <input type="email" name="email">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900222-58e47cd3-914f-4ab5-843c-7ec41f031398.png)

> <h3>URL 주소 입력(url)</h3>

`<input>`태그의 type 속성값을 "url"로 설정하면, input 요소는 사용자가 URL 주소를 입력할 수 있도록 해줍니다.

브라우저 지원 여부에 따라 전송할 때 입력한 URL 주소가 유효한 URL 주소인지 자동으로 검사합니다.

``` html
<form action="/examples/media/request.php">
  Naver의 URL 주소를 입력해 주세요 :<br><br>
  <input type="url" name="url">
  <input type="submit" value="전송"><br><br>
  ("http://"까지 모두 정확히 입력해야 전송할 수 있습니다.)
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900273-a74c1574-ccf6-48a8-a09f-ed5e356471e3.png)

> <h3>전화번호 입력(tel)</h3>

`<input>`태그의 type 속성값을 "tel"로 설정하면, input 요소는 사용자가 전화번호를 입력할 수 있도록 해줍니다.

(tel 타입은 사파리 8에서만 지원합니다)

``` html
<form action="/examples/media/request.php">
  여러분의 전화번호를 입력해 주세요 :<br><br>
  <input type="tel" name="tel">
  <input type="submit" value="전송">
</form>
```

> <h3>검색어 입력(search)</h3>

`<input>`태그의 type 속성값을 "search"로 설정하면, input 요소는 사용자가 검색어를 입력할 수 있도록 해줍니다.

이러한 검색 필드는 보통의 텍스트 필드(text field)와 동일하게 동작합니다.

search 타입이 일반 text 타입과 다른 점은 입력 필드에 검색어를 입력하면, 입력 필드 우측에 입력된 검색어를 바로 삭제할 수 있는 엑스(X) 표시가 생기는 점입니다.

``` html
<h1>search 타입을 이용한 검색어 입력</h1>
<form action="/examples/media/request.php">
  여러분이 평소에 가장 많이 찾아본 검색어를 입력해 주세요 : <br>
<br>
  <input type="search" name="search">
  <input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126900355-18240ee2-d2f7-46ce-8b71-35d479a783fd.png)

