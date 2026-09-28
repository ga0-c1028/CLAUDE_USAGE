# 라이브 데모 진행표

발표 중 데모는 두 개(A, C)다. 리허설 후 하나만 남겨도 된다. 각 데모 3~5분.

## 발표 전날 준비

```bash
cd ~/demo   # 아무 작업 폴더
git clone https://github.com/stepanowon/test-svc test-svc-before
git clone https://github.com/stepanowon/test-svc test-svc-after
(cd test-svc-before && npm install)
(cd test-svc-after && npm install)
cp <이 폴더>/a-claude-md/CLAUDE.md test-svc-after/CLAUDE.md
```

**오염 체크 (중요)**: 두 폴더의 결과 차이는 CLAUDE.md 한 파일에서만 나와야 한다.
- `~/.claude/CLAUDE.md`에 "오버엔지니어링 금지" 같은 규칙이 있으면 데모 동안 잠시 빼 둔다.
- 코드를 최소화하도록 강제하는 Plugin(예: ponytail)이 켜져 있으면 `/plugin`에서 데모 동안 비활성화한다.
- 각 폴더에서 `claude` 실행 후 `/memory`로 로드된 파일을 확인한다. before에는 CLAUDE.md가 없어야 한다.

리허설 때 두 결과의 `/diff` 화면을 캡처해 9p 백업 슬라이드에 넣는다.

## 백업 녹화 영상 만들기 (리허설 때)

라이브 데모가 안 될 때 9p·16p 백업 장에서 트는 영상이다. 덱은 아래 경로의 파일을 그대로 재생하므로 **파일 이름과 위치를 바꾸지 않는다.**

| 데모 | 저장 경로 | 소리 |
|---|---|---|
| A: CLAUDE.md 전후 비교 | `presentation/demo/demo-a.mp4` | 필요 없음 (음소거 재생) |
| C: Stop Hook 음성 알림 | `presentation/demo/demo-c.mp4` | **필요** — "작업이 완료되었습니다" 음성 포함 |

1. 아래 데모 A·C를 리허설하면서 Cmd+Shift+5 → "선택 부분 기록"으로 터미널 영역만 녹화한다.
   - macOS 기본 녹화는 **시스템 소리를 담지 못한다.** 데모 C는 옵션 → 마이크를 "내장 마이크"로 켜고, 스피커 소리를 조용한 곳에서 마이크로 담는다.
2. 저장된 `.mov`를 QuickTime에서 열어 앞뒤를 자른다(Cmd+T → 저장). 각 1~2분이면 충분하다.
3. mp4로 변환해 위 경로에 저장한다 (macOS 내장 명령):
   ```bash
   avconvert --preset Preset1920x1080 --source ~/Desktop/녹화파일.mov --output presentation/demo/demo-a.mp4
   ```
4. 덱을 열어 9p·16p에서 재생되는지 확인한다.

주의: 영상은 덱 파일 안에 들어가지 않고 **덱 옆의 `demo/` 폴더에서 읽는다.** 덱을 다른 PC로 옮기거나 공유할 때는 `presentation` 폴더째 옮긴다.

## 데모 A: CLAUDE.md 한 줄의 차이 (8p)

1. 터미널 두 개를 나란히 띄운다: 왼쪽 `test-svc-before`, 오른쪽 `test-svc-after`.
2. 오른쪽 CLAUDE.md를 화면에 잠깐 보여 준다 (`cat CLAUDE.md`).
3. 양쪽에서 `claude` 실행, 같은 프롬프트를 붙여 넣는다:
   ```
   할일(todo)에 priority 필드(high/medium/low)를 추가해줘.
   ```
4. 권한 확인이 나오면 승인하며 진행한다 (시간이 부족하면 Shift+Tab으로 acceptEdits).
5. 양쪽에서 `/diff`로 비교: 바뀐 파일 수, 새 의존성, 새 추상화(검증 레이어·상수 파일 등).
6. 한 줄 정리: "같은 모델, 같은 요청. 다른 건 CLAUDE.md 한 파일."

결과가 기대와 다르게 비슷하게 나와도 괜찮다. "모델이 좋아져서 차이가 줄었지만, 팀 규칙을 강제하는 곳은 여기"라고 말하고 9p 백업으로 넘어간다.

## 데모 C: 작업이 끝나면 말해 주는 Hook (15p)

1. `test-svc-after` 폴더에서:
   ```bash
   mkdir -p .claude && cp <이 폴더>/c-hook/settings.json .claude/settings.json
   cat .claude/settings.json
   ```
2. `claude` 실행 (이미 실행 중이면 재시작). 폴더 신뢰 확인이 나오면 승인한다.
3. `/hooks`로 Stop Hook이 등록됐는지 보여 준다.
4. 아무 요청이나 보낸다: `이 프로젝트의 API 엔드포인트 목록을 알려줘`
5. 응답이 끝나면 "작업이 완료되었습니다" 음성이 나온다. (발표장 스피커 연결 확인)

macOS 전용(`say`). 리허설 때 settings.json과 `/hooks` 화면을 캡처해 16p 백업 슬라이드에 넣는다.

## 데모 후 정리

```bash
rm test-svc-after/.claude/settings.json
```
빼 둔 `~/.claude/CLAUDE.md` 규칙과 Plugin을 원래대로 돌려놓는다.
