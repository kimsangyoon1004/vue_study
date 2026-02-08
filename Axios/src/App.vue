<script setup>
/**
 * Axios: Vue(브라우저)에서 HTTP 요청을 보낼 때 쓰는 라이브러리
 * - GET, POST, PUT, DELETE 등으로 서버 API 호출
 * - 여기서는 json-server(localhost:3000)로 POST 요청을 보내서 db.json에 데이터 추가
 */
import axios from 'axios'
import { ref } from 'vue'

// ref(null): template의 <div ref="table">을 script에서 접근하기 위한 ref. DOM이 그려진 뒤 table.value로 해당 요소를 가리킴
const table = ref(null)
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

/**
 * GET 요청: 서버에서 데이터 "가져오기"
 * - axios.get(URL): body 없이 URL로 요청만 보냄. json-server는 GET /members 시 db.json의 members 배열을 그대로 반환
 * - res.data 에 그 배열이 들어옴 → 테이블 HTML을 만들어 ref="table" 인 div에 넣음
 */
const getData = () => {
  axios
    .get('http://localhost:3000/members')
    .then((res) => {
      // res.data = json-server가 준 members 배열 예: [{ id, name, email }, ...]
      const members = res.data

      // 테이블 헤더(첫 줄). 백틱(`)으로 여러 줄 문자열
      let htmlContent = `
    <table border="1">
      <tr>
        <th>id</th>
        <th>name</th>
        <th>email</th>
      </tr>
    `

      // 배열을 돌면서 각 member마다 <tr> 한 줄씩 추가
      members.forEach((member) => {
        htmlContent += `
      <tr>
        <td>${member.id}</td>
        <td>${member.name}</td>
        <td>${member.email}</td>
      </tr>`
      })

      htmlContent += '</table>'

      // ref="table" 인 div에 만든 HTML 넣기. table.value가 그 DOM 요소
      if (table.value) table.value.innerHTML = htmlContent
    })
    .catch((err) => console.error('요청 실패:', err.message))
}
</script>

<template>
  <button @click="inputData">데이터 입력</button>
  <button @click="getData">데이터 가져오기</button>

  <!-- ref="table": 이 div를 script의 table(ref)으로 참조. getData()에서 여기에 테이블 HTML을 넣음 -->
  <div ref="table"></div>
</template>

<style scoped></style>
