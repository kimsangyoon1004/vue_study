# Vue.js 기본 개념
---

## 1. Vue.js 기본 정보

| 항목 | 내용 |
|------|------|
| **창시자** | Evan You (에반 유) |
| **공개 시기** | 2014년 2월 (개인 사이드 프로젝트로 시작) |
| **배경** | Google 재직 시 Angular의 데이터 바인딩에 영감을 받았으나, 더 가벼운 대안이 필요해 만듦 |
| **현재** | 전 세계 개발자들이 유지보수, Evan You가 프로젝트 리드 |

---

## 2. Vue란?

- **프로그레시브(Progressive) JavaScript 프레임워크**
- 점진적으로 도입 가능 (일부 페이지만 Vue 적용 가능)
- SPA(Single Page Application) 구축에 적합

### Vue의 두 가지 핵심 기능

| 기능 | 설명 |
|------|------|
| **선언적 렌더링 (Declarative Rendering)** | HTML을 확장한 템플릿 문법으로, JavaScript 상태에 따라 화면을 **선언적으로** 표현 |
| **반응성 (Reactivity)** | JavaScript 상태 변경을 자동으로 추적하고, 변경 시 DOM을 효율적으로 갱신 |

### 프로그레시브 프레임워크

Vue는 상황에 따라 다양한 방식으로 사용할 수 있음:

- 빌드 없이 정적 HTML에 점진적으로 적용
- Web Components로 임베딩
- SPA (Single-Page Application)
- Fullstack / SSR (Server-Side Rendering)
- Jamstack / SSG (Static Site Generation)
- 데스크톱, 모바일, WebGL, 터미널 등

### SFC (Single-File Component)

- **`.vue` 파일** 하나에 로직(JS), 템플릿(HTML), 스타일(CSS)을 함께 작성
- 빌드 도구를 쓰는 프로젝트에서는 **권장되는** 컴포넌트 작성 방식
- `App.vue` 같은 파일이 SFC 예시

---

## 3. Options API vs Composition API

| 구분 | Options API | Composition API |
|------|-------------|-----------------|
| 스타일 | `data`, `methods`, `computed` 등 옵션별로 분리 | `setup()` 안에서 로직을 한곳에 |
| 특징 | Vue 2부터 사용, 직관적 | Vue 3 권장, 로직 재사용에 유리 |

### Options API 

- **`data()`** : 반응형 데이터 정의 (객체 return)
- **`methods`** : 함수들 정의
- **`computed`** : 계산된 값 (캐싱됨)
- **`watch`** : 특정 데이터 감시해서 변경 시 실행
- **`mounted`, `created`** : 생명주기 훅

→ 옵션별로 **나누어서** 작성. "데이터는 data, 함수는 methods" 식으로 역할이 분리됨.

### Composition API 

- **`ref()`** : 기본형(숫자, 문자열 등) 반응형 데이터. `.value`로 접근
- **`reactive()`** : 객체 반응형 데이터. `.value` 없이 바로 접근
- **`computed()`** : 계산된 값
- **`watch()`** : 특정 값 감시
- **`onMounted()`** : 마운트 시 실행
- **`provide()` / `inject()`** : 부모→자식 데이터 전달 (의존성 주입)

→ `setup()` 안에서 **한곳에** 모아서 작성. `ref`, `reactive`로 반응형 만들고, 로직을 함수로 묶어서 재사용하기 쉬움.

### Composition API의 장점 ([FAQ](https://vuejs.org/guide/extras/composition-api-faq.html))

| 장점 | 설명 |
|------|------|
| **로직 재사용** | Composable 함수로 깔끔하게 재사용 (mixins 대체) |
| **코드 구성** | 같은 관심사의 코드를 한곳에 모을 수 있음 |
| **TypeScript** | 타입 추론이 잘 됨 |
| **번들 크기** | Options API보다 작고 압축에 유리 |

### Options API는 없어질까?

**아니요.** Options API는 Vue의 핵심이고, 단순한 프로젝트에서는 여전히 좋은 선택.

### 참고 링크

- [Introduction](https://vuejs.org/guide/introduction.html)
- [Composition API FAQ](https://vuejs.org/guide/extras/composition-api-faq.html)

---




