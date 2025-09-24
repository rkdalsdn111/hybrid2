
공공데이터(API) 브라우저 뷰어 – data.go.kr 예제

data.go.kr / safetydata.go.kr 오픈API를 브라우저에서 직접 호출하고, 응답(JSON/XML)을 표 형태로 파싱·검색·정렬해 보여주는 단일 HTML 앱입니다.
(코드는 공공데이터(API) 브라우저 뷰어 – data.go.kr 예제 파일에 포함되어 있습니다.)

✨ 주요 기능

URL·서비스키·추가 파라미터를 입력해 임의의 공공데이터 API 호출

JSON 자동 파싱 및 중첩 필드 평탄화 → 표 렌더링

검색/정렬(시간·가나다) 지원

샘플 프리셋: 에어코리아(시도별 대기오염) 즉시 테스트

CORS 프록시 가이드 포함(필요 시 로컬 프록시로 우회)

🚀 빠른 시작
1) 준비물

data.go.kr(또는 safetydata.go.kr)에서 활용신청 후 발급받은 serviceKey

일부 API는 서비스키가 이미 URL 인코딩(%) 되어 제공되기도 합니다.
400/403이 뜰 경우 인코딩된 키 / 원문 키를 각각 시도해 보세요.

2) 로컬에서 열기

이 저장소를 다운로드/클론

index.html을 브라우저로 열기 (더블클릭 또는 VSCode Live Server)

브라우저에서 외부 API로 fetch 하는 것이므로 별도의 빌드 단계가 없습니다.

🧪 사용 방법

상단 입력란에 다음을 채웁니다.

엔드포인트(URL): 공공데이터 API의 요청 URL

serviceKey: 발급받은 키

type/returnType: json 또는 xml (앱에서 자동으로 함께 세팅)

pageNo/numOfRows: 페이징 옵션

추가 파라미터(JSON): 예) { "sidoName": "서울", "ver": "1.4" }

요청/파싱하기 버튼 클릭 → 표로 표시

상단의 검색 입력 및 정렬 드롭다운 활용

샘플(에어코리아)

오른쪽의 샘플 불러오기(에어코리아) 버튼 클릭

배포(정적 호스팅)

GitHub Pages / Netlify / Vercel 등 정적 호스팅에 index.html만 올리면 동작합니다.

단, 배포 환경에서도 CORS 정책은 동일하게 적용됩니다. 필요하면 프록시를 서버리스 함수(예: Netlify Functions, Vercel Serverless)로 옮기세요.

🔧 커스터마이징 아이디어

필드 라벨 매핑: API 스키마에 맞춰 영문 키 → 한글 라벨

지도 시각화: 좌표 응답이 있는 API는 Leaflet/MapLibre로 마커 표시

자동 새로고침/알림: 재난/대기질 등 주기적 폴링 + 임계치 알림

다중 API 합치기: 동일 지역 기준으로 여러 API를 조인해 대시보드 구성

serviceKey만 입력 → 요청/파싱하기

결과 표에서 검색/정렬 활용
