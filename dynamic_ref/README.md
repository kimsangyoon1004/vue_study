# v-bind 로 class 동적 바인딩

## 이 폴더에서 다루는 것

- **:class="변수"** : data(또는 ref) 값에 따라 적용되는 class 를 바꿈
- 클릭 등으로 변수만 바꿔도 스타일이 바뀜

## 핵심

- `:class="titleClass"` → titleClass 가 `''` 이면 class 없음, `'title'` 이면 `.title` 스타일 적용
- 여러 class 를 조건부로 줄 때는 객체/배열 문법도 있음 (Vue 문서 참고)
