# TestForProject
# 실시간 중고거래 + 경매 플랫폼 프론트엔드 환경 설정 문서

---

# 1. 프로젝트 개요

본 프로젝트는 **중고거래 플랫폼 + 실시간 경매 시스템**을 결합한 **웹앱 기반 서비스**이다.

### 핵심 기능

- 일반 중고거래 상품 등록 및 판매
- 실시간 경매 입찰
- 상품 검색 및 필터링
- 찜하기
- 사용자 채팅
- 알림 시스템
- 마이페이지
- 실시간 데이터 갱신

특히 이 프로젝트는 단순 게시판형 웹서비스가 아니라  

**실시간 경매 참여 중 최고 입찰가, 입찰자 수, 남은 시간, 경매 종료 상태가 즉시 반영되어야 하는 서비스**라는 점이 중요하다.

따라서 프론트엔드는 다음 조건을 만족해야 한다.

### 요구 조건

- 모바일 중심 UI
- 웹앱 형태
- 실시간 데이터 반영
- 여러 화면 라우팅 지원
- 더미 데이터 기반 선개발 가능
- GitHub 협업 및 배포 친화적 구조

---

# 2. 왜 웹앱으로 개발하는가

본 프로젝트는 **네이티브 앱이 아니라 웹앱(Web App)** 기준으로 개발한다.

## 이유

1. **개발 속도**
   - Android / iOS를 따로 만들지 않고 웹 하나로 시작 가능

2. **유지보수 용이**
   - 코드 수정 후 바로 배포 가능

3. **실시간 경매 구조와 잘 맞음**
   - SSE 같은 브라우저 기반 기술 사용 가능

4. **캡스톤 프로젝트 현실성**
   - 제한된 기간 안에서 구현 가능성이 높음

5. **향후 확장 가능**
   - PWA 또는 앱 래핑 가능

현재 목표는

> **Mobile-First Web Application**

이다.

---

# 3. 프론트 기술 스택

### 프레임워크
- **Next.js**

### 언어
- **TypeScript**

### 스타일링
- **Tailwind CSS**

### 런타임
- **Node.js**

### 코드 편집기
- **VS Code**

### AI 코딩 보조
- **GitHub Copilot**
- **GitHub Copilot Chat**

### 협업
- **GitHub**
- **GitHub Desktop**

### 배포
- **Vercel**

### 이미지 저장
- **AWS S3**

---

# 4. Next.js를 사용하는 이유

## 1. 페이지 구조 관리가 쉽다

예시 페이지

- 홈
- 로그인
- 회원가입
- 검색
- 상품 상세
- 경매 상세
- 실시간 경매 참여
- 마이페이지
- 채팅
- 고객센터

---

## 2. React 기반 컴포넌트 재사용

예

- 상품 카드
- 배지
- 찜 버튼
- 타이머
- 알림 아이콘
- 모달

---

## 3. 웹앱 구조에 적합

- 모바일 UI 중심 개발 가능
- 라우팅 관리 쉬움
- 레이아웃 관리 용이

---

## 4. 실무 사용률 높음

확장성과 유지보수성이 좋다.

---

# 5. TypeScript를 사용하는 이유

JavaScript 대신 **TypeScript**를 사용한다.

## 이유

1. **타입 안정성 확보**

예

- 상품 데이터
- 입찰 데이터
- 알림 데이터
- 사용자 데이터

2. **실시간 경매 구조 오류 방지**

3. **협업에 유리**

4. **유지보수성 향상**

---

# 6. Tailwind CSS를 사용하는 이유

## 장점

- 모바일 UI 제작 속도 빠름
- 카드형 UI 제작에 강함
- 반복 UI 제작에 효율적
- VS Code 자동완성과 궁합 좋음

예

- 상품 카드
- 경매 카드
- 버튼
- 배지
- 모달

---

# 7. Node.js 역할

Next.js는 **Node.js 위에서 실행되는 프레임워크**이다.

Node.js 역할

- Next.js 개발 서버 실행
- 패키지 설치
- 빌드 환경 제공
- 개발 도구 실행

즉

> Next.js는 Node.js 위에서 동작한다.

---

# 8. Node.js 설치 상태

현재 Node.js는 **Homebrew 기반 설치**이다.

```
node -v
npm -v
which node
```

---

# 9. VS Code 개발 환경

프론트엔드 개발은 **VS Code** 기준으로 진행한다.

### 선택 이유

- 가볍고 빠른 실행
- 플러그인 생태계 풍부
- Next.js / TypeScript / Tailwind 궁합
- GitHub Copilot 연동
- 협업 환경 통일

---

# 10. VS Code 플러그인

## Prettier

코드 자동 정렬

```javascript
const a = 1;
```

---

## ESLint

- 코드 오류 표시
- JavaScript / TypeScript 규칙 검사

---

## Tailwind CSS IntelliSense

- Tailwind 클래스 자동완성
- 스타일 미리보기

---

## GitHub Copilot

- AI 코드 자동완성
- 컴포넌트 생성 보조

---

# 11. 협업 방식

### 저장소

GitHub

### 로컬 작업 방식

1. GitHub Desktop clone
2. VS Code 코드 수정
3. commit
4. push

---

# 12. 배포 구조

```
사용자 브라우저
      │
      ▼
Vercel (Next.js)
      │
      ▼
Spring Boot API
      │
      ▼
PostgreSQL / Redis / AWS S3
```

---

# 13. 현재 완료된 환경 설정

- VS Code 개발 환경 구축
- 필수 플러그인 설치
- GitHub Copilot 설정
- Node.js 설치
- npm 정상 작동 확인
- 프론트 기술 스택 결정

---

# 14. 다음 단계

### Next.js 프로젝트 생성

```
npx create-next-app@latest frontend
```

### 실행

```
cd frontend
npm run dev
```

접속

```
http://localhost:3000
```

---

# 15. 예정 기능

- 로그인 / 회원가입
- 검색
- 상품 상세
- 경매 참여
- SSE 실시간 업데이트
- 알림
- 마이페이지
- 채팅

---

# 16. 결론

본 프로젝트 프론트엔드는

- **Next.js**
- **TypeScript**
- **Tailwind CSS**

기반의 **모바일 퍼스트 웹앱 구조**로 설계되며  

**VS Code + Copilot + Vercel**을 통해 효율적인 개발 환경을 구축한다.
