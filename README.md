# ✈️ RouteFlow

> ChatGPT로 짠 여행 일정을 보기 편하게 정리해주는 정적 웹앱

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-배포중-FF3C00?style=flat-square&logo=github)](.)
[![PWA](https://img.shields.io/badge/PWA-오프라인%20지원-4CAF50?style=flat-square)](.)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

---

## 📸 주요 화면

| 홈 (여행 목록) | 시간표 | 이동경로 | 예산 |
|:-:|:-:|:-:|:-:|
| 여행 카드 그리드 | 날짜×시간 그리드 | 날짜별 카드 | 카테고리 차트 |

---

## ✨ 기능

### 🏠 여행 목록 홈
- 저장된 모든 여행을 카드 형태로 한눈에 확인
- 여행지 국기, 기간, 일정 수, 총 경비 표시
- 여행 삭제 / 새 여행 추가

### 📅 일정 — 시간표 보기
- 날짜(열) × 시간(행) 그리드 시간표
- 분류별 컬러 배지 (이동·관광·숙소·식사·카페·쇼핑·체험)
- 🚌 이동 항목 ON/OFF 토글

### 🗺️ 이동경로 — 카드 편집
- 날짜별 탭 전환 (1일차, 2일차 ...)
- 일별 요약 카드: 총 이동시간 · 교통비 · 이동거리 · 환승 횟수
- 교통수단 칩 (기차, 버스, 도보, 택시, 지하철, 비행기)
- 번호 카드: 출발지 → 도착지, 교통 뱃지, 소요시간, 요금, 거리, 탑승 위치, 메모, Google Maps 링크
- ★ 즐겨찾기 / ✎ 편집 / 🗑 삭제
- **+ 경로 추가** 버튼으로 직접 입력 가능

### 💰 예산
- 총 지출 · 항목 수 · 카테고리 수 · 1일 평균
- 카테고리별 바 차트
- 날짜별 소계 + 전체 합계 테이블

### 기타
- 🔗 **공유** — 링크 복사 또는 텍스트 복사 (Web Share API)
- 🖨️ **인쇄** — 불필요한 버튼 자동 숨김
- 💾 **IndexedDB** — 브라우저에 여러 여행 영구 저장
- 📶 **PWA / 오프라인** — Service Worker 캐시 (인터넷 없이도 열람 가능)

---

## 🚀 사용 방법

### 1. ChatGPT에서 여행 요약 생성

아래 형식으로 ChatGPT에게 요청하세요:

```
아래 형식으로 여행 요약을 만들어줘.

📅 2026-12-31 ~ 2027-01-03
📍 일본 홋카이도
👥 가족 4명
💰 총 경비: 1,200,000원

📋 여행 일정

[2026-12-31]
13:30 | 인천공항 출발 | 탑승 수속 완료 후 대기 | 이동 | 비행기
16:00 | 신치토세 공항 도착 | 입국 심사 | 이동 | 도보

[2027-01-01]
09:00 | 호텔 체크아웃 | 짐 맡기기 | 숙소 | 도보
...

💸 지출 내역

2026-12-31 | 이동 | 공항 리무진 | 25,000원
2027-01-01 | 식사 | 스시 오마카세 | 80,000원
```

### 2. RouteFlow에서 가져오기

1. 상단 **✈️ 여행 가져오기** 클릭
2. ChatGPT 텍스트 붙여넣기
3. **분석하기** → 분류 선택 → **일정 가져오기**

---

## 📁 파일 구조

```
/
├── index.html      # 앱 전체 (CSS + JS 내장)
├── sw.js           # Service Worker (오프라인 지원)
├── favicon.svg     # 앱 아이콘
├── robots.txt
└── .nojekyll       # GitHub Pages Jekyll 비활성화
```

> **외부 의존성 없음** — CDN, 번들러, 빌드 도구 필요 없이 `index.html` 하나로 동작합니다.

---

## 🛠️ 로컬 실행

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
```

브라우저에서 `http://localhost:8080` 열기

---

## 📦 GitHub Pages 배포

1. 이 저장소를 Fork 또는 Clone
2. `Settings → Pages → Source: main branch / root` 설정
3. 자동 배포 완료 → `https://<username>.github.io/<repo>/`

---

## 🧰 기술 스택

| 항목 | 내용 |
|------|------|
| 프레임워크 | 없음 (Vanilla HTML/CSS/JS) |
| 데이터 저장 | IndexedDB (브라우저 내장) |
| 오프라인 | Service Worker (Cache API) |
| 폰트 | Google Fonts — Inter |
| 빌드 도구 | 없음 |
| 배포 | GitHub Pages |

---

## 📄 라이선스

MIT © RouteFlow
