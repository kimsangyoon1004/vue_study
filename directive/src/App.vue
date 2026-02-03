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
      age: 10,
      hobbies: ["baseball", "tennis", "soccer"],
      count: 0,
      iconPath: '/favicon.ico',
      your_name: "",
    }
  },
}
</script>

<template>
  <!-- template: 화면에 보여줄 HTML 구조. Vue가 이 부분을 렌더링함 -->

  <!-- ========== 1. Mustache {{ }} : 데이터 출력 ========== -->
  <div>
    <!-- {{ }} : data의 값을 그 자리에 넣어서 보여줌. data가 바뀌면 자동 갱신 -->
    <h1>이름: {{ name }}</h1>
    <h2>나이: {{ age }}</h2>
  </div>

  <!-- ========== 2. v-if, v-else-if, v-show : 조건부 렌더링 ========== -->
  <div>
    <!-- v-if: 조건이 true일 때만 DOM에 그려짐. false면 아예 제거 -->
    <h1 v-if="age >= 20">{{ name }}은 20살 이상입니다</h1>
    <!-- v-else-if: 위 v-if가 false일 때 이 조건 검사 -->
    <h1 v-else-if="age < 20">{{ name }}은 20살 미만입니다</h1>

    <!-- v-show: 조건이 false면 display:none. DOM은 유지됨 (v-if와 다름) -->
    <h1 v-show="age >= 20">{{ name }}은 20살 이상입니다 (v-show)</h1>
  </div>

  <!-- ========== 3. v-for : 반복 ========== -->
  <div>
    <ul>
      <!-- v-for="항목 in 배열" : 배열의 각 항목마다 이 요소를 한 번씩 그림 -->
      <!-- :key="고유값" : Vue가 요소를 구분하기 위해 필요 (배열일 때 필수) -->
      <li v-for="hobby in hobbies" :key="hobby">{{ hobby }}</li>
      <!-- (항목, 인덱스) : 인덱스(0,1,2...)도 함께 쓸 수 있음 -->
      <li v-for="(hobby, index) in hobbies" :key="index">{{ index + 1 }} : {{ hobby }}</li>
    </ul>
  </div>

  <!-- ========== 4. v-on / @ : 이벤트 처리 ========== -->
  <div>
    <p>{{ "count : " + count }}</p>
    <p>{{ "age : " + age }}</p>
    <!-- v-on:click="실행할코드" : 클릭 시 실행. @click은 v-on:click의 줄임말 -->
    <button v-on:click="count++">숫자 증가</button>
    <button v-on:click="count--">숫자 감소</button>
    <button @click="age++">나이 증가</button>
    <button @click="age--">나이 감소</button>
  </div>

  <div>
    <img src="/basketball.webp">
    <img :src="iconPath">
  </div>

  <div>
    <form>
      <p>당신의 이름은?</p>
      <br>
      <input v-model="your_name">
      <p>{{  your_name }}</p>
    </form>
  </div>
</template>

<style scoped></style>
