# watch - 값 변경 감시

## 이 폴더에서 다루는 것

- **watch(감시할대상, (newValue, oldValue) => { ... })** : 해당 값이 바뀔 때마다 콜백 실행
- "변경된 후"에 실행됨 (사이드 이펙트용)

## computed vs watch

- **computed** : "어떤 값으로부터 파생된 값"을 보여줄 때
- **watch** : "값이 바뀌었을 때 뭔가 하고 싶을 때" (API 호출, 로그 등)
