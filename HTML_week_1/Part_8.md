# Part 8. HTML5 의미 요소

+ [의미 요소(semantic element)](#의미-요소semantic-element)
+ [Input 요소](#Input-요소)
+ [input 요소의 타입](#input-요소의-타입)
+ [Input 요소의 속성](#Input-요소의-속성)

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

## input 요소의 속성

input 요소는 다양한 속성을 가질 수 있습니다.

HTML에서 자주 사용되는 input 요소의 대표적인 속성은 다음과 같습니다.

1. value
2. readonly
3. disabled
4. maxlength
5. size

HTML5에서 새롭게 추가된 form 요소의 속성은 다음과 같습니다.

1. autocomplete
2. novalidate

HTML5에서 새롭게 추가된 input 요소의 속성은 다음과 같습니다.

1. autocomplete
2. autofocus
3. form
4. formaction
5. formenctype
6. formmethod
7. formnovalidate
8. formtarget
9. height and width
10. list
11. min and max
12. multiple
13. pattern
14. placeholder
15. required
16. step

> <h3>autocomplete 속성</h3>

autocomplete 속성은 form 요소나 input 요소에 입력된 정보를 저장할지 안 할지를 명시합니다.

이 속성의 속성값이 on으로 설정되면, 브라우저는 사용자가 입력하는 정보를 자동으로 저장합니다.

그리고 나서 이후에 입력되는 입력값을 저장된 정보를 바탕으로 자동 완성해 줍니다.

이 속성은 다음과 같은 input 타입에서만 사용할 수 있습니다.

- text, password, range, color, date, datetime-local, month, week, email, url, tel, search 타입

``` html
<h1>autocomplete 속성을 이용한 자동 완성</h1>

<form action="/examples/media/request.php" autocomplete="on">
	이름 : <input type="text" name="username"><br>
	나이 : <input type="number" name="age" min="1" max="99" autocomplete="off"> (1~99 사이 값을 입력하세요)<br>
	<br>
	input 요소에 데이터를 입력하고 전송 버튼을 누른 후에 F5키를 눌러 보세요!<br>
	그리고 나서 같은 정보를 입력하려고 하면 이전 데이터가 아래에 팝업될 거에요!<br>
	<br>
	<input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127072927-eac83eac-f445-4e72-8f39-a2f90a65e057.png)

> <h3>novalidate 속성</h3>

novalidate 속성은 input 요소의 속성이 아닌 form 요소의 속성입니다.

이 속성은 입력한 정보(data)를 전송할 때 **그 정보가 유효한지 아닌지를 검사하지 않았다는 것을 명시**합니다.

***url 타입***이나 ***email 타입***과 같이 **자동으로 유효성 검사를 하는 input 타입**에 이 속성을 사용하면 유효성 검사를 **하지 않습니다.**

즉, 이 속성이 사용된 form 요소로 전달받은 정보(data)는 **반드시 서버 측에서 따로 유효성 검사를 실시해야** 합니다.

(novalidate 속성은 사파리, 익스플로러 9와 그 이전 버전에서 지원하지 않습니다)

``` html
<h1>novalidate 속성을 이용한 유효성 검사 여부 명시</h1>

<form action="/examples/media/request.php">
	여러분이 자주 들리는 사이트의 URL 주소를 입력해 주세요 :<br><br>
	<input type="url" name="url">
	<input type="submit" value="전송"><br>
</form>

<p><br>novalidate 속성을 적용하면 클라이언트 측의 유효성 검사를 건너뛸 수 있습니다.</p>
<form action="/examples/media/request.php" novalidate>
	여러분이 자주 들리는 사이트의 URL 주소를 입력해 주세요 :<br><br>
	<input type="url" name="url">
	<input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127073222-f45c15ac-9700-420e-af62-79083d1077a1.png)

위의 경우 제대로된 URL을 입력하지 않았을 때 유효성 검사를 통해 URL을 입력하라는 알림이 뜨지만

아래의 경우 novalidate 속성을 활용해 유효성 검사를 하지 않고 데이터를 그대로 전송하는 모습을 볼 수 있습니다.

> <h3>autofocus 속성</h3>

autofocus 속성은 웹 페이지가 로드(load)될 때, 속성이 적용된 input 요소에 자동으로 포커스(focus)가 가도록 해줍니다.

(autofocus 속성은 익스플로러 9와 그 이전 버전에서 지원하지 않습니다)

``` html
<h1>autofocus 속성을 이용한 오토 포커싱</h1>

<form action="/examples/media/request.php">
	사용자 : <input type="text" name="username"><br>
	비밀번호 : <input type="password" name="password" autofocus><br><br>
	<input type="submit" value="전송">
</form>
<p>페이지 로드 시 자동으로 포커스가 비밀번호를 입력하는 input 요소에 가도록 합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127073683-50b49406-0dec-42fa-ab4a-acc83aa76e8c.png)

페이지를 로드하면 입력 커서가 자동으로 비밀번호를 입력하는 란에 있는 것을 볼 수 있습니다.

> <h3>form 속성</h3>

form 속성은 해당 input 요소의 위치에 상관없이 포함될 form 요소를 명시해 줍니다.

즉, input 요소가 코드 상으로 form 요소 내에 바깥에 있어도 form 요소 내에 포함되도록 할 수 있습니다.

먼저 form 요소의 id 속성값을 준 뒤, 해당 input 요소의 속성을 form으로 주고 속성값을 연결하고 싶은 form 요소의 id로 적어줍니다.

포함할 form 요소의 id 속성값을 공백으로 연결하여, 둘 이상의 form 요소에 포함할 수도 있습니다.

``` html
<h1>form 속성</h1>

<form action="/examples/media/request.php" id="user">
	사용자 : <input type="text" name="username"><br><br>
	<input type="submit" value="전송">
</form>
<br>
<form action="/examples/media/request.php" id="email">
이메일 : <input type="email" name="emailaddress"><br><br>
<input type="submit" value="전송">
</form>
<p>아래의 비밀번호를 입력하는 input 요소는 위치상으로는 form 요소에 포함되지 않습니다.<br>
하지만 form 속성을 이용하여 하나의 form으로 인식할 수 있습니다.
</p>
<!--여러 form 요소에 포함시키기 위해 공백으로 연결시켰습니다.-->
비밀번호 : <input type="password" name="password" form="user email"><br>
```

![image](https://user-images.githubusercontent.com/43658658/127074698-af644b79-b658-49c2-8329-f6e67a4ec289.png)

> <h3>formaction 속성</h3>

formaction 속성은 입력한 정보(data)를 전송할 때 정보가 전달될 서버 측 파일을 명시합니다.

즉, ***formaction 속성***은 **form 요소의 action 속성을 덮어쓰게 됩니다.**

이 속성을 사용하면 입력된 **정보를 넘겨줄 서버 측 파일을 input 요소에서 바꿀 수 있게** 됩니다.

이 속성은 ***submit 타입***과 ***image 타입***에서만 사용할 수 있습니다.

``` html
<form action="/examples/media/request.php">
	사용자 : <input type="text" name="username"><br>
	비밀번호 : <input type="password" name="password"><br><br>
	<input type="submit" value="전송">
	<input type="submit" value="관리자 권한으로 전송" formaction="/examples/media/request_admin.php"><br>
</form>
```

"전송" 버튼을 누르게 되면 "/examples/media/request.php" 파일로 보내집니다.

![image](https://user-images.githubusercontent.com/43658658/127075210-2354554e-6cd7-4426-bc8d-c3314209cd6a.png)

"관리자 권한으로 전송" 버튼을 누르면 "/examples/media/request_admin.php" 파일로 보내집니다.

![image](https://user-images.githubusercontent.com/43658658/127075236-1275a4ce-0c37-4d11-a2d8-3b9680efb217.png)

> <h3>formenctype 속성</h3>

formenctype 속성은 입력한 정보(data)를 전송할 때 암호화하는 방법을 명시합니다.

즉, formenctype 속성은 form 요소의 enctype 속성을 덮어쓰게 됩니다.

```
form 요소에는 enctype 이라는 속성이 쓰일 수 있습니다.
enctype은 아래의 3가지 속성값을 가질 수 있습니다.
application/x-www-form-urlencoded : 기본값으로, 모든 문자들은 서버로 보내기 전에 인코딩됨을 명시함.
multipart/form-data : 모든 문자를 인코딩하지 않음을 명시함. 이 방식은 <form> 요소가 파일이나 이미지를 서버로 전송할 때 주로 사용함.
text/plain : 공백 문자(space)는 "+" 기호로 변환하지만, 나머지 문자는 모두 인코딩되지 않음을 명시함.
```

단, formenctype 속성은 form 요소의 method 속성이 **post**일 때만 적용됩니다.

이 속성은 ***submit 타입***과 ***image 타입***에서만 사용할 수 있습니다.

``` html
<form action="/examples/media/request_enctype.php" method="post">
	사용자 이름을 입력해주세요 : <input type="text" name="username"><br><br>
	<input type="submit" value="암호화하여 전송" formenctype="multipart/form-data"><br>
</form>
```

"bllu"를 전송하면 아래와 같이 인코딩되어 전송됩니다.

![image](https://user-images.githubusercontent.com/43658658/127078911-bb6bf5be-30ed-4ec0-9c0f-aa019751b87f.png)

`<keygen>`의 경우 암호화되어 전송되지만 데이터를 받고 출력할 때는 디코딩되어 원래 정보를 출력한다는 것에 차이가 있습니다.

> <h3>formmethod 속성</h3>

formmethod 속성은 입력한 정보(data)를 전송할 때 사용하는 http 메소드(method)를 명시합니다.

즉, formmethod 속성은 form 요소의 method 속성을 덮어쓰게 됩니다.

이 속성은 submit 타입과 image 타입에서만 사용할 수 있습니다.

``` html
<form action="/examples/media/request.php" method="get">
	사용자 이름 : <input type="text" name="username" autocomplete="on"><br>
	<br>
	<input type="submit" value="post방식으로 전송" formmethod="post">
</form>
```

> <h3>formnovalidate 속성</h3>

formnovalidate 속성은 입력한 정보(data)를 전송할 때 그 정보가 유효한지 아닌지를 검사하지 않았다는 것을 명시합니다.

즉, formnovalidate 속성은 form 요소의 novalidate 속성을 덮어쓰게 됩니다.

이 속성은 오직 submit 타입에서만 사용할 수 있습니다.

``` html
<h1>formnovalidate 속성</h1>
<form action="/examples/media/request.php">
	여러분이 자주 들리는 사이트의 URL 주소를 입력해 주세요 : <input type="url" name="url"><br>
	<br>
	<input type="submit" value="전송">
	<input type="submit" value="novalidate 방식으로 전송" novalidate>
</form>
```

"khyup0629"를 입력했을 떄 "전송" 버튼을 누르면 유효성 검사를 하지만, "novalidate 방식으로 전송" 버튼을 누르면 데이터가 보내지는 것을 확인할 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127103726-3196730b-0e07-4ed7-9e1d-4ecab0be669a.png)

> <h3>formtarget 속성</h3>

formtarget 속성은 입력한 정보(data)를 전송한 후, 그 결과로 받은 응답 페이지를 어디에 출력할지를 명시합니다.

즉, formtarget 속성은 form 요소의 target 속성을 덮어쓰게 됩니다.

```
form 요소의 target 속성은 action 페이지를 어느 창에 띄울 것인지를 나타냅니다.
_blank : 서버로부터 받은 응답을 새로운 윈도우나 탭(tab)에서 보여줌.
_self : 기본값으로 생략 가능. 서버로부터 받은 응답을 링크가 위치한 현재 프레임에서 보여줌.
_parent : 서버로부터 받은 응답을 현재 프레임의 부모 프레임에서 보여줌.
_top : 서버로부터 받은 응답을 현재 윈도우 전체에서 보여줌.
iframe 이름 : 서버로부터 받은 응답을 명시된 프레임(iframe)에서 보여줌.
```

이 속성은 submit 타입과 image 타입에서만 사용할 수 있습니다.

``` html
<form action="/examples/media/request.php">
	사용자 이름을 입력해주세요 : <input type="text" name="username"><br><br>
	<input type="submit" value="전송">
	<input type="submit" value="응답 화면을 새창에 표시" formtarget="_blank"><br>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127104915-1567c49b-27d6-4540-a583-033017a429f5.png)

"응답 화면을 새창에 표시" 버튼을 누르면 새로운 탭이 열리면서 action 페이지가 뜨는 것을 확인할 수 있습니다.

> <h3>height와 width 속성</h3>

`<input>`태그의 type 속성이 "image"일 경우에는 height 속성과 width 속성을 사용하여 이미지의 높이와 너비를 명시할 수 있습니다.

따라서 이 속성은 오직 image 타입에서만 사용할 수 있습니다.

또한, 이미지를 클릭하면 클릭한 곳의 x좌표와 y좌표가 x와 y라는 이름으로 같이 전송됩니다.

(image 타입 역시 전송하는 기능을 수행합니다. 차이점은 form 요소 내의 input 정보 뿐만 아니라 그림에서 클릭한 위치의 (x, y) 좌표를 같이 보낸다는 특징이 있습니다)

``` html
<h1>height와 width 속성을 이용한 이미지의 크기 설정</h1>

<form action="/examples/media/request.php">
	사용자 : <input type="text" name="username"><br>
	비밀번호 : <input type="password" name="password" autofocus><br>
	<br>
	<input type="image" src="/examples/images/img_penguin.png" alt="전송" height="26" width="26"> 그림을 클릭하시면 전송됩니다!
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127105602-b5ac35ff-744c-43be-8abe-fa4642575fb6.png)

펭귄 그림을 클릭하면 아래와 같이 그림에서 클릭한 위치인 x, y 좌표 정보도 함께 전송됩니다.

좌측 상단이 (0, 0)입니다.

![image](https://user-images.githubusercontent.com/43658658/127105677-cee68978-1cb2-48da-a9de-7ba123b03242.png)

> <h3>list 속성</h3>

***list 속성***은 해당 input 요소에 대한 미리 정의된 옵션 리스트를 설정하는 datalist 요소와 관련이 있습니다.

input 요소의 list 속성값이 datalist 요소의 id 속성값과 일치해야만 연결이 됩니다.

input 요소의 타입 대신 list가 입력됩니다.

``` html
<h1>list 속성을 이용한 datalist 요소</h1>

<form action="/examples/media/request.php">
	<input list="lectures" name="lecture">
		<datalist id="lectures">
			<option value="HTML"></option>
			<option value="CSS"></option>
			<option value="JAVA"></option>
			<option value="C++"></option>
		</datalist>
	<input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127106348-e37509d7-a258-4ccd-bd8f-26929202e48d.png)

> <h3>min과 max 속성</h3>

min속성과 max 속성은 input 요소에 입력할 수 있는 최솟값과 최댓값을 명시합니다.

이 속성은 다음과 같은 input 타입에서만 사용할 수 있습니다.

- number, range, date, time, datetime-local, month, week 타입

> <h3>multiple 속성</h3>

multiple 속성은 사용자가 input 요소에 값을 두 개 이상 입력하는 것을 허용합니다.

이 속성은 email 타입과 file 타입에서만 사용할 수 있습니다.

``` html
<h1>multiple 속성을 이용한 다중 파일 전송</h1>
<form action="/examples/media/request.php">
	서버로 전송할 파일을 선택해주세요 :<br>
	(여러 개의 파일 선택도 가능해요!)<br><br>
	<input type="file" name="uploadfile" multiple><br><br>
	<input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127107362-7a7db54d-8bad-4b60-8267-26d88cde92e7.png)

> <h3>pattern 속성</h3>

pattern 속성은 input 요소에 입력된 값을 검사하기 위한 정규 표현식(regular expression)을 명시합니다.

정규 표현식이란 문자열에서 특정한 규칙을 가지는 문자열의 집합을 찾아내기 위한 검색 패턴을 의미합니다.

정규 표현식은 자바스크립트 정규 표현식을 따릅니다.

이 속성은 다음과 같은 input 타입에서만 사용할 수 있습니다.

- text, password, email, tel, url 타입

``` html
<h1>pattern 속성을 이용한 입력 형식 제한</h1>
<form action="/examples/media/request.php">
	여러분의 이메일 주소를 입력해 주세요 :<br><br>
<!--이메일의 형식은 구간1@구간2.구간3(.구간4)로 나뉩니다. 
a-zA-Z0-9는 대소문자, 숫자를 쓸 수 있다는 것을 뜻합니다. 
*표시는 생략될 수도 있는 구간에 사용합니다.-->
	<input type="email" name="email"
		pattern="[a-zA-Z0-9]+[@][a-zA-Z0-9]+[.][a-zA-Z]+[.]*[a-zA-Z]*" title="이메일 양식">
	<input type="submit" value="전송">
</form>
```

위의 예제에서 사용된 정규 표현식의 의미는 다음과 같습니다.

1. [a-zA-Z0-9] : 영문 소문자나 영문 대문자, 숫자 중 어느 것이라도 개수에 상관없이 나올 수 있음.
2. [@] : '@' 문자만이 나와야 함.
3. [.] : '.' 문자만이 나와야 함.
4. [.]* : '.' 문자가 나와도 되고 나오지 않아도 됨.
5. [a-zA-Z0-9]* : 영문 소문자나 영문 대문자, 숫자 중 어느 것이라도 개수에 상관없이 나와도 되고 나오지 않아도 됨.

따라서 위와 같은 정규 표현식을 사용하면, 해당 문자열이 이메일 양식에 맞는 문자열인지를 확인할 수 있습니다.

> <h3>placeholder 속성</h3>

placeholder 속성은 input 요소에 입력되어야 할 값에 대한 힌트를 제공합니다.

이러한 힌트는 예시가 될 수도 있고, 입력 형식에 대한 설명이 될 수도 있습니다.

placeholder 속성값은 해당 입력 필드에 포커스가 오게 되면 더 이상 표시되지 않습니다.

이 속성은 다음과 같은 input 타입에서만 사용할 수 있습니다.

- text, password, email, tel, url, search 타입

``` html
<h1>placeholder 속성을 이용한 힌트 제공</h1>

<form action="/examples/media/request.php">
	사용자 : <input type="text" name="username" placeholder="홍길동"><br>
	비밀번호 : <input type="password" name="password" placeholder="1234"><br><br>
	<input type="submit" value="전송">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/127109028-8cffcb38-ed70-4800-bd07-2fc33c8fa577.png)

> <h3>required 속성</h3>

required 속성은 반드시 입력되어야 할 필수 input 요소를 명시합니다.

이 속성이 설정된 모든 input 요소에 입력값이 존재해야만 서버로 전송(submit)할 수 있습니다.

``` html
<h1>required 속성을 이용한 필수 입력 설정</h1>

<form action="/examples/media/request.php">
	이름 : <input type="text" name="name" required> (이름은 반드시 입력해야 해요!)<br>
	나이 : <input type="number" name="age" min="1" max="99"><br><br>
	<input type="submit" value="전송">
</form>
```

이름을 입력하지 않고 "전송" 버튼을 누르면 아래와 같은 알림이 발생합니다.

![image](https://user-images.githubusercontent.com/43658658/127109302-5c2472c7-2553-451b-9325-1d46f961b174.png)

> <h3>step 속성</h3>

step 속성은 input 요소에 입력할 수 있도록 허용된 숫자 간격을 명시합니다.

예를 들어, step 속성값이 2이면, 입력이 허용되는 숫자는 ..., -4, -2, 0, 2, 4,... 가 됩니다.

이 속성은 다음과 같은 input 타입에서만 사용할 수 있습니다.

- number, range, date, time, datetime-local, month, week 타입

``` html
<h1>step 속성을 이용한 입력 간격 설정</h1>

<form action="/examples/media/request.php">
	여러분이 가장 좋아하는 숫자는 몇인가요?<br>
	(단, -30부터 30사이에서 5단위로 골라주세요!)<br><br>
	<input type="number" name="favnum" value="0" min="-30" max="30" step="5"><br><br>
	<input type="submit" value="전송">
</form>
```

입력란 오른쪽에 화살표 버튼을 누르면 "5" 단위로 증감되는 것을 확인할 수 있습니다.

![image](https://user-images.githubusercontent.com/43658658/127109623-df240c6a-02e2-4e75-a44a-0c477bf10b2d.png)
