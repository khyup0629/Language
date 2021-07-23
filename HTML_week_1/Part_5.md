# Part 5. HTML 입력 양식

+ [Form 요소](#Form-요소)

## Form 요소

> <h3>form 요소</h3>

웹 페이지에서는 form 요소를 사용하여 사용자로부터 입력을 받을 수 있습니다.

또한, 사용자가 입력한 데이터를 서버로 보낼 때에도 form 요소를 사용합니다.

form 요소는 다음과 같은 문법으로 사용합니다.

`<form action="처리할페이지주소" method="get|post"></form>`

***action 속성***은 입력받은 데이터를 처리할 서버 상의 스크립트 파일의 주소를 명시합니다.

이렇게 전달받은 데이터를 처리하는 스크립트 파일을 **폼 핸들러(form-handler)**라고 합니다.

***method 속성***은 입력받은 데이터를 서버에 전달할 방식을 명시합니다.

따라서 사용자가 form 요소를 통해 입력한 데이터는 action 속성에 명시된 위치로 method 속성의 방식을 통해 전달됩니다.

> <h3>method 속성</h3>

method 속성을 통해 명시할 수 있는 form 요소의 전달 방식은 GET 방식과 POST 방식으로 나눠집니다.

***GET 방식***은 주소에 데이터(data)를 추가하여 전달하는 방식입니다.

데이터가 주소 입력창에 그대로 나타나며, 전송할 수 있는 데이터의 크기 또한 제한적입니다.

따라서 검색 엔진의 쿼리(query)와 같이 **크기가 작고 중요도가 낮은 정보**를 보낼 때 주로 사용합니다.

***POST 방식***은 데이터(data)를 별도로 첨부하여 전달하는 방식입니다.

데이터가 외부에 드러나지 않으며, 전송할 수 있는 데이터의 크기 또한 제한이 없습니다.

따라서 **보안성 및 활용성이 GET 방식보다 좋습니다.**

> <h3>다양한 타입의 input 요소</h3>

HTML에서는 다양한 타입의 input 요소를 사용하여 사용자로부터 입력을 받을 수 있습니다.

HTML에서 사용할 수 있는 대표적인 input 요소의 타입은 다음과 같습니다.

1. 텍스트 입력(text)
2. 비밀번호 입력(password)
3. 라디오 버튼(radio)
4. 체크박스(checkbox)
5. 파일 선택(file)
6. 선택 입력(select)
7. 문장 입력(textarea)
8. 버튼 입력(button)
9. 전송 버튼(submit)
10. 필드셋(fieldset)


> <h3>텍스트 입력</h3>

`<input>`태그의 type 속성값을 "text"로 설정하면, 사용자로부터 한 줄의 텍스트를 입력받을 수 있습니다.

``` html
<h1>텍스트 입력</h1>
<form action="/examples/media/request.php">
  검색할 내용을 입력하세요 : 
  <input type="text" name="search">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126769632-a6bbfd8e-a0d8-49f6-87f2-b5a3514ddfa1.png)

위의 예제처럼 form 요소 그 자체는 웹 페이지에 나타나지 않습니다.

하지만 form 요소에 포함된 다양한 input 요소를 통해 사용자의 입력을 받을 수 있습니다.

> <h3>비밀번호 입력</h3>

`<input>`태그의 type 속성값을 "password"로 설정하면, 사용자로부터 비밀번호를 입력받을 수 있습니다.

비밀번호를 입력받기 때문에 화면에는 입력받은 문자나 숫자 대신 별표나 작은 원 모양이 표시됩니다.

``` html
<h1>비밀번호 입력</h1>
<form>
  사용자 : <br> <input type="text" name="username"> <br>
  비밀번호 : <br> <input type="password" name="password">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126770064-9ae2d664-fb81-4550-ad5d-318bcd6585c0.png)

> <h3>라디오 버튼</h3>

`<input>`태그의 type 속성값을 "radio"로 설정하면, 사용자로부터 여러 개의 옵션(option) 중에서 단 하나의 옵션만을 입력받을 수 있습니다.

이때 서버로 정확한 입력을 전송하기 위해서는 반드시 모든 input 요소의 name 속성이 같아야 합니다.

***checked 속성***을 이용하여 여러 개의 옵션 중에서 처음에 미리 선택되는 옵션을 지정할 수 있습니다.

``` html
<h1>라디오 버튼</h1>
<p>다음 중 가장 재밌고 내용이 알찬 강좌를 하나만 골라주세요.</p>
<form>
  <input type="radio" name="lecture" value="HTML" checked> HTML <br>
  <input type="radio" name="lecture" value="CSS"> CSS <br>
  <input type="radio" name="lecture" value="JAVA"> JAVA <br>
  <input type="radio" name="lecture" value="Cpp"> C++ <br>
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126770492-99b4a095-a0db-497c-9799-b8e8e9dc9f14.png)

> <h3>체크박스</h3>

`<input>`태그의 type 속성값을 "checkbox"로 설정하면, 사용자로부터 여러 개의 옵션 중에서 다수의 옵션을 입력받을 수 있습니다.

체크박스는 라디오 버튼과는 달리 여러 개의 옵션을 한 번에 입력받을 수 있습니다.

이때 서버로 정확한 입력을 전송하기 위해서는 반드시 모든 input 요소의 name 속성이 같아야 합니다.

***checked 속성***을 이용하여 여러 개의 옵션 중에서 처음에 미리 선택되는 옵션을 지정할 수 있습니다.

또한, ***disabled 속성***을 이용하여 해당 옵션을 선택할 수 없게 설정할 수도 있습니다.

``` html
<h1>체크박스</h1>
<p>다음 중 재밌고 내용이 알찬 강좌를 모두 골라주세요.</p>
<form>
  <input type="checkbox" name="lecture" value="html" checked> HTML <br>
  <input type="checkbox" name="lecture" value="css"> CSS <br>
  <input type="checkbox" name="lecture" value="java"> JAVA <br>
  <input type="checkbox" name="lecture" value="cpp" disabled> C++
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126770877-6a18e15e-5ba6-44b4-957c-aa17c25ca54a.png)

> <h3>파일 선택</h3>

`<input>`태그의 type 속성값을 "file"로 설정하면, 사용자로부터 파일을 전송받을 수 있습니다.

***accept 속성***을 이용하여 입력받을 수 있는 파일의 확장자 및 종류를 명시할 수 있습니다.

``` html
<h1>파일 선택 박스</h1>
<p>여러분이 가장 행복했던 날의 사진을 선택해 주세요.</p>
<form>
  <input type="file" name="upload_file" accept="image/*">
</form>
```

![image](https://user-images.githubusercontent.com/43658658/126771021-9ff31407-35d8-402c-9a84-7e5df56c4dd4.png)

> <h3>선택 입력</h3>

`<select>` 태그는 여러 개의 옵션이 드롭다운 리스트(drop-down list)로 되어 있으며, 그중에서 단 하나의 옵션만을 입력받을 수 있습니다.

`<option>` 태그는 드롭다운 리스트에서 선택할 수 있는 각각의 옵션을 명시합니다.

***selected 속성***을 이용하여 드롭다운 리스트 중에서 처음에 미리 선택되는 옵션을 지정할 수 있습니다.

``` html
<h1>선택 입력</h1>
<p>다음 중 여러분이 가장 좋아하는 과일을 골라주세요.</p>
<form>
  <select name="fruit">
    <option value="apple"> 사과 </option>
    <option value="orange" selected> 귤 </option>
    <option value="strawberry"> 딸기 </option>
    <option value="peach"> 복숭아 </option>
  </select>
</form>
```

<form>
  <select name="fruit">
    <option value="apple"> 사과 </option>
    <option value="orange" selected> 귤 </option>
    <option value="strawberry"> 딸기 </option>
    <option value="peach"> 복숭아 </option>
  </select>
</form>

![image](https://user-images.githubusercontent.com/43658658/126772359-ecc5626a-f84c-4b4c-9a9f-98c134a546f1.png)
