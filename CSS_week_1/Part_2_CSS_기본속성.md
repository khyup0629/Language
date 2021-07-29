# Part 2. CSS 기본 속성

+ [배경](#배경)
+ [텍스트](#텍스트)
+ [글꼴](#글꼴)
+ 

## 배경

CSS에서 사용할 수 있는 background 속성은 다음과 같습니다.

1. background-color
2. background-image
3. background-repeat
4. background-position
5. background-attachment

> <h3>background-color 속성</h3>

background-color 속성은 해당 HTML 요소의 배경색(background color)을 설정합니다.

``` html
<style>
    body { background-color: lightblue; }
    h1 { background-color: rgb(255,128,0); }
    p { background-color: #FFFFCC; }
</style>
```

> <h3>background-image 속성</h3>

background-image 속성은 해당 HTML 요소의 배경으로 나타날 배경 이미지(image)를 설정합니다.

설정된 배경 이미지는 기본 설정으로 HTML 요소 전체에 걸쳐 반복되어 나타납니다.

``` html
<style>
    body { background-image: url("/examples/images/img_background_good.png"); }
</style>
```

> <h3>background-repeat 속성</h3>

배경 이미지는 기본 설정으로 수평과 수직 방향으로 모두 반복되어 나타납니다.

background-repeat 속성을 이용하면 이러한 배경 이미지를 수평이나 수직 방향으로만 반복되도록 설정할 수 있습니다.

다음 예제는 배경 이미지의 수평 반복을 보여줍니다.

``` html
<style>
		body {
			background-image: url("/examples/images/img_man.png");
			background-repeat: repeat-x;  
		}
</style>
```

다음 예제는 배경 이미지의 수직 반복을 보여줍니다.

``` html
<style>
		body {
			background-image: url("/examples/images/img_man.png");
			background-repeat: repeat-y;  
		}
</style>
```

배경 이미지가 반복되지 않고 한 번만 나타나게 할 수도 있습니다.

``` html
body { 
  background-image: url("/examples/images/img_man.png"); 
  background-repeat: no-repeat; 
}
```

> <h3>background-position 속성</h3>

background-position 속성은 반복되지 않는 배경 이미지의 상대 위치(relative position)를 설정합니다.

``` html
body {
  background-image: url("/examples/images/img_man.png");
  background-repeat: no-repeat;
  background-position: top right;
}
```

이 속성에서 사용할 수 있는 키워드의 조합은 다음과 같습니다.

두 키워드의 순서는 상관이 없습니다.

1. left top
2. left center
3. left bottom
4. right top
5. right center
6. right bottom
7. center top
8. center center
9. center bottom

또한, 퍼센트(%)나 픽셀(px)을 사용하여 상대 위치를 직접 명시할 수도 있습니다.

이때 상대 위치를 결정하는 기준은 해당 요소의 왼쪽 상단(left top)이 됩니다.

다음 예제는 배경 이미지의 상대 위치를 픽셀 단위로 직접 명시한 예제입니다.

``` html
body {
    background-image: url("/examples/images/img_man.png");
    background-repeat: no-repeat;
    background-position: 100px 200px;
}
```

> <h3>background-attachment 속성</h3>

background-attachment 속성을 사용하여 위치가 설정된 배경 이미지를 해당 위치에 고정시킬 수도 있습니다.

이렇게 고정된 배경 이미지는 스크롤과는 무관하게 화면의 위치에서 이동하지 않습니다.

``` html
body {
  background-image: url("/examples/images/img_man.png");
  background-repeat: no-repeat;
  background-position: left bottom;
  background-attachment: fixed;
}
```

> <h3>background 속성 한 번에 적용하기</h3>

위에서 언급한 모든 background 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.

순서는 상관 없습니다.

``` html
body { background: #FFCCCC url("/examples/images/img_man.png") no-repeat left bottom fixed; }
```

> <h4>CSS background 속성</h4>

background 속성에 대해 다시 한 번 정리하면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>background</td>
			<td>모든 background 속성을 이용한 스타일을 한 줄에 설정할 수 있음.</td>
		</tr>
		<tr>
			<td>background-color</td>
			<td>HTML 요소의 배경색을 설정함.</td>
		</tr>
		<tr>
			<td>background-image</td>
			<td>HTML 요소의 배경 이미지를 설정함.</td>
		</tr>
		<tr>
			<td>background-repeat</td>
			<td>설정된 배경 이미지의 반복 유무를 설정함.</td>
		</tr>
		<tr>
			<td>background-position</td>
			<td>반복되지 않는 배경 이미지의 상대 위치를 설정함.</td>
		</tr>
		<tr>
			<td>background-attachment</td>
			<td>배경 이미지를 스크롤과는 무관하게 해당 위치에 고정시킴.</td>
		</tr>
	</tbody>
</table>

## 텍스트

CSS는 여러 기능을 가진 다양한 Text 속성을 제공합니다.

CSS에서 사용할 수 있는 대표적인 text 속성은 다음과 같습니다.

1. color

2. direction

3. letter-spacing

4. word-spacing

5. text-indent

6. text-align

7. text-decoration

8. text-transform

9. line-height

10. text-shadow

> <h3>direction 속성</h3>

direction 속성은 텍스트가 써지는 방향을 설정합니다.

웹 페이지에서 텍스트는 기본적으로 왼쪽에서 오른쪽 방향으로 써집니다.

direction 속성이 left-to-right(`ltr`)일 때는 기본 설정처럼 텍스트가 `왼쪽에서 오른쪽 방향`으로 써집니다.

하지만, direction 속성이 right-to-left(`rtl`)일 때는 텍스트가 반대 방향인 `오른쪽에서 왼쪽 방향`으로 써집니다.

- ltr : 왼쪽에서 오른쪽 방향
- rtl : 오른쪽에서 

다음 예제는 "객체 지향 프로그래밍"이라는 문자열을 한글과 아랍어로 각각 나타낸 예제입니다.

``` html
.rightToLeft { direction:rtl; }
...
<p class="rightToLeft">برمجة كائنية التوجه!!!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127436615-300b00d4-eea1-4dde-b43c-555d251581c1.png)

아랍어는 한글이나 영어와는 달리 오른쪽에서 왼쪽 방향으로 텍스트를 읽고 쓰는 언어입니다.

따라서 아랍어와 같이 텍스트를 반대 방향으로 쓰는 언어를 나타낼 때는 텍스트가 써지는 방향을 direction 속성을 사용하여 변경해 줘야 합니다.

> <h3>unicode-bidi 속성</h3>

주로 `direction`이랑 연계해서 씁니다.

아랍어가 아닌 일반적으로 왼쪽에서 오른쪽으로 쓰는 언어의 경우 `direction:rtl` 을 쓰게 되면 아래와 같이 출력됩니다.

``` html
p.ex1 {
  direction: rtl;
}
...
<p class="ex1">This is right-to-left text direction.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127440069-fca678d2-86c6-4b83-b991-36880e8c8617.png)

여기서 `unicode-bidi` 속성을 추가해주면 완벽하게 오른쪽부터 출력됩니다.

``` html
p.ex1 {
  direction: rtl;
  unicode-bidi: bidi-override;
}
...
<p class="ex1">This is right-to-left text direction.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127440232-5b57523b-2068-4f11-bb99-ac18170d61d3.png)

> <h3>letter-spacing 속성</h3>

letter-spacing 속성은 텍스트 내에서 글자 사이의 간격을 설정합니다.

``` html
<style>
  .decLetterSpacing { letter-spacing: -3px; }
  .incLetterSpacing { letter-spacing: 10px; }
</style>
...
<h1>letter-spacing 속성을 이용한 글자 간격 설정</h1>
<p class="decLetterSpacing">글자 간격을 줄여봅시다!</p>
<p>기본적인 글자 간격은 이 정도입니다.</p>
<p class="incLetterSpacing">글자 간격을 늘려봅시다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127436978-f7a821dd-9cd2-443d-834b-24a5145d0ef1.png)

> <h3>word-spacing 속성</h3>

word-spacing 속성은 텍스트 내에서 단어 사이의 간격을 설정합니다.

letter-spacing 속성과는 달리 문자 간의 간격이 아닌 단어 간의 간격을 기준으로 설정합니다.

``` html
<style>
    .decWordSpacing { word-spacing: -3px; }
    .incWordSpacing { word-spacing: 10px; }
</style>
...
<h1>word-spacing 속성을 이용한 단어 간격 설정</h1>
<p class="decWordSpacing">단어 간격을 줄여봅시다!</p>
<p>기본적인 단어들의 간격은 이 정도입니다.</p>
<p class="incWordSpacing">단어 간격을 늘려봅시다!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127437205-0bf9adba-26cc-408d-84f8-74f2264ae3ea.png)

> <h3>white-space 속성</h3>

`white-space: nowrap`이 **없으면** 아래와 같이 출력됩니다.

``` html
<p>
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
</p>
```

![image](https://user-images.githubusercontent.com/43658658/127441767-21ae0272-c6c9-4603-96eb-7501941499d0.png)

`white-space: nowrap`이 **있으면** 아래와 같이 출력됩니다.

``` html
<style>
  p {
    white-space: nowrap;
  }
</style>
...
<p>
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
This is some text. This is some text. This is some text.
</p>
```

![image](https://user-images.githubusercontent.com/43658658/127441940-7f7605cf-dc77-4e7d-baa7-875a5e399418.png)

> <h3>text-indent 속성</h3>

text-indent 속성은 단락의 첫 줄에 들여쓰기할지 안 할지를 설정합니다.

웹 페이지에서 단락은 기본적으로 들여쓰기가 설정되어 있지 않습니다.

``` html
<style>
  .paraIndent { text-indent: 30px; }
</style>
...
<h1>text-indent 속성을 이용한 들여쓰기 설정</h1>
<p>기본 설정은 들여쓰기를 사용하지 않습니다!! </p>
<p class="paraIndent">자 이제 들여쓰기를 설정해 봅시다!! </p>
```

![image](https://user-images.githubusercontent.com/43658658/127437348-04a451c6-d506-4d85-9349-c4d03a874bd6.png)

> <h3>text-align 속성</h3>

text-align 속성은 텍스트의 수평 방향 정렬을 설정합니다.

text-align 속성으로 설정된 정렬 방향은 text-direction 속성과는 상관없이 우선적으로 적용됩니다.

- left : 왼쪽 정렬
- right : 오른쪽 정렬
- center : 가운데 정렬
- justify : 

``` html
<style>
  h2 { text-align: left; }
  h3 { text-align: right; }
  h4 { text-align: center; }
  h5 { text-align: justify; }
</style>
```

> <h3>vertical-align 속성</h3>

HTML 요소 내에서 수직방향 정렬을 수행할 때 이용합니다.

- baseline : 기본값으로, 요소의 수직 가운데에 정렬됩니다.
- text-top : 텍스트의 상단에 정렬됩니다.
- text-bottom : 텍스트의 하단에 정렬됩니다.
- sub : 요소의 하단에 정렬됩니다.
- super : 요소의 상단에 정렬됩니다.

``` html
<style>
  img.a {
    vertical-align: baseline;
  }

  img.b {
    vertical-align: text-top;
  }

  img.c {
    vertical-align: text-bottom;
  }

  img.d {
    vertical-align: sub;
  }

  img.e {
    vertical-align: super;
  }
</style>
...
<h1>The vertical-align Property</h1>

<h2>vertical-align: baseline (default):</h2>
<p>An <img class="a" src="sqpurple.gif" width="9" height="9"> image with a default alignment.</p> 

<h2>vertical-align: text-top:</h2>
<p>An <img class="b" src="sqpurple.gif" width="9" height="9"> image with a text-top alignment.</p> 

<h2>vertical-align: text-bottom:</h2>
<p>An <img class="c" src="sqpurple.gif" width="9" height="9"> image with a text-bottom alignment.</p>

<h2>vertical-align: sub:</h2>
<p>An <img class="d" src="sqpurple.gif" width="9" height="9"> image with a sub alignment.</p> 

<h2>vertical-align: super:</h2>
<p>An <img class="e" src="sqpurple.gif" width="9" height="9"> image with a super alignment.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127441192-37adc4fc-9104-41de-9411-497c2369f61f.png)

> <h3>text-decoration 속성</h3>

text-decoration 속성은 텍스트에 여러 가지 효과를 설정하거나 제거하는데 사용합니다.

- overline : 윗줄
- line-throught : 중간 줄
- underline : 아랫줄
- none : 줄 없음(주로 하이퍼링크에 밑줄을 제거하기 위해 사용)

``` html
<style>
  h2 { text-decoration: overline; }
  h3 { text-decoration: line-through; }
  h4 { text-decoration: underline; }
  a { text-decoration: none; }
</style>
...
<h1>text-decoration 속성을 이용한 텍스트의 효과 설정</h1>
<h2>텍스트에 윗줄을 만듭니다.</h2>
<h3>텍스트를 통과하는 가운데 줄을 만듭니다.</h3>
<h4>텍스트에 밑줄을 만듭니다.</h4>
<a href="#"><p>링크에 생기는 밑줄을 제거합니다!</p></a>
```

![image](https://user-images.githubusercontent.com/43658658/127438290-1d0d305d-1a17-47f5-a6cd-ba70e3969d31.png)

+ text-decoration 속성값을 none으로 설정하여 링크(link)가 설정된 텍스트의 밑줄을 제거하는데 자주 사용합니다.

> <h3>text-transform 속성</h3>

text-transform 속성은 텍스트에 포함된 영문자에 대한 대소문자를 설정합니다.

이 속성은 텍스트에 포함된 모든 영문자를 대문자나 소문자로 변경시켜 줍니다.

또한, 단어의 첫 문자만을 대문자로 변경시킬 수도 있습니다.

- uppercase : 모든 문자를 대문자로
- lowercase : 모든 문자를 소문자로
- capitalize : 첫 글자를 대문자로 나머지는 소문자로

text-transform 속성은 한글에는 영향을 주지 않으며, 오직 영문자에만 적용됩니다.

``` html
<style>
  h2 { text-transform:uppercase; }
  h3 { text-transform:lowercase; }
  h4 { text-transform:capitalize; }
</style>
...
<h2>텍스트의 모든 영문자를 대문자(upper case)로 만듭니다.</h2>
<h3>텍스트의 모든 영문자를 소문자(LOWER CASE)로 만듭니다.</h3>
<h4>텍스트의 모든 영단어의 첫 문자(first character)만을 대문자(upper case)로 만듭니다.</h4>
```

![image](https://user-images.githubusercontent.com/43658658/127438792-fa1b6634-a8cb-4fb4-841a-da8aebcf2a65.png)

> <h3>line-height 속성</h3>

line-height 속성은 텍스트의 줄 간격을 설정합니다.

``` html
<style>
    .narrowLineHeight { line-height: 0.8; }
    .wideLineHeight { line-height: 1.8; }
</style>
...
<h1>line-height 속성을 이용한 줄간격 설정</h1>
<p class="narrowLineHeight">이 부분은 줄간격을 줄여보았어요!<br>
  이 부분은 줄간격을 줄여보았어요!</p>
<p>이 부분은 기본 줄간격입니다.<br>
  이 부분은 기본 줄간격입니다.</p>
<p class="wideLineHeight">이 부분은 줄간격을 늘려보았어요!<br>
  이 부분은 줄간격을 늘려보았어요!</p>
```

![image](https://user-images.githubusercontent.com/43658658/127439256-3c4c50f0-d478-4e53-a16b-3539d09bb2f6.png)

> <h3>text-shadow 속성</h3>

text-shadow 속성은 텍스트에 간단한 그림자 효과를 설정합니다.

속성값은 각각 x, y, blur effect, color를 나타냅니다.

즉, 그림자가 드리우는 x, y축 간격과 흐림 정도, 그림자의 색을 나타냅니다.

``` html
h1 {
  text-shadow: 2px 2px 5px red;
}
...
<h1>Text-shadow effect!</h1>
```

![image](https://user-images.githubusercontent.com/43658658/127442286-843d360e-bd99-490a-aa24-c826ded98fc4.png)

> <h4>CSS text 속성</h4>

CSS text 속성을 정리해보면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>color</td>
			<td>텍스트의 색상을 설정함.</td>
		</tr>
		<tr>
			<td>direction</td>
			<td>텍스트가 쓰이는 방향을 설정함.</td>
		</tr>
		<tr>
			<td>letter-spacing</td>
			<td>텍스트 내에서 문자 사이의 간격을 설정함.</td>
		</tr>
		<tr>
			<td>word-spacing</td>
			<td>텍스트 내에서&nbsp;단어 사이의&nbsp;간격을 설정함.</td>
		</tr>
		<tr>
			<td>text-indent</td>
			<td>단락의&nbsp;첫 줄을&nbsp;들여쓰기할지 안&nbsp;할지를 설정함.</td>
		</tr>
		<tr>
			<td>text-align</td>
			<td>텍스트의 수평 방향&nbsp;정렬을 설정함.</td>
		</tr>
		<tr>
			<td>text-decoration</td>
			<td>텍스트에 여러 가지 효과를 설정하거나 제거함.</td>
		</tr>
		<tr>
			<td>text-transform</td>
			<td>텍스트에 포함된&nbsp;영문자에 대한 대소문자를 설정함.</td>
		</tr>
		<tr>
			<td>line-height</td>
			<td>텍스트의 줄 간격을 설정함.</td>
		</tr>
		<tr>
			<td>text-shadow</td>
			<td>텍스트에 그림자 효과를 설정함.</td>
		</tr>
		<tr>
			<td>unicode-bidi</td>
			<td>direction 속성과 같이 사용하여&nbsp;텍스트의 기본 출력 방향을 설정함.</td>
		</tr>
		<tr>
			<td>vertical-align</td>
			<td>HTML 요소 내의 수직 방향 정렬을 설정함.</td>
		</tr>
		<tr>
			<td>white-space</td>
			<td>HTML 요소 내의 여백을 설정함.</td>
		</tr>
	</tbody>
</table>

## 글꼴
 
CSS를 사용하면 웹 페이지에 나타나는 글꼴(Font)을 다양하게 설정할 수 있습니다.
 
CSS에서 사용할 수 있는 font 속성은 다음과 같습니다.

1.font-family

2.font-style

3.font-variant

4.font-weight

5.font-size

> <h3>CSS 글꼴 집합(font-family)</h3>

CSS에는 두 가지의 글꼴 집합(font family)이 존재합니다.

- generic family : 비슷한 모양을 가지는 글꼴 집합 ("Serif", "Monospace" 등)
- font family : 특정 글꼴 집합 ("Times", "Courier" 등)

> <h3>font-family 속성</h3>

font-family 속성은 하나의 글꼴만을 설정할 수도 있고, 여러 개의 글꼴을 같이 설정할 수도 있습니다.

font-family 속성값이 여러 개의 글꼴로 설정되어 있으면, 웹 브라우저는 위에서부터 순서대로 글꼴을 읽어 들입니다.

만약 사용자의 컴퓨터에 첫 번째로 읽어 들인 글꼴이 없으면 다음 글꼴을 확인하게 됩니다.

이런 방식으로 계속해서 읽어 들인 글꼴이 존재하는지를 확인하여, 읽어 들인 글꼴이 사용자의 컴퓨터에 존재하면 해당 글꼴로 표시하게 됩니다.

글꼴의 이름이 **한 단어 이상**으로 이루어지면 반드시 따옴표(")를 사용하여 둘러 쌓아야 합니다.

또한, **여러 개의 글꼴을 나열**할 때에는 쉼표(,)로 구분 짓습니다.

``` html
<style>
  .serif { font-family: "Times New Roman", Times, serif; }
  .sansserif { font-family: Arial, Helvetica, sans-serif; }
</style>
...
<p class="serif">Times New Roman 글꼴을 적용합니다.</p>
<p class="sansserif">Arial 글꼴을 적용합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127443069-0371e573-8e50-4e4d-aeb7-9dd1c893f55f.png)

> <h3>font-style 속성</h3>

font-style 속성은 주로 ***이탤릭체***를 사용하기 위해 사용하며, 다음과 같이 3가지의 속성값을 가집니다.

- normal : 기본값, 텍스트에 어떠한 스타일도 적용하지 않습니다.
- italic : 텍스트를 이탤릭체로 나타냅니다.
- oblique : 텍스트를 기울입니다. 이 속성값은 italic과 매우 유사하지만 지원하는 웹 브라우저가 거의 없습니다.

``` html
<style>
    .normal { font-style: normal; }
    .italic { font-style: italic; }
    .oblique { font-style: oblique; }
</style>
...
<p class="normal">이 문단은 normal 스타일이 적용되어 있습니다.</p>
<p class="italic">이 문단은 italic 스타일이 적용되어 있습니다.</p>
<p class="oblique">이 문단은 oblique 스타일이 적용되어 있습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127443391-cbe7ce25-7f82-4df9-abe6-ddf589f89747.png)

> <h3>font-variant 속성</h3>

font-variant 속성은 속성값이 `small-caps`로 설정되면, 텍스트에 포함된 영문자 중 모든 소문자를 작은 대문자(small-caps) 글꼴로 변경시킵니다.

이때 영문자 중 대문자는 기존 크기 그대로 출력합니다.

작은 대문자(small-caps) 글꼴이란 텍스트의 기존 대문자보다는 약간 작은 크기의 대문자를 의미합니다.

``` html
<style>
  .normal { font-variant: normal; }
  .smallCaps { font-variant: small-caps; }
</style>
...
<p class="normal">이 문단은 normal 스타일이 적용되어 있습니다.</p>
<p class="smallCaps">이 문단은 Small-Caps 글꼴이 적용되어 있습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127443915-c37c2760-c153-4e28-87c3-454ab035dce3.png)

> <h3>font-weight 속성</h3>

font-weight 속성은 텍스트를 얼마나 두껍게 표현할지를 설정합니다.

사용할 수 있는 속성값에는 lighter, normal, bold, bolder 등이 있습니다.

또한, 100, 200, 300, ... , 900 등과 같이 숫자로 텍스트의 두께를 설정할 수도 있습니다.

``` html
<style>
  .normal { font-weight: normal; }
  .bold { font-weight: 600; }
  .bolder { font-weight: bolder; }
</style>
...
<p class="normal">이 텍스트의 두께는 normal 스타일이 적용되어 있습니다.</p>
<p class="bold">이 텍스트의 두께는 600이 적용되어 있습니다.</p>
<p class="bolder">이 텍스트의 두께는 bolder 스타일이 적용되어 있습니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127444109-ee244f7b-04cf-4922-8bda-bac5d5ed45c3.png)

> <h3>font-size 속성</h3>

font-size 속성은 텍스트의 크기를 설정합니다.

웹 디자인에서 텍스트의 크기는 매우 중요한 표현 요소입니다. 

하지만 제목을 표현하기 위해서 텍스트의 크기만을 크게 해서는 안 됩니다.

이때에는 제목을 위한 HTML 요소인 `<h1>`태그부터 `<h6>`태그를 사용해야 합니다.

font-size 속성값은 다음과 같이 두 가지 방식으로 표현할 수 있습니다.

1. 절대적 크기
2. 상대적 크기

절대적 크기는 텍스트의 크기를 명시된 크기 그대로 설정하고자 할 때 사용합니다.

절대적 크기로 설정된 텍스트는 모든 웹 브라우저에서 같은 크기로 표현됩니다.

상대적 크기는 텍스트를 둘러싸고 있는 HTML 요소들의 크기에 따라 텍스트의 크기도 같이 변하는 방식입니다.

또한, 사용자가 웹 브라우저를 통해 텍스트의 크기를 직접 변경할 수도 있습니다.

font-size 속성값에 자주 사용되는 대표적인 크기 단위는 다음과 같습니다.

- 백분율 단위(%) : 기본 크기를 100%로 놓고, 그에 대한 상대적인 크기를 설정합니다.
- 배수 단위(em) : 해당 글꼴(font)의 기본 크기를 1em으로 놓고, 그에 대한 상대적인 크기를 설정합니다.
- 픽셀 단위(px) : 스크린의 픽셀(pixel)을 기준으로 하는 절대적인 크기를 설정합니다.

``` html
<style>
  body { font-size: 100%; }
  #large { font-size: 2.5em; }
  #small { font-size: 0.7em; }
  #fixed { font-size: 20px; }
</style>
...
<h1>font-size 속성을 이용한 글꼴의 크기 설정</h1>
<p id="large">글꼴의 크기를 2.5em 으로 변경합니다.</p>
<p>글꼴의 기본 크기인 1em 입니다.</p>
<p id="small">글꼴의 크기를 0.7em 으로 변경합니다.</p>
<p id="fixed">글꼴의 크기를 20px 로 변경합니다.</p>
```

![image](https://user-images.githubusercontent.com/43658658/127444752-bff5f6f8-abb7-4c29-9a5b-f6f5f4d22af6.png)

> <h3>font 속성</h3>

font 속성을 이용해 인라인으로 모든 font 속성을 설정할 수 있습니다.

꼭 아래의 순서대로 적어야합니다.

- font-style
- font-variant
- font-weight
- font-size/line-height
- font-family

``` html
<style>
  .ont { font: italic small-caps bolder 20px/30px "Times New Roman"; }
</style>
...
<p class="ont">font 속성을 이용한 글꼴 설정<br>
  한 줄 띄우기</p>
```

![image](https://user-images.githubusercontent.com/43658658/127447831-9b8e776b-433a-42b2-8d31-8e03022be802.png)

> <h4>CSS font 속성</h4>

CSS에 font 속성을 다시 정리하면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 25%;">속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>font</td>
			<td>모든 font 속성을 이용한 스타일을 한 줄에 설정할 수 있음.</td>
		</tr>
		<tr>
			<td>font-family</td>
			<td>텍스트의 글꼴 집합(font family)을 설정함.</td>
		</tr>
		<tr>
			<td>font-style</td>
			<td>주로&nbsp;이탤릭체를 사용하기 위해 사용함.</td>
		</tr>
		<tr>
			<td>font-variant</td>
			<td>
			<p>텍스트에 포함된&nbsp;영문자 중 소문자만을&nbsp;작은 대문자(small-caps) 글꼴로 변경시킴.</p>
			</td>
		</tr>
		<tr>
			<td>font-weight</td>
			<td>텍스트를 얼마나 두껍게 표현할지를 설정함.</td>
		</tr>
		<tr>
			<td>font-size</td>
			<td>텍스트의 크기를 설정함.</td>
		</tr>
	</tbody>
</table>

## 
