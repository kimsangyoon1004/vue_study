# defineEmits - 자식 → 부모 이벤트 알리기

## 이 폴더에서 다루는 것

- **defineEmits** : 자식이 부모에게 "이벤트"를 보낼 수 있게 선언
- 자식: `emit('customEvent', '메시지')` → 부모: `@customEvent="handleCustomEvent"` 에서 메시지 받음

## 핵심

- 자식에서 **emit('이벤트이름', 인자1, 인자2...)** 호출
- 부모에서 **@이벤트이름="핸들러"** 로 받고, 핸들러의 첫 번째 인자로 넘긴 값이 들어옴
- props 는 부모→자식, emit 은 자식→부모 소통
