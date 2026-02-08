<script setup>
/**
 * Axios: Vue(브라우저)에서 HTTP 요청을 보낼 때 쓰는 라이브러리
 * - GET, POST, PUT, DELETE 등으로 서버 API 호출
 * - 여기서는 json-server(localhost:3000)로 POST 요청을 보내서 db.json에 데이터 추가
 */
import axios from 'axios'

/**
 * 버튼 클릭 시 실행되는 함수
 * - axios.post(URL, 보낼데이터) 로 POST 요청
 * - 요청은 비동기: 요청을 보내고 응답을 기다리는 동안 다른 코드가 먼저 실행될 수 있음
 */
const inputData = () => {
  // axios.post(URL, body)
  // - URL: 요청을 보낼 주소. json-server는 db.json의 키를 경로로 씀 → /members
  // - 두 번째 인자: 서버로 보낼 JSON 데이터 (객체)
  axios
    .post('http://localhost:3000/members', {
      name: 'John Doe',
      email: 'test@test.com',
    })
    // .then(콜백): 요청이 성공적으로 끝났을 때 실행됨. res = 서버 응답
    .then((res) => {
      console.log('전송 완료', res.data)
    })
    // .catch(콜백): 요청이 실패했을 때 (서버 꺼짐, 네트워크 에러 등)
    .catch((err) => {
      console.error('요청 실패:', err.message)
    })

  // 이 줄은 "요청을 보낸 직후" 바로 실행됨. 응답을 기다리지 않음 (비동기)
  console.log('Hello')
}
</script>

<template>
  <button @click="inputData">데이터 입력</button>
</template>

<style scoped></style>
