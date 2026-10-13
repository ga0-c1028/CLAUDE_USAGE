# 발표 구성 (PRESENTATION SPEC)


## Slide 1 — 오프닝 (제목)


- 제목 "AI 시대에 개발자로 살아남기", 소제목 "멀티캠퍼스 「바이브코딩으로 완성하는 풀스택 서비스」 교육 내용 공유", 발표자(생산실행개발파트 노가영)만 표시


---


## Slide 1-2 — 오프닝 (사진, 클릭 단계마다 한 장씩: 1-2 ~ 1-2g)


> 이미지는 `presentation/자료/`에 있음 (question.png, image.png, suno.png, suno_2.png).


- 처음: img1 자리에 image.png, img2 자리에 suno_2.png (suno_2.png는 세로로 크게)


- 클릭 1 → question.png가 화면 가로를 채워 등장


- 클릭 2 → image.png가 question.png와 상단·가로 폭을 맞춰 덮어씀


- 클릭 3 → 왼쪽에 suno.png


- 클릭 4 → 오른쪽에 suno_2.png


- 클릭 5 → 왼쪽 image.png, 오른쪽 suno_2.png


- 클릭 6 → 🫢 이모지가 화면 가득


---


## Slide 2 — AI 시대의 개발자


- AI 시대에 우리는 개발자로서 어떻게 살아남아야 하는가?


- 과거의 개발자: **code writer**


- 현재의 개발자: **problem solver**


- 미래의 개발자: **AI collaborator**


- ⇒ **"AI Native"**


### Slide 2-2 — "AI Native" 클릭 시 연결되는 상세 슬라이드


- (정의) AI를 단순히 활용하는 것을 넘어, 핵심 구성 요소로서 시작부터 AI로 설계된 대상


- 기존의 코드를 직접 작성하는 방식에서 AI와 대화하며 개발하는 패러다임으로 전환


- 자연어로 의도를 표현하는 능력


- AI의 강점과 한계를 이해하고 적절히 활용


- 코드 작성보다는 문제 정의와 방향 제시에 집중


---


## Slide 3 — 바이브 코딩이란?


- `01_Vibe Coding 개요.pdf` 내용을 참고하여 간결하게 정리


---


## Slide 4 — 3대 부채


- 기술부채 (Technical debt)


- 인지부채 (Cognitive debt)


- 의도부채 (Intent debt)


- 각 부채 카드를 클릭하면 보충 설명 슬라이드로 이동


### Slide 4-1 / 4-2 / 4-3 — 기술부채 / 인지부채 / 의도부채 보충 설명


- 제목만 두고, 보충 설명은 추후 직접 작성


---


## Slide 5 — SDD 설명


- `01_Vibe Coding 개요.pdf` 22~23페이지 SDD 설명 부분 참고


---


## Slide 6 — 개발 환경 구성


- 본 강의에서는 풀스택 개발을 완성하는 것이 목표였기 때문에 아래의 것들을 사용했음


- `02_환경설정.pdf` 15페이지 내용 참고


  - 설치한 항목, 설치 이유(사용처)를 **한 문장 이하**로 최대한 간결하게 정리


  - 한 장에 모두 보이도록 구성


---


## Slide 7 — 프롬프트 엔지니어링 (예정)


> ⚠️ 현재 4번 PDF가 없는 상태이므로, 이 페이지는 일단 공란으로 두기


- 프롬프트 엔지니어링


- 참고: 4번 PDF 50p / [andrej-karpathy-skills CLAUDE.md](https://github.com/multica-ai/andrej-karpathy-skills/blob/main/CLAUDE.md)


---


## Slide 8 — 프롬프트 엔지니어링 핵심 원칙


- `03_Vibe Coding을 위한 프롬프트 엔지니어링.pdf` 3페이지 내용 정리


  - 지시어에 대한 것 중요하게 강조


  - 흥미로웠던 사실: 역할에 대한 언급 (이전 Claude Code, GPT 사용 교육 시에도 동일 — AI 모델들 모두 비슷)


- 핵심 원칙과 프롬프트 전략도 함께 정리


---


## Slide 9 — 프롬프트 작성 원칙 1: 최소 충분 컨텍스트


- **최소 충분 컨텍스트 (Minimal Sufficient Context)**


- 강사님이 강조하신 유튜브 "하네스 엔지니어링" 관련 대본 첨부


  - [YouTube 영상](https://www.youtube.com/watch?v=bSHLtglLbJA) 캡처


- 잘못된 내용 찾아보기 (TODO)


---


## Slide 10 — 프롬프트 작성 원칙 2: DO/DON'T 병행


- **긍정/부정 지시 병행 (DO / DON'T)**


- 목적: 명확한 경계 설정 / 품질 보장 / 위험 회피


### 예시 템플릿


```


### 필수 DO [ 핵심 요구 사항 ]


### 권장 DO [ 추가 권장 사항 ]


### 절대 DON'T [ 절대 금지 사항 ]


### 권장하지 않는 DON'T [ 권장하지 않는 사항 ]


```


### 상황별 조정


| 상황 | 조정 방향 |


|---|---|


| 초보자 대상 | DON'T 항목 상세히 |


| 경험자 대상 | DO 항목 중심으로 |


| 보안 중요 | 보안 관련 DON'T 강화 |


| 성능 중요 | 성능 관련 DO 강화 |


> 내가 만든 프롬프트 사진 첨부


---


## Slide 11 — 프롬프트 작성 원칙 3: 검수 루프


**검수 루프의 4단계 순환 과정**


1. **생성 (Generation)** — 초기 프롬프트로 AI 결과 생성


2. **평가 (Evaluation)** — 결과의 명확성, 완성도를 검토·평가


3. **개선 (Refinement)** — 문제점을 식별해 프롬프트를 수정·보강


4. **재생성 (Re-generation)** — 개선된 프롬프트로 다시 결과물 생성


- 이 과정을 여러 차례 반복적으로 진행하여 고품질의 결과물 획득


- 결과물의 품질과 정확성을 검증하고 개선하는 것이 목적


---


## Slide 12 — 슬래시 명령어


- 4번 강의자료 6~9페이지 참고


- 13~16페이지는 참고만 (자주 쓰이는 유형)


---


## Slide 13 — 서브 에이전트


- 서브에이전트가 너무 구체적이면 범용성이 낮아지므로 너무 상세한 내용은 넣지 않음


- 상세한 내용은 **skill** / **사용자 정의 command**에 넣는 것을 추천


- 나만의 서브에이전트를 만드는 것보다, 이미 만들어진 제3자의 검증된 것을 활용하는 것이 좋음


  - [aitmpl.com/agents](https://www.aitmpl.com/agents/)


  - [awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents)


---


## Slide 14 — MCP


- **MCP**: AI 모델이 외부 도구, 서비스와 안전하고 구조적으로 상호작용할 수 있도록 만든 표준 프로토콜


  - 예: 데이터베이스 연결 MCP, Git 리소스 관리 (Git 관련 작업을 자연어로 수행)


- 자주 사용하는 MCP 서버: **context7** — 사용하는 라이브러리의 최신 버전 설명 참조


### 참고 링크


- [context7 (upstash)](https://github.com/upstash/context7)


- [github-mcp-server](https://github.com/github/github-mcp-server)


- [playwright-mcp (microsoft)](https://github.com/microsoft/playwright-mcp)


- [aitmpl.com/agents](https://www.aitmpl.com/agents) — agent, skills, hook, mcp를 모아둔 사이트


---


## Slide 15 — Hook


- **Hook**


- 하네스와의 차이점: 4번 강의자료 36페이지에 적어둠


---


## Slide 16 — Plan Mode 활용


- 작업 계획만 수립, 실행하지는 않음


- 채팅창에서 Plan Mode로 전환하려면 `Shift + Tab`


---


## Slide 17 — Skills


- [skills.sh](https://skills.sh)


- Skills 53~55페이지 — prompt + script 명령까지 재사용


> **Tip. 토큰 절약 Skill**


> [ponytail (dietrichgebert)](https://github.com/dietrichgebert/ponytail)


>


> ```


> /plugin marketplace add DietrichGebert/ponytail


> /plugin install ponytail@ponytail


> ```


>


> 설치하면 토큰 절약 가능!


---


## Slide 18 — 비교


- 56페이지 비교 내용 참고


---


## Slide 19 — 프로젝트 생성 과정


- 프로젝트 만드는 과정 간단하게 소개


