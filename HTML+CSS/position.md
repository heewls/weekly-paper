# Position

**static, relative, absolute, fixed, sticky**

<br>

## static

-   position의 기본값
-   원래 있어야 할 위치인 HTML에 작성된 순서 그대로 브라우저 화면에 표시된다.

<br>

## relative

-   요소의 원래 위치를 기준으로 상대적으로 배치한다.
-   `요소의 원래 자리`는 그대로 차지하고 있다.
-   **top, bottom, left, right** 속성을 이용해서 요소의 원래 위치 기준 이동하도록 설정할 수 있다.

<br>

## absolute

-   가장 가까운 포지셔닝(static 이 아닌 position 속성 값)이 된 조상 요소를 기준으로 배치된다.
-   보통 상위 요소의 position 속성을 **relative**로 지정하여 배치할 기준을 잡고 사용한다.
-   글의 흐름에서 완전히 빠져서, `요소의 원래 자리는 차지하지 않는다.`

<br>

## fixed

-   브라우저 전체 화면을 기준으로 고정된 배치를 가진다.
-   **top, bottom, left, right** 속성은 브라우저의 상, 하, 좌, 우에서 해당 요소가 얼마나 떨어져 있는지를 결정한다.
-   글의 흐름에서 완전히 빠져서, `요소의 원래 자리는 차지하지 않는다.`

<br>

## sticky

-   static 처럼 원래 위치에 배치해 있다가, 정해진 위치에 브라우저가 스크롤되면 그때부터 fixed처럼 고정되어 배치된다.
-   기본적으로는 static 처럼 배치하기 때문에 `요소의 원래 자리`를 차지한다.
-   **top, bottom, left, right** 설정이 필요하고, 가장 가까운 scroll되는 조상을 기준으로 배치된다.
