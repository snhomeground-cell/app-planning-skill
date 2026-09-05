---
name: app-planning
description: 앱·웹 서비스의 아이디어 또는 현재 구현 상태를 분석해 무엇을·누구를 위해·왜·어떤 범위와 구조로 개발할지 정의하고, 프로젝트를 READY TO BUILD 상태로 만드는 스킬. 신규 프로젝트는 Problem → Product → Scope → System → Build Preparation 5단계로 진행하고, 이미 구현된 프로젝트는 Current State → Reverse Planning → Gap Analysis → Planning Recovery 순서로 진행한다. 확정되지 않은 정보는 Observed·Confirmed·Inferred·Assumption·TBD로 구분하며, 사용자가 결정해야 할 Product Decision을 임의로 결정하지 않는다. 트리거 — "앱 기획", "기획 정리해줘", "PRD 만들어줘", "이거 뭐부터 만들지", "MVP 범위 잡아줘", "기술 스택 정해줘", "태스크 쪼개줘", "이 프로젝트 기획 역으로 정리해줘", "지금 만든 거 기획이랑 안 맞는 것 같아", "READY TO BUILD", "/app-planning". UX 사용성 평가는 범위 밖(=ux-audit) / 기능 QA와 코드 품질 감사도 범위 밖.
---

# App Planning

## Purpose

앱/웹 서비스의 아이디어 또는 현재 구현 상태를 분석하여
무엇을, 누구를 위해, 왜, 어떤 범위와 구조로 개발할지 정의한다.

최종 목표는 프로젝트를 `READY TO BUILD` 상태로 만드는 것이다.

이 Skill은 UX 사용성 평가, 기능 QA, 코드 품질 감사를 수행하지 않는다.

---

## Operating Mode

프로젝트 상태에 따라 모드를 선택한다.

### New Project
아이디어 단계라면 처음부터 Product Planning을 수행한다.

### Existing Project
이미 구현된 프로젝트라면 먼저 현재 상태를 분석하고
Reverse Planning → Gap Analysis를 수행한다.

Existing Project Review 중에는 코드를 수정하지 않는다.

---

# Core Rules

1. 기획이 충분히 명확해지기 전에 구현하지 않는다.
2. 사용자가 결정해야 할 Product Decision을 임의로 결정하지 않는다.
3. Feature보다 User Goal을 먼저 정의한다.
4. Screen보다 User Journey를 먼저 정의한다.
5. Technology보다 Product Requirement를 먼저 정의한다.
6. MVP에 필요하지 않은 기능은 적극적으로 분리한다.
7. 현재 규모보다 복잡한 Architecture를 제안하지 않는다.
8. 한 번에 많은 질문을 하지 말고 현재 단계에 필요한 질문부터 한다.
9. 이미 확정된 내용은 다시 질문하지 않는다.
10. 불확실한 정보는 다음으로 구분한다:
   - Observed
   - Confirmed
   - Inferred
   - Assumption
   - TBD

---

# Workflow

## Phase 1 — Problem

정의:

- 해결하려는 문제
- 주요 사용자
- 현재 문제 해결 방식
- 핵심 가치

완료 조건:

- 문제를 설명할 수 있음
- 주요 사용자를 설명할 수 있음
- 핵심 가치를 한 문장으로 설명할 수 있음

---

## Phase 2 — Product

정의:

### User
- User Type
- Goal
- Context
- Permission

### Core Journey
- Starting Point
- Goal
- Major Steps
- Success Condition

### Feature
각 기능을 User Journey와 연결한다.

### Information Architecture
- 주요 정보 구조
- Navigation
- 필요한 Screen

### Data
- 핵심 Entity
- 주요 Field
- Relationship

### Permission / Policy
- 역할별 권한
- 삭제
- 탈퇴
- 공개 범위
- 데이터 보존 등 주요 정책

### Planning-level Edge Cases
핵심 흐름에서 제품이 어떻게 행동해야 하는지 결정한다.

---

## Phase 3 — Scope

기능을 다음으로 분류한다.

- MVP
- Next
- Later
- Out of Scope

MVP 판단 기준:

"이 기능이 없으면 사용자가 핵심 목적을 달성할 수 없는가?"

---

## Phase 4 — System

제품 요구사항을 기반으로 기술 구조를 결정한다.

### Technical Requirements
필요한 경우만 정의한다.

- Authentication
- Database
- Storage
- Search
- Realtime
- Notification
- External API
- Deployment

### Technology
선택:

- Frontend
- Backend
- Database
- Authentication
- Storage
- Hosting

의미 있는 대안이 존재하면
Trade-off를 설명하고 사용자에게 선택을 요청한다.

### Architecture

목표는 복잡한 Pattern이 아니라
책임을 명확하게 하는 것이다.

예:

UI
→ Application Logic
→ Service / API
→ Database

정의:

- UI responsibility
- Business logic
- Data access
- State
- Shared components
- Error handling

### Project Structure

프로젝트 규모에 맞는 최소 구조를 정의한다.

---

## Phase 5 — Build Preparation

### Development Rules

필요한 프로젝트 규칙을 정의한다.

기본:

- 요청 범위 밖 수정 금지
- 불필요한 Refactoring 금지
- 기존 Architecture 준수
- 중복 구현 방지
- Dependency 추가 최소화
- 기존 Component 우선 사용
- Data Access 방식 통일
- 작업 후 검증

### Task Breakdown

MVP를 작은 구현 단위로 나눈다.

각 Task:

- Task ID
- Objective
- Dependencies
- Scope
- Requirements
- Acceptance Criteria
- Verification Method

하나의 Task는 가능한 한 하나의 결과물을 가진다.

---

# Existing Project Mode

이미 구현된 프로젝트라면 다음 순서로 진행한다.

## 1. Current State

확인:

- 기술 스택
- 주요 화면
- Navigation
- 구현된 기능
- User Type
- Data Model
- Permission
- Architecture
- Project Structure

## 2. Reverse Planning

현재 구현에서 다음을 추론한다.

- Problem
- Product Goal
- User
- Core Journey
- Feature Structure

추론한 내용은 `Inferred`로 표시하고
사용자 확인 후 `Confirmed`로 변경한다.

## 3. Gap Analysis

각 영역을 비교한다.

- Intended
- Current
- Gap
- Impact
- Required Decision

Gap을 다음으로 분류한다.

- Missing
- Inconsistent
- Overbuilt
- Unclear
- Planning Debt
- No Issue

## 4. Planning Recovery

Gap이 존재하는 Phase만 다시 수행한다.

이미 명확한 영역은 반복하지 않는다.

---

# Ready to Build Gate

다음을 확인한다.

- [ ] Problem이 명확하다.
- [ ] 주요 User가 정의됐다.
- [ ] Core Journey가 정의됐다.
- [ ] MVP가 명확하다.
- [ ] 핵심 Data와 Permission이 정의됐다.
- [ ] Technical Stack이 결정됐다.
- [ ] Architecture가 설명 가능하다.
- [ ] Development Rules가 존재한다.
- [ ] MVP가 작은 Task로 나뉘었다.
- [ ] 각 Task에 Acceptance Criteria가 있다.
- [ ] 각 Task에 Verification Method가 있다.

충족하면:

`STATUS: READY TO BUILD`

---

# Boundaries

다음 문제가 발견되면 기록만 하고 적절한 후속 Audit으로 넘긴다.

### UX
사용자가 쉽게 발견하거나 이해할 수 있는가?
→ UX Audit

### QA
기능이 실제로 정상 작동하는가?
→ QA

### Code
코드 품질과 구조가 건강한가?
→ Code Audit

App Planning은 이 영역을 대신 수행하지 않는다.

---

# Output

필요한 경우 다음 산출물을 생성한다.

- PRODUCT_SPEC.md
- DATA_MODEL.md
- PERMISSIONS.md
- TECH_STACK.md
- PROJECT_STRUCTURE.md
- DEVELOPMENT_RULES.md / CLAUDE.md
- TASKS.md
- DECISIONS.md

Existing Project에서는 추가:

- PLANNING_GAPS.md

모든 문서를 반드시 생성할 필요는 없다.
현재 프로젝트에 필요한 문서만 생성한다.
