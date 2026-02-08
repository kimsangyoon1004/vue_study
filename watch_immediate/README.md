# watch 옵션 - immediate, deep

## 이 폴더에서 다루는 것

- **immediate: true** : 마운트 직후에 콜백을 한 번 바로 실행 (초기값도 감지)
- **deep: true** : 객체 안의 속성이 바뀌어도 감지 (ref/reactive 객체 내부 변경)

## 사용 예

- `immediate` : 처음 로드 시에도 한 번 실행해야 할 때
- `deep` : `ref({ name, age })` 같은 객체의 `name` 이 바뀌는 것까지 감지할 때
