# directive 
---

## 디렉티브란?

- HTML 요소에 붙이는 **특수 속성**
- `v-`로 시작함
- 화면을 **조건에 따라 보여주거나**, **반복해서** 그리거나, **클릭 같은 이벤트**를 처리할 때 사용

---

## 조건부 렌더링 (보이기/숨기기)

### v-if
- **조건이 true일 때만** 해당 요소를 화면에 그림
- false면 **DOM에서 아예 제거**됨 (없는 것처럼 처리)
- 예: `v-if="isLoggedIn"` → 로그인했을 때만 보임

### v-else-if
- `v-if` 다음에 붙여서 **여러 조건**을 나눌 때 사용
- 위의 `v-if`가 false일 때만 이 조건을 검사함

### v-else
- `v-if` / `v-else-if`의 **그 외 모든 경우**에 해당할 때 사용
- 조건식을 쓰지 않음

### v-show
- **조건이 true일 때만** 보이고, false면 `display: none`으로 숨김
- DOM에는 남아 있음 (그냥 안 보일 뿐)
- 자주 켜고 끄는 경우에 `v-if`보다 적합

---

## 리스트 렌더링 (반복)

### v-for
- **배열이나 객체를 반복**해서 같은 구조를 여러 번 그림
- 예: `v-for="item in items"` → items 배열의 각 항목마다 한 번씩 렌더링
- 리스트를 만들 때 가장 많이 사용

### v-for 문법 정리 ([List Rendering](https://vuejs.org/guide/essentials/list.html))

| 문법 | 설명 | 예시 |
|------|------|------|
| `item in items` | 배열 반복 | `v-for="hobby in hobbies"` |
| `(item, index) in items` | 인덱스도 함께 사용 | `v-for="(hobby, i) in hobbies"` |
| `value in object` | 객체의 값 반복 | `v-for="value in myObject"` |
| `(value, key) in object` | 객체의 키와 값 | `v-for="(value, key) in myObject"` |
| `n in 10` | 1부터 10까지 숫자 반복 | `v-for="n in 10"` → 1,2,3...10 |

### :key (필수에 가깝게 쓰기)

- `v-for`로 그릴 때 **각 항목을 구분**하기 위해 `:key`를 붙임
- Vue가 요소를 추적해서 **재사용·정렬**을 올바르게 함
- `:key="item.id"` 처럼 **고유한 값** (문자열, 숫자)을 써야 함. 객체는 X

### v-for와 v-if 같이 쓸 때

- **같은 요소에** `v-for`와 `v-if`를 같이 쓰면 안 됨 (v-if가 먼저 적용됨)
- **해결**: `<template v-for="...">`로 감싼 뒤, 안쪽에 `v-if` 붙이기
- **필터링**이 필요하면 `computed`로 필터된 배열을 만든 뒤 `v-for`에 넣기

### 참고 링크

- [List Rendering](https://vuejs.org/guide/essentials/list.html)

---

## 이벤트 / 속성 바인딩

### v-on
- **클릭, 입력, 마우스 오버** 같은 이벤트가 일어났을 때 실행할 함수를 연결
- 예: `v-on:click="handleClick"` → 클릭하면 handleClick 실행
- `@click`처럼 짧게 쓸 수 있음

### v-bind
- HTML **속성**에 data 값을 연결할 때 사용
- 예: `v-bind:src="imageUrl"` → src에 imageUrl 값이 들어감
- `:src`처럼 짧게 쓸 수 있음

### v-model
- **입력값과 data를 양방향으로 연결**
- input에 입력하면 data가 바뀌고, data를 바꾸면 input 값도 바뀜
- 폼 입력 처리할 때 자주 사용

---

## v-if vs v-show 차이

| 구분 | v-if | v-show |
|------|------|--------|
| false일 때 | DOM에서 **제거** | `display: none` (DOM은 유지) |
| 자주 토글할 때 | 비효율적 | 적합 |
| 처음 렌더 비용 | 낮음 | 높음 (항상 렌더 후 숨김) |

---

## 폼 입력 처리 (v-model)

### v-model
- **입력 요소(input, textarea, select)** 와 data를 **양방향으로 연결**
- 사용자가 입력하면 data가 바뀌고,
- data가 바뀌면 입력값도 자동으로 갱신됨
- 폼 입력 처리에서 가장 많이 사용되는 디렉티브

