# Vibe Coding 전파 세미나 — 용어집

슬라이드, speaker notes, SCRIPT.md는 여기 있는 표기를 따릅니다. Claude Code 용어는 영문 그대로 씁니다.

## 발표

**전파 세미나**:
외부 교육(멀티캠퍼스 「바이브코딩으로 완성하는 풀스택 서비스」) 내용을 Claude를 이미 쓰는 사내 백엔드 개발자 약 20명에게 다시 전달하는 30~40분짜리 발표입니다.

**원자료**:
`VIBE_CODING/VIBE_CODING/`의 01~08 PDF입니다. 이 밖의 자료(강의내용.txt, chat/, script_zip/ 등)는 SCRIPT.md에서만 `파일:줄` 출처를 달아 씁니다.

**PRESENTATION-SPEC.md / SCRIPT.md**:
SPEC은 덱의 설계서이고, SCRIPT.md는 슬라이드별로 말할 포인트(3~5개)입니다. SCRIPT.md는 덱의 speaker notes와 내용이 같습니다.

## 개념

**Vibe Coding**:
자연어 프롬프트로 LLM이 코드를 만들게 하고, 개발자는 평가하고 지시하기를 반복하는 대화형 개발 방식입니다. 안드레 카파시가 처음 제시했습니다.
_Avoid_: 바이브 코딩 (슬라이드 제목에서는 영문으로 씁니다)

**Code Writer → Problem Solver → AI Collaborator**:
과거, 현재, 미래 개발자의 역할 변화입니다(01 개요 15p).

**AI Native**:
코드를 직접 작성하던 방식에서 AI와 대화하며 개발하는 방식으로 넘어간 사고방식입니다. 코드를 쓰는 일보다 문제를 정의하고 방향을 제시하는 일에 집중합니다(01 개요 17p).

**3대 부채**:
기술부채(Technical debt), 인지부채(Cognitive debt), 의도부채(Intent debt)입니다. 원자료에 없는 내용이라 슬라이드에는 키워드만 넣었고, 설명은 발표자가 보충합니다.

**SDD (Spec Driven Development)**:
코드보다 명세를 먼저 쓰고, 그 명세를 단일 진실 공급원으로 삼는 방법론입니다. 진행 순서는 Steering → Spec → Implement입니다.

**하네스 엔지니어링**:
AI가 내가 원하는 대로 동작하도록 제어하는 일입니다. Hook은 반드시 지켜야 할 규칙을 강제하는 강력한 하네스입니다.

**최소 충분 컨텍스트 / DO·DON'T 병행 / 검수 루프**:
프롬프트 핵심 원칙 10개 가운데 Slide 9~11에서 자세히 다루는 세 가지입니다.

## Claude Code 용어 (영문 그대로)

**CLAUDE.md**: Claude Code가 매번 읽는 프로젝트 지침 파일입니다.
**Slash command**: `/clear`, `/compact`처럼 `/`로 시작하는 명령어입니다.
**Subagent**: 독립된 컨텍스트에서 일하는 전문 에이전트입니다. _Avoid_: 서브 에이전트(띄어쓰기)
**MCP**: 외부 도구와 서비스를 연결하는 표준 프로토콜입니다.
**Hook**: 생명주기 이벤트가 생길 때 자동으로 실행되는 동작입니다.
**Plan Mode**: 계획만 세우고 실행은 하지 않는 모드입니다(Shift + Tab).
**Skill**: SKILL.md와 스크립트로 이루어진, 재사용할 수 있는 기능입니다.
