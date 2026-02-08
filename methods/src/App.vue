<script>
/**
 * Options API - methods 연습
 * methods: 컴포넌트에서 쓰는 함수들을 정의. template에서 @click, {{ fn() }} 등으로 호출
 */
export default {
  data() {
    return {
      userName1: '홍길동',
      userName2: '',
      num: 0,
    }
  },
  methods: {
    // 반환값만 보여줄 때: template에서 {{ greeting() }} 로 호출
    greeting() {
      return 'Hi, there ' + this.userName1
    },
    // 인자를 받는 함수: {{ bye('김길동') }} 처럼 호출
    bye(userName2) {
      return 'Bye, there ' + userName2
    },
    // 클릭 시 상태 변경: @click="increment" (괄호 없이 메서드 이름만 넘기면 됨)
    increment() {
      this.num++
    },
    decrease() {
      this.num--
    },
  },
}
</script>

<template>
  <h1>{{ greeting() }}</h1>
  <h1>{{ bye('김길동') }}</h1>
  <button @click="increment">Increase Number</button>
  <button @click="decrease">Decrease Number</button>
  <p>{{ num }}</p>
</template>

<style scoped></style>
