# Vue.js 기본 개념

> directive, components... 연습하면서 배운 내용을 여기에 정리합니다.

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

→ `setup()` 안에서 **한곳에** 모아서 작성. `ref`, `reactive`로 반응형 만들고, 로직을 함수로 묶어서 재사용하기 쉬움.

---




