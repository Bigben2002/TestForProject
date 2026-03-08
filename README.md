# TestForProject
실시간 중고거래 + 경매 플랫폼
프론트엔드 개발 환경 설정 문서
1. 프로젝트 개요

본 프로젝트는 중고거래 플랫폼 + 실시간 경매 시스템을 결합한 웹 기반 서비스이다.

서비스의 핵심 특징은 다음과 같다.

일반 중고거래 상품 등록 및 판매

실시간 경매 입찰 시스템

상품 탐색 및 검색 기능

사용자 간 채팅

알림 시스템

실시간 데이터 업데이트

특히 경매 시스템에서는 실시간 입찰가 변경, 남은 시간 업데이트, 낙찰 상태 변경과 같은 이벤트가 발생하기 때문에 실시간 데이터 반영 구조가 필요하다.

이를 위해 프론트엔드에서는 다음과 같은 기술을 사용할 예정이다.

SSE (Server Sent Events)

Next.js 기반 웹 애플리케이션

2. 개발 환경

프론트엔드 개발은 다음 환경을 기준으로 진행한다.

개발 장비

macOS (MacBook M3)

Visual Studio Code

협업 및 버전 관리

GitHub

GitHub Desktop

코드 작성 환경

VS Code

GitHub Copilot (AI 코딩 보조)

런타임 환경

Node.js

프레임워크

Next.js

3. VS Code 플러그인

프론트엔드 개발 생산성을 높이기 위해 다음 확장을 사용한다.

1. Prettier - Code Formatter

역할

코드 자동 정렬

코드 스타일 통일

예시

저장 시 코드가 자동 정리된다.

const a=1

↓

const a = 1;

팀 협업에서 코드 스타일 충돌을 방지하기 위해 필수적으로 사용한다.

2. ESLint

역할

코드 오류 검출

JavaScript / TypeScript 규칙 검사

예

사용하지 않는 변수

잘못된 문법

React 규칙 위반

개발 과정에서 발생할 수 있는 오류를 실시간으로 표시한다.

3. Tailwind CSS IntelliSense

역할

Tailwind CSS 자동완성

클래스 오류 검출

스타일 미리보기

예

bg-blue-500

입력 시 자동완성 제공.

4. GitHub Copilot

역할

AI 코드 자동 생성

코드 자동완성

함수 생성

예

// create auction countdown timer

작성하면 관련 코드 자동 생성.

특히 다음 기능에서 활용도가 높다.

SSE 연결 코드

API 호출

React 컴포넌트 생성

4. 사용 언어
TypeScript

Next.js 프로젝트에서는 JavaScript 대신 TypeScript를 사용한다.

사용 이유

타입 안정성 확보

코드 오류 사전 방지

협업 시 코드 이해도 증가

유지보수 용이

예

interface Product {
  id: number
  name: string
  price: number
}
5. 프레임워크 선택
Next.js

본 프로젝트의 프론트엔드 프레임워크는 Next.js를 사용한다.

Next.js는 React 기반의 웹 프레임워크로 다음 특징을 가진다.

장점

서버 사이드 렌더링 지원

빠른 페이지 로딩

SEO 최적화

API Routes 제공

대규모 서비스 구조 지원

특히 중고거래 플랫폼에서는

상품 목록 페이지

검색 페이지

상품 상세 페이지

등 데이터 중심 페이지가 많기 때문에 Next.js가 적합하다.

6. Node.js 사용 이유

Next.js는 Node.js 환경에서 실행되는 프레임워크이다.

Node.js는 다음 역할을 한다.

Next.js 개발 서버 실행

패키지 관리 (npm)

빌드 시스템

개발 도구 실행

예

npm run dev

개발 서버 실행

7. Node 설치 방식

Node는 Homebrew 기반으로 관리한다.

선택 이유

버전 관리 용이

업데이트 간단

macOS 개발 환경과 호환성 좋음

예

업데이트

brew upgrade node

설치

brew install node
8. 웹앱 구조

본 서비스는 웹 기반 애플리케이션으로 개발한다.

이유

모바일 / 웹 동시 지원

빠른 개발

배포 용이

유지보수 편리

9. 실시간 데이터 구조

경매 시스템의 핵심은 실시간 데이터 업데이트이다.

예

최고 입찰가 변경

남은 시간 감소

낙찰 상태 변경

이를 위해 SSE(Server Sent Events) 방식을 사용한다.

SSE 특징

서버 → 클라이언트 단방향 스트리밍

WebSocket보다 구현 단순

HTTP 기반

프론트 구조

Next.js Client
      │
      │ SSE
      ▼
Auction Server
10. UI 주요 기능

홈 화면에서 상품은 다음 정보를 포함한다.

상품 이미지

상품 이름

현재 가격

남은 시간

조회수

찜 여부

판매 방식

판매 방식은 배지 형태로 표시한다.

예

일반 판매

경매 상품

11. 검색 기능

검색 입력 시

자동완성 방식으로 연관 키워드만 표시한다.

예

검색어

맥북

추천 검색어

맥북 에어
맥북 프로
맥북 m3

이 방식은 당근마켓 UI 구조와 유사하다.

12. 앞으로 남은 환경 설정

현재까지 완료된 설정

VS Code 설치

개발 플러그인 설치

GitHub Copilot 설정

Node.js 설치

개발 환경 정리

앞으로 진행할 단계

1단계

Next.js 프로젝트 생성

2단계

프로젝트 폴더 구조 설계

예

src
components
features
hooks
services
types
3단계

API 연결 구조 설계

4단계

SSE 실시간 연결 구현

5단계

홈 화면 UI 구현

6단계

상품 상세 페이지

7단계

경매 입찰 기능

13. 개발 목표

본 프로젝트의 목표는 다음과 같다.

실시간 경매 시스템 구현

사용자 친화적인 중고거래 UI 제공

안정적인 데이터 처리

실시간 이벤트 반영

결론

본 프로젝트는

Next.js + TypeScript + SSE 기반의 실시간 중고거래 플랫폼

을 목표로 한다.

이를 위해

VS Code 기반 개발 환경

Node.js 런타임

Next.js 프레임워크

GitHub 협업 구조

AI 코딩 도구(Copilot)

를 활용하여 개발을 진행한다.
