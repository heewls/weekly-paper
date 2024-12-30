# Closure

클로저는 함수와 그 `함수가 선언됐을 때의 렉시컬 환경`과의 조합<br>
반환된 내부함수가 자신이 선언됐을 때의 환경인 스코프를 기억하여 자신이 선언됐을 때의 환경 밖에서 호출되어도 그 환경에 접근할 수 있는 함수이다.<br>
간단하게 정리하면 클로저는 `자신이 생성될 때의 환경을 기억`(Lexical environment)하는 함수다.

<br>

```js
const x = 1;

function outer() {
    const x = 10;
    const inner = function () {
        console.log(x);
    };
    return inner;
}

// outer 함수를 호출하면 중첩 함수 inner를 반환
// outer 함수의 실행 컨택스트는 실행 컨텍스트 스택에서 pop되어 제거
const innerFunc = outer();
innerFunc();
```

-   outer 함수는 호출하면 inner 함수를 반환하고 생명 주기 마감된다.
    -   즉, outer 함수의 실행이 종료되면 outer 함수의 실행 컨텍스트는 스택에서 제거된다.
    -   outer 함수의 지역 변수 x 또한 생명 주기 마감된다.<br>
        => x 변수에 접근할 수 있는 방법 없어 보이지만
-   BUT innerFunc의 실행 결과는 지역 변수 x의 값인 10가 나온다.
-   자신을 포함하고 있는 외부함수보다 내부함수가 더 오래 유지되는 경우 `외부함수 밖에서 내부함수가 호출되더라도 외부함수의 지역 변수에 접근 가능`하다.
    => 이러한 함수를 클로저라고 부른다.
