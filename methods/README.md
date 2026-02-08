# methods - Options API에서 함수 정의

## 이 폴더에서 다루는 것

- **methods** : 컴포넌트에서 쓸 함수들을 정의
- template 에서 `{{ greeting() }}` 처럼 호출하거나, `@click="increment"` 처럼 이벤트에 연결

## 핵심

- `this.userName1` 처럼 data 에 접근할 때는 `this` 사용
- 클릭 시 실행만 할 때는 `@click="increment"` (괄호 없이 메서드 이름만)
