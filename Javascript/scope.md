# Scope

변수나 함수가 `유효하게 접근할 수 있는 범위`이며 `함수가 선언될 때 결정`된다.

<br>

## Javascript scope

```js
var x = 0;
{
    var x = 1;
    console.log(x); // 1
}
console.log(x); // 1

let y = 0;
{
    let y = 1;
    console.log(y); // 1
}
console.log(y); // 0
```

-   자바스크립트는 함수 레벨 스코프(function-level scope)를 따른다.
-   함수 레벨 스코프란 함수 코드 블록 내에서 선언된 변수는 함수 코드 블록 내에서만 유효하고 함수 외부에서는 유효하지 않다는 것이다.
-   let, const를 사용하면 블록 레벨 스코프를 사용할 수 있다.

<br>

## Global scope & Local scope

```js
var x = "global"; // 전역변수

function globalScope() {
    var x = "local"; // 지역변수
    console.log(x);
}

globalScope(); // local
console.log(x); // global
```

-   global scope : 코드 어디에서든지 참조할 수 있는 스코프
-   local scope : 함수 코드 블록이 만든 스코프로 함수 자신과 하위 함수에서만 참조할 수 있는 스코프
-   자바스크립트는 변수의 범위를 호출한 함수의 지역 스코프부터 전역 변수들이 있는 전역 스코프까지 점차 넓혀가며 찾는다.
-   함수 globalScope의 범위 안에 지역변수 x가 존재하기 때문에 전역변수 x가 아닌 지역변수 x를 참조한다.

<br>

## Lexical scope

```js
var x = 0;
function outer() {
    var y = 1;
    function inner() {
        console.log(x); // 0
        console.log(y); // 1
    }
    inner();
}
```

-   스코프는 함수를 호출할 때가 아니라 `함수를 어디서 선언`했는지에 따라 상위 스코프를 결정한다.
    => 이를 렉시컬 스코프라고 한다.
-   함수의 상위 스코프는 함수를 정의한 위치에 의해 정적으로 결정되고 변하지 않는다.
-   함수 inner가 함수 outer의 내부에 선언된 내부함수이므로 함수 inner는 자신이 속한 렉시컬 스코프(전역, 함수 outer, 자신의 스코프)를 참조할 수 있다.

<br>

## Scope chain

```js
var x = "x";
function outer() {
    var y = "y";
    function inner() {
        var z = "z";
        console.log(x + y + z);
    }
    inner();
}
outer(); // XYZ
```

-   내부 스코프의 렉시컬 환경(inner)에서 필요한 값을 찾을 수 없을 때 외부 스코프의 렉시컬 환경(함수 outer, 전역)을 점진적으로 탐색하게 되는데, 이처럼 `렉시컬 환경을 매개로 내부와 외부의 스코프가 이어진 것`을 스코프 체인 이라고 부른다.
