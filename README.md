# halfdone-cc-planner

Claude Code 프로젝트 플래너 플러그인 — 아이디어를 3단계 복잡도로 진단하고 즉시 사용 가능한 설계 산출물을 자동 생성합니다.

## 기능

| 복잡도 | 조건 | 생성 산출물 |
|--------|------|------------|
| Tier 1 (단순) | 기능 1개, AI 판단 불필요 | `docs/REQUEST.md` — Claude Code 요청문 |
| Tier 2 (중간) | 기능 2~5개, 런타임 AI 판단 불필요 | `docs/PRD.md` — 제품 요구사항 문서 |
| Tier 3 (복잡) | 런타임 AI 판단 또는 실패 복구 필요 | `docs/AGENT_DESIGN.md` (+ `docs/PRD.md`) |

## 설치

```bash
claude plugin install halfdone-cc-planner
```

또는 GitHub에서 직접 설치:

```bash
claude plugin install https://github.com/halfdoneclub/halfdone-cc-planner
```

## 사용 방법

설치 후 Claude Code에서 프로젝트 아이디어를 자유롭게 입력하면 자동으로 스킬이 동작합니다.

**트리거 예시 (한국어):**
- "이미지 변환 스크립트 짜고 싶어"
- "운동 기록 웹사이트 만들고 싶어"
- "이메일 자동 분류 자동화 만들어줘"
- "PRD 만들어줘", "기획해줘", "에이전트 설계서 짜줘"

**트리거 예시 (English):**
- "I want to build a CLI tool that..."
- "How do I build this?"
- "Scaffold a project plan for..."
- "Write a PRD for..."

## 산출물 예시

### Tier 1 — `docs/REQUEST.md`
Claude Code에 바로 붙여넣을 수 있는 구조화된 요청문.

### Tier 2 — `docs/PRD.md`
개요 · 사용자 · 기능(P0/P1/P2) · 기술 요구사항 · 범위 외 · 구현 가이드 포함 PRD.

### Tier 3 — `docs/AGENT_DESIGN.md`
작업 컨텍스트 · 워크플로우 · 에이전트 구조 · 구현 스펙 · 구현 가이드 포함 설계서.
판단(AI)과 코드(스크립트) 역할 분리 명시.

## Claude Code 시작 방법

산출물 저장 후 새 Claude Code 세션에서:

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
