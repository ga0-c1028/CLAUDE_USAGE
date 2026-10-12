# 발표 대본 (SCRIPT)

슬라이드별로 말할 포인트입니다. 덱의 speaker notes와 내용이 같습니다.
`[출처]`에서 PDF가 아닌 자료는 `파일:줄` 형식으로 적었습니다.
목표 시간은 30~40분이고, 슬라이드당 약 2분입니다.

---

## Slide 1 — 오프닝

- 아이스브레이킹: 사진 3장으로 시작
- img1 자기소개서 → img2 책 추천사 → img3 지금 현재(놀람) 순서로 공개
- 교육을 듣고 느낀 변화로 자연스럽게 연결

---

## Slide 2 — AI 시대의 개발자

- 질문 던지기: AI 시대에 개발자로서 어떻게 살아남아야 하는가?
- 과거 Code Writer → 현재 Problem Solver → 미래 AI Collaborator (01 개요 15p)
- 미래의 개발자에게는 자연어로 요구를 정확히 표현하고 결과 품질을 판단하는 안목이 필요
- 결론 키워드 "AI Native" → 버튼을 눌러 상세 슬라이드로 이동
> [출처] 01_Vibe Coding 개요 15p

---

## Slide 2-2 — AI Native (클릭 시 열리는 숨김 슬라이드)

- AI Native 사고방식 4가지 (01 개요 17p)
- 핵심: 코드를 직접 쓰기보다 문제를 정의하고 방향을 제시하는 역할로 이동
- '돌아가기'로 2번 슬라이드 복귀 후 다음 장으로
> [출처] 01_Vibe Coding 개요 17p

---

## Slide 3 — 바이브 코딩이란?

- 안드레 카파시가 처음 제시: 자연어 프롬프트로 코드를 만드는 방식 (01 개요 2p)
- 기존 코딩과 비교: 개발자 역할이 '작성자'에서 '가이드·테스터'로 (3p)
- 적합/부적합: 프로토타입에는 좋지만 미션 크리티컬·보안 영역은 단독 사용 금지 (11p)
- 현실적 해법은 하이브리드: VDT + TDD + 코드리뷰
> [출처] 01_Vibe Coding 개요 2·3·11·21p

---

## Slide 4 — 3대 부채

- 키워드만 제시: 기술부채 / 인지부채 / 의도부채
- (발표자 보충 필요 — 원자료 PDF에 없는 내용이라 키워드만 둠)
- '해결하기 위한 첫 걸음'으로 다음 장 SDD로 연결

---

## Slide 5 — SDD

- SDD = 명세를 먼저 쓰고, 명세를 단일 진실 공급원으로 삼는 방법론 (01 개요 22p)
- 작업 방식: Steering → Spec → Implement
- 명세는 개발 후 버리는 게 아니라 계속 관리하는 '살아있는 문서'
- Spec kit 흐름: Specify → Plan → Tasks → Implement (23p)
> [출처] 01_Vibe Coding 개요 22–23p

---

## Slide 6 — 개발 환경 구성

- 목표가 풀스택 완성이라 프론트·백엔드·DB·배포까지 한 번에 세팅 (02 환경설정 15p)
- 개발: Node.js(Claude Code 실행), Python(일부 MCP), Git·gh(리포·PR·이슈), VS Code
- 운영: Supabase는 PostgreSQL만 사용, Vercel로 배포
- 참고 — 포트 구성: 개발 FE 5173 / BE 3000 / DB 5432, 운영 Vercel + Supabase
- 참고 — 모델 분담: opus 요구사항 정의 / sonnet 개발 / haiku 문서 작업
> [출처] 02_환경설정 7·12·15p / 강의내용.txt:58-66, 72-74

---

## Slide 7 — 프롬프트 엔지니어링 — CLAUDE.md

- CLAUDE.md = Claude Code가 매번 읽는 프로젝트 지침 (04 도구 50p)
- 넣을 것: 명령어, 구조, 스타일·테스트 지침, 환경 설정, 반드시 지킬 규칙
- /init보다 직접 작성, 200줄 이내로
- 참고 링크: Karpathy 지침 — 코딩 전에 생각하기 / 단순함 최우선 / 외과적 변경 / 목표 지향 실행
- 강사가 이 링크를 두 번 공유할 만큼 강조
> [출처] 04_Vibe Coding을 위한 도구 8·50p / script_zip/CLAUDE.md:20-74 / chat/2026-08-25.md:10, 2026-08-26.md:90

---

## Slide 8 — 프롬프트 엔지니어링 핵심 원칙

- 프롬프트 7가지 구성 요소 (03 프롬프트 엔지니어링 3p)
- 강조 1 — 지시어: 해야 할 것과 하지 말아야 할 것을 분리해서 쓰기
- 강조 2 — 역할: 이전 Claude Code·GPT 교육에서도 똑같이 강조 → AI 모델 모두 비슷
- 핵심 원칙 10개·전략 3개 중 다음 3장에서 최소 충분 컨텍스트 / Do·Don't / 검수 루프를 자세히
> [출처] 03_프롬프트 엔지니어링 3–4p

---

## Slide 9 — 원칙 1: 최소 충분 컨텍스트

- 정의: 정확한 결과에 필요한 최소한의 정보만 (03 프롬프트 엔지니어링 20p)
- 목적 3가지: 효율성·집중도·비용
- 강사가 강조한 '하네스 엔지니어링' 영상 소개 (캡처 자리)
- TODO: 대본 요약 / 퀴즈
> [출처] 03_프롬프트 엔지니어링 20p / chat/2026-08-24.md:39-40 (영상 링크)

---

## Slide 10 — 원칙 2: DO/DON'T 병행

- DO와 DON'T를 함께 써서 경계를 명확히 (03 프롬프트 엔지니어링)
- 템플릿: 필수 DO / 권장 DO / 절대 DON'T / 권장하지 않는 DON'T
- 상황별 조정: 초보자는 DON'T 상세히, 경험자는 DO 중심
- 실제 예시: CLAUDE.md에 do / do not 작성, "Prisma 사용 금지", "개발서버 직접 실행하지 마"
- 내가 만든 프롬프트 사진으로 마무리
> [출처] 03_프롬프트 엔지니어링 21–23p / 강의내용.txt:82-83 / chat/2026-08-26.md:32 / chat/2026-08-27.md:8-9

---

## Slide 11 — 원칙 3: 검수 루프

- 4단계 순환: 생성 → 평가 → 개선 → 재생성 (03 프롬프트 엔지니어링)
- 한 번에 완벽한 프롬프트는 없다 — 반복이 전제
- 실습 예: 도메인 정의서를 AI에게 완전성·명확성·추적성·검증 가능성·유지보수성 5가지 기준으로 평가하게 함
- 문서 정합성 확인, Swagger 일관성 검토도 같은 루프
> [출처] 03_프롬프트 엔지니어링 / 05_프로젝트 기획 및 설계 (도메인 정의서 평가) / chat/2026-08-26.md:7-13

---

## Slide 12 — 슬래시 명령어

- 카테고리별 주요 명령어 (04 도구 6–9p)
- 자주 쓰는 조합: 기능 구현 → /simplify → /diff → 마음에 안 들면 /rewind, PR 직전 /review
- /compact [args]: 지침을 주며 압축 / /permissions: default·acceptEdits·plan·bypassPermissions (13–16p 참고)
- 팁: /context가 80% 정도면 /compact 하고 시작해야 auto-compaction을 피함
> [출처] 04_Vibe Coding을 위한 도구 6–9p, 13–16p / 강의내용.txt:98-100

---

## Slide 13 — 서브에이전트

- 서브에이전트: 독립 컨텍스트로 일해서 메인 컨텍스트 용량을 늘리지 않음 (04 도구 18p)
- 너무 구체적이면 범용성이 떨어짐 → 상세 내용은 Skill·사용자 정의 command로
- 직접 만들기보다 검증된 제3자 것을 가져다 쓰기: aitmpl, VoltAgent
- 실습 예: docs-architect, frontend-expert 같은 역할 에이전트 생성
> [출처] 04_Vibe Coding을 위한 도구 18–19p / chat/2026-08-25.md:29-108

---

## Slide 14 — MCP

- MCP = AI가 외부 도구·서비스를 쓰는 표준 프로토콜 (04 도구 25p)
- 예: DB를 자연어로 조회, Git 작업을 자연어로
- 자주 쓰는 것: context7 — 최신 라이브러리 문서를 참조해 옛날 코드 생성 방지 (26p)
- 링크: context7 / github-mcp-server / playwright-mcp / aitmpl.com
- 실습에서 실제로 쓴 MCP: context7, playwright, chrome-devtools, supabase, postgres
> [출처] 04_Vibe Coding을 위한 도구 25–26p / script_zip/opencode.json

---

## Slide 15 — Hook

- Hook = 특정 이벤트에 자동 실행되는 동작, 트리거 기반 자동화 (04 도구 34–35p)
- 예: Stop 이벤트에 say로 완료 알림 / 파일 수정 후 prettier 자동 실행
- 작성 위치는 프로젝트 수준 .claude/settings.json 추천 (36p)
- 하네스와의 차이: 하네스는 AI를 원하는 대로 제어하는 것, Hook은 '무조건' 지켜야 할 것에 쓰는 강력한 하네스 (36–37p 메모)
- 실습 예: PostToolUse + matcher "Write|Edit|MultiEdit"로 prettier 실행
> [출처] 04_Vibe Coding을 위한 도구 34–37p / chat/2026-08-25.md:123-133

---

## Slide 16 — Plan Mode 활용

- Plan Mode: 계획만 세우고 실행하지 않음 (04 도구 46p)
- 전환: Shift + Tab (또는 /plan)
- 예시 4단계: 방법 추천 → 계획 수립 → 빠진 것 확인 → 계획 재수립 (46–49p)
- 계획을 여러 번 다듬은 뒤 실행하는 게 핵심
- 참고: 권한 모드 default / acceptEdits / plan / bypassPermissions
> [출처] 04_Vibe Coding을 위한 도구 16·46–49p / 강의내용.txt:110-114

---

## Slide 17 — Skills

- Skill = SKILL.md + 스크립트, prompt와 script 명령까지 재사용 (04 도구 54p)
- 자동 호출, 필요할 때만 전체 로드 → 토큰 절감
- 작성 위치 .claude/skills/<이름>/SKILL.md, 주요 필드 name·description·allowed-tools·context (55p)
- skills.sh에서 찾아보기, Tip: ponytail로 토큰 절약 (57p)
- 토큰 절약 관련: Ponytail·Caveman, /config output-style concise
> [출처] 04_Vibe Coding을 위한 도구 53–57p / 강의내용.txt:24-28, 126

---

## Slide 18 — 비교

- 세 가지를 한 표로 비교 (04 도구 56p)
- Skill = 절차적 지식, 필요할 때만 로드
- Subagent = 독립 컨텍스트에서 일하는 전문 에이전트
- MCP = 외부 도구와 연결하는 프로토콜, 항상 연결
> [출처] 04_Vibe Coding을 위한 도구 56p

---

## Slide 19 — 프로젝트 생성 과정

- 실습 프로젝트 '팀캘린더톡'을 만든 흐름 (05~08 강의자료)
- 기획·설계: 도메인 정의서 → PRD → 시나리오 → 와이어프레임 → 아키텍처 → ERD → 작업 계획 → Swagger
- 백엔드: DB 구성, Issue 생성, 개발 / 프론트엔드: 스타일, 개발, 통합 테스트
- 배포: Supabase + Vercel, GitHub Actions로 CI/CD
- 실습 팁: '개발서버는 내가 띄움' 지시, E2E는 Playwright MCP
> [출처] 05~08 강의자료 목차 / chat/2026-08-27.md:8-9 / chat/2026-08-28.md:10-11
