# TestForProject
# 실시간 중고거래 + 경매 플랫폼 프론트엔드 환경 설정 문서

## 1. 프로젝트 개요

본 프로젝트는 **중고거래 플랫폼 + 실시간 경매 시스템**을 결합한 **웹앱 기반 서비스**이다.

핵심 기능은 다음과 같다.

- 일반 중고거래 상품 등록 및 판매
- 실시간 경매 입찰
- 상품 검색 및 필터링
- 찜하기
- 사용자 채팅
- 알림 시스템
- 마이페이지
- 실시간 데이터 갱신

특히 이 프로젝트는 단순 게시판형 웹서비스가 아니라,  
**실시간 경매 참여 중 최고 입찰가, 입찰자 수, 남은 시간, 경매 종료 상태가 즉시 반영되어야 하는 서비스**라는 점이 중요하다.

따라서 프론트엔드는 일반적인 정적 페이지가 아니라 다음 조건을 만족해야 한다.

- 모바일 중심 UI
- 웹앱 형태
- 실시간 데이터 반영
- 여러 화면 라우팅 지원
- 더미 데이터 기반 선개발 가능
- GitHub 협업 및 배포 친화적 구조

---

## 2. 왜 웹앱으로 개발하는가

본 프로젝트는 **네이티브 앱이 아니라 웹앱(Web App)** 기준으로 개발한다.

### 이유

1. **개발 속도**
   - Android / iOS를 따로 만들지 않고 웹 하나로 시작 가능
2. **유지보수 용이**
   - 코드 수정 후 바로 배포 가능
3. **실시간 경매 구조와 잘 맞음**
   - SSE 같은 브라우저 기반 기술을 사용하기 좋음
4. **캡스톤 프로젝트 현실성**
   - 제한된 기간 안에서 구현 가능성이 높음
5. **향후 확장 가능**
   - 추후 PWA 또는 앱 래핑도 가능

즉 현재 목표는  
**모바일 퍼스트 반응형 웹앱(Mobile-First Web Application)** 이다.

---

## 3. 현재 확정한 프론트 기술 선택

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

### 파일 저장소
- **AWS S3**  
  (프론트 배포와는 별개로 이미지 저장용)

---

## 4. 왜 Next.js를 사용하는가

이번 프로젝트의 프론트엔드는 **Next.js**를 사용한다.

### 선택 이유

1. **페이지 구조가 명확하다**
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

   위와 같은 다수의 화면을 구조적으로 관리하기 좋다.

2. **React 기반이라 컴포넌트 재사용이 쉽다**
   - 상품 카드
   - 배지
   - 찜 버튼
   - 타이머
   - 알림 아이콘
   - 모달

3. **웹앱 구조에 적합하다**
   - 모바일 UI 중심으로 제작 가능
   - 라우팅과 레이아웃 관리가 쉬움

4. **실무/현업에서도 많이 사용된다**
   - 확장성과 유지보수성이 좋다.

---

## 5. 왜 TypeScript를 사용하는가

JavaScript 대신 **TypeScript**를 사용한다.

### 이유

1. **타입 안정성 확보**
   - 상품 데이터
   - 입찰 데이터
   - 알림 데이터
   - 사용자 데이터

2. **실시간 경매 구조에서 오류 방지**
   - SSE 이벤트 구조를 명확하게 다룰 수 있다.

3. **협업에 유리**
   - 어떤 데이터가 어떤 형태인지 바로 알 수 있다.

4. **유지보수에 강함**
   - 기능이 많아질수록 TypeScript의 장점이 커진다.

---

## 6. 왜 Tailwind CSS를 사용하는가

UI 스타일링은 **Tailwind CSS**를 사용한다.

### 이유

1. **모바일 UI 제작이 빠르다**
2. **카드형 UI에 강하다**
   - 중고거래 상품 카드
   - 경매 상품 카드
3. **배지 / 버튼 / 리스트 / 모달 같은 반복 UI를 빠르게 만들 수 있다**
4. **VS Code 자동완성과 함께 생산성이 높다**

---

## 7. 왜 Node.js가 필요한가

Next.js는 **Node.js 위에서 실행되는 프레임워크**이기 때문에 Node.js가 필요하다.

Node.js는 다음 역할을 한다.

- Next.js 개발 서버 실행
- 패키지 설치
- 빌드 및 실행 환경 제공
- 개발 도구 구동

즉 **Next.js는 설치 프로그램이 아니라 Node.js 위에서 생성되는 프레임워크 프로젝트**다.

---

## 8. Node.js 설치 방식

현재 Node.js는 **Homebrew 기반으로 설치 및 관리**하도록 정리했다.

### 현재 상태

- `node -v` → `v25.8.0`
- `npm -v` → `11.11.0`
- `which node` → `/opt/homebrew/bin/node`

### 의미

이제 Node는 Homebrew가 관리한다.

### 장점

- 업데이트 쉬움
- 삭제 쉬움
- macOS 개발 환경과 잘 맞음
- 경로가 깔끔함

### 예시 명령

```bash
brew upgrade node
## 9. VS Code 개발 환경

현재 프론트엔드 개발은 **Visual Studio Code(VS Code)**를 기준으로 진행한다.

### 사용 이유

1. 가볍고 빠른 실행 환경
2. 풍부한 플러그인 생태계
3. Next.js / TypeScript / Tailwind와 궁합이 좋음
4. GitHub Copilot과의 연동이 쉬움
5. 협업 시 동일한 개발 환경 유지가 가능

VS Code는 프론트엔드 개발에서 가장 널리 사용되는 코드 편집기 중 하나이며,  
프로젝트 생산성과 협업 효율을 높이기 위해 선택하였다.

---

## 10. 설치한 VS Code 플러그인

프론트엔드 개발 생산성을 높이기 위해 다음 플러그인을 사용한다.

### 1️⃣ Prettier - Code Formatter

역할

- 코드 자동 정렬
- 저장 시 코드 스타일 통일

예

```javascript
const a=1

저장 후

const a = 1;

팀 협업 시 코드 스타일 충돌을 방지하기 위해 필수적으로 사용한다.

2️⃣ ESLint

역할

코드 오류 표시

JavaScript / TypeScript 코드 규칙 검사

예

사용하지 않는 변수 감지

잘못된 문법 감지

React 규칙 위반 표시

개발 중 발생할 수 있는 오류를 실시간으로 확인할 수 있다.

3️⃣ Tailwind CSS IntelliSense

역할

Tailwind CSS 클래스 자동완성

스타일 미리보기

클래스 오류 검출

예

bg-blue-500

입력 시 자동완성 제공.

4️⃣ GitHub Copilot

역할

AI 코드 자동완성

함수 및 컴포넌트 생성 보조

반복 코드 작성 자동화

예

// create auction countdown timer

위와 같은 주석을 작성하면 관련 코드가 자동 생성된다.

5️⃣ GitHub Copilot Chat

역할

코드 설명

코드 수정 제안

코드 생성 요청

예

Next.js SSE 예제 만들어줘
11. GitHub Copilot을 사용하는 이유

이번 프로젝트는 기능이 많고 실시간 데이터 처리가 포함되기 때문에
AI 코딩 보조 도구를 활용하여 개발 생산성을 높이기로 했다.

활용 예상 영역

React 컴포넌트 생성

상품 카드 UI 생성

검색 UI 초안 생성

API 호출 코드 작성

SSE 연결 코드 생성

TypeScript 타입 정의 생성

단, Copilot은 보조 도구이며 프로젝트 구조와 로직 설계는 직접 이해하고 관리한다.

12. 협업 방식
저장소 관리

GitHub

로컬 작업 방식

GitHub Desktop으로 repository clone

VS Code에서 코드 수정

GitHub Desktop에서 commit

GitHub Desktop에서 push

선택 이유

Git 명령어에 익숙하지 않은 팀원도 쉽게 협업 가능

변경 파일을 시각적으로 확인 가능

commit 및 push 과정이 직관적

협업 진입 장벽이 낮음

13. 배포 및 저장소 구조
프론트엔드 배포

Vercel

이미지 저장소

AWS S3

역할 구분
Vercel

프론트 웹앱 배포

GitHub 연동 자동 배포

Next.js와 높은 호환성

AWS S3

상품 이미지 저장

이미지 URL 제공

전체 구조
사용자 브라우저
      │
      ▼
Vercel (Next.js 프론트)
      │
      ▼
Spring Boot API 서버
      │
      ▼
PostgreSQL / Redis / AWS S3
14. 왜 이 환경이 프로젝트에 적합한가

우리 팀 프로젝트는 다음 특징을 가진다.

핵심 특성

중고거래 + 경매 결합 플랫폼

상품 카드 기반 UI

검색 및 탐색 기능

로그인 / 회원가입 / 마이페이지

경매 참여 화면

실시간 데이터 반영

알림 및 채팅

선택한 기술이 적합한 이유
Next.js

다양한 페이지 구조 관리에 적합

TypeScript

데이터 타입 안정성 확보

Tailwind CSS

카드 기반 UI 제작에 효율적

Node.js

Next.js 실행 환경 제공

VS Code + Copilot

개발 생산성 향상

Vercel

무료 배포 가능

Next.js와 최적화

GitHub Desktop

협업 진입 장벽 낮음

15. 현재까지 완료된 환경 설정
완료된 항목

VS Code 개발 환경 구축

필수 플러그인 설치

GitHub Copilot 설정

GitHub Copilot Chat 설정

Node.js 환경 정리

Homebrew 기반 Node 설치

npm 정상 작동 확인

프론트 기술 스택 결정

확정된 기술 스택

Next.js

TypeScript

Tailwind CSS

Node.js

VS Code

GitHub Copilot

GitHub Desktop

Vercel

AWS S3

16. 앞으로 남은 환경 설정

현재 환경 구축은 대부분 완료되었으며
이제 실제 프론트 프로젝트를 생성해야 한다.

1️⃣ Next.js 프로젝트 생성
npx create-next-app@latest frontend
생성 시 선택 옵션

TypeScript → Yes

ESLint → Yes

Tailwind CSS → Yes

src directory → Yes

App Router → Yes

Turbopack → Yes

import alias → @/*

2️⃣ 프로젝트 실행 확인
cd frontend
npm run dev

브라우저 접속

http://localhost:3000
3️⃣ 프로젝트 폴더 구조 설계

예시 구조

src/
 ├ app/
 ├ components/
 ├ features/
 ├ shared/
 ├ stores/
 ├ mocks/
 ├ types/
4️⃣ 공통 레이아웃 설계

초기 구현 예정 UI

상단 헤더

검색창

알림 아이콘

메뉴 버튼

메인 피드 레이아웃

5️⃣ 홈 화면 UI 구현

먼저 구현할 UI

상품 카드

경매 / 일반 판매 배지

남은 시간

최고 입찰가

조회수

찜 버튼

6️⃣ 이후 구현 예정 기능

로그인 / 회원가입

검색 및 자동완성

상품 상세 페이지

경매 참여 화면

SSE 실시간 업데이트

알림 시스템

마이페이지

채팅 기능

17. 경매 시스템과 SSE

이번 프로젝트의 핵심은 실시간 데이터 반영이다.

실시간 반영 대상

최고 입찰가

입찰자 수

남은 시간

경매 종료 상태

사용자 알림

데이터 흐름

초기 데이터 → REST API

실시간 데이터 → SSE

즉 프론트는 단순 조회 서비스가 아니라
실시간 경매 상태를 반영하는 웹 애플리케이션이다.

18. 최종 정리

본 프로젝트의 프론트엔드 환경은 다음과 같이 구성된다.

기술 스택

Next.js

TypeScript

Tailwind CSS

Node.js

VS Code

GitHub Copilot

GitHub Desktop

Vercel

AWS S3

현재 상태

개발 도구 준비 완료

Node 환경 정리 완료

프론트 기술 방향 확정 완료

다음 목표

Next.js 프로젝트 생성

프로젝트 폴더 구조 설계

홈 화면 UI 구현

상품 카드 컴포넌트 제작

19. 결론

본 프로젝트의 프론트엔드 환경은

“중고거래 + 실시간 경매 웹앱”이라는 서비스 특성에 맞춰
Next.js 기반 모바일 퍼스트 구조로 설계하고,
TypeScript와 Tailwind CSS로 안정성과 생산성을 확보하며,
VS Code와 GitHub Copilot을 활용해 효율적인 개발을 진행하기 위한 환경으로 구성하였다.”
