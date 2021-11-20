# Part1
## 005.값(value)과 변수(variable)이해하기

* 선언 키워드

  * 프로그래밍할 때 값의 유형을 일일이 명시하지 않으면, 런타임 시 변수의 값에 의해 동적으로 유형이 결정된다. 이를 **동적 바인딩**(Dynamic Binding)이라고 한다.

* 변수명

  * 변수를 선언할 때 선언 키워드 다음에 변수명을 작성한다

    * ex)

      ```javascript
      var name = "Peter"
      ```

  * 키워드를 변수명으로 선언한다면 에러가 발생한다.

    * 자바스크립트 키워드(Keyword)의 종류

      ```javascript
      break case catch class const continue debugger default delete do else export extends finally for function if import in instanceof let new return super switch this throw try typeof var void while with yield
      ```

      

  * 등호 (=)
    * 등호를 사이에 두고 왼쪽에 변수명과 오른쪽에 값을 작성한다.
    * 변수명이 정의된 변수 메모리에 값을 대입한다는 의미이다.



## 006.자바스크립트 문장 배우기

자바스크립트를 구성하는 가장 작은 기본단위는 **값, 변수, 연산자, 키워드**이다.

그리고 이 작은 요소들이 모여 하나의 자바스크립트 문장을 구성한다.

### 표현식(Expressions)과 명령문(Statements)

자바스크립트 코드의 구문 패턴을 살펴보면 표현식과 명령문, 두 종류로 나눌 수 있다.

#### 표현식

표현식은 값을 생성한다. 연산자를 통해 값을 생성하거나, 변수 또는 함수 인자로 값을 넣을 때 표현식을 사용한다.

```javascript
(3 + 12) / 5
declaredVariable
greeting("Hello")
```

#### 명령문

명령문은 일종의 행동 또는 행위를 수행하게 하는 코드이다.

**if, if-else, for, switch** 등이 있다.



## 008.자료형 이해하기

프로그래밍 언어는 값을 특정 유형으로 분류한다.

특정 유형을 다른말로 **자료형** 또는 **타입(type)**이라고 한다.

```javascript
var x = 5; // 숫자형(Number)
var y = 'five'; // 문자형(String)
var isTrue = true; // 불린형(Boolean)
var empty = null; // null
var nothing // undefined
var sym = Symbol('me'); // Symbol

var item = {
	price: 5000,
	count: 10
}; // 객체(Object)
var fruits = ['apple', 'orange', 'kiwi']; // 배열(Array)
var addFruit = function (fruit) {
	fruits.push(fruit);
} // 함수(function)
addFruit('watermelon');
console.log(fruits);
```

자바스크립트는 크게 **원시타입**(Primitive Data Type)과 **참조타입**(Reference Data Type)으로 나뉜다.

![image-20211120175135402](README.assets/image-20211120175135402.png)

### 원시타입

원시타입은 값이 변수에 할당될 때 메모리 상에 고정된 크기로 저장된다. 즉, 해당 변수가 직접 값을 보관한다.

이렇듯 고정된 공간에 보관된 원시 타입의 값은 변경 불가능한 값, 불변값(Immutable Value)인 특징을 가진다.

ex)

* 숫자형(Number)

  숫자를 표현하는 자료형이다. 숫자안에서도 정수, 실수 등 여러 종류로 구분하지만, 자바스크립트의 숫자 자료형은 그 종류들을 숫자형 하나로 포괄한다. 숫자형끼리 연산이 가능하다.

* 불린형(Boolean)

  참(true) 또는 거짓 (false) 두 가지 값을 가진다.

* 문자형(String)

  작은따옴표 '' 또는 큰따옴표""를 양 끝에 두고, 그 안에 한 글자 이상의 문자, 기호 또는 숫자가 있는 자료형

* 심볼형(Symbol)

  ES6부터 추가된 원시 자료형이다. 다른 원시형과 다르게 유일하게 변경 불가능한 자료형으로, 참조형의 키(key)로도 사용 가능하다.

* null

  빈값

* undefined

  존재하지 않는 값

### 참조타입

참조타입은 원시타입과 달리 변수에 고정된 크기를 저장하지 않고, 값의 메모리 주소를 참조한다.

참조 타입인 객체의 특징은

객체는 속성들(Properties)의 집합을 의미하며, 집합 내부에는 순서도 크기도 고정되어있지 않다.

이렇게 고정되지 않은 값을 변수에 할당하려면 직접 해당 값을 저장할 순 없으나 참조하는 것은 가능하다. 따라서 참조타입은 값의 메모리 주소를 변수에 할당하여 값을 참조한다.

* 객체

  객체는 {} 안에 **키:값** 형태로 이루어진 속성들의 모음이다.

  키는 반드시 문자(String) 자료형이어야 하고, 이 속성 키를 통해 해당 속성에 매핑된 값에 접근할 수 있다.

자바스크립트에는 특성에 따라 여러 형태의 객체들이 있다.

Global Object 객체는 모든 객체의 부모가 되는 객체이다. 이를 부모삼아 함수(Function), 배열(Array), 원시 자료형을 객체로 감싼 새로운 형태의 객체(String, Number, Boolean)와 특수 연산에 특화된 내장 객체(Math, JSON, RegEx) 그리고 Iterable과 Collection 특성의 객체(Map, Set, WeakMap, WeakSet) 등의 **표준 내장 객체**가 있다.

## 009.콘솔로 자료형 출력하기

console.log(출력할 내용)

log 메소드 외 활용할 수 있는 다른 console 메소드들

* debug(디버그-로그)
* error(에러)
* info(정보)
* warn(경고)

