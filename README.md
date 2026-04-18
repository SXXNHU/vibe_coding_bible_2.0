# Vibe Coding Guide

**대부분의 AI 코딩 가이드는 어떤 툴을 쓸지 알려줍니다. 이건 그 툴로 어떻게 생각할지를 알려줍니다.**

"Cursor 설치했는데, 막상 쓰려니 어디서부터 시작해야 할지 모르겠다."  
그 막막함이 이 프로젝트의 출발점입니다.

AI 코딩 툴을 처음 접하는 사람, 써봤지만 워크플로우가 정착되지 않은 사람을 위한 **구조화된 학습 흐름 가이드**입니다.

→ **[vibecodingv2.vercel.app](https://vibecodingv2.vercel.app/)**
<img width="1883" height="837" alt="image" src="https://github.com/user-attachments/assets/d674d62c-89dc-431e-ad3c-07308aa76436" />
<img width="1892" height="851" alt="image" src="https://github.com/user-attachments/assets/466760d0-b9f4-4f3a-96fe-5df3d3097457" />
<img width="1893" height="865" alt="image" src="https://github.com/user-attachments/assets/0e800585-c187-4cc9-80fe-0b5a1252746c" />
<img width="1895" height="863" alt="image" src="https://github.com/user-attachments/assets/52df0a84-4046-42ae-a483-de729c8ac5d8" />




---

## 무엇이 다른가

단순한 툴 비교표나 사용법 나열이 아닙니다.  
이 가이드는 AI와 함께 코딩할 때 반복되는 사고 루프를 명시적으로 훈련시킵니다:

```
설명(Explain) → 생성(Generate) → 실행(Run) → 평가(Evaluate) → 반복(Iterate)
```

이 루프를 무의식적으로 쓰는 사람과 쓰지 못하는 사람 사이의 격차가,  
"AI 코딩이 편하다"와 "AI 코딩이 어렵다"의 차이를 만듭니다.

---

## 트랙 시스템

트랙은 **실력 수준**이 아니라 **AI 워크플로우 친숙도**를 기준으로 구분됩니다.  
코딩을 오래 한 사람도 AI 툴이 처음이라면 Beginner 트랙이 맞습니다.

| 트랙 | 이런 분께 맞습니다 |
|---|---|
| **Beginner** | AI 툴을 한두 번 써봤지만 매번 흐름이 끊기는 분 |
| **Intermediate** | AI 툴을 꾸준히 쓰지만 워크플로우가 일정하지 않은 분 |
| **Advanced** | 감(vibe)이 아닌 시스템으로 AI 코딩을 하고 싶은 분 |

> 잘못된 트랙을 골라도 괜찮습니다 — 다른 트랙을 읽는 것 자체가 의도된 학습입니다.

---

## 사용 흐름

사이트에 진입하면 짧은 결정 흐름으로 시작합니다.  
몇 가지 질문을 통해 "내가 생각하는 나의 수준"이 아닌 **실제 위치**를 찾아냅니다.

<!-- 스크린샷: docs/screenshots/screenshot-decision-flow.png -->
<!-- 스크린샷: docs/screenshots/screenshot-track-page.png -->

각 트랙은 다음을 제공합니다:
- 해당 단계에 맞는 AI 코딩 사고 모델
- 툴 간 비교 및 워크플로우 비교 (주관적 권고 없이, 트레이드오프 중심)
- 다음 단계로 넘어가는 시점의 기준

---

## 라이브 데모

**[vibecodingv2.vercel.app](https://vibecodingv2.vercel.app/)** — 로그인 없음, 설치 없음, 모바일 지원

---

## 기술 스택

| 항목 | 내용 |
|---|---|
| 프레임워크 | React 19 + TypeScript (Vite) |
| 정적 페이지 | Vanilla HTML/CSS (런타임 의존성 없음) |
| 배포 | Vercel |
| 폰트 | Noto Sans KR, JetBrains Mono, Bebas Neue |

콘텐츠 페이지는 JavaScript 없이도 동작하는 정적 HTML로 제공됩니다.  
React 레이어는 향후 인터랙션 확장을 위한 구조로 분리되어 있습니다.

> 이 가이드 자체가 여기서 소개하는 워크플로우로 만들어졌습니다.

---

## 대상 독자

**이 가이드가 맞는 분:**
- AI 툴에 익숙하지 않은 개발자 및 코딩 입문자
- Cursor, Copilot, Claude를 써봤지만 한 시간 만에 포기한 경험이 있는 분
- AI 코딩 문화를 팀에 정착시키고 싶은 분

**이 가이드가 맞지 않는 분:**
- "AI 툴 TOP 10" 같은 목록형 정보를 찾는 분
- 단계별 튜토리얼 시리즈를 원하는 분

---

## 로컬 실행

```bash
git clone https://github.com/SXXNHU/vibe_coding_v2.git
cd vibe_coding_v2
npm install
npm run dev
```

개발 서버: `http://localhost:5173`

---

## 기여하기

의견이 다르다면 — 그게 이슈를 여는 좋은 이유입니다.

1. `main`에서 브랜치를 생성하세요
2. 정적 HTML 수정 시, 인라인 CSS/JS 구조를 유지해주세요
3. `npm run lint` 통과 후 PR을 열어주세요

오탈자나 내용 수정은 개발 환경 없이 HTML 파일을 직접 수정해도 됩니다.

---

## 라이선스

MIT License

---

*시작했다가 막혔지만, 그래도 계속 해보려는 분들을 위해 만들었습니다.*
