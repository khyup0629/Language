# Part 7. 객체

+ [객체의 개념](#객체의-개념)
+ [객체의 생성](#객체의-생성)
+ [프로토타입](#프로토타입)
+ [객체 다루기](#객체-다루기)
+ [객체 프로퍼티와 메소드](#객체-프로퍼티와-메소드)

## 객체의 개념

객체(object)란 실생활에서 우리가 인식할 수 있는 사물로 이해할 수 있습니다.

> <h3>객체의 예</h3>

객체(object)

- 고양이

프로퍼티(property)

- cat.name = "나비"

- cat.family = "코리안 숏 헤어"

- cat.age = 0.1

- cat.weight = 300

 

메소드(method)

- cat.mew()

- cat.eat()

- cat.sleep()

- cat.play()

 

고양이 객체는 모두 위와 같은 프로퍼티를 가지지만, 각 프로퍼티의 값은 인스턴스마다 전부 다를 것입니다.

> <h3>자바스크립트 객체</h3>

자바스크립트의 기본 타입(data type)은 객체(object)입니다.

객체란 `이름(name)과 값(value)`으로 구성된 `프로퍼티(property)`의 정렬되지 않은 집합입니다.

`프로퍼티의 값으로 함수`가 올 수도 있는데, 이러한 프로퍼티를 `메소드(method)`라고 합니다.

``` html
var cat = "나비"; // 일반적인 변수의 선언
// 객체도 많은 값을 가지는 변수의 하나임.
var kitty = { name: "나비", family: "코리안 숏 헤어", age: 1, weight: 0.1 };

document.write(cat + "<br>");
document.write(kitty.name);
```

> <h3>객체의 프로퍼티 참조</h3>

자바스크립트에서 객체의 프로퍼티를 참조하는 방법은 다음과 같습니다.

``` html
var person = {
  name: "홍길동",			// 이름 프로퍼티를 정의함.
  birthday: "030219",		// 생년월일 프로퍼티를 정의함.
  pId: "1234567",			// 개인 id 프로퍼티를 정의함.
  fullId: function() {	// 생년월일과 개인 id를 합쳐서 주민등록번호를 반환함.
    return this.birthday + this.pId;
  }
};

document.write(person.name + "<br>");	// 홍길동
document.write(person["name"]);			// 홍길동
```

> <h3>객체의 메소드 참조</h3>

자바스크립트에서 객체의 메소드를 참조하는 방법은 다음과 같습니다.

``` html
var person = {
  name: "홍길동",			// 이름 프로퍼티를 정의함.
  birthday: "030219",		// 생년월일 프로퍼티를 정의함.
  pId: "1234567",			// 개인 id 프로퍼티를 정의함.
  fullId: function() {
    return this.birthday + this.pId;
  }
};

document.write(person.fullId() + "<br>");	// 0302191234567
document.write(person.fullId);				// function () { return this.birthday + this.pId; }
```

## 객체의 생성

자바스크립트에서 객체를 생성하는 방법은 다음과 같습니다.

1. 리터럴 표기(literal notation)를 이용한 방법

2. 생성자 함수(constructor function)를 이용한 방법

3. Object.create() 메소드를 이용한 방법

위와 같은 방법으로 생성되어 메모리에 대입된 객체를 인스턴스(instance)라고 합니다.

> <h3>리터럴 표기를 이용한 객체의 생성</h3>

자바스크립트에서 객체를 생성하는 가장 쉬운 방법은 리터럴 표기(literal notation)를 이용하는 방법입니다.

``` html
var 객체이름 = {
    프로퍼티1이름 : 프로퍼티1의값,
    프로퍼티2이름 : 프로퍼티2의값,
    ...
};
```
 

각각의 프로퍼티는 이름과 값을 콜론(:)으로 연결하고, 쉼표(,)를 사용해 다른 프로퍼티와 구분합니다.

프로퍼티의 이름으로는 자바스크립트의 식별자(identifier)나 문자열을 사용할 수 있습니다.

``` html
var kitty = {
  name: "나비",
  family: "코리안 숏 헤어",
  age: 1,
  weight: 0.1
};
```

> <h3>생성자를 이용한 객체의 생성</h3>

new 연산자를 사용하여 객체를 생성하고 초기화할 수 있습니다.

이때 사용되는 메소드를 생성자(constructor)라고 하며, 이 메소드는 새롭게 생성되는 객체를 초기화하는 역할을 합니다.

자바스크립트는 원시 타입을 위한 생성자를 미리 정의하여 제공합니다.

``` html
var day = new Date();
document.write("올해는 " + day.getFullYear() + "년입니다.<br>");
```

> <h3>Object.create() 메소드를 이용한 객체의 생성</h3>

Object.create() 메소드를 이용하여 객체를 생성할 수도 있습니다.

Object.create() 메소드는 지정된 프로토타입(prototype) 객체와 프로퍼티를 가지고 새로운 객체를 만들어 줍니다.

따라서 이 메소드를 이용하면 사용자가 프로토타입 객체를 직접 명시할 수 있으므로, 상당히 유용하게 사용됩니다.

``` html
Object.create(프로토타입객체[, 새로운객체의프로퍼티1, 새로운객체의프로퍼티2, ...]);
```

Object.create() 메소드의 첫 번째 인수로는 프로토타입으로 사용할 객체를 전달합니다.

두 번째 인수로는 새로운 객체의 추가할 프로퍼티 정보를 전달합니다.

``` html
var obj = Object.create(null, {				// null 프로토타입을 사용하여 새로운 객체를 만들고
        x: { value: 100, enumerable: true },	// x좌표를 나타내는 열거할 수 있는 속성과
        y: { value: 200, enumerable: true }		// y좌표를 나타내는 열거할 수 있는 속성을 추가함.
    });

document.write(obj.x + "<br/>");			// x좌표
document.write(obj.y + "<br/>");			// y좌표
document.write(Object.getPrototypeOf(obj));	// 객체의 프로토타입을 반환해 줌.
```

## 프로토타입

> <h3>상속(inheritance)</h3>

상속(inheritance)이란 새로운 클래스에서 기존 클래스의 모든 프로퍼티와 메소드를 사용할 수 있는 것을 의미합니다.

상속을 통해 새로운 프로그램의 요구에 맞게 기존 클래스를 수정하여 재사용할 수 있습니다.

또한, 클래스 간의 종속 관계를 형성함으로써 객체의 관계를 조직화할 수 있는 장점이 있습니다.

따라서 이러한 상속은 추상화, 캡슐화와 더불어 객체 지향 프로그래밍을 구성하는 중요한 특징 중 하나가 됩니다.

 

하지만 C#이나 C++과 같은 클래스 기반(class-based)의 객체 지향 언어와는 달리 자바스크립트는 프로토타입 기반(prototype-based)의 객체 지향 언어입니다.

프로토타입 기반이기 때문에 상속의 개념이 클래스 기반의 객체 지향 언어와는 약간 다릅니다.

쉽게 말해, 다른 언어에서 `클래스`의 개념이 자바스크립트에서는 `프로토타입`입니다.

`자바스크립트에서는 현재 존재하고 있는 객체를 프로토타입으로 사용하여, 해당 객체를 복제하여 재사용하는 것`을 상속이라고 합니다.

> <h3>프로토타입(prototype)</h3>

자바스크립트의 모든 객체는 프로토타입(prototype)이라는 객체를 가지고 있습니다.

모든 객체는 그들의 프로토타입으로부터 프로퍼티와 메소드를 상속받습니다.

이처럼 자바스크립트의 모든 객체는 최소한 하나 이상의 다른 객체로부터 상속을 받으며, 이때 상속되는 정보를 제공하는 객체를 프로토타입(prototype)이라고 합니다.

> <h3>프로토타입 체인(prototype chain)</h3>

자바스크립트에서는 객체 이니셜라이저를 사용해 생성된 같은 타입의 객체들은 모두 같은 프로토타입을 가집니다.

또한, new 연산자를 사용해 생성한 객체는 생성자의 프로토타입을 자신의 프로토타입으로 상속받습니다.

``` html
var obj = new Object(); // 이 객체의 프로토타입은 Object.prototype입니다.
var arr = new Array();  // 이 객체의 프로토타입은 Array.prototype입니다.
var date = new Date();  // 이 객체의 프로토타입은 Date.prototype입니다.
```

하지만 Object.prototype 객체는 어떠한 프로토타입도 가지지 않으며, 아무런 프로퍼티도 상속받지 않습니다.

또한, 자바스크립트에 내장된 모든 생성자나 사용자 정의 생성자는 바로 이 객체를 프로토타입으로 가집니다.

``` html
var date = new Date(); // 이 객체는 Date.prototype 뿐만 아니라 Object.prototype도 프로토타입으로 가집니다.
```
 
위와 같이 프로토타입이 상속되는 가상의 연결 고리를 프로토타입 체인(prototype chain)이라고 합니다.

Object.prototype 객체는 이러한 프로토타입 체인에서도 가장 상위에 존재하는 프로토타입입니다.

따라서 자바스크립트의 모든 객체는 Object.prototype 객체를 프로토타입으로 상속받습니다.

> <h3>프로토타입의 생성</h3>

프로토타입을 생성하는 가장 기본적인 방법은 객체 생성자 함수(object constructor function)를 작성하는 것입니다.

생성자 함수를 작성하고 new 연산자를 사용해 객체를 생성하면, 같은 프로토타입을 가지는 객체들을 생성할 수 있습니다.

객체 생성자 함수를 작성할 때에는 관례상 이름의 첫 문자만을 대문자로 작성합니다.

``` html
function Dog(color, name, age){
    this.color = color;
    this.name = name;
    this.age = age;
}
var myDog = new Dog("흰색", "마루", "1");
document.write("우리 집 강아지는 " + myDog.name + "라는 이름의 " + myDog.color + " 털이 매력적인 강아지입니다.");
```

> <h3>객체에 프로퍼티 및 메소드 추가</h3>

이미 생성된 객체에 새로운 프로퍼티나 메소드를 추가하는 방법은 다음과 같습니다.

``` html
function Dog(color, name, age){ // Dog라는 프로토타입을 생성
    this.color = color;
    this.name = name;
    this.age = age;
}
var myDog = new Dog("흰색", "마루", "1"); // myDog라는 객체를 생성
myDog.family = "시베리안 허스키";
myDog.breed = function() {
  return this.color + " " + this.family;
}
```

위의 예제에서 새롭게 추가된 family 프로퍼티와 breed() 메소드는 오직 `myDog 인스턴스`에만 추가됩니다.

이미 생성된 다른 Dog 객체나 차후에 생성되는 어떠한 다른 Dog 객체에도 추가되지 않습니다.

> <h3>프로토타입에 프로퍼티 및 메소드 추가</h3>

프로토타입에 새로운 프로퍼티나 메소드를 추가하는 것은 객체에 추가할 때와는 다른 방법을 사용해야 합니다.

프로토타입의 경우에는 생성자 함수에 직접 추가해야만 이후에 생성되는 모든 다른 객체에도 적용할 수 있습니다.

``` html
function Dog(color, name, age) {
  this.color = color;
  this.name = name;
  this.age = age;
  this.family = "시베리안 허스키"; // 프로토타입에 프로퍼티를 추가할 때에는 기본값을 가지게 할 수 있음.
  this.breed = function() { return this.color + " " + this.family; };
}

var myDog = new Dog("흰색", "마루", 1);
var hisDog = new Dog("갈색", "콩이", 3);

document.write("우리 집 강아지는 " + myDog.family + "이고, 친구네 집 강아지도 " + hisDog.family + "입니다.");
```

> <h3>prototype 프로퍼티</h3>

`prototype` 프로퍼티를 이용하면 현재 존재하고 있는 프로토타입에 새로운 프로퍼티나 메소드를 손쉽게 추가할 수 있습니다.

``` html
function Dog(color, name, age){
  this.color = color;
  this.name = name;
  this.age = age;
}

Dog.prototype.family = "시베리안 허스키";
Dog.prototype.breed = function() {
  return this.color + " " + this.family;
}

var myDog = new Dog(("흰색", "마루", 1);
var hisDog = new Dog("갈색", "콩이", 3);

document.write("우리 집 강아지는 " + myDog.family + "이고, 친구네 집 강아지도 " + hisDog.family + "입니다.");
document.write("우리 집 강아지의 품종은 " + myDog.breed() + "입니다.<br>");
document.write("친구네 집 강아지의 품종은 " + hisDog.breed() + "입니다.");
```

![image](https://user-images.githubusercontent.com/43658658/129217933-2a73920c-009e-4f83-91b3-f8359066b0bf.png)

직접 생성한 프로토타입은 위와 같이 새로운 프로퍼티나 메소드를 마음껏 추가하거나 삭제할 수 있습니다.

물론 자바스크립트 표준 객체의 프로토타입도 임의로 수정할 수 있으나, 심각한 오류가 발생할 가능성이 있습니다.

따라서 자바스크립트 표준 객체의 프로토타입은 수정해서는 안됩니다.

## 객체 다루기

> <h3>this 키워드</h3>

자바스크립트에서 this 키워드는 해당 키워드가 사용된 자바스크립트 코드 영역을 포함하고 있는 객체를 가리킵니다.

예를 들어, 메소드 내부에서 사용된 this 키워드는 해당 메소드를 포함하고 있는 객체를 가리킵니다.

또한, 객체 내부에서 사용된 this 키워드는 객체 그 자신을 가리킵니다.

이러한 this는 변수가 아닌 키워드이므로, 사용자가 임의로 가리키는 값을 바꿀 수 없습니다.

> <h3>객체 프로퍼티의 삭제</h3>

자바스크립트에서 객체의 프로퍼티를 참조하는 방법은 다음과 같습니다.

자바스크립트에서는 delete 키워드를 사용하여 객체의 프로퍼티를 삭제할 수 있습니다.

``` html
delete 객체이름.프로퍼티이름;
```
 
delete 키워드를 사용하여 프로퍼티를 삭제하면, 프로퍼티의 값뿐만 아니라 프로퍼티 그 자체도 삭제됩니다.

이 키워드는 본래 객체의 프로퍼티만을 삭제하기 위해 만들어졌기 때문에 함수나 변수에 사용하면 아무런 동작도 하지 않습니다.

``` html
function Dog(color, name, age) {
    this.color = color;
    this.name = name;
    this.age = age;
}

var myDog = new Dog("흰색", "마루", 1);
delete myDog.age; // age 프로퍼티를 삭제함.
// age 프로퍼티가 삭제되었기 때문에 undefined를 출력함.
document.write("우리집 강아지의 나이는 " + myDog.age + "입니다.");
```

![image](https://user-images.githubusercontent.com/43658658/129218333-97139170-1ac8-45f7-9535-80d5c60eda87.png)

> <h3>객체 프로퍼티의 순회</h3>

자바스크립트에서는 for / in 문을 사용하여 객체의 모든 프로퍼티를 순회할 수 있습니다.

for / in 문은 객체의 모든 열거할 수 있는 프로퍼티(enumerable properties)를 손쉽게 순회할 수 있도록 해줍니다.

객체의 프로퍼티를 순회하는 방법으로는 for / in 문 이외에도 다음과 같은 메소드를 사용할 수 있습니다.


1. Object.keys()

2. Object.getOwnPropertyNames()

 

Object.keys() 메소드는 해당 객체가 가진 고유 프로퍼티 중에서 열거할 수 있는 프로퍼티의 이름을 배열에 담아 반환합니다.

Object.getOwnPropertyNames() 메소드는 해당 객체가 가진 모든 고유 프로퍼티의 이름을 배열에 담아 반환합니다.

``` html
function Dog(color, name, age) {
  this.color = color;
  this.name = name;
  this.age = age;
}
var myDog = new Dog("흰색", "마루", 1);

// color 프로퍼티의 enumerable 속성을 false로 설정함.
Object.defineProperty(myDog, 'color', { enumerable : false} );
// 객체가 가진 고유 프로퍼티 중에서 열거할 수 있는 프로퍼티 이름을 배열에 담아 반환함.
document.write(Object.keys(myDog) + "<br>"); // name, age
// 객체가 가진 모든 고유 프로퍼티의 이름을 배열에 담아 반환함.
document.write(Object.getOwnPropertyNames(myDog)); // color, name, age
```

> <h3>객체간의 비교</h3>

자바스크립트에서 별개의 두 객체는 프로퍼티의 값이 모두 같아도, 절대로 같다고 말할 수 없습니다.

``` html
function Dog(color, name, age) {
    this.color = color;
    this.name = name;
    this.age = age;
}
var myDog = new Dog("흰색", "마루", 1);
var hisDog = new Dog("흰색", "마루", 1);      // 모든 프로퍼티의 값이 모두 같은 객체를 생성함.
document.write((myDog == hisDog) + "<br>");   // false
document.write((myDog === hisDog) + "<br>");  // false
 
var herDog = hisDog;                          // hisDog 객체를 변수 herDog에 대입함.
document.write((hisDog == herDog) + "<br>");  // true
document.write((hisDog === herDog) + "<br>"); // true
```
 
위의 예제에서 myDog과 hisDog 객체는 가지고 있는 프로퍼티의 값이 모두 같습니다.

하지만 이 두 객체는 별개의 객체이므로, 동등(==) 연산자와 일치(===) 연산자로 비교해도 모두 false를 반환합니다.
 

위의 예제에서는 변수 herDog에 hisDog 객체를 대입합니다.

이렇게 객체를 대입한 변수를 `객체 레퍼런스(object reference)`라고 하며, 이제부터 `변수 herDog`은 `hisDog 객체를 가리키게 됩니다.`

즉, 객체 레퍼런스는 객체 자체를 저장하는 것이 아니라, 객체가 위치한 주소를 저장하는 것입니다.

따라서 변수 herDog과 hisDog을 동등 연산자와 일치 연산자로 비교하면, 모두 true를 반환하게 됩니다.

## 
