# halfdone-cc-planner

만들고 싶은 걸 말하면 복잡도를 보고 판단해서, Claude Code / Codex로 구현하기 전에 필요한 설계 문서를 알아서 골라 써주는 Claude Code 스킬.

- **간단한 스크립트나 도구?** → Claude Code 요청문 작성 (`docs/REQUEST.md`)
- **기능 여러 개인 앱·웹사이트?** → P0/P1/P2 우선순위 포함 PRD 작성 (`docs/PRD.md`)
- **AI 에이전트, 자동화 파이프라인, 런타임 판단 필요한 것?** → 워크플로우·AI vs 코드 역할 분리·실패 처리 포함 에이전트 설계서 작성 (`docs/AGENT_DESIGN.md`)

| 복잡도 | 조건 | 생성 파일 |
|--------|------|----------|
| **Tier 1 — 단순** | 기능 1개, AI 판단 불필요 | `docs/REQUEST.md` |
| **Tier 2 — 중간** | 기능 2~5개, 런타임 AI 판단 없음 | `docs/PRD.md` |
| **Tier 3 — 복잡** | 런타임 AI 판단 또는 실패 복구 필요 | `docs/AGENT_DESIGN.md` |

## 설치

```bash
claude plugin install halfdoneclub/halfdone-cc-planner
```

## 사용 방법

Claude Code에서 만들고 싶은 걸 자유롭게 설명하면 스킬이 자동으로 동작합니다.

**트리거 예시:**
- "이미지 100장을 webp로 변환하는 파이썬 스크립트 짜고 싶어"
- "운동 기록 웹사이트 만들고 싶어. 날짜·운동·세트·횟수 적고 월별 통계 보고 싶음"
- "받은 이메일 자동 분류해서 답장 초안 써주고 슬랙으로 결과 보내는 자동화"
- "PRD 만들어줘", "기획해줘", "에이전트 설계서 짜줘"

## Claude Code 시작 방법

```
# Tier 1
docs/REQUEST.md를 읽고 구현해줘.

# Tier 2
docs/PRD.md를 읽고 구현해줘. P0 기능부터, 각 기능 끝날 때마다 확인시켜줘.

# Tier 3
docs/ 폴더의 설계서를 읽고 구현해줘. 워크플로우 1단계부터, 각 단계 끝날 때마다 성공 기준 확인해줘.
```

## 라이선스

MIT
