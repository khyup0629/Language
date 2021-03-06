# HTML 확장

+ [HTML과 CSS](#HTML과-CSS)
+ [HTML과 자바스크립트](#HTML과-자바스크립트)
+ [HTML과 XHTML](#HTML과-XHTML)

## HTML과 CSS

> <h3>CSS란?</h3>

CSS란 Cascading Style Sheets의 약자입니다.

CSS는 HTML 요소들이 각종 미디어에서 어떻게 보이는가를 정의하는 데 사용되는 스타일 시트 언어입니다.

HTML4 부터는 이러한 모든 서식 설정을 HTML 문서로부터 따로 분리하는 것이 가능해졌습니다.

오늘날 대부분의 웹 브라우저들은 모두 CSS를 지원하고 있습니다.

> <h3>CSS 적용 방법</h3>

HTML 문서에 CSS 스타일을 적용하는 방법은 다음과 같습니다.

1. 인라인 스타일(Inline style)
2. 내부 스타일 시트(Internal style sheet)
3. 외부 스타일 시트(External style sheet)

> <h3>인라인 스타일(Inline style)</h3>

인라인 스타일이란 HTML 요소 내부에 style 속성을 사용하여 CSS 스타일을 적용하는 방법입니다.

이러한 인라인 스타일은 해당 요소에만 스타일을 적용할 수 있습니다.

``` html
<h1>인라인 스타일</h1>
<p style="color:green; text-decoration:underline">인라인 스타일을 이용하여 스타일을 적용하였습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126784166-a5d4338b-f932-4620-8813-890f23d69252.png)

> <h3>내부 스타일 시트(Internal style sheet)</h3>

내부 스타일 시트를 이용한 방법은 HTML 문서의 `<head>`태그 내에 `<style>`태그를 사용하여 스타일을 지정합니다.

이러한 내부 스타일 시트는 해당 HTML 문서에만 스타일을 적용할 수 있습니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
    <style>
      body { background-color:lightyellow; }
      p {
        color:red;
        text-decoration:underline;
      }
    </style>
  </head>
  <body>
    <h1>내부 스타일 시트</h1>
    <p>내부 스타일 시트를 이용하여 스타일을 적용하였습니다.</p>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126784713-157cebf1-a68d-4157-a553-9aaada6542b2.png)

> <h3>외부 스타일 시트(External style sheet)</h3>

외부 스타일 시트를 이용한 방법은 웹 사이트 전체의 스타일을 하나의 파일에서 변경할 수 있도록 해줍니다.

스타일을 적용할 모든 웹 페이지의 `<head>`태그 내에 `<link>`태그를 사용하여 외부 스타일 시트를 포함하면 됩니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>HTML CSS</title>
    <link rel="stylesheet" href="/examples/media/expand_style.css">
  </head>
  <body>
    <h1>외부 스타일 시트</h1>
    <p>외부 스타일 시트를 이용하여 스타일을 적용하였습니다.</p>
  </body>
</html>
```

위의 예제에서 사용된 CSS 파일의 내용은 다음과 같습니다.

``` html
<!--expand_style.css-->
body { background-color: lightyellow; }
p { color: red; text-decoration: underline; }
```

> <h3>스타일 적용의 우선순위</h3>

위에서 설명한 스타일 적용 방법들이 혼합되어 사용될 경우, 최종적으로 적용되는 스타일은 다음 순서에 따라 결정됩니다.

1. 인라인 스타일
2. 내부 / 외부 스타일 시트
3. 웹 브라우저 기본 스타일

예를 들어 인라인 스타일이 적용된 태그는 내부나 외부 스타일 시트와는 상관없이 무조건 인라인 스타일이 적용됩니다.

또한, 내부 스타일 시트와 외부 스타일 시트는 가장 마지막에 적용된 스타일 시트가 적용됩니다.

> <h3>CSS 선택자(selector)</h3>

스타일을 적용할 HTML 요소를 선택하는데 사용하는 대표적인 선택자는 다음과 같습니다.

- HTML 요소 선택자
- 아이디(id) 선택자
- 클래스(class) 선택자

> <h3>HTML 요소 선택자</h3>

CSS를 적용할 대상으로 HTML 요소의 이름을 직접 사용하여 선택할 수 있습니다.

``` html
<!--HTML 요소 선택자-->
p { color: red; font-size: 14px; }
```

> <h3>아이디(id) 선택자</h3>

아이디 선택자는 CSS를 적용할 대상으로 특정 요소를 선택할 때 사용합니다.

이 선택자는 웹 페이지에 포함된 여러 요소 중에서 특정 아이디 이름을 가지는 요소만을 선택해 줍니다.

style을 지정할 때 '#'을 앞에 붙이고 인라인에서 style 대신 id="요소 이름"을 입력하면 서식이 적용됩니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>HTML CSS</title>
    <style>
      #para {
        color: teal;
        text-decoration: line-through;
      }
    </style>
  </head>
  <body>
    <h1>아이디 선택자를 이용한 선택</h1>
    <p id="para">이 부분에 스타일을 적용합니다.</p>
    <p>아이디 선택자를 이용하여 스타일을 적용할 특정 HTML 요소를 선택할 수 있습니다.</p>
  </body>
</html>
```

HTML과 CSS에서는 하나의 웹 페이지에 속하는 여러 요소에 같은 아이디 이름을 사용해도 별 문제없이 동작합니다.

하지만 이렇게 중복된 아이디를 가지고 자바스크립트 작업을 하게 되면 오류가 발생합니다.

따라서 되도록이면 하나의 웹 페이지에 속하는 요소에는 다른 아이디 이름을 사용하거나 클래스를 사용하는 것이 좋습니다.

> <h3>클래스(class) 선택자</h3>

클래스 선택자는 특정 집단의 여러 요소를 한 번에 선택할 때 사용합니다.

이러한 특정 집단을 클래스(class)라고 하며, 동일한 클래스 이름을 가지는 요소들을 모두 선택해 줍니다.

style을 지정할 때 맨 앞에 '.'을 붙이고 클래스 이름과 함께 CSS를 입력합니다. 이후 인라인에서 style 대신 class="클래스 이름"으로 서식을 적용합니다.

``` html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title>HTML CSS</title>
    <style>
      .paras {
        color: lime;
        text-decoration: overline;
      }
    </style>
  </head>
  <body>
    <h1>클래스 선택자를 이용한 선택</h1>
    <p class="paras">이 부분에 스타일을 적용합니다.</p>
    <p>클래스 선택자를 이용하여 스타일을 적용할 HTML 요소들을 한 번에 선택할 수 있습니다.</p>
    <p class="paras">이 부분에도 같은 스타일을 적용합니다.</p>
  </body>
</html>
```

## HTML과 자바스크립트

> <h3>자바스크립트란?</h3>

자바스크립트(JavaScript)는 객체(object) 기반의 스크립트 언어입니다.

HTML로는 웹의 내용을 작성하고, CSS로는 웹을 디자인하며, 자바스크립트로는 웹의 동작을 구현할 수 있습니다.

자바스크립트는 주로 웹 브라우저에서 사용되나, Node.js와 같은 프레임워크를 사용하면 서버 측 프로그래밍에서도 사용할 수 있습니다.

현재 컴퓨터나 스마트폰 등에 포함된 대부분의 웹 브라우저에는 자바스크립트 인터프리터가 내장되어 있습니다.

> <h3>script 요소</h3>

***script 요소***는 해당 웹 페이지에 사용할 스크립트(script)를 정의하기 위해 사용합니다.

script 요소 내부에 직접 스크립트를 작성하거나, 외부 스크립트 파일의 주소를 src 속성값으로 명시하면 됩니다.

``` html
<h1>자바스크립트를 이용한 문장 삽입</h1>
<p id="demo"></p>
<script>
  document.getElementById("demo").innerHTML = "자바스크립트를 배워보죠!";
</script>
```

![image](https://user-images.githubusercontent.com/43658658/126787375-c2bf3b76-776c-4b89-ad1c-e90d08837b03.png)

> <h3>noscript 요소</h3>

***noscript 요소***는 스크립트를 지원하지 않는 웹 브라우저를 사용하는 사용자에게 보여줄 문자열을 설정할 때 사용합니다.

noscript 요소는 일반적인 HTML 문서의 body 요소 내부에 나올 수 있는 모든 요소를 포함할 수 있습니다.

``` html
<p id="demo"></p>
<script>
  document.getElementById("demo").innerHTML = "자바스크립트를 배워보죠!";
</script>
<noscript>당신의 웹 브라우저는 자바스크립트를 지원하지 않습니다!</noscript>
```

## HTML과 XHTML

> <h3>XHTML(EXtensible HTML)</h3>

XHTML은 EXtensible HTML을 의미합니다.

XHTML은 HTML과 거의 비슷하지만, 문법의 적용이 조금 더 엄격한 특징을 가지고 있습니다.

> <h3>좀 더 엄격한 버전인 XHTML을 사용하는 이유</h3>

오늘날 웹 콘텐츠는 기존의 PC 위주의 환경에서 벗어나 여러 다양한 플랫폼에서 더욱 많이 이용되고 있습니다.

따라서 부정확한 HTML 문법을 지원하는 데 필요한 자원이 부족한 환경이 점차 생겨나기 시작합니다.

XHTML 문서는 하나의 XML 문서로서 문법적으로 정확하므로, 표준 XML 라이브러리를 이용한 자동화된 처리가 가능해집니다.

> <h3>XHTML에서의 변경 사항</h3>
 
#### 문서의 구조적 측면
  
- XHTML DOCTYPE을 반드시 명시해야 합니다.
- `<html>`태그의 xmlns 속성을 반드시 명시해야 합니다.
- `<html>, <head>, <title>, <body>`태그를 반드시 사용해야 합니다.

 
#### 문서의 요소적 측면
  
- 모든 태그는 반드시 닫혀야 합니다.
- 모든 태그는 순서대로 닫혀야 합니다.
- 모든 요소는 반드시 소문자로 사용되어야 합니다.
- XHTML 문서는 반드시 하나의 root 요소를 포함해야 합니다.

 
#### 문서의 속성적 측면
  
- 속성 이름은 반드시 소문자로 사용되어야 합니다.
- 속성값은 반드시 따옴표로 감싸야 합니다.
- 속성값 생략이 없어졌기 때문에 반드시 속성값을 명시해야 합니다.

> <h3>HTML과 XHTML의 차이점</h3>

다음 예제들은 HTML과 XHTML의 차이점을 보여주고 있습니다.

1. 종료 태그가 없는 빈 태그(empty tag)는 반드시 끝에 공백과 함께 슬래시(/)를 붙여야 합니다.

```
HTML  : <hr>
XHTML : <hr />
```

2. 비어있지 않은 요소는 반드시 종료 태그를 가져야 합니다.

```
HTML  : <p>첫 번째 문장</p><p>두 번째 문장
XHTML : <p>첫 번째 문장</p><p>두 번째 문장</p>
```
 
3. 요소들은 반드시 열린 순서대로 닫혀야 합니다.

```
HTML  : <em><p>This is some text.</em></p>
XHTML : <em><p>This is some text.</p></em>
```
 
4. <img>태그에는 반드시 alt 속성이 기술되어야 합니다.

```
HTML  : <img src="alternative.png" />
XHTML : <img src="alternative.png" alt="explanation" />
```
 
5. 모든 텍스트(text)는 반드시 태그로 감싸야 합니다.

```
HTML  : <body>본문에 사용되는 텍스트 단락</body>
XHTML : <body><p>본문에 사용되는 텍스트 단락</p></body>
```

6. 속성값은 반드시 따옴표로 감싸야 합니다.

```
HTML  : <td rowspan=3>
XHTML : <td rowspan="3">
```
 
7. 태그 이름이나 속성 이름에는 반드시 소문자만을 사용해야 합니다.

```
HTML  : <BODY><P>태그 이름과 태그 속성은</P></BODY>
XHTML : <body><p>반드시 소문자만을 사용하자.</p></body>
```
 
8. 속성값 생략이 없어졌으므로, 반드시 속성값을 명시해야 합니다.

```
HTML  : <textarea readonly>읽기만 가능합니다.</textarea>
XHTML : <textarea readonly="readonly">읽기만 가능합니다.</textarea>
```

> <h3>HTML 문서를 XHTML 문서로 변환하는 방법</h3>

1. 첫줄에 다음 코드를 추가합니다.

```
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml">
```

2. xmlns 속성을 추가합니다.
3. 모든 태그 이름을 소문자로 바꿔줍니다.
4. 모든 빈 태그를 닫아줍니다.
5. 모든 속성 이름을 소문자로 바꿔줍니다.
6. 모든 속성값을 따옴표로 둘러쌉니다.
