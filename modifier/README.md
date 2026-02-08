# 이벤트 수정자 (Event Modifier)

## 이 폴더에서 다루는 것

- **.once** : 해당 이벤트를 한 번만 실행 (두 번째부터 무시)
- **.prevent** : `event.preventDefault()` (기본 동작 막기, 예: form 제출)
- **.stop** : `event.stopPropagation()` (버블링 막기)
- **키 수정자** : `.enter`, `.s` 등 → 해당 키를 눌렀을 때만 핸들러 실행

## 예시

- `@click.once="fn"` → 클릭은 한 번만
- `@submit.prevent="fn"` → form 제출 시 페이지 이동 안 함
- `@keydown.enter="fn"` → Enter 키 눌렀을 때만
