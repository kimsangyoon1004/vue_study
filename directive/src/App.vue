<script>
/**
 * Vue 컴포넌트 - Options API 방식
 * export default: 이 파일을 Vue 컴포넌트로 내보냄
 */
export default {
  // data(): 반응형 데이터를 정의하는 함수
  // - 함수로 작성하고, 객체를 return 해야 함
  // - 여기 넣은 값이 바뀌면 화면이 자동으로 갱신됨 (반응형)
  data() {
    return {
      name: "John Doe",
      age: 20,
      hobby: "tennis", // v-if, v-show 연습용
    }
  },
}
</script>

<template>
  <!--
    template: 화면에 보여줄 HTML 구조
    - Vue가 이 부분을 렌더링해서 사용자에게 보여줌
  -->
  <div>
    <!--
      Mustache(머스타치) 문법: {{ }}
      - data에 있는 값을 화면에 출력할 때 사용
      - {{ name }} → data의 name 값("John Doe")이 그 자리에 들어감
      - {{ age }}, {{ hobby }} 도 마찬가지
      - data가 바뀌면 {{ }} 안의 값도 자동으로 갱신됨
    -->
    <h1>이름: {{ name }}</h1>
    <h2>나이: {{ age }}</h2>
    <h3>취미: {{ hobby }}</h3>
  </div>
</template>

<style scoped></style>
