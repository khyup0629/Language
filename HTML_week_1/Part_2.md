# Part 2. HTML 텍스트 요소

+ [제목(Heading)](#제목Heading)
+ [단락(Paragraph)](#단락Paragraph)
+ [서식(Formatting)](#서식Formatting)
+ [인용구(Quotation)](#인용구Quotation)

## 제목(Heading)

HTML은 제목을 표현할 수 있는 다양한 크기의 ```<h>```태그를 제공합니다.

가장 큰 ```<h1>```태그부터 가장 작은 ```<h6>```태그까지 다양한 크기로 제목을 표현할 수 있습니다.
  
```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body>
    <h1>제목1의 크기입니다!</h1>
    <h2>제목2의 크기입니다!</h2>
    <h3>제목3의 크기입니다!</h3>
    <h4>제목4의 크기입니다!</h4>
    <h5>제목5의 크기입니다!</h5>
    <h6>제목6의 크기입니다!</h6>
  </body>
</html>
```

+ ```<h>```태그의 위아래로는 약간의 여백이 자동으로 삽입됩니다.

이런 ```<h>```태그는 제목의 표현이라는 기능 외에도 또 다른 중요한 역할을 하고 있습니다.

여러 검색엔진은 각 웹 사이트의 내용을 바로 이 ```<h>```태그를 이용하여 키워드를 수집하고, 그 내용을 파악합니다.

따라서 HTML 문서에 포함되는 제목은 ```<h>```태그로 작성해야만 검색엔진에 의해 제대로 검색될 확률을 높일 수 있습니다.

+ HTML 문서의 제목에 해당하는 부분을 ```<big>```태그나 ```<bold>```태그를 사용하여 표현하지 않도록 합니다.

> ***종료 태그***를 잊지 맙시다!

대부분의 웹 브라우저는 종료 태그를 사용하지 않더라도 HTML 문서를 제대로 표현해 줍니다.

하지만 종료 태그가 없으면 예상치 못한 오류나 결과가 발생할 수도 있습니다.

또한, XHTML이나 XML과 같은 문법이 엄격한 언어에서는 종료 태그의 유무를 엄격하게 검사합니다.

따라서 가급적 **종료 태그를 빠트리지 말고 코드를 작성**하는 것이 좋습니다.

## 단락(Paragraph)

단락이란 내용상 끊어서 구분할 수 있는 하나하나의 부분을 의미하며, 문단이라고도 부릅니다.

HTML에서는 ```<p>```태그를 이용하여 이러한 단락을 표현합니다.
  
```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body>
    <h1>제목1의 크기입니다!</h1>
    <h2>제목2의 크기입니다!</h2>
    <h3>제목3의 크기입니다!</h3>
    <p>여기서부터 단락입니다.</p>
  </body>
</html>
```
+ `<p>`태그의 위아래로 약간의 여백(margin)이 자동으로 삽입됩니다.

> 띄어쓰기와 줄 나누기

HTML 코드에서 띄어쓰기나 줄 나누기를 여러 번 하더라도 웹 브라우저를 통해 나타나는 화면에는 전혀 영향을 주지 못합니다.

웹 브라우저는 여러 번의 띄어쓰기나 줄 나누기를 오직 하나의 띄어쓰기나 줄로만 인식하기 때문입니다.

다음 예제는 웹 페이지에 여러 번의 띄어쓰기와 줄 나누기를 표현하기 위해 작성한 예제입니다.

```
<!DOCTYPE html>
<html lang="ko">
  <head>
	  <meta charset="UTF-8">
	  <title>HTML Paragraph</title>
  </head>

  <body>
	  <p>
줄을 나누고 싶어서
이렇게 줄을 나눠봤습니다.

과연     그대로     출력이     될까요?
	  </p>
  </body>
</html>
```
![image](https://user-images.githubusercontent.com/43658658/126150884-a64860ae-f4ac-4867-9243-f815b8a91a1d.png)

위의 예제는 여러 번의 띄어쓰기와 줄 나누기를 표현하고자 `<p>`태그를 이용합니다.

하지만 `<p>`태그 내에서 작성된 여러 번의 띄어쓰기와 줄 나누기는 오직 하나의 띄어쓰기로만 표현됩니다.

***`<br>`태그(break line)*** 를 사용하면 새로운 단락을 만들지 않고도 줄을 나눌 수 있습니다.

이러한 `<br>`태그는 종료 태그가 없는 빈 태그(empty tag)입니다.

```
<p>
줄을 나누고 싶어서<br>
이렇게 줄을 나눠봤습니다.<br>
<br>
과연     그대로     출력이     될까요?
</p>
```

![image](https://user-images.githubusercontent.com/43658658/126151153-942c8aed-9dde-4466-aa25-c2e15869d520.png)

> 텍스트(text) 서식 미리 정의하기

HTML 코드에서 작성한 **텍스트 서식을 그대로 표현**하려면 `<pre>`태그를 사용해야 합니다.

`<pre>`태그(preformatted text) 내에 작성된 텍스트의 **모든 띄어쓰기와 줄 나누기**는 **웹 브라우저에 그대로 표현**됩니다.

+ `<pre>`태그 내에 작성된 텍스트의 글꼴(font)은 **고정폭 글꼴(fixed-width font)로 자동변환**됩니다.

```
<pre>
줄을 나누고 싶어서
이렇게 줄을 나눠봤습니다.

과연     그대로     출력이     될까요?
</pre>
```
![image](https://user-images.githubusercontent.com/43658658/126151278-22279e11-4dcb-4411-8f71-4fd664579394.png)

> 수평 가로 구분선

단락을 나눌 때나 내용상의 구분을 표현하고자 할 때 **수평 가로 구분선**을 사용합니다.

이렇게 사용되는 수평 가로 구분선을 HTML 코드에서는 ***`<hr>`태그(horizontal rule)*** 로 간단하게 만들 수 있습니다.

+ `<hr>`태그는 종료 태그가 없는 빈 태그(empty tag)입니다.

```
<p>저는 하나의 단락입니다.</p>
<hr>
<p>저는 하나의 단락입니다.</p>
<hr>
<p>저는 하나의 단락입니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126151404-bc804cf8-a402-4571-9ac7-ff565165de4c.png)

`<p>`, `<br>`, `<hr>`, `<pre>` 태그를 모두 한 번에 써보겠습니다.

```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body>
    <p>저는 하나의 단락입니다.</p>
    <hr>
    <pre>
    아녕하세욜다
    
    저는    오리입니다.
    </pre>
    <hr>
    <p>안녕하세요<br>
      저는 너구리입니다.<br>
      히히
    </p>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126152048-70edf700-1016-4193-8334-7d220cf0f32e.png)

## 서식(Formatting)

HTML은 텍스트(text)에 다양한 효과를 주는 여러 태그(tag)를 제공합니다.

> 강조 효과

HTML 문서에서 텍스트를 굵게 표현하고 싶을 때에는 `<b>`태그(bold text)나 `<strong>`태그를 사용하면 됩니다.

```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset='UTF-8'>
    <title></title>
  </head>
  <body>
    <h1>b태그와 strong태그의 차이점</h1>
    <p><b>"이 부분"</b>은 단순히 글씨가 굵은 부분이예요!</p>
    <p><strong>"이 부분"</strong>은 중요한 부분이라서 굵게 표현됐어요!</p>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126155381-57e05ef1-2651-4477-a6e3-f6a9a089e665.png)

`<b>`태그는 단순히 화면의 텍스트를 굵게 표현해 줍니다.

하지만 `<strong>`태그는 텍스트를 굵게 표현해줄 뿐만 아니라 그 내용이 중요하다는 의미도 함께 포함해 줍니다.

HTML 문서에서 ***이탤릭체***를 표현하고 싶을 때에는 `<i>`태그(italic text)나 `<em>`태그(emphasized text)를 사용합니다.

```
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8">
    <title></title>
  </head>
  <body>
    <h1>i태그와 em태그의 차이점</h1>
    <p><i>"이 부분"</i>은 단순히 글씨가 이탤릭체인 부분이에요!</p>
    <p><em>"이 부분"</em>은 중요한 부분이라서 이탤릭체로 표현됐어요!</p>
  </body>
</html>
```

![image](https://user-images.githubusercontent.com/43658658/126155713-91cc5ef7-ee57-4e02-a655-6b599578d8bf.png)

`<i>`태그는 단순히 화면의 텍스트를 이탤릭체로 표현해 줍니다.

하지만 `<em>`태그는 텍스트를 이탤릭체로 변환해줄 뿐만 아니라 그 내용이 중요하다는 의미도 함께 포함해 줍니다.

검색엔진은 `<strong>`태그나 `<em>`태그를 사용하여 강조된 텍스트를 더 중요하게 인식합니다.

> 하이라이팅 효과

`<mark>`태그는 텍스트에 하이라이팅(highlighting) 효과를 적용시켜 줍니다.

```
<h1>mark태그를 이용한 하이라이팅</h1>
<p><mark>"이 부분"</mark>만 하이라이팅하고 싶어요.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126155807-70edac79-5082-4f6e-b6f6-3bc4d98548db.png)

> 삭제 효과

`<del>`태그(delete)는 텍스트 중앙에 가로줄을 만들어 마치 텍스트를 지운 것과 같은 효과를 내줍니다.

```
<h1>del태그를 이용한 삭제 효과</h1>
<p><del>"이 부분"</del>을 지운 것처럼 하고 싶어요.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126155907-a0a20893-3c2a-4b1d-8128-1101fc9f7fbf.png)

> 삽입 효과

`<ins>`태그(insert)는 텍스트 밑줄을 만들어 마치 빈칸에 텍스트를 삽입한 것과 같은 효과를 내줍니다.

```
<h1>ins태그를 이용한 삽입 효과</h1>
<p><ins>"밑줄 친 부분"</ins>에 들어갈 알맞은 말을 고르세요.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126156046-e4582474-883c-411c-a36a-4382d5b5602e.png)

> 위첨자와 아래첨자 효과

위첨자는 `<sup>`태그(superscript)를 사용하여, 아래첨자는 `<sub>`태그(subscript)를 사용하여 각각 표현할 수 있습니다.
  
```
<h1>sup태그와 sub태그를 이용한 첨자</h1>
<p>X<sup>2</sup> + Y<sup>3</sup> = Z</p>
<p>물을 나타내는 화학식은 H<sub>2</sub>O 입니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/126156227-0debc4e3-2ca7-44d0-aaf8-a8b2af1c1dd7.png)

## 인용구(Quotation)

HTML에서 인용구를 표현하는 방법은 다음과 같이 두 가지로 나뉩니다.

1. 짧은 인용구
2. 블록 인용구

> 짧은 인용구

짧은 인용구는 `<q>`태그(quotation)를 사용하여 표현할 수 있으며, 자동으로 앞뒤에 큰따옴표가 붙습니다.

```
<h1>q태그를 이용한 짧은 인용구</h1>
<p>HTML의 정의는
<q>웹 페이지를 만들기 위한 하이퍼텍스트 마크업 언어</q>
입니다.</p>
```
<h1>q태그를 이용한 짧은 인용구</h1>
<p>HTML의 정의는
<q>웹 페이지를 만들기 위한 하이퍼텍스트 마크업 언어</q>
입니다.</p>
