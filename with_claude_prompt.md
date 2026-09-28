# Claude Code와 나눈 대화 기록

바이브 코딩 전파 세미나 발표 자료 준비 세션 (2026-09-28 ~ 09-29).
도구 실행 과정은 빼고, 주고받은 메시지만 순서대로 담았다.

---

## [1] 나

/mattpocock-skills:grill-with-docs

### Claude

I've loaded both skills: grilling (one round of questions at a time) and domain modeling (I'll write `CONTEXT.md` and ADRs as terms and decisions get settled).

You didn't say what plan we're testing, so I looked around first. There's no `CONTEXT.md` or `docs/adr/` yet, and no code. What's here:
- `VIBE_CODING/` holds the Multicampus course materials: lectures 01–08 as PDFs, the supplementary PDFs (JWT, CORS, social auth, architecture, UI/UX & ERD), `chat/`, `script_zip/`, and your notes from 0826 and 0828.
- `presentation/` is empty. It was created at 01:33 today, a minute before the combined course PDF was saved at 01:34.

My guess is that you're about to build a presentation from this course. I'll use that as the working guess until you answer.

---

❓ **Q1** - **What are we working through?** Which of these is it?
- (a) A **presentation** built from this vibe-coding course (going by the new `presentation/` folder)
- (b) The **full-stack service** you'd build in the course (planning, ERD, backend, frontend, deployment)
- (c) Something else

➡️ (a). The empty folder next to a just-saved combined PDF points that way.

---

❓ **Q2** - **Who is it for, and what should they get out of it?** Who's the audience (other students, coworkers, your team, a teaching session), and what should they be able to do or decide afterwards? Please answer even if Q1 turns out not to be (a), since "who is this for" shapes (b) as well.

➡️ If it's a presentation: people who haven't taken the course. They should leave knowing the vibe-coding workflow (prompt → tools → plan → build → deploy) well enough to try it themselves, not just having heard a summary of the course.

---

❓ **Q3** - **Is the source material fixed?** Should I treat these course PDFs and notes as the only source, or can your own opinions and experience override or add to them?

➡️ The course is the backbone, and your own experience and opinions can override it. A talk that only retells the slides isn't worth giving.

Once you answer, I'll read the relevant PDFs and notes myself before the next round, so I won't ask you for anything that's already in them.

---

## [2] 나

VIBE_CODING 폴더 안에 있는 01_* ~ 08_* 까지의 pdf 자료를 보고 pptx를 bento-slides 스킬을 사용해서 만들려고 해. 첫번째로 presentation 폴더 안에 CONTEXT.md 파일을 만드는 것부터 시작해야할 것 같아. 1) presentation 폴더에 발표 자료를 만들거야 2) 대상은 같이 일하는 회사 사람 20명 정도이고, 이들은 cladue를 쓰고 있지만 아직 용어나 스킬, md, 하네스, 등과는 친하지 않은 사람들도 있어. 발표 목적은 내가 교육 들은 내용을 전파 세미나 하는거라서 기본적인 내용들을 탄탄히 소개해주면 좋을 것 같아. 3) VIBE_CODING 폴더 안에 있는 강의자료(pdf파일들 참고해서 만들면 되는데, 01_VIBE_CODING ~ 08_배포 까지 총 8개의 자료를 참고하면 돼

### Claude

강의자료 03~08을 계속 읽는 중이에요. 용어집(CONTEXT.md)을 원자료의 표현에 맞춰 쓰려고 확인하고 있습니다.

강의자료 8개를 모두 읽었어요. 이제 확정된 내용만 담아 `presentation/CONTEXT.md` 초안을 만들게요.

`presentation/CONTEXT.md`를 만들었어요. 지금은 이미 확정된 것(전파 세미나·청중·원자료)과, 원자료에서 뜻이 분명하게 정의된 Claude Code 용어 12개만 들어 있어요. 뜻이 갈리는 용어는 아래 질문에 대한 답을 듣고 채울게요.

강의자료 8개(총 274쪽)를 읽다가 먼저 정해야 할 충돌을 몇 가지 발견했어요.

---

❓ **Q1 - 결과물 형식**: bento-slides 스킬로 만들면 **`.bento.html`** 파일이 나와요. pptx가 아니에요. 스킬 문서를 확인해 보니 PDF로는 내보낼 수 있지만 pptx 내보내기는 없어요. 선택지는 이렇습니다.
- (a) **bento로 만들기**: 결과물은 `.bento.html`이고 브라우저에서 바로 발표해요. 배포용은 PDF로 내보내요.
- (b) **pptx로 만들기**: bento 대신 pptx 스킬을 써요. 받은 사람이 파워포인트로 열고 고칠 수 있어요.
- (c) 둘 다 만들기: 작업량이 두 배예요.

➡️ **(a)**. bento를 직접 지목하셨고, 동료에게 돌릴 파일은 PDF로 충분해요. 회사에서 pptx 파일을 꼭 받아야 한다면 (b)로 가요.

---

❓ **Q2 - 발표 시간**: 몇 분짜리 세미나인가요? 원자료는 274쪽인데, 이 중 얼마를 쓸지가 시간에 따라 완전히 달라져요.

➡️ 질의응답 포함 **60분, 슬라이드 25~30장**으로 가정할게요.

---

❓ **Q3 - 청중이 개발자인가요?** 원자료 05~08은 Team CalTalk 앱을 기획→백엔드→프론트엔드→배포까지 만드는 실습이에요. ERD, Swagger, GitHub Actions YAML이 나와요. 청중이 모두 개발자인지, 기획자·디자이너 등 비개발자가 섞여 있는지에 따라 05~08을 **실습 흐름 그대로** 보여줄지, **"문서 → 이슈 → 커맨드 → 테스트"라는 작업 패턴만** 뽑아서 보여줄지가 갈려요.

➡️ 섞여 있다고 보고 **패턴만** 뽑아요. 코드와 YAML 캡처는 빼고, "AI에게 일을 어떻게 나눠 맡기는가"에 집중해요.

---

❓ **Q4 - '하네스'를 다룰지**: 청중이 낯설어하는 용어로 '하네스'를 꼽으셨는데, **원자료 8개에는 이 단어가 한 번도 안 나와요.** 원자료만 쓴다는 원칙과 부딪혀요.
- (a) 원자료 밖이지만 **'하네스'를 묶음 개념으로 추가**해요. "Claude 모델을 감싸서 도구·권한·CLAUDE.md·스킬·훅·MCP를 붙여 주는 실행 환경 = Claude Code"로 한 장에 정리하고, 나머지 구성 요소는 그 아래에 배치해요.
- (b) 원자료 용어만 써요.

➡️ **(a)**. 지목하신 용어이고, 흩어진 구성 요소를 한 그림으로 묶어 주는 틀로 유용해요. 이 경우 CONTEXT.md의 원자료 정의에 "하네스 개념은 예외"라고 적어 둘게요.

---

❓ **Q5 - '바이브 코딩'이 무슨 뜻인지**: 원자료가 스스로 모순돼요. 01장은 카파시의 원래 정의를 따라요. "코드를 세세히 관리하지 않고 AI 제안을 자유롭게 수용, 직감에 의존"하는 방식이죠. 그런데 05~08장은 도메인 정의서 → PRD → ERD → 실행 계획 → 이슈 → 테스트로 이어지는, 매우 **문서 주도적인** 방식을 가르쳐요. 이건 원자료 01장 뒷부분의 SDD(Spec Driven Development) 쪽에 가까워요. 발표에서 '바이브 코딩'은 어느 쪽인가요?
- (a) 카파시식 원래 의미예요. 그러면 05~08은 "바이브 코딩을 넘어선 방식"이 돼요.
- (b) 넓은 의미예요. "AI와 대화하며 개발하는 방식 전반"이고, 카파시식은 그 한쪽 끝이에요.

➡️ **(b)**. 강의 제목부터 넓은 의미로 쓰고 있어요. 대신 "그냥 던지는 것"과 "문서로 조종하는 것"의 차이를 발표의 핵심 메시지로 삼아요.

---

❓ **Q6 - 오래된 정보 처리**: 04장에는 Claude Code 기능과 수치가 많이 나오는데, 일부는 지금과 다를 수 있어요. 예를 들어 "컨텍스트 200k", "Node.js 22 필수", 커맨드가 스킬로 대체된 일 등이에요.
- (a) 원자료 그대로 전해요.
- (b) 발표 전에 현재 공식 문서와 대조해서 바뀐 부분만 고치고, "교육 이후 변경"이라고 표시해요.

➡️ **(b)**. 청중이 발표를 듣고 바로 따라 해 볼 텐데, 틀린 명령어를 보여주면 신뢰를 잃어요. 대조 작업은 제가 할게요.

---

❓ **Q7 - '메모리'라는 말이 두 가지 뜻**: 원자료는 CLAUDE.md를 "프로젝트 수준의 메모리"라고 부르면서, 동시에 Claude가 대화에서 스스로 배워 저장하는 **자동 메모리**(`~/.claude/projects/.../memory`)도 '메모리'라고 불러요. 청중에게는 이렇게 구분하는 걸 제안해요.
- **CLAUDE.md** = 내가 직접 써 두는 규칙
- **자동 메모리** = Claude가 스스로 적는 기록
- '메모리'라는 말을 단독으로는 쓰지 않기

➡️ 위처럼 나눠요. 동의하시면 CONTEXT.md에 반영할게요.

---

## [3] 나

1. .bento.html이면 괜찮아 2. 발표 시간은 3-40분정도면 돼  3. 청중은 백엔드 개발자들이야. 그래서 어떤 웹을 개발했느냐보다 클로드 코드를 활용한 바이브코딩이라는 것 자체에 좀 더 집중하면 좋겠어. 기본적인 개념과 사용 방법 등 4. 하네스도 다뤄주면 좋을 것 같아 5. 카파시의 방식이 처음 시작이었다고 생각하면 될 것 같고, 넓은 의미로 보면 돼 6. 현재 정보에 최대한 맞추면 좋을 것 같고, 강의 자료와 다른 점은 따로 기입해줘. 7. 제안을 받아들일게. // SKILL.md도 없는거로 아는데 같이 만들어주면 좋겠어

### Claude

답변을 `presentation/CONTEXT.md`에 반영했어요.
- **청중**: 백엔드 개발자로 고쳤어요.
- **원자료**: 하네스와 사실 정정만 예외로 원자료 밖에서 가져온다고 적었어요.
- **새 용어 5개**: 교육 이후 변경, 바이브 코딩, 카파시식 바이브 코딩, 하네스, 자동 메모리를 추가했어요.
- **CLAUDE.md**: 설명에서 '메모리'를 빼고, 다른 이름으로 부르지 않도록 표시했어요.

현재 공식 문서와 대조하는 작업(Q6)은 슬라이드를 만들 때 할게요. 지금 정할 질문들은 그 결과에 영향을 받지 않아요.

---

❓ **Q1 - 'SKILL.md를 같이 만들어 달라'가 무슨 뜻인지**: 먼저 사실 하나만 말씀드리면, bento-slides 스킬의 SKILL.md는 이미 설치돼 있어요(`~/.claude/plugins/cache/bento/bento-slides/1.0.6/skills/bento-slides/SKILL.md`). 제가 이번 세션에서 읽었어요. 그래서 요청하신 게 무엇인지 확인하고 싶어요.
- (a) **이 발표를 만드는 작업용 스킬**: 예를 들어 `presentation/.claude/skills/seminar-deck/SKILL.md`에 CONTEXT.md 참조, 원자료 경로, bento 작성 규칙, "교육 이후 변경 표기법"을 담아요. 다음 세션에서도 같은 방식으로 덱을 고칠 수 있어요.
- (b) **발표에서 보여줄 예시 스킬**: 청중에게 "스킬이란 이런 것"을 보여주는 실물이에요. 예를 들어 백엔드 개발자용 `api-review` 스킬이요.
- (c) 둘 다

➡️ **(c)**. (a)는 이 작업을 반복할 수 있게 해 주고, (b)는 발표 중 스킬 장에서 실물 데모로 써요. 하나만 고르신다면 (a)예요.

---

❓ **Q2 - 이야기 흐름(목차)**: 30~40분이면 슬라이드 18~22장 정도예요. 이렇게 제안해요.
1. **바이브 코딩이란** (01장, 3장 분량): 카파시식에서 시작해 넓은 의미로 넘어가는 흐름, 개발자 역할의 변화
2. **하네스로 보는 Claude Code** (04장 + 원자료 밖, 7~8장 분량, **핵심 파트**): 하네스 그림 하나를 두고 CLAUDE.md, 자동 메모리, 권한·플랜 모드, 서브에이전트, 스킬, MCP, 훅, 플러그인을 차례로 짚어요.
3. **AI에게 잘 시키는 법** (03장, 3~4장 분량): 프롬프트 구성 요소, 최소 충분 컨텍스트, Do/Don't, 검수 루프
4. **실전 작업 흐름** (05~08장, 3~4장 분량): 도메인 정의서 → PRD → 실행 계획 → GitHub 이슈 → 이슈 해결 커맨드/스킬 → 테스트 → PR → CI/CD. Team CalTalk은 예시로 한 줄만 언급해요.
5. **주의점 + 내일 해 볼 것** (01장 한계, 2장 분량)

02장 환경설정은 빼요. 청중이 이미 Claude를 쓰고 있어서요.

➡️ 위 흐름대로 가요. 무게를 2번에 두는 게 "Claude Code를 활용한 바이브 코딩 자체"라는 요청과 맞아요. 빼거나 더할 파트가 있으면 말씀해 주세요.

---

❓ **Q3 - '교육 이후 변경'을 어디에 적을지**:
- (a) 해당 슬라이드에 작은 **"교육 이후 변경"** 배지를 달고, 무엇이 달라졌는지는 발표자 노트에 적어요.
- (b) 덱 맨 끝에 **부록 슬라이드 한 장**으로 모아요.
- (c) 덱과 별도로 `presentation/CHANGES.md` 파일을 만들어요.

➡️ **(a) + (c)**. 청중은 슬라이드에서 바로 알아보고, 전체 목록은 파일 하나로 관리해요. 덱에 부록 장을 두면 발표 시간만 잡아먹어요.

---

❓ **Q4 - 용어 표기**: 슬라이드에서 Claude Code 용어를 어떻게 쓸까요?
- (a) 한글 위주로 쓰고 첫 등장 때만 영문을 병기해요. 예: 스킬(Skill), 훅(Hook), 서브에이전트(Subagent)
- (b) 영문 그대로 써요. 예: Skill, Hook, Subagent

➡️ **(a)**. 원자료와 CONTEXT.md가 한글 표기를 쓰고, 실제 설정 파일과 명령어(`/skills`, `hooks`)는 영문이라 첫 등장 때 이어 주는 게 좋아요.

---

❓ **Q5 - 라이브 데모를 할지**: 30~40분 안에서
- (a) 데모 없이 슬라이드와 캡처만 써요.
- (b) 하네스 파트에서 짧은 라이브 데모 1회(3~5분)를 해요. 예: CLAUDE.md 한 줄을 바꾸고 결과가 달라지는 걸 보여 주거나, 예시 스킬을 호출해요.

➡️ **(b)**. 백엔드 개발자에게는 "말로 들은 개념"보다 터미널에서 한 번 보는 게 훨씬 오래 남아요. 데모가 실패할 때를 대비해 백업 캡처 슬라이드도 한 장 둬요.

---

## [4] 나

1. 작업용 스킬을 만든거였어(a) 2. 일단 이대로 만들어주면 내가 참고해서 스크립트를 수정해볼게. 아, bento에 들어갈 SCRIPT.md 도 만들어야 해 3. (a)로 해주면, 내가 참고해서 변경해볼게 4. 영문 그대로(b) 5. 라이브 데모 좋아(b)

### Claude

CONTEXT.md를 영문 표기로 바꿨어요. Harness, Auto memory, Subagent, Skill, Hook, Plugin, Plan mode, Context가 표제어가 됐고, 한글 표기는 `_Avoid_`로 옮겼어요. '교육 이후 변경'은 배지와 발표자 노트로만 표시하고, 별도 CHANGES.md 파일은 만들지 않을게요.

파일 이름은 `presentation/vibe-coding-seminar.bento.html`과 `presentation/SCRIPT.md`로 정할게요. 다른 이름을 원하시면 말씀해 주세요.

---

❓ **Q1 - SCRIPT.md는 무엇이고 발표자 노트와 어떤 관계인가요?** 제 이해로는 "슬라이드별로 실제로 말할 발표 대본"이에요. bento 덱에도 슬라이드마다 발표자 노트 칸이 있어서, 두 곳에 같은 내용이 생기게 돼요. 한쪽을 원본으로 정해야 나중에 어긋나지 않아요.
- (a) **SCRIPT.md가 원본**이에요. 대본은 여기서만 고치고, 작업용 Skill이 그 내용을 덱의 발표자 노트로 복사해요. '교육 이후 변경' 설명도 SCRIPT.md의 해당 슬라이드 아래에 적어요.
- (b) **덱의 발표자 노트가 원본**이에요. SCRIPT.md는 거기서 뽑아 낸 읽기용 사본이에요.

➡️ **(a)**. 직접 대본을 수정하신다고 하셨는데, 마크다운 파일이 bento 안의 JSON보다 훨씬 고치기 쉬워요. 대본은 구어체 존댓말로, 슬라이드마다 `## 07. Harness란?`처럼 제목을 달아 둘게요.

---

❓ **Q2 - 작업용 Skill을 어디에 둘지**: Claude Code는 **실행한 폴더**의 `.claude/skills/`에서 프로젝트 Skill을 찾아요.
- (a) `vibe_coding/.claude/skills/seminar-deck/SKILL.md`: 지금처럼 `vibe_coding`에서 `claude`를 실행하면 잡혀요.
- (b) `presentation/.claude/skills/...`: `presentation` 폴더 안에서 실행할 때만 확실히 잡혀요.
- (c) `~/.claude/skills/`: 모든 프로젝트에서 보여요. 이 발표 전용이라 맞지 않아요.

➡️ **(a)**. 원자료(`VIBE_CODING/`)와 결과물(`presentation/`)을 둘 다 참조해야 하니, 두 폴더를 모두 품는 `vibe_coding`이 루트로 맞아요.

---

❓ **Q3 - 작업용 Skill이 맡을 일**: 이 Skill을 부르면 다음을 하도록 만들 생각이에요.
1. `presentation/CONTEXT.md`를 읽고 그 용어만 써요.
2. 원자료 경로와, 장별로 어느 파트에 쓰이는지 연결표를 참조해요.
3. 덱을 고칠 때는 bento-slides Skill의 규칙을 따라요.
4. SCRIPT.md 내용을 발표자 노트로 동기화해요.
5. 현재 공식 정보와 다른 내용이 나오면 '교육 이후 변경' 배지를 달고 SCRIPT.md에 기록해요.

뺄 것이나 더할 것이 있나요?

➡️ 위 5가지 그대로 가요. 발표 목차(Q2에서 정한 5개 파트)도 Skill에 적어 두면, 다음 세션에서도 같은 구조를 유지할 수 있어요.

---

❓ **Q4 - 라이브 데모에서 무엇을 보여줄지** (3~5분, 실패 대비 백업 캡처 1장 포함):
- (a) **CLAUDE.md 전후 비교**: 작은 Express API에 기능 하나를 추가해 달라고 요청해요. CLAUDE.md에 "오버엔지니어링 금지, 요청한 기능만 구현" 한 줄이 없을 때와 있을 때 결과가 어떻게 다른지 보여줘요.
- (b) **Skill 호출**: 예를 들어 API 리뷰 Skill을 불러서, 평소에는 설명만 로드돼 있다가 부를 때 전체가 로드되는 걸 보여줘요.
- (c) **Hook**: Stop 이벤트가 오면 `say "작업이 완료되었습니다"`가 실행되게 해요. 청중이 바로 체감하는 데모예요.

➡️ **(a)**. 백엔드 개발자가 다음 날 바로 따라 할 수 있고, 원자료가 가장 강조하는 교훈("오버엔지니어링 금지"를 CLAUDE.md에 반드시 넣으라는 것)을 눈으로 보여줘요. 데모용 예제 프로젝트는 원자료에 나온 `stepanowon/test-svc` 저장소를 쓰는 걸 제안해요.

---

## [5] 나

1.  nyblnet/bento github 에서 받은 bento-skill 을 사용해서 발표자료를 만들건데, 이때 SCRIPT.md에 각 장에 들어갈 내용을 마크다운으로 적어서 주려고 해. CONTEXT.md 도 물론 참고하겠지만, 발표자료 html을 만들 기본 뼈대는 SCRIPT.md에 있을거야. 1p- ~~~ 2p- ~~~ 이런 식으로 2. 잡힌다는게 무슨 말인지 정확히 모르겠는데, (a)가 좋을 것같으면 a로 해줘 3. 일단 그대로 가보자 4. 일단 a 랑 c 둘 다 만들어줄 수 있어? 내가 직접 눈으로봐보고 더 좋아보이는걸 골라 남기고 나머지는 뺼게

### Claude

SCRIPT.md는 제가 생각한 '발표 대본'이 아니라 **덱의 뼈대, 즉 페이지별로 슬라이드에 들어갈 내용**이었네요. 그래서 CONTEXT.md에 SCRIPT.md 항목을 추가하고, '대본'이나 '발표 스크립트'로 부르지 않도록 표시해 뒀어요.

Q2에서 '잡힌다'는 건 **Claude Code가 그 Skill을 인식해서 목록에 띄우고 쓸 수 있게 되는 것**을 말해요. `vibe_coding` 폴더에서 `claude`를 실행하면 `vibe_coding/.claude/skills/` 안의 Skill이 자동으로 인식돼요. 그래서 (a)로 할게요.

데모는 (a) CLAUDE.md 전후 비교와 (c) Hook을 둘 다 넣을게요. 보시고 하나를 고르시면 돼요.

아직 남은 질문이 몇 개 있어요.

---

❓ **Q1 - 발표자 노트는 어디서 오나요?** SCRIPT.md가 슬라이드에 보이는 내용이라면, 발표할 때 말할 멘트와 '교육 이후 변경' 설명(이전에 (a)로 정한 것)을 둘 곳이 따로 필요해요.
- (a) SCRIPT.md의 각 페이지 아래에 `> 노트:` 블록을 둬요. 여기 적힌 내용은 슬라이드에는 안 보이고 발표자 노트로만 들어가요.
- (b) 발표자 노트는 제가 덱에 직접 써요. SCRIPT.md에는 슬라이드 내용만 둬요.

➡️ **(a)**. 모든 내용이 파일 하나에 있어야 수정하실 때 편하고, 덱을 다시 만들어도 노트가 사라지지 않아요. 예를 들면 이런 모양이에요.
```
## 7p- Harness란?
- Claude 모델 + 도구 실행 + 권한 + CLAUDE.md + Skill + Hook + MCP
> 노트: "모델 자체보다 모델을 감싼 환경이 결과를 좌우합니다…"
> 교육 이후 변경: 강의에서는 Node.js 22가 필수라고 했지만, 지금은 네이티브 설치로 Node 없이도 됩니다(확인 후 기재)
```

---

❓ **Q2 - SCRIPT.md 초안의 분량**: 제가 초안을 쓰고 직접 고치시는 흐름이 맞죠? 초안을 어느 정도로 채울까요?
- (a) **내용까지 다 채워요**: 페이지별로 제목, 핵심 불릿 3~5개, 노트까지 써요. 고치시기만 하면 돼요.
- (b) **목차만 잡아요**: 페이지 제목과 한 줄 의도만 적고, 내용은 직접 채우세요.

➡️ **(a)**. 원자료 274쪽을 이미 다 읽어 뒀으니, 비우는 것보다 채워 놓고 지우는 편이 빨라요.

---

❓ **Q3 - 데모 준비물**: 데모 2개를 슬라이드로만 소개할까요, 바로 실행할 수 있는 키트도 만들까요?
- (a) 슬라이드만 만들어요. 데모 소개 1장과 백업 캡처 자리 1장씩이에요. 캡처는 리허설 때 직접 찍어서 넣으시면 돼요.
- (b) (a)에 더해서 `presentation/demo/` 폴더를 만들어요. 안에는 전후 비교용 `CLAUDE.md` 두 벌, Hook용 `.claude/settings.json`, 순서대로 따라 할 수 있는 `DEMO.md`를 넣어요.

➡️ **(b)**. 발표 당일 긴장한 상태에서 설정을 타이핑하는 게 데모가 실패하는 가장 흔한 원인이에요. 파일을 복사만 하면 되게 준비해 둘게요.

---

위 세 가지에 답해 주시면 정해야 할 건 다 정해져요. 그다음에는 지금까지 합의한 내용을 한 번에 정리해서 보여드리고, 확인을 받은 뒤에 작업을 시작할게요. 작업은 SCRIPT.md 초안, 작업용 Skill, 데모 키트, 현재 공식 정보 대조, 덱 생성 순서로 진행해요.

---

## [6] 나

1. a 2. a 3. b

### Claude

이제 더 정할 게 없어요. 지금까지 합의한 내용을 정리했으니, 맞는지 확인해 주세요. `presentation/CONTEXT.md`의 SCRIPT.md 정의에는 '발표자 노트도 포함한다'는 내용을 추가했어요.

## 합의한 내용

**발표**
- **형식**: bento-slides Skill로 만든 `presentation/vibe-coding-seminar.bento.html`
- **분량**: 30~40분, 슬라이드 18~22장
- **청중**: 사내 백엔드 개발자 약 20명
- **초점**: 어떤 웹을 만들었는지가 아니라, Claude Code를 활용한 Vibe Coding 자체예요. 기본 개념과 사용법을 다뤄요.
- **용어**: Claude Code 용어는 영문 그대로 쓰고, 나머지 용어는 CONTEXT.md를 따라요.
- **Vibe Coding의 뜻**: 넓은 의미로 써요. 카파시식은 출발점으로 소개해요.

**목차**
1. Vibe Coding이란 (01장)
2. Harness로 보는 Claude Code (04장 + 원자료 밖) ← 핵심 파트예요. 라이브 데모 2개를 넣어요.
3. AI에게 잘 시키는 법 (03장)
4. 실전 작업 흐름 (05~08장): 패턴만 다루고, Team CalTalk은 예시로 한 줄만 언급해요.
5. 주의점 + 내일 해 볼 것

02장 환경설정은 빼요.

**만들 파일**

| 파일 | 내용 |
|---|---|
| `presentation/SCRIPT.md` | 덱의 뼈대예요. `## Np- 제목` 아래에 슬라이드 불릿을 쓰고, `> 노트:`와 `> 교육 이후 변경:` 블록을 둬요. 내용까지 다 채운 초안으로 드려요. |
| `vibe_coding/.claude/skills/seminar-deck/SKILL.md` | 작업용 Skill이에요. CONTEXT.md 용어 지키기, 원자료 연결표, 목차, bento-slides 규칙 따르기, SCRIPT.md를 기준으로 덱 만들기(노트 포함), '교육 이후 변경' 배지 달기를 담아요. |
| `presentation/demo/` | 데모 키트예요. (a) CLAUDE.md 전후 비교용 두 벌(`stepanowon/test-svc` 사용), (c) Stop Hook용 `settings.json`, 순서대로 따라 할 수 있는 `DEMO.md`를 넣어요. |
| `presentation/vibe-coding-seminar.bento.html` | SCRIPT.md로 만든 덱이에요. 데모마다 소개 1장과 백업 캡처 자리 1장씩 넣어요. |

**'교육 이후 변경' 처리**
- 원자료 내용을 현재 Claude Code 공식 문서와 대조해요.
- 달라진 부분은 슬라이드에 작은 배지를 달고, 설명은 SCRIPT.md의 노트 블록에 적어요.

**작업 순서**
1. 공식 문서와 대조하기
2. SCRIPT.md 초안 쓰기 → 여기서 한 번 멈추고 보여드려요. 직접 수정하시는 단계예요.
3. 작업용 Skill과 데모 키트 만들기
4. 덱 만들기 → 모든 슬라이드를 직접 열어서 확인해요.

이대로 시작해도 될까요? 고칠 부분이 있으면 말씀해 주세요.

---

## [7] 나

응 이대로 시작해줘

### Claude

공식 문서 대조가 거의 끝났어요. 마지막으로 Auto memory 부분을 확인하고 있습니다.

대조를 마쳤어요. 확인된 '교육 이후 변경' 항목만 골라 SCRIPT.md 초안을 쓸게요.

Demo kit is done. Now I'm writing the working Skill (`seminar-deck`).

`presentation/SCRIPT.md` 초안을 다 썼어요. 약속대로 덱은 아직 만들지 않았으니 먼저 SCRIPT.md를 검토해 주세요. 작업용 Skill과 데모 키트는 SCRIPT.md 수정과 상관없는 파일이라 먼저 만들어 뒀어요.

**만든 파일**
- `presentation/SCRIPT.md`: 23페이지이고, 그중 2장(9p, 16p)은 데모가 실패할 때 쓰는 백업 장이에요. 각 장은 `## Np- 제목` 아래에 불릿, `> 노트:`, `> 교육 이후 변경:`을 두는 형식이에요.
- `.claude/skills/seminar-deck/SKILL.md`: 작업용 Skill이에요. `vibe_coding` 폴더에서 `claude`를 실행하면 `/seminar-deck`으로 불러 쓸 수 있어요. 덱 내용을 고칠 때는 SCRIPT.md를 먼저 고치고 덱에 반영하도록 적어 뒀어요.
- `presentation/demo/`: `DEMO.md`(진행표), `a-claude-md/CLAUDE.md`, `c-hook/settings.json`이에요. 데모용 저장소 `stepanowon/test-svc`가 실제로 있는 것도 확인했어요.

**공식 문서와 대조한 결과 '교육 이후 변경'으로 표시한 7곳**
- **7p CLAUDE.md**: 우선순위로 덮어쓰는 게 아니라 모든 파일이 이어 붙여져 로드돼요. CLAUDE.md가 없으면 AGENTS.md도 읽어요.
- **10p 권한 모드**: `auto`와 `dontAsk`가 추가됐어요. 최신 버전에서는 `auto`가 기본으로 시작하는 모드예요.
- **11p Subagent**: `model` 값이 늘었어요(haiku, fable, inherit 등). frontmatter 필드도 추가됐어요.
- **12p Skill**: 강의에서는 사용자 정의 명령어가 "deprecated"라고 했지만, 공식 문서는 "여전히 동작하는 이전 형식"이라고 설명해요.
- **13p MCP**: SSE 전송 방식은 deprecated예요.
- **14p Hook**: 이벤트가 30개 이상으로 늘었어요. 강의의 Prettier 예시에 쓰인 `$CLAUDE_FILE_PATHS`는 존재하지 않아요. 파일 경로 같은 값은 stdin의 JSON으로 전달돼요.
- **설치 관련**: 지금은 Node.js 없이 네이티브로 설치할 수 있어요. 다만 02장 환경설정을 발표에서 빼서 슬라이드에는 반영하지 않았어요.

**확인이 필요한 부분**
- **확인 못 한 명령어**: `/recap`, `/simplify`, `/statusline`은 문서 조회 결과가 불확실했어요. 그래서 '변경'으로 적지 않고 슬라이드에서도 언급하지 않았어요. 컨텍스트 크기(200k)도 같은 이유로 숫자를 빼고 "`/context`로 확인하라"로 바꿨어요.
- **데모 A 오염 위험**: 지금 ponytail Plugin이 켜져 있어요. 이 Plugin은 코드를 최소화하도록 강제해서, CLAUDE.md가 없는 쪽도 결과가 간결하게 나올 수 있어요. 그러면 전후 비교가 무의미해져요. DEMO.md에 데모 동안 이 Plugin을 꺼 두라고 적어 뒀어요.

SCRIPT.md를 다 고치셨다고 알려 주시면, 그 내용으로 `vibe-coding-seminar.bento.html` 덱을 만들고 슬라이드를 전부 직접 열어서 확인할게요.

---

## [8] 나

내가 조금 잘못 이야기한 부분이 있어. SCRIPT.md에는 실제 발표에서 전달할 내용과 설명 중심, 발표자가 말할 내용 위주로 담아주고, PRESENTATION-SPEC.md 라는 파일을 새로 만들어서 여기에 - 슬라이드별 제목 -핵심 메세지 -슬라이드에 들어갈 핵심 내용 -필요한 시각자료 -발표자 노트 -전체 슬라이그 흐름. 이렇게 들어갔으면 좋겠어. 기존 내용은 누락하지 말고 적절한 파일로 이동해줘

### Claude

SCRIPT.md는 발표 대본으로, 슬라이드 설계는 PRESENTATION-SPEC.md로 나눌게요. 먼저 용어집의 정의부터 바꿀게요.

Spec is done. Now I'm rewriting SCRIPT.md as the talk script: what I actually say on each slide, with explanations.

대본까지 옮겼어요. 이제 작업용 Skill이 덱을 SCRIPT.md가 아니라 PRESENTATION-SPEC.md 기준으로 만들도록 고칠게요.

SCRIPT.md는 발표 대본으로, 슬라이드 설계는 새 파일 `PRESENTATION-SPEC.md`로 나눴어요. 기존 내용은 빠짐없이 둘 중 맞는 파일로 옮겼어요.

**`presentation/PRESENTATION-SPEC.md`** (새 파일, 덱의 원본)
- **전체 흐름**: 맨 위에 파트별 슬라이드 범위, 권장 시간, 전달할 내용을 표로 정리했어요. 파트 사이를 잇는 연결 고리도 적었어요. 예를 들어 5p "주니어 동료" 비유에서 6p Harness로 넘어가요.
- **23장 각각에 담은 것**: 제목, 핵심 메시지, 핵심 내용, 시각자료, 발표자 노트예요.
- **기존 내용**: 슬라이드 불릿은 "핵심 내용"으로 그대로 옮겼어요. '교육 이후 변경' 6건(7p, 10p~14p)은 해당 슬라이드의 별도 항목으로 옮겼어요.
- **시각자료**: 새로 채웠어요. 6p Harness 다이어그램을 기준 그림으로 두고, 7p와 10p~14p에서 설명하는 요소만 강조하며 이어 가도록 적었어요.

**`presentation/SCRIPT.md`** (발표 대본으로 새로 썼어요)
- 슬라이드마다 실제로 말할 문장을 구어체로 썼어요. 기존 노트는 대본 안에 풀어서 넣었어요.
- 동작 지시는 괄호로 표시했어요. 예: (다이어그램 가리키며), (DEMO.md 데모 A 진행)
- '교육 이후 변경'은 말로 짚는 한두 문장으로 넣었어요.
- 페이지 번호는 SPEC과 똑같이 23장으로 맞췄어요.

**함께 고친 파일**
- `CONTEXT.md`: SCRIPT.md는 발표 대본, PRESENTATION-SPEC.md는 덱 설계서로 정의를 바꿨어요.
- `.claude/skills/seminar-deck/SKILL.md`:
  - 덱은 SPEC을 기준으로 만들어요.
  - 슬라이드 내용을 바꿀 때는 SPEC을 먼저 고치고, 덱에 반영한 뒤 SCRIPT와 맞는지 확인해요.
  - 슬라이드 순서가 바뀌면 네 파일(SPEC, SCRIPT, 덱, DEMO.md)의 페이지 번호를 같이 맞춰요.

두 파일을 검토하고 고치신 뒤 알려 주시면, PRESENTATION-SPEC.md로 `vibe-coding-seminar.bento.html` 덱을 만들고 슬라이드를 전부 직접 열어서 확인할게요.

---

## [9] 나

/bento-slides:bento-slides

### Claude

덱을 만들기 시작할게요. 먼저 Bento 앱 파일을 내려받고 작성 규칙 문서를 읽어요.

스키마 문서를 다 읽었어요. 덱을 JSON으로 생성하는 스크립트를 쓰기 전에, 렌더링 결과를 직접 확인할 수단부터 확인할게요.

Chrome이 있어서 CDP로 렌더링하고 캡처하는 방식으로 확인할 수 있어요. 이제 SPEC을 바탕으로 덱을 생성하는 스크립트를 쓸게요.

덱 JSON을 파일에 써 넣었어요(23장). 이제 헤드리스 Chrome으로 열어서 `validate()`를 돌리고 슬라이드를 캡처할게요.

`validate()` 결과 경고는 2건뿐이고, 둘 다 코드 상자 높이가 9px 모자란 문제예요. 이걸 고친 다음 화면을 캡처해 볼게요.

에디터에서 정상적으로 열려요. 이제 슬라이드쇼 모드로 전환해서 한 장씩 넘기며 전부 캡처할게요.

Still fixing the layout. One replacement pattern didn't match, so I'm correcting it and applying everything again.

The backup slides didn't load in-memory, so I'm rendering them from a temporary copy of the file instead.

PRESENTATION-SPEC.md를 기준으로 덱 `presentation/vibe-coding-seminar.bento.html`을 만들었고, 기본 브라우저로 열어 뒀어요. 23장 전부를 헤드리스 Chrome으로 캡처해 한 장씩 봤어요. 겹침이나 넘침은 고쳤고, 마지막으로 돌린 `validate()` 결과 오류와 경고는 0건이에요.

**덱 구성**
- **Harness 다이어그램**: 6p에서 그린 그림을 7p, 10p~14p에서 작게 다시 쓰고, 설명하는 요소만 주황색으로 강조해요. 17p에서는 전체가 켜진 상태를 Plugin 점선 상자가 감싸요.
- **시각자료**: SPEC에 적힌 대로 불릿 대신 표(3p·7p·10p·17p), 흐름도(10p Plan mode, 14p Hook 타임라인, 20p 파이프라인), 순환 그림(19p 검수 루프)을 넣었어요.
- **움직임**:
  - 표지에는 궤도를 도는 점이 있어요.
  - 다이어그램 링, 파이프라인, 검수 루프, Q&A에는 점선이 흐르는 효과를 넣었어요.
  - 20p의 "35"는 숫자가 올라가며 나타나요.
- **'교육 이후 변경' 배지**: 7p와 10p~14p, 모두 6장이에요. 설명은 각 슬라이드의 발표자 노트 끝에 들어 있어요.
- **발표자 노트**: 모든 장에 SPEC의 발표자 노트를 넣었어요.
- **데모 백업 (9p, 16p)**: 숨김 슬라이드로 만들어 슬라이드쇼에서는 건너뛰어요. 데모 장 오른쪽 아래 "백업 캡처 ▸"를 누를 때만 열려요.

**직접 하셔야 할 것**
- **발표자 이름**: 표지에 "발표자 이름"으로 들어가 있어요. 문서 속성의 author를 바꾸면 반영돼요.
- **백업 캡처**: 9p와 16p는 아직 회색 자리 표시만 있어요. 리허설 때 찍은 캡처를 주시면 넣어 드릴게요.
- **쪽 번호**: 숨긴 2장은 쪽 번호에서 빠져서 화면에는 21쪽으로 나와요. 그래서 8p 이후로는 화면의 쪽 번호가 SPEC·SCRIPT의 번호보다 작아요. 예를 들어 SPEC의 10p가 화면에는 "9 / 21"로 보여요. 이 내용을 작업용 Skill에 적어 뒀어요.
- **저장 방식**: 덱 파일은 브라우저에서 고치고 Save로 저장해요. SPEC을 바꾼 뒤 덱에 반영할 때는 `/seminar-deck`을 불러 쓰시면 돼요.

---

## [10] 나

라이브 데모는 슬라이드에서 어떻게 볼 수 있어?

### Claude

슬라이드 안에서 데모 자체가 돌아가지는 않아요. 8p와 15p는 데모를 소개하는 장이고, 실제 데모는 **터미널에서 진행**해요.

**발표 흐름**
1. 슬라이드쇼에서 8p(데모 A)를 띄우고, 무엇을 볼지 설명해요. 요청 문장과 "볼 것"이 슬라이드에 적혀 있어요.
2. **Cmd+Tab**으로 미리 띄워 둔 터미널로 넘어가요. 준비는 `presentation/demo/DEMO.md` 순서대로 하면 돼요. 두 창을 나란히 두고 `claude`를 실행한 다음 같은 요청을 넣고 `/diff`로 비교해요.
3. 다시 Cmd+Tab으로 브라우저에 돌아와 다음 장으로 넘어가요.
4. 데모가 실패하면 8p 오른쪽 아래 **"백업 캡처 ▸"**를 눌러 9p로 가요. 15p(데모 C)와 16p도 같은 방식이에요.

**준비 팁**
- 터미널 글자를 크게 키워 두세요(Cmd +). 20명이 한 화면을 보니 평소 크기로는 안 보여요.
- 발표용 모니터를 확장 모드로 쓰면 창을 옮기는 게 보이지 않아서 깔끔해요. 미러링 모드라면 전환하는 모습이 그대로 보여요.

**다른 방법: 녹화 영상을 슬라이드에 넣기**
Bento는 슬라이드에 동영상을 넣을 수 있어요. 리허설 때 데모를 화면 녹화(Cmd+Shift+5)해 두면, 9p·16p의 캡처 자리 대신 그 영상을 넣을 수 있어요. 그러면 라이브가 실패해도 영상으로 바로 이어 갈 수 있어요.

영상 파일은 짧게 편집해 주세요. 파일 안에 넣는 방식이라 길면 덱 파일이 무거워져요. 녹화하시면 파일 경로를 알려 주세요. 백업 장에 넣어 드릴게요.

---

## [11] 나

라이브 데모니까 지금 demo 방식 좋은 것 같아. 근데 녹화 영상도 있으면 좋을 것 같아서 하나 넣어줄 수 있나? demo 방식을 지우지는 말아줘. 같이 보여주면 좋은데 혹시라도 안될 때를 대비해서 녹화 영상도 있으면 좋을 것 같아

### Claude

녹화 영상은 **데모 백업 장(9p, 16p)**에 넣을게요. 라이브 데모 흐름은 그대로 두고, 영상은 라이브가 안 될 때 "백업 캡처 ▸"로 들어가서 트는 용도예요.

영상 파일 자체는 제가 만들 수 없어요. 녹화는 리허설 때 직접 하셔야 해요. 그래서 지금은 영상이 들어갈 자리를 만들어 두고, 정해진 경로에 파일을 넣으면 바로 재생되게 할게요. 먼저 덱 파일이 브라우저에서 저장된 적이 있는지 확인할게요.

파일은 제가 만든 뒤로 바뀐 적이 없어요. 9p와 16p만 JSON 안에서 직접 고칠게요. 다른 슬라이드는 건드리지 않아요.

영상 자리를 넣었어요. 이제 브라우저에서 영상 경로가 제대로 해석되는지 확인할게요.

화면은 잘 나와요. 제목이 아직 "캡처"로만 되어 있어서 "녹화 · 캡처"로 바꾸고, SPEC·SCRIPT·DEMO.md·Skill도 같이 맞출게요.

Deck titles updated. Now syncing PRESENTATION-SPEC.md, SCRIPT.md, and DEMO.md.

`avconvert`와 `Preset1920x1080` 프리셋이 실제로 있는 것을 확인했어요. 마지막으로 작업용 Skill의 백업 장 설명을 영상 기준으로 고칠게요.

녹화 영상 자리를 백업 장(9p, 16p)에 넣었어요. 라이브 데모 장(8p, 15p)은 그대로 두었어요. 다만 아직 영상 파일이 없어서, 지금은 빈 플레이어만 보여요.

**데모 흐름**
1. 8p나 15p에서 터미널로 넘어가 라이브 데모를 해요.
2. 라이브가 안 되면 브라우저로 돌아와 "백업 캡처 ▸"를 눌러요.
3. 9p나 16p에서 재생 버튼을 눌러 녹화 영상을 틀어요.

**백업 장 구성**
- 왼쪽에 영상 플레이어를 크게, 오른쪽에 캡처 자리 두 개를 뒀어요.
- 제목은 "[백업] 데모 A 녹화 · 캡처", "[백업] 데모 C 녹화 · 캡처"로 바꿨어요.
- 데모 A 영상은 음소거로, 데모 C 영상은 음성 알림을 들어야 해서 소리가 켜진 채로 재생돼요.
- 헤드리스 Chrome으로 확인해 보니 플레이어는 `presentation/demo/demo-a.mp4`, `demo-c.mp4` 경로를 제대로 찾아요.

**직접 하실 것 (리허설 때)**
- **녹화**: 두 데모를 녹화해서 `presentation/demo/demo-a.mp4`와 `demo-c.mp4`로 저장해 주세요. 파일 이름과 위치가 정확해야 덱이 찾아요.
- **mp4 변환**: macOS 화면 녹화는 `.mov` 파일로 저장돼요. mp4로 바꾸는 명령어를 DEMO.md에 적어 뒀어요. macOS 기본 도구인 `avconvert`를 써요.
- **데모 C 소리**: macOS 기본 녹화는 시스템 소리를 담지 못해요. 내장 마이크를 켜고, 스피커에서 나오는 음성을 조용한 곳에서 녹화해야 해요.
- **덱을 옮길 때**: 영상은 덱 파일 안이 아니라 옆의 `demo/` 폴더에서 읽어요. 다른 PC로 옮길 때는 `presentation` 폴더째 옮겨 주세요.

PRESENTATION-SPEC.md, SCRIPT.md, DEMO.md, 작업용 Skill도 같은 내용으로 맞췄어요. 녹화 파일 경로를 알려 주시면 변환해서 넣고, 재생되는지 확인해 드릴게요.

---

## [12] 나

bento 슬라이드 내용도 변경됐나?

### Claude

네, `vibe-coding-seminar.bento.html` 파일에 반영됐어요. 파일을 다시 열어 확인했더니, 백업 장 두 곳의 제목이 "[백업] 데모 A 녹화 · 캡처", "[백업] 데모 C 녹화 · 캡처"로 바뀌어 있고 영상 경로(`demo/demo-a.mp4`, `demo/demo-c.mp4`)도 들어가 있어요. 나머지 21장은 그대로예요.

**바뀐 장면을 보려면**
- **새로고침(Cmd+R)**: 아까 제가 브라우저로 열어 드린 탭은 수정 전 버전이에요. 새로고침하면 새 내용이 보여요.
- **9p·16p 여는 법**: 숨김 슬라이드라 슬라이드쇼에서는 건너뛰어요. 8p나 15p의 "백업 캡처 ▸"를 누르거나, 에디터 왼쪽 썸네일 목록에서 여세요.

**주의할 점**
새로고침하기 전의 옛 탭에서 Save를 누르면, 수정 전 내용이 파일을 덮어써서 이번 변경이 사라져요. 옛 탭은 저장하지 말고 닫거나 새로고침해 주세요.
