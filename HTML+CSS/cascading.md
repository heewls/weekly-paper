# Cascading

<br>

최종적으로 적용할 CSS 속성들을 결정할 때, 계단식 폭포처럼 CSS 규칙을 순서에 따라 합쳐서 적용하는 걸 말한다.
우선순위가 높은 규칙일수록 우선적으로 속성을 적용한다.

<br>

## 1. 중요도

-   CSS가 어디에 선언되었는지에 따라서 우선순위가 달라진다.
-   User Agent Stylesheet : 브라우저가 기본적으로 제공하는 stylesheet
    -   ex) p tag에 자동으로 적용되는 margin, h1 tag에 자동으로 적용되는 font-size, font-weight
-   Author Stylesheet : 웹 개발자가 작성한 stylesheet
    -   ex) Internal Style(HTML 문서에 작성한 style tag), External CSS(link한 CSS style), Inline Style
    -   우선순위 : `Inline Style > Internal Style > External Style`
-   User Stylesheet : 웹 사이트 사용자가 설정하는 stylesheet
    -   ex) 구글 설정 font-size 조절
-   우선순위 : `Author Stylesheet > User Stylesheet > User Agent Stylesheet`

<br>

## 2. 명시도

-   대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
-   우선순위 : `!important > Inline style > id > class/attribute/:pseudo-class > tag > 전체 선택자(\*) > 상위 요소에 의해 상속된 속성`
-   0 - 0 - 0
    -   id - class - tag 이용하여 점수 비교

<br>

## 3. 코드 순서

-   선언된 순서에 따라 우선 순위가 적용한다.
-   즉, **나중에 선언된 스타일**이 우선 적용한다.

<br>

## 4. 상속

-   부모 요소에 적용된 property를 자식 / 자손 요소가 물려 받는다.
    -   visibility, opacity, font, color, line-height, text-align, white-space
    -   상속되지 않는 경우여도 **inherit** 사용하여 명시적으로 상속받을 수 있다.
-   요소에 따라 상속 받지 않는 경우도 있습니다.(button, input, textarea …)

<br>

## 주의사항

-   !important와 inline style 지양하기!

<br>
