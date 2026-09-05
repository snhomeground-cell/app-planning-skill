# app-planning

앱·웹 서비스를 `READY TO BUILD` 상태까지 기획하는 Claude Code 스킬

무엇을, 누구를 위해, 왜, 어떤 범위와 구조로 개발할지를 순서대로 확정한 뒤에 구현으로 넘어가도록 강제하는 것이 목적

- 기획이 명확해지기 전에 구현하지 않음
- 사용자가 결정해야 할 Product Decision을 임의로 결정하지 않음
- Feature보다 User Goal, Screen보다 User Journey, Technology보다 Product Requirement를 먼저 정의

## 설치

Claude Code에서 아래 두 줄 실행 (권장)

```
/plugin marketplace add snhomeground-cell/app-planning-skill
/plugin install app-planning@app-planning-skill
```

수동 설치를 원할 경우 저장소를 스킬 폴더로 복제

```bash
git clone https://github.com/snhomeground-cell/app-planning-skill.git ~/.claude/skills/app-planning
```

`SKILL.md` 한 파일만 내려받아 아래 위치에 배치해도 동작

| 운영체제 | 경로 |
|---|---|
| macOS / Linux | `~/.claude/skills/app-planning/SKILL.md` |
| Windows | `%USERPROFILE%\.claude\skills\app-planning\SKILL.md` |

## 사용

Claude Code에서 `/app-planning` 호출, 또는 아래 표현으로 실행

- "앱 기획 정리해줘"
- "이거 뭐부터 만들지"
- "MVP 범위 잡아줘"
- "기술 스택 정해줘"
- "태스크 쪼개줘"
- "이 프로젝트 기획 역으로 정리해줘"

## 두 가지 모드

`New Project` — 아이디어 단계. Phase 1부터 순서대로 진행

`Existing Project` — 이미 구현된 프로젝트. 현재 상태 파악 → Reverse Planning → Gap Analysis → 부족한 Phase만 재수행. 검토 중 코드 미수정

## 진행 단계

1. Problem — 해결하려는 문제·주요 사용자·핵심 가치
2. Product — User, Core Journey, Feature, Information Architecture, Data, Permission, Edge Case
3. Scope — MVP · Next · Later · Out of Scope 분류
4. System — Technical Requirements, Technology, Architecture, Project Structure
5. Build Preparation — Development Rules, Task Breakdown

각 Task는 Acceptance Criteria와 Verification Method를 갖춤

## Ready to Build Gate

11개 항목을 모두 충족하면 `STATUS: READY TO BUILD` 판정

Problem · User · Core Journey · MVP · Data와 Permission · Technical Stack · Architecture ·
Development Rules · Task 분해 · Acceptance Criteria · Verification Method

## 산출물

현재 프로젝트에 필요한 문서만 생성

PRODUCT_SPEC.md, DATA_MODEL.md, PERMISSIONS.md, TECH_STACK.md, PROJECT_STRUCTURE.md,
DEVELOPMENT_RULES.md, TASKS.md, DECISIONS.md

- Existing Project에서는 PLANNING_GAPS.md 추가

## 범위 밖

| 영역 | 질문 | 담당 |
|---|---|---|
| UX | 사용자가 쉽게 발견하거나 이해할 수 있는가 | [ux-audit](https://github.com/snhomeground-cell/ux-audit-skill) |
| QA | 기능이 실제로 정상 작동하는가 | 별도 QA |
| Code | 코드 품질과 구조가 건강한가 | 별도 Code Audit |

발견 시 기록만 하고 해당 절차로 인계

## 라이선스

MIT
