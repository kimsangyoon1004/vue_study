# Axios - Vue에서 HTTP 요청 (json-server 연습)

이 폴더에서는 **axios**로 HTTP 요청을 보내고, **json-server**로 가짜 REST API 서버를 띄워서 연습합니다.

---

## 1. 설치

### axios (이 프로젝트에만 필요)

코드에서 `import axios from 'axios'` 하므로 **이 폴더에서** 설치합니다.

```sh
cd Axios
npm install
```

→ `package.json`에 axios가 있으면 `npm install` 한 번이면 됩니다. 없으면 `npm install axios` 실행.

### json-server (가짜 API 서버)

**방법 A: 전역 설치 (한 번만 하면 됨)**

```sh
npm install -g json-server
```

설치 후 터미널 어디서든 `json-server` 명령어 사용 가능.

**방법 B: 전역 없이 매번 npx 로 실행**

```sh
npx json-server --watch db.json --port 3000
```

→ 설치 없이 그때그때 실행. 매번 위 명령어만 치면 됨.

---

## 2. 실행 순서

**1단계: json-server 실행 (API 서버)**

`Axios` 폴더에서:

```sh
json-server --watch db.json --port 3000
```

또는 (전역 설치 안 했으면):

```sh
npx json-server --watch db.json --port 3000
```

- `db.json` 이 이 폴더에 있어야 함.
- `http://localhost:3000` 에 서버가 떠 있고, 예: `http://localhost:3000/members` 로 POST/GET 가능.

**2단계: Vue 앱 실행**

**새 터미널**을 열고 같은 `Axios` 폴더에서:

```sh
npm run dev
```

- 브라우저에서 `http://localhost:5173` 접속.
- "데이터 입력" 버튼을 누르면 axios 로 `http://localhost:3000/members` 에 POST 요청이 감.

---

## 3. 동작 흐름 요약

| 순서 | 하는 일 |
|------|----------|
| 1 | json-server 가 `db.json` 을 읽어서 `localhost:3000` 에 API 제공 |
| 2 | Vue 앱(`npm run dev`)은 `localhost:5173` 에 뜸 |
| 3 | 버튼 클릭 → `inputData()` 실행 → `axios.post('http://localhost:3000/members', { name, email })` 호출 |
| 4 | json-server 가 POST 요청을 받아서 `db.json` 의 `members` 배열에 데이터 추가 |
| 5 | `.then()` 안의 코드가 실행됨 (예: 콘솔에 "전송 완료") |

---

## 4. json-server 주요 URL (db.json 기준)

- `GET  http://localhost:3000/members` → 목록 조회
- `POST http://localhost:3000/members` → 항목 추가 (body에 `name`, `email` 등)
- `GET  http://localhost:3000/members/1` → id=1 항목 조회

`db.json` 의 최상위 키가 `members` 이면 경로는 `/members` 입니다.
