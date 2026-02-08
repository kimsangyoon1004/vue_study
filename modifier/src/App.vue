<script>
/**
 * 이벤트 수정자 (Event Modifier)
 * - .once : 해당 이벤트를 한 번만 실행
 * - .prevent : event.preventDefault() 자동 호출 (예: form 제출 막기)
 * - .stop : event.stopPropagation() (버블링 막기)
 * - 키 수정자: .enter, .s 등 → 해당 키를 눌렀을 때만 핸들러 실행
 */
export default {
  data() {
    return {
      kValue: '',
    }
  },
  methods: {
    createAlert() {
      alert('경고창 한번만')
    },
    getKey(e) {
      this.kValue = e.key
    },
  },
}
</script>

<template>
  <!-- @click.once : 클릭 이벤트가 "한 번만" 실행됨. 두 번째 클릭부터는 무시 -->
  <button @click.once="createAlert">경고 한번만</button>
  <!-- keydown.s : 's' 키를 눌렀을 때만 getKey 실행 (키 수정자) -->
  <input type="text" v-on:keydown.s="getKey" /> <br />
  <span>{{ kValue }}</span>
</template>

<style></style>
