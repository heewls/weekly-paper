# Loose Equality vs Strict Equality

<br>

## == (loose equality)

-   느슨한 같음(loose equality)으로 두 값이 같은지 비교한다.
-   두 값을 공통 타입으로 암묵적으로 변환합니다. 서로 다른 타입이면 Number 타입으로 변환하고 최종 같음 비교는 === 처럼 수행된다.

<br>

## === (strict equality)

-   엄격한 같음(strict equality)으로 두 값이 같은지 비교한다.
-   타입 변환은 일어나지 않고, 둘이 서로 다른 타입이면, 둘은 같지 않다고 판단한다.
