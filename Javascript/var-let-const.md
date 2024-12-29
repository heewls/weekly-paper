# Var vs Let vs Const

-   `var` : 변수 재선언, 재할당 모두 가능, [function scope](#function-scope)
-   `let` : 변수 재선언 불가능, 재할당 가능, [block scope](#block-scope)
-   `const` : 변수 재선언, 재할당 불가능, [block scope](#block-scope)

<br>

## var

-   블록 스코프를 따르지 않는 var 특성 상, 코드 블록 내의 변수 x는 전역변수다.
-   이미 전역변수 x가 선언되었고 var는 중복 선언이 허용되므로 코드 블록 내 변수 x가 전역에서 선언된 변수 x를 재할당하여 덮어쓴다.

```js
var x = 123; // 전역변수

console.log(x); // 123

{
    var x = 456; // 전역변수
}

console.log(x); // 456
```

<br>

## let, const

-   코드 블록 내에 변수 x는 블록 스코프를 갖는 지역변수다.
-   전역변수 x와는 다른 별개의 변수다.
-   변수 y도 블록 스코프를 갖는 지역 변수이기 때문에 전역에서는 변수 y를 참조할 수 없다.

```js
let x = 123; // 전역변수

{
    let x = 456; // 지역변수
    let y = 456; // 지역변수
}

console.log(x); // 123
console.log(y); // y is not defined
```

<br>

## function scope

-   함수 내에서 선언된 변수는 함수 내에서만 유효하며 함수 외부에서는 참조할 수 없다.<br>
    즉, 함수 내부에서 선언한 변수는 지역 변수이며 함수 외부에서 선언한 변수는 모두 전역 변수이다.

```js
var x = 0; // 전역변수

function functionScope() {
    var y = 1; // 지역변수
}

console.log(x); // 0
console.log(y); // y is not defined
functionScope(); // 1
```

<br>

## block scope

-   모든 코드 블록(함수, if, for, while, try/catch 등) 내에서 선언된 변수는 코드 블록 내에서만 유효하며 코드 블록 외부에서는 참조할 수 없다.<br>
    즉, 코드 블록 내부에서 선언한 변수는 지역 변수이다.

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
