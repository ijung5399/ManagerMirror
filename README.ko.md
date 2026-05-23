# ManagerMirror

> [🇺🇸 English](README.md) | 🇰🇷 한국어

> 사람 관리라는 가장 어려운 문제를 마주한 엔지니어링 매니저를 위한 자기 성찰 프레임워크.

---

## 왜 이 프로젝트가 필요한가

엔지니어에서 엔지니어링 매니저로의 전환은 기술적 문제를 푸는 것에서 사람 문제를 푸는 것으로의 전환이다. 도구가 다르고, 피드백 루프가 느리며, 코드와 달리 사람은 예측대로 움직이지 않는다.

ManagerMirror는 그 과정을 위한 하네스(harness)다:
- 핵심 이론을 담은 **지식 베이스** (심리학, 피드백, 신뢰, 리더십)
- 실제 상황을 기록하고 성찰하는 **구조화된 포맷**
- 답을 주는 것이 아니라 질문을 통해 스스로 보게 만드는 **코칭 접근법**
- 세션을 안내하고 결과를 자동 저장하는 **Claude Code 스킬** (`/managermirror`)

---

## 동작 방식

```
실제 상황
    ↓
코칭 질문 (한 번에 하나, 감정 먼저)
    ↓
인사이트 — 전에는 보이지 않던 것
    ↓
원칙 — 시간이 지나며 축적됨
```

각 세션은 세 개의 파일을 생성한다:
- `situation.md` — 팩트 중심으로 무슨 일이 있었는가
- `challenge.md` — 제기된 불편한 질문들
- `insight.md` — 무엇을 알게 됐는가, 다음엔 무엇을 다르게 할 것인가

패턴은 `profile/`에 쌓이고, 원칙은 `principles/`에 쌓인다. 세션이 늘수록 거울은 더 선명해진다.

---

## 시작하기

```bash
git clone https://github.com/{your-username}/ManagerMirror.git
cd ManagerMirror
```

개인 폴더를 만든다:
```
users/
└── {your_username}/
    ├── profile/
    │   ├── self.md        # 매니저로서 나 자신에 대한 이해 (누적)
    │   └── triggers.md    # 나를 흔드는 상황과 그 이유
    ├── situations/        # 세션당 하나의 폴더
    ├── principles/
    │   └── principles.md  # 누적된 원칙
    └── log/               # 세션 원본 기록 (선택)
```

각 파일 형식은 `template/`을 참고한다.

> `users/` 폴더는 `.gitignore`에 의해 **커밋되지 않는다**. 개인 데이터는 로컬에만 존재한다.

---

## 프로젝트 구조

```
ManagerMirror/
├── .gitignore              # users/ 제외
├── README.md               # 영어
├── README.ko.md            # 한국어
├── foundations/            # 공유 지식 베이스 (11개 파일)
│   ├── 01_human_is_not_a_system.md
│   ├── 02_basic_human_needs.md
│   ├── 03_psychological_safety.md
│   ├── 04_trust.md
│   ├── 05_radical_candor.md
│   ├── 06_nonviolent_communication.md
│   ├── 07_difficult_conversations.md
│   ├── 08_feedback.md
│   ├── 09_situational_leadership.md
│   ├── 10_engineering_manager_traps.md
│   └── 11_questioning_techniques.md
├── template/               # 파일 형식 레퍼런스
│   ├── situation.md
│   ├── challenge.md
│   ├── insight.md
│   └── principles.md
└── users/                  # gitignored — 개인 데이터
    └── {your_username}/
```

---

## 지식 베이스 (foundations/)

코칭 세션의 기반이 되는 11개의 레퍼런스 문서.

| 파일 | 주제 |
|------|------|
| `01` | 사람은 시스템이 아니다 — 엔지니어 마인드셋의 함정 |
| `02` | 자기결정이론 — 자율성, 유능감, 연결감 |
| `03` | 심리적 안전감 — 팀 성과를 예측하는 가장 강력한 단일 요소 |
| `04` | 신뢰 방정식 — 자기중심성이 신뢰를 무너뜨리는 이유 |
| `05` | Radical Candor — 개인적으로 돌보되 직접적으로 도전하라 |
| `06` | 비폭력 대화 — 관찰 → 감정 → 욕구 → 요청 |
| `07` | 어려운 대화 — 모든 힘든 대화 안에 있는 3개의 층 |
| `08` | 피드백 — SBI 모델, 타이밍, 잘 받는 법 |
| `09` | 상황적 리더십 — 사람의 단계에 맞게 스타일을 바꿔라 |
| `10` | 엔지니어링 매니저의 함정 — Fix-it 모드, 명확성 강박 외 |
| `11` | 질문 기술 — 말하지 못하는 것을 끌어내는 방법 |

---

## Claude Code 스킬

[Claude Code](https://claude.ai/code)를 사용한다면 `/managermirror` 스킬을 사용할 수 있다.

스킬이 자동으로 처리하는 것:
- 상황에 맞는 foundations 파일 선택적 로드
- 누적된 profile, triggers, principles 읽기
- 코칭 질문으로 세션 진행 (한 번에 하나, 감정 먼저)
- 세션 종료 시 올바른 폴더 구조로 결과 저장

스킬 폴더를 Claude 스킬 디렉토리에 넣으면 설치된다.

**세션 시작 방법:**
```
/managermirror
```
또는 직원/팀원 관련 상황을 설명하면 자동 트리거.

---

## 프라이버시 모델

| 항목 | 위치 | 커밋 여부 |
|------|------|----------|
| 지식 베이스 | `foundations/` | ✅ 커밋됨 |
| 템플릿 | `template/` | ✅ 커밋됨 |
| 나의 상황 기록 | `users/{나}/situations/` | ❌ 로컬 전용 |
| 나의 프로파일 | `users/{나}/profile/` | ❌ 로컬 전용 |
| 나의 원칙 | `users/{나}/principles/` | ❌ 로컬 전용 |

프레임워크는 공유하되, 개인 데이터는 공유하지 않는다.

---

## 라이선스

MIT
