# ManagerMirror

> [🇺🇸 English](README.md) | 🇰🇷 한국어

> 매니저-엔지니어 관계를 마주하는 모든 사람을 위한 코칭 프레임워크 — 관리하는 쪽이든, 관리받는 쪽이든.

테크에서 가장 어려운 것은 코드가 아니다. 사람이다. 이 프로젝트는 실제 상황을 정리하고, 상대방의 관점을 이해하고, 나만의 원칙을 쌓을 수 있게 돕는다.

원래 엔지니어링 매니저를 위해 만들어졌다. 하지만 매니저를 이해하려는 엔지니어, PIP나 성과 평가·예상치 못한 갈등을 처리하려는 엔지니어에게도 동등하게 유용하다.

---

## 왜 이 프로젝트가 필요한가

매니저-엔지니어 관계는 테크에서 가장 중요하면서도 가장 이해받지 못하는 관계 중 하나다. 매니저 입장에서는 피드백, 저성과 대응, 신뢰 구축. 엔지니어 입장에서는 PIP 대응, 매니저의 반응 이해, 조직 권력 구조 파악.

양쪽 모두 상황을 구조적으로 정리하고 상대를 진짜로 이해할 공간이 부족하다.

ManagerMirror가 제공하는 것:
- 핵심 이론을 담은 **지식 베이스** (심리학, 피드백, 신뢰, 리더십)
- 실제 상황을 기록하고 성찰하는 **구조화된 포맷**
- GROW 모델 기반으로 답 대신 질문을 통해 스스로 보게 만드는 **코칭 접근법**
- **역지사지 단계** — 상대방의 입장을 상상하기 어려울 때, 가능한 관점을 가설로 제시하고 함께 탐색
- **다양한 AI 도구 연동** — Claude Code, GitHub Copilot, ChatGPT, Hermes (Ollama) 등 파일을 읽을 수 있는 모든 AI에서 사용 가능

---

## 동작 방식

세션은 **GROW 모델**을 따르며, 역지사지(P) 단계가 추가된 구조다:

```
실제 상황
    ↓
G — Goal: 이 세션에서 무엇을 얻고 싶은가?
    ↓
R — Reality: 실제로 무슨 일이 있었는가? (한 번에 하나의 질문)
    ↓
P — Perspective: 상대방은 무엇을 생각하고, 느끼고, 두려워하고, 필요로 했을까?
    ↓
O — Options: 다음에는 무엇을 다르게 할 수 있는가?
    ↓
W — Will: 실제로 무엇을 할 것인가?
    ↓
원칙 — 시간이 지나며 축적됨
```

각 세션은 세 개의 파일을 생성한다:
- `situation.md` — 팩트만으로 무슨 일이 있었는가
- `challenge.md` — 제기된 불편한 질문들
- `insight.md` — 무엇을 알게 됐는가, 다음엔 무엇을 다르게 할 것인가

패턴은 `profile/`에 쌓이고, 원칙은 `principles/`에 쌓인다. 세션이 늘수록 거울은 더 선명해진다.

---

## 시작하기

```bash
git clone https://github.com/{your-username}/ManagerMirror.git
cd ManagerMirror
```

이후 원하는 AI 도구로 세션을 시작한다. 아래 [지원하는 AI 도구](#지원하는-ai-도구) 참고.

개인 폴더(`users/{your_username}/`)는 세션이 진행되면서 자동으로 생성된다 — 별도 설정 불필요.

> `users/` 폴더는 `.gitignore`에 의해 **커밋되지 않는다**. 개인 데이터는 로컬에만 존재한다.

---

## 세션 예시

`/managermirror`를 입력하고 상황을 설명하면 세션이 시작된다. 각 역할에서 어떻게 진행되는지 비교:

| | 👨‍💻 엔지니어 | 👔 매니저 |
|---|---|---|
| **상황 설명** | "연말 리뷰에서 'meets expectations'를 받았다. 1:1에서 한 번도 문제 얘기를 들은 적이 없는데. 뭘 놓친 건지 모르겠다." | "지난주 1:1에서 엔지니어에게 커뮤니케이션 관련 피드백을 했다. 그 이후로 꼭 필요한 미팅 외에는 거의 말을 안 한다. 내가 잘못 처리한 건지 모르겠다." |
| **Claude — Reality 단계** | "올해 1:1들을 돌아볼 때, 매니저가 주저하거나 주제를 바꾸거나 생각보다 부드럽게 넘어간 순간이 있었나?" | "정확히 어떻게 말했나? 실제 표현에 가깝게 적어봐라." |
| **Claude — Perspective 단계** | "매니저가 직접 말하기 어려웠던 조직적·개인적 제약이 있었다면 무엇일까? *(foundations/12 참고)*" | "엔지니어가 피드백 이후 조용해졌다. 지금 무엇을 느끼고, 무엇을 두려워하고 있을까?" |
| **세션 결과물** | `situation.md` · `challenge.md` · `insight.md` | `situation.md` · `challenge.md` · `insight.md` |

각 단계는 한 번에 하나의 질문을 던진다. 구체적인 다음 행동 — 또는 남길 만한 원칙 — 에 도달하면 세션이 마무리된다.

---

## 프로젝트 구조

```
ManagerMirror/
├── .gitignore              # users/ 제외
├── AGENTS.md               # 모든 AI 도구를 위한 안내
├── README.md               # 영어
├── README.ko.md            # 한국어
├── skill/
│   └── SKILL.md            # Claude Code 스킬 정의
├── foundations/            # 영문 지식 베이스 — 기본값 (AI가 읽는 파일)
│   ├── 01_human_is_not_a_system.md
│   ├── 02_basic_human_needs.md
│   ├── ...
│   └── 14_manager_managing_engineers.md
├── foundations.ko/         # 한글 지식 베이스 — 한국어 사용자 참조용 (한글 파일명)
│   ├── 01_사람은_시스템이_아니다.md
│   ├── 02_기본_심리_욕구.md
│   ├── ...
│   └── 14_매니저의_엔지니어_관리.md
├── template/               # 파일 형식 레퍼런스
│   ├── situation.md
│   ├── challenge.md
│   ├── insight.md
│   └── principles.md
└── users/                  # gitignored — 개인 데이터
    └── {your_username}/
        ├── profile/
        ├── situations/
        └── principles/
```

---

## 지식 베이스 (foundations/)

코칭 세션의 기반이 되는 14개의 레퍼런스 문서:

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
| `12` | 매니저가 말하지 못하는 것들 — 법적·HR·조직·심리적 제약이 만드는 침묵과 간접 표현의 이해 |
| `13` | 엔지니어가 매니저를 대하는 방법 — 가시성 확보, 1:1 활용, 피드백 채널, 커리어 주도권 |
| `14` | 매니저가 엔지니어를 대하는 방법 — 엔지니어 마인드셋, 집중 보호, 시니어리티 기대치, 조기 피드백 |

---

## 지원하는 AI 도구

ManagerMirror는 파일을 읽을 수 있는 어떤 AI와도 사용할 수 있다. 전체 안내는 [`AGENTS.md`](AGENTS.md)에 있다.

| AI 도구 | 사용 방법 |
|---------|----------|
| **Claude Code** | `skill/SKILL.md` 설치 → `/managermirror` 입력 |
| **GitHub Copilot** | VS Code에서 프로젝트 열기 → `@workspace`로 `AGENTS.md` 참조 |
| **ChatGPT** | `AGENTS.md` + 관련 foundations 파일 업로드 |
| **Hermes (Ollama)** | `AGENTS.md`를 시스템 프롬프트로 사용 |

### Claude Code (완전 자동화)

스킬을 Claude 스킬 디렉토리에 복사한다:

```bash
# macOS
cp -r skill/ ~/Library/Application\ Support/Claude/claude_desktop_config/skills/managermirror/

# Windows
cp -r skill/ "$env:APPDATA\Claude\skills\managermirror\"
```

이후 Claude Code 세션에서:
```
/managermirror
```

프로젝트 위치와 사용자명을 자동으로 감지한다. 별도 설정 불필요.

### 다른 AI 도구

도구별 상세 안내는 [`AGENTS.md`](AGENTS.md)를 참고한다.

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
