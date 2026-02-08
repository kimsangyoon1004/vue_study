# ref - Composition API 기초 (ref, reactive, computed)

## 이 폴더에서 다루는 것

- **ref()** : 숫자·문자열 같은 기본형을 반응형으로 만듦. script 안에서는 `.value`, template에서는 생략
- **reactive()** : 객체 전체를 반응형으로. `.value` 없이 속성만 접근
- **computed()** : 다른 반응형 값으로부터 계산된 값. 캐시됨

## 핵심

- `<script setup>` 은 Composition API. 반응형을 직접 `ref()`, `reactive()` 로 선언
- template 에서는 `ref` 는 자동으로 unwrap 되므로 `{{ cnt }}` 만 씀
