# defineProps - 부모 → 자식 데이터 전달

## 이 폴더에서 다루는 것

- **defineProps** : 자식 컴포넌트가 부모로부터 받을 "props" 를 선언
- 부모: `<Child :title="post.title" />` → 자식: `props.title` 로 사용

## 핵심

- 부모는 **:속성명="값"** 으로 넘기고, 자식은 **defineProps(['title', ...])** 또는 **defineProps({ title: { type: String, required: true } })** 로 받음
- props 는 읽기 전용. 자식에서 바꾸면 안 됨
