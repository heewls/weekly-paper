# Hoisting

var 선언문이나 function 선언문 등을 해당 스코프의 선두로 옮긴 것처럼 동작하는 특성을 말한다.

<br>

## 변수의 3단계

-   변수 생성 3단계
    -   `선언 단계`(Declaration phase) : 변수를 변수 객체에 등록, 이 변수 객체는 스코프가 참조하는 대상이 된다.
    -   `초기화 단계`(Initialization phase) : 변수 객체에 등록된 변수를 위한 공간을 메모리에 확보, 변수는 undefined로 초기화
    -   `할당 단계`(Assignment phase) : undefined로 초기화된 변수에 실제 값 할당

<br>

## var

-   var로 선언한 변수는 함수 스코프를 기준으로 선언되기 이전에 사용될 수 있다.
-   var로 선언된 변수는 `선언 단계와 초기화 단계가 한번에` 이루어진다.<br>
    -> 스코프에 변수를 등록하고 메모리 공간을 확보한 수 undefined로 초기화한다.<br>
    -> 변수 선언문 이전에 변수에 접근해도 스코프에 변수가 존재하기 때문에 에러 발생하지 않고 undefined 반환한다.<br>
    => `변수 호이스팅`

```js
// 선언 단계 & 초기화 단계
console.log(x); // undefined

var x;
console.log(x); // undefined

x = 1; // 할당 단계
console.log(x); // 1
```

<br>

## let, const

-   let, const로 선언한 변수는 선언되기 이전에 사용될 수 없다.
-   스코프의 시작에서 변수의 선언까지 `일시적 사각지대`(Temporal Dead Zone; [TDZ](#tdz))에 빠지기 때문이다.

```js
// 선언 단계
console.log(x); // ReferenceError: x is not defined

let x; // 초기화 단계
console.log(x); // undefined

x = 1; // 할당 단계
console.log(x); // 1
```

<br>

## TDZ

-   일시적 사각지대로 변수가 선언되고 초기화되기 사이의 사각지대이다.
-   초기화 단계에 오면 TDZ 상태가 해제된다.
