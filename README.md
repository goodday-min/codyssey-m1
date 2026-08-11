# 오늘 뭐 먹지❓ AI 냉장고 파먹기 🍴 
    AI 냉장고 레시피 추천 웹서비스   

- 서비스 URL: https://al-3web.vercel.app/
- 백엔드 API URL: https://ai-recipe-backend-jxo3.onrender.com
- GitHub Repository: https://github.com/goodday-min/A1_3
- Commit History: https://github.com/goodday-min/A1_3/commits/main

#### 냉장고에 있는 재료를 입력하면 AI가 레시피와 식단을 추천해주는 반응형 웹서비스입니다.  
#### 프론트엔드는 HTML, CSS, JavaScript로 구현하고, 백엔드는 FastAPI로 개발하여 프론트엔드는 Vercel, 백엔드는 Render에 배포했습니다.

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
- FastAPI 기반 **백엔드 API** 연동
- **Vercel / Render 배포** 환경에서 정상 동작
- CORS 설정을 통한 프론트엔드-백엔드 통신 문제 해결

---

## 3. 서비스 화면 구성

### 배포된 웹 서비스 (Vercel URL)

https://a1-3web.vercel.app/ 

### 메인 페이지
- 서비스 소개
- 주요 기능 안내
- 추천 페이지 이동 버튼 제공

### AI 추천 페이지
- 사용자가 재료 입력
- 레시피 추천 / 식단 추천 버튼 선택
- AI 응답 결과 출력

### 소개 페이지
- 서비스 목적 설명
- 제철 식재료 / 제철 음식 정보 제공

- 데스크탑에서 실행
  
| 메인 화면 | AI 추천 화면 | 소개화면 |
| --- | --- | --- |
| <img width="501" height="783" alt="image" src="https://github.com/user-attachments/assets/a3c61c8c-2be8-442d-a820-07222eebb3ed" /> | <img width="499" height="794" alt="image" src="https://github.com/user-attachments/assets/636d0c3b-e210-4215-832b-949003984b7b" /> | <img width="490" height="763" alt="image" src="https://github.com/user-attachments/assets/ba6f2d02-77ce-4eb6-90e0-324bc21bc02d" /> |

- 모바일에서 실행
  
| 메인 화면 | AI 추천 화면1 | AI 추천 화면2 | AI 추천 화면3 | 소개화면 | 
| --- | --- | --- | --- |--- |
| <img width="283" height="831" alt="image" src="https://github.com/user-attachments/assets/32aa8784-1405-44b5-aba5-5d655e42e798" /> | <img width="297" height="834" alt="image" src="https://github.com/user-attachments/assets/ddced869-e53a-4e25-b4d5-50c78f7c9a2d" /> | <img width="288" height="821" alt="image" src="https://github.com/user-attachments/assets/88e5821c-bd36-4797-9264-60d540fad69a" /> | <img width="288" height="834" alt="image" src="https://github.com/user-attachments/assets/f47c6b52-9155-4255-98a1-7c2f6fa2b01c" /> | <img width="283" height="825" alt="image" src="https://github.com/user-attachments/assets/976a6e45-3e1a-4717-adaa-0e2981589825" />
 |



---

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
    json
        {
          "ingredients": "계란, 양파, 감자"
        }
        와 같은 요청을 보내면,
        {
          "result": "입력한 재료를 활용한 레시피를 추천합니다..."
        }
        와 같은 응답을 받는 구조입니다.

#### fetch() 
    JavaScript에서 HTTP 요청을 보내기 위한 기능입니다.
    본 프로젝트에서는 fetch()로 FastAPI 서버에 POST 요청을 보내고 결과를 받아 화면에 출력합니다.

### 4-4. Deployment

#### Vercel

    프론트엔드를 배포한 플랫폼입니다.
    정적 웹페이지(HTML/CSS/JS)를 빠르게 배포할 수 있습니다.
    배포 후 URL을 통해 누구나 웹서비스에 접속할 수 있습니다.

#### Render

    Python FastAPI 백엔드를 배포한 플랫폼입니다.
    로컬 환경에서 실행하던 API 서버를 인터넷에서 접근 가능한 형태로 운영할 수 있습니다.

### 4-5. Environment Variables

**환경 변수(.env)**  

    API 키와 같은 민감한 정보를 코드에 직접 작성하지 않고 별도로 관리하기 위해 사용합니다.
    예를 들어 AI API 키를 코드에 그대로 넣으면 GitHub에 업로드될 때 보안 문제가 생길 수 있습니다.
    따라서 .env 파일에 API 키를 저장하고, 코드에서는 이를 불러와 사용하도록 구성합니다.
    예시:
    OPENAI_API_KEY=your_api_key

**환경 변수를 사용하는 이유:**

    - 보안성 향상
    - 로컬/배포 환경 분리
    - 코드 수정 없이 설정 변경 가능

### 4-6. Version Control / Tools

- Git: 버전 관리
- GitHub: 코드 저장 및 협업
- VS Code: 개발 환경
- Live Server: 프론트엔드 로컬 테스트


## 5. 시스템 구성

본 프로젝트는 **프론트엔드(사용자 화면)**와 **백엔드(API 서버)**가 분리된 구조로 동작합니다.

- 프론트엔드: 사용자의 입력을 받고 결과를 화면에 보여줌
- 백엔드: 입력값을 받아 추천 결과를 생성하고 응답함

---

### 5-1. 전체 구조

**GitHub 저장소 구조 예시**
Vercel에서 Python 백엔드를 인식하게 하려면 아래와 같은 구조가 필요합니다.  
    
    A1_3/
    ├── api/                # 백엔드 (Vercel Serverless Functions)
    │   └── index.py        # Python API 코드 (FastAPI 등)
    ├── js/
    │   ├── main.js        → 홈 화면 버튼, 공통 동작
    │   ├── recipe.js       # 프론트엔드 로직 (API 호출) → 재료 입력값 처리, API 요청, 결과 출력
    │   └── about.js      → About 페이지용 간단한 동작이 있으면 사용
    ├── css/
    │   └── style.css       # 스타일 (반응형 디자인) 전체 공통 스타일
    ├── index.html          # 메인 페이지
    ├── recipe.html         # 재료 입력, AI 레시피 추천 결과 표시 레시피 생성 페이지
    ├── about.html          # 제철음식 정보 페이지
    ├── requirements.txt    # Python 패키지 목록 (openai, fastapi 등) → FastAPI, uvicorn 등 설치 목록
    ├── vercel.json         Vercel 배포 설정
    ├── .env                OpenAI API 키 저장
    └── README.md           # 프로젝트 설명서
    └── 서비스 기획서.md    # 프로젝트 설명서


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
JavaScript를 통해 백엔드 서버로 전달되고, 백엔드가 처리한 결과를 다시 받아 사용자에게 보여주는 방식입니다.

### 5-2. 동작 흐름

    1. 사용자가 재료를 입력한다  
    
        예: 계란, 양파, 감자
        사용자는 추천 페이지에서 재료를 입력창에 작성합니다.
    
    2. JavaScript가 입력값을 읽는다
    
      버튼 클릭 이벤트가 발생하면 JavaScript가 input 값이나 textarea 값을 가져옵니다.
    
        예시:
        const ingredients = document.getElementById("ingredients").value;
    
        설명:
        document.getElementById()로 입력창 요소를 선택하고,
        .value로 사용자가 입력한 텍스트를 가져옵니다.
    
    3. JavaScript가 fetch 요청으로 바꾼다
    
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
        
    4. 백엔드가 요청을 받는다
    
        FastAPI는 프론트엔드가 보낸 JSON 데이터를 받아서 처리합니다.
    
        예를 들어,
        어떤 재료가 들어왔는지 확인하고
        레시피 추천 또는 식단 추천 로직을 수행한 뒤
        결과를 JSON 형태로 반환합니다.
    
    
    
    5. 프론트엔드가 응답을 받는다
    
      백엔드가 보낸 응답을 다시 JavaScript가 받아옵니다.
    
        예시:
        const data = await response.json();
        설명:
        response.json()은 서버 응답을 JavaScript 객체로 변환합니다.
        이때 data.result와 같은 방식으로 실제 추천 결과를 사용할 수 있습니다.
    
    6. 응답 결과를 화면에 반영한다
    
      받아온 결과를 결과 영역에 출력합니다.
    
        예시:
        document.getElementById("result").innerText = data.result;
        설명:
        결과를 출력할 HTML 요소를 선택한 뒤,
        서버에서 받은 추천 문장을 화면에 표시합니다.

### 5-3. 프론트엔드 → 백엔드 API 통신 흐름 요약

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

### 5-4. 예시 코드로 보는 통신 흐름

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

### 5-5. 배포 구조 이해
본 프로젝트는 다음과 같이 배포됩니다.

- Frontend: Vercel
- Backend: Render
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

### 5-6. Vercel Serverless Functions와의 관계

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

### 5-7. 로컬 환경과 배포 환경의 차이

개발 중에는 보통 로컬 환경에서 먼저 테스트합니다.

1.로컬 환경
    프론트: Live Server 또는 브라우저  
    백엔드: http://127.0.0.1:8000  
    직접 수정 후 바로 테스트 가능  
2. 배포 환경 (배포 URL)  
    - 프론트: Vercel URL (https://a1-3web.vercel.app/)  
    - 백엔드: Render URL (https://ai-recipe-backend-jxo3.onrender.com)  
    - 실제 인터넷 주소를 통해 접근  
    - CORS, 환경 변수, API URL 차이 같은 문제가 발생할 수 있음  
    
    예를 들어,  
      로컬에서는 아래처럼 동작하던 코드가 fetch("http://127.0.0.1:8000/recommend-recipe")    
      배포 후에는 아래처럼 수정되어야 합니다.  
      fetch("https://your-backend-url.onrender.com/recommend-recipe")    
      즉, 로컬에서 되던 기능도 배포 후에는 주소, 보안, 환경 설정 차이로 인해 다시 점검해야 합니다.  
      5-8. 배포 후 수정 및 재배포 흐름  
      배포 후 문제가 발견되면 다음 순서로 수정합니다.  

3. 오류 상황 확인  
    브라우저 콘솔 및 네트워크 탭 확인  
    백엔드 로그 확인  
    코드 수정  
    GitHub에 반영  
    Vercel / Render 재배포 확인  
    실제 배포 주소에서 다시 테스트  
    이 과정을 통해 로컬 개발과 실제 서비스 운영의 차이를 이해할 수 있습니다.  
  
### 5-8. 성능 개선  

#### 입력 검증 정책

    사용자가 입력하는 재료 문자열에 대해 기본적인 유효성 검사를 적용합니다.
    
    - 빈 입력은 허용하지 않음
    - 최소 길이: 1자
    - 최대 길이: 100자
    - 허용 문자: 한글, 영문, 숫자, 공백, 쉼표(,)
    - 과도하게 긴 입력 또는 허용되지 않은 특수문자는 안내 메시지와 함께 차단
    
    예시:
    - 가능: `감자, 양파, 계란`
    - 가능: `chicken, onion, rice`
    - 제한 가능: HTML 태그, 스크립트 형태 문자열, 비정상적으로 긴 문장
    
    이 정책은 프론트엔드 1차 검증과 백엔드 입력 검증 강화 방향을 함께 고려한 것입니다.

#### 성능 최적화 및 응답 지연 개선 방안

현재 서비스는 기본적인 추천 기능 구현을 우선으로 완성하였으며, 다음과 같은 방식으로 응답 지연을 줄이도록 설계 및 확장 가능합니다.

##### 1) 캐시 전략
- 동일한 재료 입력에 대해 일정 시간 동안 결과를 재사용하는 캐시 적용 가능
- 예: `감자, 양파, 계란` 요청 결과를 5~10분 캐싱
- 기대 효과: 반복 요청 시 API 응답 시간 단축 및 서버 부하 감소

##### 2) 모델 경량화 전략
- 고비용/고지연 모델 대신 더 빠른 경량 모델 사용 가능
- 응답 속도가 중요한 상황에서는 요약형 응답 또는 간단 추천 모드 제공 가능

##### 3) 응답 요약 옵션
- 레시피 설명 길이를 줄인 '간단 추천 모드' 제공 가능
- 예: 재료, 조리 시간, 핵심 단계만 우선 출력
- 기대 효과: 사용자 대기 시간 감소, 모바일 화면 가독성 향상

##### 4) 운영 관점 개선 방향
- 자주 요청되는 레시피 패턴을 사전 템플릿화
- 서버 콜드 스타트 영향을 줄이기 위한 배포 환경 최적화 검토
- API 호출 실패 시 재시도 또는 기본 추천 결과 제공

#### 보안 및 비밀키 관리

본 프로젝트는 API 키 및 민감한 설정값을 프론트엔드에 직접 노출하지 않고, 서버 환경변수(.env 및 배포 환경 변수)로 관리하는 것을 원칙으로 합니다.

##### 1) 기본 보안 원칙
- API 키는 프론트엔드 코드에 직접 작성하지 않음
- 민감정보는 Render 환경변수로 관리
- `.env` 파일은 Git에 포함하지 않음
- CORS는 허용된 프론트엔드 도메인만 허용하도록 설정

##### 2) 키 유출 대응 절차
만약 API 키 유출이 의심되거나 확인될 경우 다음 절차를 수행합니다.

1. 유출된 키 즉시 비활성화 또는 재발급
2. Render/Vercel 환경변수 값 교체
3. GitHub 커밋 이력 및 공개 저장소 내 키 노출 여부 확인
4. 필요 시 노출된 커밋/파일 정리 후 재배포
5. API 사용 로그 및 비정상 호출 내역 점검
6. 재발 방지를 위해 `.gitignore`, 환경변수 분리, 키 검출 도구 적용 검토

##### 3) 프론트엔드 보안 고려사항
- 사용자의 입력값은 그대로 HTML에 삽입하지 않고 안전하게 출력
- 배포 URL은 HTTPS를 사용
- 사용자 입력에 대한 길이 제한 및 기본 패턴 검증 수행

##### 4) 백엔드(FastAPI) 보안 고려사항
- 요청 데이터 검증 강화
- 예외 발생 시 내부 정보가 과도하게 노출되지 않도록 일반화된 에러 메시지 사용
- 허용된 Origin만 CORS 설정
- 향후 Rate Limiting, 요청 크기 제한, 로그 모니터링 추가 가능

##### 5) 향후 보안 강화 계획
- 요청 횟수 제한(Rate Limiting)
- 관리자용 로그 모니터링
- 의심 트래픽 탐지
- 비밀키 자동 회전 정책 검토
