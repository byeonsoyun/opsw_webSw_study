# CSS란 무엇인가?

CSS(Cascading Style Sheets)는 웹 페이지의 스타일과 레이아웃을 정의하는 스타일 시트 언어이다. HTML 등의 마크업 언어와 함께 사용되며, 웹 페이지의 디자인을 개선하고 일관된 스타일을 적용하는 데 사용된다.

## Cascading Style Sheets란?

CSS의 풀네임인 **Cascading Style Sheets**에서 "Cascading"은 스타일이 여러 계층에서 적용될 수 있으며, 특정 규칙이 우선순위를 갖는 방식을 의미한다. 즉, 스타일 규칙이 여러 곳에서 정의되었을 때 어떤 규칙이 최종적으로 적용될지를 결정하는 메커니즘이 존재한다.

## CSS의 주요 기능

- **레이아웃 및 디자인 조정**: 요소의 크기, 위치, 색상, 배경, 여백 등을 조정할 수 있다.
- **반응형 웹 디자인**: 다양한 화면 크기에 맞춰 스타일을 조정할 수 있다.
- **코드의 재사용성 증가**: CSS 파일을 분리하여 여러 HTML 문서에서 공통 스타일을 적용할 수 있다.
- **웹 접근성 향상**: 스타일을 적절히 조정하여 사용자 경험을 개선할 수 있다.

## CSS의 기본 문법

```css
선택자 {
  속성: 값;
}
```

예제:
```css
p {
  color: blue;
  font-size: 16px;
}
```

이 코드는 모든 `<p>` 요소의 글자 색상을 파란색으로 지정하고, 글자 크기를 16px로 설정한다.

---

# CSS 선택자(Selector)

CSS 선택자는 HTML 요소를 선택하여 스타일을 적용하는 데 사용된다. 선택자에는 다양한 유형이 있으며, 각각 특정한 방식으로 요소를 선택할 수 있다.

## 1. 기본 선택자

### Type 선택자 (태그 선택자)
특정 HTML 태그 이름을 사용하여 해당 요소를 선택한다.
```css
p {
  color: blue;
}
```
위 코드는 모든 `<p>` 요소의 글자 색상을 파란색으로 변경한다.

### ID 선택자
`#` 기호를 사용하여 특정 `id` 속성을 가진 요소를 선택한다.
```css
#header {
  background-color: lightgray;
}
```
위 코드는 `id="header"`인 요소의 배경색을 연한 회색으로 변경한다.

### Class 선택자
`.` 기호를 사용하여 특정 `class` 속성을 가진 요소를 선택한다.
```css
.button {
  font-weight: bold;
}
```
위 코드는 `class="button"`을 가진 요소의 글자를 굵게 만든다.

### Universal 선택자 (전체 선택자)
`*` 기호를 사용하여 모든 요소를 선택한다.
```css
* {
  margin: 0;
  padding: 0;
}
```
위 코드는 모든 요소의 `margin`과 `padding`을 0으로 설정한다.

## 2. 그룹 선택자

### Grouping 선택자 (그룹 선택자)
쉼표(`,`)를 사용하여 여러 요소를 한 번에 선택할 수 있다.
```css
h1, h2, h3 {
  color: green;
}
```
위 코드는 `<h1>`, `<h2>`, `<h3>` 요소의 글자 색상을 초록색으로 변경한다.

### Descendant 선택자 (하위 선택자)
공백을 사용하여 특정 요소의 모든 하위 요소를 선택한다.
```css
div p {
  color: red;
}
```
위 코드는 `<div>` 내부의 모든 `<p>` 요소의 글자 색상을 빨간색으로 변경한다.

### Child 선택자 (자식 선택자)
`>` 기호를 사용하여 특정 요소의 직계 자식만 선택한다.
```css
div > p {
  color: blue;
}
```
위 코드는 `<div>`의 **직계 자식** `<p>` 요소만 선택하여 글자 색상을 파란색으로 변경한다.

### Next Sibling 선택자 (인접 형제 선택자)
`+` 기호를 사용하여 특정 요소의 **바로 다음 형제 요소**를 선택한다.
```css
h1 + p {
  font-style: italic;
}
```
위 코드는 `<h1>` 다음에 오는 `<p>` 요소의 글꼴을 기울인다.

### General Sibling 선택자 (일반 형제 선택자)
`~` 기호를 사용하여 특정 요소의 **모든 형제 요소**를 선택한다.
```css
h1 ~ p {
  color: gray;
}
```
위 코드는 `<h1>` 이후의 모든 `<p>` 요소의 글자 색상을 회색으로 변경한다.

## 3. 속성 선택자 (Attribute Selector)

### 특정 속성이 있는 요소 선택
```css
input[type="text"] {
  border: 1px solid black;
}
```
위 코드는 `type="text"`인 `<input>` 요소에 테두리를 추가한다.

### 특정 속성값을 포함하는 요소 선택
```css
a[href*="example"] {
  color: orange;
}
```
위 코드는 `href` 속성에 `"example"`이 포함된 모든 `<a>` 요소의 글자 색상을 주황색으로 변경한다.

## 4. 가상 클래스 선택자 (Pseudo-Class)

### 링크 상태 선택자
```css
a:link {
  color: blue;
}
a:visited {
  color: purple;
}
a:hover {
  text-decoration: underline;
}
a:active {
  color: red;
}
```
- `:link` → 방문하지 않은 링크
- `:visited` → 방문한 링크
- `:hover` → 마우스를 올린 상태
- `:active` → 클릭한 상태

### 위치 기반 선택자
```css
li:nth-child(2) {
  color: red;
}
li:first-child {
  font-weight: bold;
}
li:last-child {
  font-style: italic;
}
```
- `:nth-child(n)` → n번째 자식을 선택
- `:first-child` → 첫 번째 자식 선택
- `:last-child` → 마지막 자식 선택

## 5. 가상 요소 선택자 (Pseudo-Element)

### `::before` & `::after`
```css
p::before {
  content: "★ ";
}
p::after {
  content: " ★";
}
```
- `::before` → 요소 앞에 콘텐츠 추가
- `::after` → 요소 뒤에 콘텐츠 추가

### `::first-letter` & `::first-line`
```css
p::first-letter {
  font-size: 2em;
  color: red;
}
p::first-line {
  font-weight: bold;
}
```
- `::first-letter` → 첫 글자 스타일 변경
- `::first-line` → 첫 줄 스타일 변경

### `::marker` (목록 기호 스타일링)
```css
li::marker {
  color: blue;
  font-size: 1.2em;
}
```
- `::marker` → 리스트 아이템의 마커(`•`, `1.` 등) 스타일 변경

### `::selection` (선택된 텍스트 스타일링)
```css
::selection {
  background-color: yellow;
  color: black;
}
```
- `::selection` → 사용자가 선택한 텍스트의 스타일 변경

## 6. 정리

| 선택자 유형 | 설명 |
|------------|------|
| **Type** | 특정 태그 이름으로 선택 |
| **ID** | 특정 `id` 값을 가진 요소 선택 (`#id`) |
| **Class** | 특정 `class` 값을 가진 요소 선택 (`.class`) |
| **Universal** | 모든 요소 선택 (`*`) |
| **Grouping** | 여러 요소를 동시에 선택 (`h1, h2, h3`) |
| **Descendant** | 특정 요소 내부의 모든 자손 선택 (`div p`) |
| **Child** | 특정 요소의 직계 자식 선택 (`div > p`) |
| **Next Sibling** | 특정 요소의 다음 형제 선택 (`h1 + p`) |
| **General Sibling** | 특정 요소의 모든 형제 선택 (`h1 ~ p`) |
| **Attribute** | 특정 속성을 가진 요소 선택 (`input[type="text"]`) |
| **Pseudo-Class** | 요소의 특정 상태 선택 (`:hover`, `:first-child`, `:nth-child(n)`) |
| **Pseudo-Element** | 요소 내부의 특정 부분 선택 (`::before`, `::first-letter`, `::selection`) |

CSS 선택자는 웹 페이지의 스타일을 세밀하게 조정하는 강력한 도구이며, 다양한 조합을 통해 복잡한 디자인 요구를 충족할 수 있다.

---

# CSS 스타일 적용 방법과 우선순위

CSS는 여러 가지 방법으로 웹 페이지에 스타일을 적용할 수 있으며, 각각의 방법은 특정한 **우선순위(Priority)** 를 가진다. 또한 **특정성(Specificity)** 과 **계층 구조(Hierarchy)** 를 통해 최종적으로 어떤 스타일이 적용될지 결정된다.

## 1. CSS 스타일 적용 방법

### 1.1 External Style Sheet (외부 스타일 시트)
별도의 `.css` 파일을 만들어 `<link>` 태그로 연결하여 스타일을 적용하는 방법이다.

- **장점**:
  - 여러 HTML 문서에서 같은 스타일을 공유할 수 있어 유지보수가 용이함.
  - HTML과 스타일을 분리하여 코드 가독성을 높일 수 있음.
- **단점**:
  - 별도의 파일을 불러와야 하므로 네트워크 속도에 영향을 받을 수 있음.

```html
<!-- HTML 문서에서 외부 CSS 파일을 연결 -->
<link rel="stylesheet" href="styles.css">
```

```css
/* styles.css */
p {
  color: blue;
  font-size: 16px;
}
```

### 1.2 Internal Style Sheet (내부 스타일 시트)
HTML 문서 내 `<style>` 태그를 사용하여 스타일을 적용하는 방법이다.

- **장점**:
  - 외부 CSS 파일이 필요하지 않으므로 빠르게 로드됨.
  - 특정 HTML 파일에만 스타일을 적용할 때 유용함.
- **단점**:
  - 여러 HTML 파일에서 동일한 스타일을 사용할 경우 중복 작성해야 함.
  - HTML과 CSS가 섞여 가독성이 떨어질 수 있음.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <style>
    p {
      color: green;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <p>이것은 내부 스타일 시트입니다.</p>
</body>
</html>
```

### 1.3 Inline Style (인라인 스타일)
HTML 요소의 `style` 속성을 사용하여 직접 스타일을 적용하는 방법이다.

- **장점**:
  - 특정 요소에만 빠르게 스타일을 적용할 수 있음.
  - 외부 CSS 파일 없이 간단한 수정이 가능함.
- **단점**:
  - 코드가 지저분해지고 유지보수가 어려움.
  - 스타일을 여러 요소에 적용하려면 중복 코드가 발생함.

```html
<p style="color: red; font-size: 20px;">이것은 인라인 스타일입니다.</p>
```

### 1.4 Web Browser Default Value (웹 브라우저 기본 스타일)
웹 브라우저는 HTML 요소에 기본 스타일을 적용한다. 예를 들어:

```css
body {
  margin: 8px;
}

h1 {
  font-size: 2em;
  font-weight: bold;
}

p {
  margin-top: 16px;
  margin-bottom: 16px;
}
```

기본 스타일을 제거하고 싶은 경우 다음과 같이 `reset` 또는 `normalize` CSS를 사용할 수 있다.

```css
/* 기본 스타일 제거 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## 2. CSS 우선순위(Priority)와 특정성(Specificity)

CSS 스타일이 여러 곳에서 정의되었을 때 어떤 스타일이 적용될지를 결정하는 요소는 **우선순위(Priority)**, **특정성(Specificity)**, 그리고 **계층 구조(Hierarchy)** 이다.

### 2.1 우선순위 (Priority)
아래 순서대로 스타일이 적용되며, **아래에 위치할수록 높은 우선순위를 가진다.**
1. **웹 브라우저 기본 스타일** (가장 낮음)
2. **외부 스타일 시트 (External)**
3. **내부 스타일 시트 (Internal)**
4. **인라인 스타일 (Inline)**
5. **`!important` 키워드 사용** (가장 높음)

```css
p {
  color: blue !important;  /* 최우선 적용 */
}

p {
  color: green;  /* 적용되지 않음 */
}
```

### 2.2 특정성 (Specificity)
특정성이 높을수록 우선적으로 적용된다. 특정성은 아래 기준으로 점수를 계산할 수 있다.

| 선택자 유형 | 특정성 점수 |
|------------|------------|
| 태그 선택자 (`p`, `div`) | 1점 |
| 클래스 선택자 (`.class`) | 10점 |
| ID 선택자 (`#id`) | 100점 |
| 인라인 스타일 (`style="color: red;"`) | 1000점 |
| `!important` 키워드 | 무조건 최우선 |

#### 특정성 예제:
```css
p { color: black; }          /* 특정성: 1 */
.class-name { color: blue; } /* 특정성: 10 */
#id-name { color: red; }     /* 특정성: 100 */
```

적용 결과:
- `#id-name`이 가장 높은 특정성을 가지므로 **빨간색**이 적용됨.

### 2.3 계층 구조 (Hierarchy)
CSS는 **계층적(Cascading)** 으로 적용되며, 동일한 특정성을 가진 스타일이 여러 개 있다면 **나중에 작성된 스타일이 적용된다.**

```css
p {
  color: black;
}

p {
  color: green; /* 마지막에 선언되어 적용됨 */
}
```

결과적으로 **초록색**이 적용된다.

## 3. 정리

| 개념 | 설명 |
|------|------|
| **External Style Sheet** | 별도의 `.css` 파일에서 스타일을 정의하고 `<link>` 태그로 불러옴 |
| **Internal Style Sheet** | HTML 문서 내부의 `<style>` 태그에 스타일을 작성 |
| **Inline Style** | 개별 HTML 요소에 `style` 속성을 사용하여 직접 스타일 지정 |
| **Web Browser Default Value** | 브라우저가 기본적으로 적용하는 스타일 |
| **Priority (우선순위)** | `!important` > 인라인 스타일 > 내부 스타일 시트 > 외부 스타일 시트 > 브라우저 기본값 |
| **Specificity (특정성)** | `ID (100점) > Class (10점) > 태그 (1점)` |
| **Hierarchy (계층 구조)** | 동일한 특정성을 가진 스타일이 여러 개 있다면, **나중에 선언된 스타일이 적용됨** |

이러한 개념을 이해하면 CSS를 더욱 정밀하게 제어할 수 있으며, 스타일 충돌을 방지할 수 있다.

---

# CSS Properties - Background 관련 속성

CSS에서 `background` 관련 속성들은 요소의 배경을 설정하는 데 사용된다. 이 문서에서는 **배경색, 배경 이미지, 배경 크기, 반복 여부, 위치 등**을 설정하는 주요 속성을 설명한다.

## 1. `background` (Shorthand Property)

`background` 속성은 여러 배경 관련 속성을 한 번에 설정할 수 있는 단축 속성이다.

```css
body {
  background: #ffcc00 url("background.jpg") no-repeat center fixed;
}
```

위의 예제는 아래의 속성을 한 번에 설정한 것이다.
- `background-color: #ffcc00;`
- `background-image: url("background.jpg");`
- `background-repeat: no-repeat;`
- `background-position: center;`
- `background-attachment: fixed;`

## 2. `background-attachment`

배경 이미지가 스크롤과 함께 움직일지 고정될지를 설정하는 속성이다.

| 값 | 설명 |
|----|------|
| `scroll` | 기본값, 배경이 스크롤됨 |
| `fixed` | 배경이 고정됨 |
| `local` | 요소의 내용과 함께 배경이 스크롤됨 |

```css
body {
  background-attachment: fixed;
}
```

## 3. `background-color`

배경 색상을 지정하는 속성이다. 다양한 방식으로 표현할 수 있다.

### 3.1 색상명을 이용한 표현 (Express by Text)
```css
body {
  background-color: red;
}
```

### 3.2 16진수(HEX) 값으로 표현 (Express Hexadecimals)
```css
body {
  background-color: #ff0000;
}
```

### 3.3 RGB 값을 이용한 표현 (Express by 10 Digits)
```css
body {
  background-color: rgb(255, 0, 0);
}
```

### 3.4 퍼센트(%)를 이용한 표현 (Express by Percent)
```css
body {
  background-color: rgba(100%, 0%, 0%, 1);
}
```

### 3.5 투명도 설정 (Opacity)
```css
body {
  background-color: rgba(255, 0, 0, 0.5); /* 반투명 빨간색 */
}
```

## 4. `background-image`

배경 이미지를 설정하는 속성이다.

```css
body {
  background-image: url("image.jpg");
}
```

- `none`: 배경 이미지 없음 (기본값)
- `url("이미지경로")`: 배경 이미지 적용

## 5. `background-position`

배경 이미지의 위치를 설정하는 속성이다.

```css
body {
  background-position: center top;
}
```

| 값 | 설명 |
|----|------|
| `left top` | 왼쪽 상단 |
| `center center` | 중앙 정렬 |
| `right bottom` | 오른쪽 하단 |
| `50% 50%` | 가로 50%, 세로 50% 위치 |

## 6. `background-repeat`

배경 이미지의 반복 여부를 설정하는 속성이다.

```css
body {
  background-repeat: no-repeat;
}
```

| 값 | 설명 |
|----|------|
| `repeat` | 기본값, 배경 이미지를 반복 |
| `no-repeat` | 배경 이미지를 한 번만 표시 |
| `repeat-x` | 가로 방향으로만 반복 |
| `repeat-y` | 세로 방향으로만 반복 |

## 7. `background-size`

배경 이미지의 크기를 조절하는 속성이다.

```css
body {
  background-size: cover;
}
```

| 값 | 설명 |
|----|------|
| `auto` | 기본값, 원본 크기로 표시 |
| `cover` | 요소의 전체 크기에 맞게 조정 (비율 유지) |
| `contain` | 요소에 맞게 배경 이미지를 조정 (비율 유지) |
| `100px 200px` | 가로 100px, 세로 200px 크기로 조정 |
| `50% 50%` | 요소 크기의 50%만큼 설정 |

---

# CSS Properties - Text 관련 속성

CSS에서 텍스트와 관련된 속성들은 웹 페이지의 가독성을 높이고, 다양한 스타일을 적용하는 데 사용된다.  
이 문서에서는 **색상, 방향, 간격, 정렬, 장식, 그림자, 변형 등**과 관련된 속성을 설명한다.

## 1. `color`
텍스트의 색상을 설정하는 속성이다.

```css
p {
  color: blue;
}
```

- 색상명 (`red`, `blue` 등)
- 16진수 (`#ff0000`)
- RGB (`rgb(255, 0, 0)`)
- RGBA (`rgba(255, 0, 0, 0.5)`, 투명도 포함)

## 2. `direction`
텍스트의 읽기 방향을 설정하는 속성이다.

```css
p {
  direction: rtl;
}
```

| 값 | 설명 |
|----|------|
| `ltr` | 기본값, 왼쪽에서 오른쪽(LTR) 방향 |
| `rtl` | 오른쪽에서 왼쪽(RTL) 방향 |

## 3. `letter-spacing`
글자 간격을 조정하는 속성이다.

```css
p {
  letter-spacing: 2px;
}
```

- `normal`: 기본값
- `2px`: 글자 간격을 2px로 설정

## 4. `line-height`
줄 간격을 설정하는 속성이다.

```css
p {
  line-height: 1.5;
}
```

- `normal`: 기본값
- `1.5`: 글자 크기의 1.5배 높이

## 5. `text-align`
텍스트 정렬을 설정하는 속성이다.

```css
p {
  text-align: center;
}
```

| 값 | 설명 |
|----|------|
| `left` | 왼쪽 정렬 (기본값) |
| `center` | 가운데 정렬 |
| `right` | 오른쪽 정렬 |
| `justify` | 양쪽 정렬 |

## 6. `text-decoration`
텍스트의 장식을 설정하는 속성이다.

```css
p {
  text-decoration: underline;
}
```

| 값 | 설명 |
|----|------|
| `none` | 기본값, 장식 없음 |
| `underline` | 밑줄 표시 |
| `overline` | 위쪽 선 표시 |
| `line-through` | 취소선 표시 |

## 7. `text-indent`
첫 줄 들여쓰기를 설정하는 속성이다.

```css
p {
  text-indent: 20px;
}
```

- `20px`: 첫 줄을 20px 들여쓰기

## 8. `text-shadow`
텍스트에 그림자를 추가하는 속성이다.

```css
p {
  text-shadow: 2px 2px 5px gray;
}
```

| 값 | 설명 |
|----|------|
| `2px` | 그림자의 가로 위치 |
| `2px` | 그림자의 세로 위치 |
| `5px` | 그림자의 흐림 정도 |
| `gray` | 그림자 색상 |

## 9. `text-transform`
텍스트의 대소문자를 변환하는 속성이다.

```css
p {
  text-transform: uppercase;
}
```

| 값 | 설명 |
|----|------|
| `none` | 변환 없음 (기본값) |
| `uppercase` | 모든 문자 대문자로 변환 |
| `lowercase` | 모든 문자 소문자로 변환 |
| `capitalize` | 각 단어의 첫 글자를 대문자로 변환 |

## 10. `text-decoration-line`
텍스트 장식을 추가하는 속성이다.

```css
p {
  text-decoration-line: underline;
}
```

| 값 | 설명 |
|----|------|
| `none` | 장식 없음 |
| `underline` | 밑줄 표시 |
| `overline` | 위쪽 선 표시 |
| `line-through` | 취소선 표시 |

---

# CSS Properties - Font 관련 속성

CSS의 `font` 속성들은 텍스트의 **서체, 크기, 스타일, 두께** 등을 설정하는 데 사용된다.  
이 문서에서는 **폰트 관련 주요 속성**과 **단축 속성(Shorthand)**에 대해 설명한다.

## 1. `font`
`font` 속성은 개별적인 **폰트 관련 속성을 한 번에 설정**할 수 있는 단축 속성이다.

```css
p {
  font: italic small-caps bold 16px/1.5 "Arial", sans-serif;
}
```

위의 설정은 아래와 동일하다.
- `font-style: italic;`
- `font-variant: small-caps;`
- `font-weight: bold;`
- `font-size: 16px;`
- `line-height: 1.5;`
- `font-family: "Arial", sans-serif;`

**사용법**
```css
font: [font-style] [font-variant] [font-weight] [font-size]/[line-height] [font-family];
```

## 2. `font-family`
글꼴(서체)을 설정하는 속성이다. 여러 개를 입력할 경우, 앞쪽 폰트가 없으면 뒤쪽 폰트를 대체한다.

```css
p {
  font-family: "Arial", "Helvetica", sans-serif;
}
```

- `"Arial"`, `"Helvetica"`: 우선적으로 적용될 폰트
- `sans-serif`: 모든 폰트가 없을 경우 기본 sans-serif 폰트 사용

## 3. `font-size`
폰트의 크기를 설정하는 속성이다.

```css
p {
  font-size: 20px;
}
```

### (1) 단위 종류 (Units of Font)
| 단위 | 설명 |
|------|------|
| `px` | 픽셀 단위 (고정 크기) |
| `pt` | 포인트 단위 (인쇄물에서 많이 사용) |
| `%` | 부모 요소 대비 백분율 |
| `em` | 부모 요소의 폰트 크기 배율 (`1em = 부모 크기와 동일`) |
| `vw` | 화면 너비(Viewport Width)의 백분율 |

### 예제
```css
p {
  font-size: 150%; /* 부모 크기의 150% */
}

h1 {
  font-size: 2em; /* 부모 크기의 2배 */
}

h2 {
  font-size: 5vw; /* 화면 너비의 5% */
}
```

## 4. `font-style`
폰트의 스타일을 지정하는 속성이다.

```css
p {
  font-style: italic;
}
```

| 값 | 설명 |
|----|------|
| `normal` | 기본 스타일 |
| `italic` | 이탤릭체 (기울어진 글꼴) |
| `oblique` | 글자를 기울임 (기울어진 형태의 일반 글꼴) |

## 5. `font-weight`
폰트의 굵기를 설정하는 속성이다.

```css
p {
  font-weight: bold;
}
```

| 값 | 설명 |
|----|------|
| `normal` | 기본값 (보통 굵기) |
| `bold` | 굵은 글씨 |
| `lighter` | 부모 요소보다 가는 글씨 |
| `bolder` | 부모 요소보다 굵은 글씨 |
| `100 ~ 900` | 폰트의 굵기를 100~900 사이로 설정 (100: 가장 얇음, 900: 가장 굵음) |

**예제**
```css
h1 {
  font-weight: 900; /* 매우 굵게 */
}

h2 {
  font-weight: 300; /* 얇게 */
}
```

## 6. Font Shorthand (단축 속성)

`font` 속성을 사용하면 여러 폰트 속성을 **한 줄로 설정**할 수 있다.

```css
p {
  font: italic bold 20px/1.5 "Arial", sans-serif;
}
```

**속성 순서**
1. `font-style` (선택 사항)
2. `font-variant` (선택 사항)
3. `font-weight` (선택 사항)
4. `font-size` (필수)
5. `/line-height` (선택 사항)
6. `font-family` (필수)

## 정리

- `font-family`로 **서체 지정**
- `font-size`와 `font-weight`로 **크기와 굵기 조절**
- `font-style`로 **이탤릭 등 스타일 적용**
- `font` 단축 속성으로 **효율적인 설정 가능**

---

# CSS Properties - Table 관련 속성

CSS에서 테이블(`table`)의 스타일을 조정하는 다양한 속성이 있다.  
이 문서에서는 **테두리, 크기, 간격, 정렬, 캡션 위치 등**과 관련된 속성을 설명한다.

## 1. `border`
테이블 및 셀(`td`, `th`)의 테두리를 설정하는 속성이다.

```css
table, th, td {
  border: 1px solid black;
}
```

| 값 | 설명 |
|----|------|
| `border-width` | 테두리 두께 지정 (예: `1px`) |
| `border-style` | 테두리 스타일 지정 (`solid`, `dashed`, `dotted` 등) |
| `border-color` | 테두리 색상 지정 (`black`, `red` 등) |

## 2. `border-collapse`
셀 테두리 간격을 설정하는 속성이다.

```css
table {
  border-collapse: collapse;
}
```

| 값 | 설명 |
|----|------|
| `collapse` | 인접한 테두리를 하나로 합침 |
| `separate` | 기본값, 각 셀의 테두리를 개별적으로 유지 |

## 3. `width`
테이블 또는 셀의 너비를 설정하는 속성이다.

```css
table {
  width: 80%;
}
```

| 값 | 설명 |
|----|------|
| `px` | 고정 크기 (예: `500px`) |
| `%` | 부모 요소 대비 백분율 (예: `80%`) |

## 4. `height`
테이블 또는 셀의 높이를 설정하는 속성이다.

```css
table {
  height: 300px;
}
```

- `px` 또는 `%` 단위 사용 가능

## 5. `border-spacing`
셀 사이의 간격을 조정하는 속성이다.  
(`border-collapse: separate`일 때만 적용됨)

```css
table {
  border-spacing: 10px;
}
```

| 값 | 설명 |
|----|------|
| `px` | 셀 간격을 픽셀 단위로 지정 |
| `0` | 간격 없음 |

## 6. `empty-cells`
비어 있는 셀의 테두리 표시 여부를 결정하는 속성이다.

```css
table {
  empty-cells: hide;
}
```

| 값 | 설명 |
|----|------|
| `show` | 기본값, 빈 셀에도 테두리 표시 |
| `hide` | 빈 셀의 테두리를 숨김 |

## 7. `table-align`
테이블을 페이지 내에서 정렬하는 속성이다.  
(`table` 요소에는 `margin`을 활용하여 정렬 가능)

```css
table {
  margin-left: auto;
  margin-right: auto;
}
```

| 값 | 설명 |
|----|------|
| `left` | 왼쪽 정렬 (`margin-right: auto;`) |
| `center` | 가운데 정렬 (`margin-left: auto; margin-right: auto;`) |
| `right` | 오른쪽 정렬 (`margin-left: auto;`) |

## 8. `caption-side`
테이블 제목(`<caption>`)의 위치를 설정하는 속성이다.

```css
caption {
  caption-side: bottom;
}
```

| 값 | 설명 |
|----|------|
| `top` | 기본값, 테이블 위쪽에 위치 |
| `bottom` | 테이블 아래쪽에 위치 |

---

# CSS Properties - List 관련 속성

CSS에서 목록(`list`)의 스타일을 조정하는 다양한 속성이 있다.  
이 문서에서는 **목록 유형, 배경색, 리스트 아이템 마커(custom marker)** 등을 설정하는 방법을 설명한다.

## 1. `list-style-type`
목록의 아이템 앞에 표시되는 마커(marker) 유형을 설정하는 속성이다.

```css
ul {
  list-style-type: square;
}

ol {
  list-style-type: upper-roman;
}
```

### (1) `ul` (순서 없는 목록)
| 값 | 설명 |
|----|------|
| `disc` | ● 기본값 (채워진 원) |
| `circle` | ○ 빈 원 |
| `square` | ■ 채워진 정사각형 |
| `none` | 마커 없음 |

### (2) `ol` (순서 있는 목록)
| 값 | 설명 |
|----|------|
| `decimal` | 1, 2, 3, ... (기본값) |
| `decimal-leading-zero` | 01, 02, 03, ... |
| `lower-roman` | i, ii, iii, iv, ... |
| `upper-roman` | I, II, III, IV, ... |
| `lower-alpha` | a, b, c, ... |
| `upper-alpha` | A, B, C, ... |

## 2. Add Background Colors to Lists and List Items
목록 자체(`ul`, `ol`) 또는 개별 아이템(`li`)에 배경색을 추가할 수 있다.

```css
ul {
  background-color: lightgray;
}

li {
  background-color: lightblue;
  padding: 5px;
  margin: 2px;
}
```

- `ul`의 배경색은 전체 목록에 적용됨
- `li`의 배경색은 개별 목록 항목에 적용됨

## 3. Set an Image as the List Item Marker
기본 마커 대신 **이미지를 리스트 마커로 설정**할 수 있다.

```css
ul {
  list-style-image: url("marker.png");
}
```

**단점:** `list-style-image`는 크기 조정이 어렵고, 배경 이미지와 함께 쓰는 경우 제어가 어려움.  
**대안:** `::before` 가상 요소를 활용하여 커스텀 마커를 추가할 수 있다.

```css
li::before {
  content: url("marker.png");
  margin-right: 10px;
}
```

## 4. Set Different List Item Markers for Unordered Lists
순서 없는 목록(`ul`)에서 **각 항목마다 다른 마커를 설정**할 수 있다.

```css
ul li:nth-child(1) {
  list-style-type: circle;
}

ul li:nth-child(2) {
  list-style-type: square;
}

ul li:nth-child(3) {
  list-style-type: disc;
}
```

- `nth-child(n)` 선택자를 사용하여 특정 항목에 개별 스타일 적용 가능

## 5. Set Different List Item Markers for Ordered Lists
순서 있는 목록(`ol`)에서 **각 항목마다 다른 마커를 설정**할 수 있다.

```css
ol li:nth-child(1) {
  list-style-type: decimal;
}

ol li:nth-child(2) {
  list-style-type: lower-roman;
}

ol li:nth-child(3) {
  list-style-type: upper-alpha;
}
```

- 첫 번째 항목 → `1, 2, 3, ...`
- 두 번째 항목 → `i, ii, iii, ...`
- 세 번째 항목 → `A, B, C, ...`

## 정리

- `list-style-type`으로 **마커 유형 변경**
- `list-style-image`로 **이미지 마커 설정 가능**
- `nth-child(n)`를 활용하여 **각 아이템별 다른 마커 적용 가능**
- `background-color`로 **목록 및 개별 아이템 배경색 지정 가능**