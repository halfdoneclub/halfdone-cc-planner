# halfdone-cc-planner

만들고 싶은 것을 말하면 복잡도를 진단하고, 다음 코딩 세션에서 바로 쓸 수 있는 설계 산출물을 `docs/`에 저장해주는 Claude Code 스킬.

| 복잡도 | 조건 | 생성 파일 |
|--------|------|----------|
| **Tier 1 — 단순** | 기능 1개, AI 판단 불필요 | `docs/REQUEST.md` — Claude Code 요청문 |
| **Tier 2 — 중간** | 기능 2~5개, 런타임 AI 판단 없음 | `docs/PRD.md` — 제품 요구사항 문서 |
| **Tier 3 — 복잡** | 런타임 AI 판단 또는 실패 복구 필요 | `docs/AGENT_DESIGN.md` (+ 외부 제품이면 `docs/PRD.md`) |

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
- "PRD 만들어줘", "기획해줘", "에이전트 설계서 짜줘", "이거 어떻게 만들지"

필요하면 최대 3개 질문 후 `docs/`에 파일 저장 + 경로·3~5줄 요약 출력.

## 산출물별 내용

### Tier 1 → `docs/REQUEST.md`
목적 → 입력 → 처리 → 출력 → 제약 → 완료 기준 구조의 Claude Code 요청문. 새 세션에 붙여넣으면 바로 구현 시작 가능.

### Tier 2 → `docs/PRD.md`
개요 · 사용자 · 기능(P0/P1/P2) · 기술 요구사항 · 범위 외 · 구현 가이드 포함 PRD.

### Tier 3 → `docs/AGENT_DESIGN.md`
작업 컨텍스트 · 워크플로우(AI vs. 코드 역할 분리 명시) · 에이전트 구조 · 구현 스펙 · 구현 가이드 포함 설계서. 단계별 실패 처리 및 검증 패턴 포함.

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
