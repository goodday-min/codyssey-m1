# AI 냉장고 레시피 추천 웹서비스

냉장고에 있는 재료를 입력하면 AI가 레시피와 식단을 추천해주는 반응형 웹서비스입니다.  
프론트엔드는 HTML, CSS, JavaScript로 구현하고, 백엔드는 FastAPI로 개발하여 프론트엔드는 Vercel, 백엔드는 Render에 배포했습니다.

---

## 1. 프로젝트 소개

본 프로젝트는 사용자가 냉장고에 남아 있는 재료를 입력하면,  
해당 재료를 활용한 **레시피 추천**과 **식단 추천**을 제공하는 AI 기반 웹서비스입니다.

불필요한 식재료 낭비를 줄이고, 사용자가 손쉽게 식사 아이디어를 얻을 수 있도록 돕는 것을 목표로 했습니다.  
또한 프론트엔드와 백엔드를 분리하여 개발하고 실제 배포까지 완료함으로써,  
풀스택 웹서비스 개발의 전체 흐름을 경험하는 데 중점을 두었습니다.

---

## 2. 주요 기능

- 냉장고 재료 입력 기반 **AI 레시피 추천**
- 입력 재료 기반 **AI 식단 추천**
- 직관적인 UI를 통한 쉬운 사용
- 모바일 / 태블릿 / 데스크탑 환경을 지원하는 **반응형 웹**
- FastAPI 기반 백엔드 API 연동
- Vercel / Render 배포 환경에서 정상 동작
- CORS 설정을 통한 프론트엔드-백엔드 통신 문제 해결

---

## 3. 서비스 화면 구성

### 메인 페이지
- 서비스 소개
- 주요 기능 안내
- 추천 페이지 이동 버튼 제공

### 소개 페이지
- 서비스 목적 설명
- 제철 식재료 / 제철 음식 정보 제공

### 추천 페이지
- 사용자가 재료 입력
- 레시피 추천 / 식단 추천 버튼 선택
- AI 응답 결과 출력

> 아래는 예시이며, 실제 이미지 경로로 교체해 주세요.

```md
![메인 화면]([스크린샷_주소])
![레시피 추천 화면]([스크린샷_주소])
![식단 추천 화면]([스크린샷_주소])


## 4. 기술 스택

본 프로젝트는 **프론트엔드와 백엔드를 분리한 풀스택 웹서비스**로 구성했습니다.  
사용자는 웹페이지에서 재료를 입력하고, 프론트엔드는 해당 입력을 백엔드 API로 전송하며,  
백엔드는 추천 결과를 생성한 뒤 다시 프론트엔드에 응답합니다.

### 4-1. Frontend

#### HTML5
- 웹페이지의 **구조**를 담당합니다.
- 제목, 입력창, 버튼, 결과 영역과 같은 화면 요소를 배치합니다.
- 예를 들어, 재료를 입력하는 input 태그와 추천 버튼, 결과를 보여줄 div 영역이 HTML로 구성됩니다.

#### CSS3
- 웹페이지의 **디자인과 레이아웃**을 담당합니다.
- 색상, 폰트, 버튼 모양, 카드 스타일, 여백 등을 꾸밉니다.
- 반응형 웹을 위해 미디어쿼리를 사용하여 모바일 / 태블릿 / PC 화면에 맞게 레이아웃을 조정했습니다.

#### JavaScript
- 웹페이지의 **동작과 상호작용**을 담당합니다.
- 사용자가 버튼을 클릭했을 때 입력값을 읽고,
- `fetch()`를 이용해 백엔드 API에 요청을 보내고,
- 응답으로 받은 데이터를 화면에 출력합니다.

즉,
- **HTML = 뼈대**
- **CSS = 꾸미기**
- **JavaScript = 동작**
역할을 합니다.

---

### 4-2. Backend

#### Python
- 백엔드 로직을 작성하는 언어입니다.
- 사용자가 입력한 재료를 받아 추천 결과를 생성하는 처리를 담당합니다.

#### FastAPI
- Python으로 API 서버를 빠르게 만들 수 있는 프레임워크입니다.
- 프론트엔드에서 보낸 요청을 받아 처리하고, JSON 형태로 응답을 반환합니다.
- 예를 들어 `/recommend-recipe`, `/recommend-mealplan` 같은 API 엔드포인트를 구성할 수 있습니다.

#### Uvicorn
- FastAPI 애플리케이션을 실행하는 ASGI 서버입니다.
- 로컬 개발 환경에서 백엔드를 실행할 때 사용합니다.

---

### 4-3. API 통신

#### REST API
- 프론트엔드와 백엔드가 데이터를 주고받는 방식입니다.
- 프론트엔드는 사용자의 입력을 JSON 형태로 백엔드에 전송하고,
- 백엔드는 처리 결과를 다시 JSON으로 응답합니다.

예를 들어,
```json
{
  "ingredients": "계란, 양파, 감자"
}
와 같은 요청을 보내면,
{
  "result": "입력한 재료를 활용한 레시피를 추천합니다..."
}
와 같은 응답을 받는 구조입니다.
fetch()
JavaScript에서 HTTP 요청을 보내기 위한 기능입니다.
본 프로젝트에서는 fetch()로 FastAPI 서버에 POST 요청을 보내고 결과를 받아 화면에 출력합니다.
4-4. Deployment
Vercel
프론트엔드를 배포한 플랫폼입니다.
정적 웹페이지(HTML/CSS/JS)를 빠르게 배포할 수 있습니다.
배포 후 URL을 통해 누구나 웹서비스에 접속할 수 있습니다.
Render
Python FastAPI 백엔드를 배포한 플랫폼입니다.
로컬 환경에서 실행하던 API 서버를 인터넷에서 접근 가능한 형태로 운영할 수 있습니다.
4-5. Environment Variables
환경 변수(.env)
API 키와 같은 민감한 정보를 코드에 직접 작성하지 않고 별도로 관리하기 위해 사용합니다.
예를 들어 AI API 키를 코드에 그대로 넣으면 GitHub에 업로드될 때 보안 문제가 생길 수 있습니다.
따라서 .env 파일에 API 키를 저장하고, 코드에서는 이를 불러와 사용하도록 구성합니다.
예시:
OPENAI_API_KEY=your_api_key

환경 변수를 사용하는 이유:

보안성 향상
로컬/배포 환경 분리
코드 수정 없이 설정 변경 가능
4-6. Version Control / Tools
Git: 버전 관리
GitHub: 코드 저장 및 협업
VS Code: 개발 환경
Live Server: 프론트엔드 로컬 테스트











5. 시스템 구성
## 5. 시스템 구성

본 프로젝트는 **프론트엔드(사용자 화면)**와 **백엔드(API 서버)**가 분리된 구조로 동작합니다.

- 프론트엔드: 사용자의 입력을 받고 결과를 화면에 보여줌
- 백엔드: 입력값을 받아 추천 결과를 생성하고 응답함

---

### 5-1. 전체 구조

```text
사용자
  ↓
Frontend (HTML/CSS/JavaScript, Vercel)
  ↓ fetch API 요청
Backend (FastAPI, Python, Render)
  ↓ JSON 응답
Frontend
  ↓
브라우저 화면에 결과 출력

이 구조는 사용자의 입력이 단순히 화면 안에서만 처리되는 것이 아니라,
JavaScript를 통해 백엔드 서버로 전달되고,
백엔드가 처리한 결과를 다시 받아 사용자에게 보여주는 방식입니다.

5-2. 동작 흐름
1) 사용자가 재료를 입력한다
예:

계란, 양파, 감자
사용자는 추천 페이지에서 재료를 입력창에 작성합니다.

2) JavaScript가 입력값을 읽는다
버튼 클릭 이벤트가 발생하면 JavaScript가 input 값이나 textarea 값을 가져옵니다.

예시:
const ingredients = document.getElementById("ingredients").value;

설명:

document.getElementById()로 입력창 요소를 선택하고,
.value로 사용자가 입력한 텍스트를 가져옵니다.

3) JavaScript가 fetch 요청으로 바꾼다
가져온 입력값을 JSON 데이터로 만들어 백엔드 API에 POST 요청을 보냅니다.

예시:
const response = await fetch("https://your-backend-url.onrender.com/recommend-recipe", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    ingredients: ingredients
  })
});
설명:

fetch()는 백엔드 주소로 요청을 보내는 함수입니다.
method: "POST"는 데이터를 서버로 전달하겠다는 의미입니다.
Content-Type: "application/json"은 JSON 형식으로 보낸다는 뜻입니다.
JSON.stringify()는 JavaScript 객체를 JSON 문자열로 바꿔 전송합니다.
4) 백엔드가 요청을 받는다
FastAPI는 프론트엔드가 보낸 JSON 데이터를 받아서 처리합니다.

예를 들어,

어떤 재료가 들어왔는지 확인하고
레시피 추천 또는 식단 추천 로직을 수행한 뒤
결과를 JSON 형태로 반환합니다.
5) 프론트엔드가 응답을 받는다
백엔드가 보낸 응답을 다시 JavaScript가 받아옵니다.

예시:
const data = await response.json();
설명:

response.json()은 서버 응답을 JavaScript 객체로 변환합니다.
이때 data.result와 같은 방식으로 실제 추천 결과를 사용할 수 있습니다.
6) 응답 결과를 화면에 반영한다
받아온 결과를 결과 영역에 출력합니다.

예시:
document.getElementById("result").innerText = data.result;
설명:

결과를 출력할 HTML 요소를 선택한 뒤,
서버에서 받은 추천 문장을 화면에 표시합니다.
5-3. 프론트엔드 → 백엔드 API 통신 흐름 요약
사용자가 재료 입력
버튼 클릭
JavaScript가 입력값 읽기
fetch()로 백엔드 API에 POST 요청 전송
FastAPI가 요청 처리
JSON 응답 반환
JavaScript가 응답 데이터 추출
결과를 HTML에 반영
즉,
사용자 입력 → JavaScript 처리 → 백엔드 요청 → 응답 수신 → 화면 출력
의 흐름으로 동작합니다.

5-4. 예시 코드로 보는 통신 흐름
async function recommendRecipe() {
  const ingredients = document.getElementById("ingredients").value;
  const resultBox = document.getElementById("result");

  if (!ingredients.trim()) {
    resultBox.innerText = "재료를 한 개 이상 입력해주세요.";
    return;
  }

  resultBox.innerText = "추천 결과를 불러오는 중입니다...";

  try {
    const response = await fetch("https://your-backend-url.onrender.com/recommend-recipe", {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify({ ingredients })
    });

    const data = await response.json();
    resultBox.innerText = data.result;
  } catch (error) {
    resultBox.innerText = "서버와 연결할 수 없습니다. 잠시 후 다시 시도해주세요.";
    console.error(error);
  }
}

설명:

입력값이 비어 있으면 요청을 보내지 않고 바로 안내 메시지를 보여줍니다.
요청을 보내는 동안 로딩 문구를 표시합니다.
정상 응답이 오면 결과를 출력합니다.
통신 실패 시 오류 메시지를 출력합니다.
이 코드는 사용자 경험과 오류 처리까지 포함한 기본적인 API 연동 흐름을 보여줍니다.

5-5. 배포 구조 이해
본 프로젝트는 다음과 같이 배포됩니다.

Frontend: Vercel
Backend: Render
즉, 사용자는 Vercel에 배포된 웹페이지에 접속하지만,
실제 추천 기능은 Render에 배포된 FastAPI 서버가 처리합니다.

구조는 아래와 같습니다.
브라우저 접속
→ Vercel에 배포된 프론트 페이지 로드
→ 사용자가 재료 입력
→ JavaScript fetch로 Render의 FastAPI API 호출
→ Render가 응답 반환
→ 결과를 브라우저에 표시

이처럼 프론트와 백엔드가 서로 다른 도메인에서 동작하기 때문에
CORS 설정이 필요했습니다.

5-6. Vercel Serverless Functions와의 관계
Vercel은 정적 프론트엔드 배포뿐 아니라,
서버 기능을 함수 단위로 실행하는 Serverless Functions도 제공합니다.

Serverless Functions란?
별도의 전통적인 서버를 직접 관리하지 않아도
요청이 들어왔을 때만 실행되는 함수 형태의 백엔드 방식입니다.
본 프로젝트와의 관계
본 프로젝트는 Vercel Serverless Functions를 직접 사용하지 않고
Vercel에는 프론트엔드, Render에는 Python(FastAPI) 백엔드를 배포했습니다.
하지만 구조 이해를 위해 보면,

프론트엔드가 백엔드를 호출한다는 점은 동일하며,
차이점은 백엔드가 Vercel 내부 함수인지, **외부 Python 서버(Render)**인지입니다.
즉, 본 프로젝트는
프론트(Vercel) → 외부 백엔드(Render, Python)
구조라고 설명할 수 있습니다.

5-7. 로컬 환경과 배포 환경의 차이
개발 중에는 보통 로컬 환경에서 먼저 테스트합니다.

로컬 환경
프론트: Live Server 또는 브라우저
백엔드: http://127.0.0.1:8000
직접 수정 후 바로 테스트 가능
배포 환경
프론트: Vercel URL
백엔드: Render URL
실제 인터넷 주소를 통해 접근
CORS, 환경 변수, API URL 차이 같은 문제가 발생할 수 있음
예를 들어,
로컬에서는 아래처럼 동작하던 코드가
fetch("http://127.0.0.1:8000/recommend-recipe")
배포 후에는 아래처럼 수정되어야 합니다.
fetch("https://your-backend-url.onrender.com/recommend-recipe")
즉, 로컬에서 되던 기능도 배포 후에는 주소, 보안, 환경 설정 차이로 인해 다시 점검해야 합니다.
5-8. 배포 후 수정 및 재배포 흐름
배포 후 문제가 발견되면 다음 순서로 수정합니다.

오류 상황 확인
브라우저 콘솔 및 네트워크 탭 확인
백엔드 로그 확인
코드 수정
GitHub에 반영
Vercel / Render 재배포 확인
실제 배포 주소에서 다시 테스트
이 과정을 통해 로컬 개발과 실제 서비스 운영의 차이를 이해할 수 있습니다.


---

# README에 추가할 학습 성과 섹션
과제 요구사항이 분명하니까, README 뒤쪽에 아예 별도 섹션으로 넣는 게 가장 좋아요.  
아래 내용을 **`16. 학습 내용 및 성과`** 같은 제목으로 추가하세요.

```md
## 16. 학습 내용 및 성과

본 프로젝트를 수행한 후 다음 내용을 스스로 설명할 수 있게 되었습니다.

### 16-1. HTML / CSS / JavaScript의 역할 구분
- **HTML**은 웹페이지의 구조를 만든다.
- **CSS**는 화면의 디자인과 레이아웃을 꾸민다.
- **JavaScript**는 사용자 입력 처리, 버튼 클릭 이벤트, API 요청, 결과 출력 같은 동작을 담당한다.

즉,
- HTML은 뼈대
- CSS는 스타일
- JavaScript는 기능
으로 이해할 수 있다.

---

### 16-2. 사용자 입력이 요청(fetch)으로 바뀌고, 응답이 화면에 반영되는 흐름
사용자가 입력창에 재료를 입력하고 버튼을 누르면,
JavaScript가 입력값을 읽어 `fetch()` 요청으로 백엔드에 전달한다.  
백엔드는 해당 입력을 처리한 뒤 JSON 응답을 반환하고,  
프론트엔드는 그 응답을 받아 화면에 결과를 출력한다.

흐름 요약:
1. 입력값 작성
2. 버튼 클릭
3. JavaScript가 값 읽기
4. `fetch()`로 API 요청 전송
5. 백엔드 응답 수신
6. 결과를 HTML 요소에 출력

---

### 16-3. 프론트에서 백엔드(Python)를 호출하는 구조
본 프로젝트는 프론트엔드와 백엔드가 분리되어 있다.

- 프론트엔드: Vercel에 배포
- 백엔드: Render에 배포된 Python(FastAPI) 서버

따라서 사용자가 프론트 화면에서 버튼을 눌렀을 때,  
JavaScript가 Render의 Python API 주소로 요청을 보내고,  
응답 결과를 다시 받아 화면에 보여주는 구조로 동작한다.

흐름은 다음과 같다.

1. 사용자가 브라우저에서 프론트엔드 페이지에 접속한다.
2. 사용자가 재료를 입력하고 버튼을 클릭한다.
3. JavaScript가 입력값을 읽는다.
4. `fetch()`를 사용해 Render에 배포된 FastAPI API로 요청을 보낸다.
5. FastAPI가 입력값을 처리하고 결과를 JSON으로 반환한다.
6. JavaScript가 응답 데이터를 받아 화면에 출력한다.

즉,  
**브라우저 화면은 Vercel에서 제공하고, 실제 추천 처리 기능은 Render의 Python 서버가 담당한다**  
고 설명할 수 있다.

---

### 16-4. Vercel Serverless Functions의 개념 이해
Vercel은 정적 웹페이지를 배포하는 기능뿐 아니라,  
요청이 들어올 때만 실행되는 **Serverless Functions**도 제공한다.

#### Serverless Functions란?
- 항상 켜져 있는 전통적인 서버를 직접 운영하는 대신
- 특정 요청이 들어왔을 때만 함수처럼 실행되는 백엔드 방식이다.
- 서버 관리 부담이 적고, 간단한 API를 만들 때 유용하다.

#### 본 프로젝트에서의 구조
본 프로젝트는 **Vercel Serverless Functions를 직접 사용하지 않고**,  
프론트엔드는 Vercel에, 백엔드는 Render의 Python(FastAPI) 서버에 배포했다.

즉, 이 프로젝트는 다음 구조이다.

```text
Frontend (Vercel)
→ Backend API 호출 (Render의 FastAPI)
→ 결과 응답
→ 화면 출력

따라서
Vercel Serverless Functions도 백엔드 역할을 할 수 있지만, 이번 프로젝트에서는 별도의 Python 백엔드를 Render에 두고 이를 호출하는 구조를 사용했다
고 설명할 수 있다.

16-5. 환경 변수로 API 키를 안전하게 관리해야 하는 이유
API 키는 외부 서비스에 접근하기 위한 중요한 인증 정보이므로,
코드에 직접 작성하면 보안상 위험하다.

예를 들어,

GitHub에 코드를 올릴 때 API 키가 함께 노출될 수 있고
타인이 해당 키를 무단으로 사용할 수 있으며
과금, 정보 유출, 서비스 제한 등의 문제가 생길 수 있다.
그래서 .env 파일이나 배포 플랫폼의 환경 변수 설정을 사용해
코드와 비밀 정보를 분리해서 관리해야 한다.

환경 변수를 사용하면 다음과 같은 장점이 있다.

보안
민감한 정보를 코드에 직접 남기지 않는다.
환경 분리
로컬 환경과 배포 환경에서 서로 다른 설정값을 사용할 수 있다.
유지보수
코드 수정 없이 설정만 바꿔도 된다.
즉,
API 키는 코드에 하드코딩하지 않고 환경 변수로 관리해야 안전하다
고 설명할 수 있다.

16-6. 로컬 환경과 배포 환경의 차이 이해
로컬 환경은 내 컴퓨터에서 개발하고 테스트하는 환경이고,
배포 환경은 실제 인터넷에서 사용자가 접속하는 서비스 환경이다.

로컬 환경의 특징
빠르게 수정하고 바로 확인 가능
보통 localhost 또는 127.0.0.1 주소를 사용
개발용 설정으로 테스트 가능
배포 환경의 특징
실제 도메인 주소 사용
프론트와 백엔드가 서로 다른 서버에 존재할 수 있음
CORS, 환경 변수, API 주소, 빌드 설정 같은 문제가 발생할 수 있음
예를 들어 로컬에서는
fetch("http://127.0.0.1:8000/recommend-recipe")
로 요청했지만, 배포 후에는
fetch("https://your-backend-url.onrender.com/recommend-recipe")
처럼 실제 배포 주소로 바꿔야 한다.

즉,
로컬에서는 잘 되던 코드도 배포 환경에서는 주소, 보안, 서버 설정 차이 때문에 추가 수정이 필요할 수 있다
고 설명할 수 있다.

16-7. 배포 후 문제를 수정하고 재배포하는 흐름
배포 후 문제가 생기면 단순히 "안 된다"에서 끝나는 것이 아니라,
원인을 찾고 수정한 뒤 다시 배포하는 과정이 필요하다.

기본 흐름은 다음과 같다.

배포된 사이트에서 문제 확인
브라우저 콘솔(Console) 확인
네트워크(Network) 탭에서 요청/응답 상태 확인
백엔드(Render) 로그 확인
코드 수정
GitHub에 푸시
Vercel / Render 재배포
배포 주소에서 다시 테스트
이 과정을 통해
개발 → 테스트 → 수정 → 재배포 → 재확인
흐름을 경험할 수 있었다.

16-8. AI 코딩 도구를 사용하더라도 오류 원인을 설명할 수 있어야 함
AI 코딩 도구를 사용하면 코드 작성 속도는 빨라질 수 있지만,
생성된 코드가 항상 바로 정상 동작하는 것은 아니다.

따라서 중요한 것은 코드를 단순히 복사해서 사용하는 것이 아니라,

어떤 기능을 하는 코드인지 이해하고
오류가 발생했을 때 원인을 확인하고
수정 방향을 설명할 수 있는 능력을 갖추는 것이다.
예를 들어 이번 프로젝트에서는 다음과 같은 오류를 직접 확인하고 수정할 수 있었다.

예시 1. 버튼 이벤트가 동작하지 않는 문제
원인: HTML 버튼의 id와 JavaScript에서 선택한 id가 다름
해결: HTML과 JavaScript의 id를 일치시킴
예시 2. 배포 후 API 호출이 실패하는 문제
원인: 로컬 주소(127.0.0.1)로 요청하고 있었음
해결: Render에 배포된 실제 백엔드 주소로 변경
예시 3. CORS 오류 발생
원인: 프론트와 백엔드가 서로 다른 도메인이라 브라우저가 요청을 차단
해결: FastAPI에 CORSMiddleware를 설정하여 허용 도메인을 추가
즉,
AI가 코드를 생성해주더라도, 개발자는 오류 원인을 파악하고 왜 수정해야 하는지 말로 설명할 수 있어야 한다
고 정리할 수 있다.

16-9. 종합 학습 성과
이번 프로젝트를 통해 다음과 같은 풀스택 웹 개발 흐름을 실제로 경험하였다.

HTML / CSS / JavaScript의 역할 구분
사용자 입력을 JavaScript로 처리하는 방법
fetch()를 이용한 API 요청과 응답 처리
FastAPI를 활용한 Python 백엔드 구성
프론트엔드와 백엔드의 분리 배포 구조 이해
환경 변수와 API 키 보안 관리의 중요성 이해
로컬 환경과 배포 환경의 차이 이해
배포 후 오류 수정 및 재배포 경험
AI 도구 활용과 동시에 디버깅 및 원인 설명 능력 향상
이 프로젝트는 단순히 웹페이지를 만드는 수준을 넘어,
사용자 입력 → API 통신 → 서버 처리 → 응답 출력 → 배포 → 문제 해결
까지 전체 흐름을 학습한 프로젝트라고 정리할 수 있다.




6. 폴더 구조
project/
├─ frontend/
│  ├─ index.html
│  ├─ about.html
│  ├─ recommend.html
│  ├─ style.css
│  └─ script.js
│
├─ backend/
│  ├─ main.py
│  ├─ requirements.txt
│  └─ .env
│
└─ README.md
실제 프로젝트 구조에 맞게 수정해 주세요.

7. 실행 방법
7-1. 프론트엔드 실행
정적 웹페이지이므로 VS Code의 Live Server 또는 브라우저에서 직접 실행할 수 있습니다.

방법 1: Live Server
VS Code에서 index.html 파일 열기
우클릭 후 Open with Live Server 선택
방법 2: 브라우저 직접 실행
index.html 파일을 브라우저에서 열기

7-2. 백엔드 실행
1) 패키지 설치
pip install -r requirements.txt
2) 서버 실행
uvicorn main:app --reload
3) 실행 주소
http://127.0.0.1:8000

8. 환경변수 설정
AI API를 사용하는 경우 .env 파일에 API 키를 설정합니다.
OPENAI_API_KEY=your_api_key

9. 배포 주소
Frontend
Vercel: [프론트 배포 주소]
Backend
Render: [백엔드 배포 주소]

10. API 명세
아래 경로는 예시입니다. 실제 프로젝트의 API 경로에 맞게 수정해 주세요.

10-1. 레시피 추천 API
Method: POST
Endpoint: /recommend-recipe
Request
{
  "ingredients": "계란, 양파, 감자"
}
Response
{
  "result": "입력한 재료를 활용한 레시피를 추천합니다..."
}

10-2. 식단 추천 API
Method: POST
Endpoint: /recommend-mealplan
Request
{
  "ingredients": "닭가슴살, 브로콜리, 고구마"
}

Response
{
  "result": "입력한 재료를 바탕으로 하루 식단을 추천합니다..."
}
11. 반응형 웹 적용
본 프로젝트는 다양한 디바이스에서 원활히 사용할 수 있도록 반응형 웹으로 구현했습니다.

테스트 환경
모바일
태블릿
데스크탑
확인 항목
레이아웃 깨짐 여부
버튼 및 입력창 정렬 상태
텍스트 줄바꿈 처리
가로 스크롤 발생 여부
추천 결과 영역 표시 상태
12. 트러블슈팅
1) CORS 오류 발생
프론트엔드와 백엔드가 서로 다른 도메인에서 동작하여 API 요청 시 CORS 오류가 발생했습니다.
FastAPI의 CORSMiddleware를 적용하여 허용 도메인을 설정함으로써 문제를 해결했습니다.

2) 버튼 클릭 이벤트 미작동
HTML 버튼의 id와 JavaScript에서 선택한 id가 일치하지 않아 이벤트가 연결되지 않았습니다.
버튼 요소의 id를 통일하여 정상적으로 동작하도록 수정했습니다.

3) 배포 후 API 호출 실패
로컬에서는 정상 동작했지만, 배포 환경에서는 API 주소가 달라 호출 오류가 발생했습니다.
프론트엔드의 API 요청 URL을 Render에 배포된 백엔드 주소로 변경하여 해결했습니다.

4) 모바일 레이아웃 정렬 문제
모바일 화면에서 버튼과 카드 요소 정렬이 어색한 문제가 있었습니다.
미디어쿼리를 적용해 화면 크기별 레이아웃을 조정하여 해결했습니다.

13. 기대 효과
냉장고 속 재료 활용도를 높여 식재료 낭비를 줄일 수 있음
사용자가 쉽고 빠르게 레시피 및 식단 아이디어를 얻을 수 있음
AI 기반 추천 기능을 실제 웹서비스에 적용해볼 수 있음
프론트엔드부터 백엔드, 배포까지 풀스택 개발 경험을 쌓을 수 있음
14. 향후 개선점
로그인 / 회원가입 기능 추가
즐겨찾기 레시피 저장 기능
알레르기 / 기피 재료 필터링 기능
조리 시간 및 난이도 선택 기능
결과 카드 UI 개선
추천 결과 이미지 연동
사용자 맞춤형 식단 추천 고도화
15. 프로젝트 회고
이번 프로젝트를 통해 단순한 화면 구현을 넘어,
사용자 입력 → API 요청 → AI 응답 처리 → 결과 출력 → 배포 환경 검증까지
웹서비스 개발의 전체 흐름을 직접 경험할 수 있었습니다.

특히 프론트엔드와 백엔드를 연결하는 과정,
배포 후 발생하는 CORS 및 API 주소 문제를 해결하는 과정,
그리고 모바일/태블릿/데스크탑 환경에서의 반응형 UI를 조정하는 과정을 통해
실제 서비스 개발에 필요한 문제 해결 능력을 키울 수 있었습니다.

16. GitHub
GitHub Repository: [GitHub 저장소 주소]
프론트엔드와 백엔드가 분리된 경우 아래처럼 작성해도 됩니다.

Frontend Repository: [프론트 저장소 주소]
Backend Repository: [백엔드 저장소 주소]








