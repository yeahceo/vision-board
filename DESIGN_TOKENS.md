# 예사장 Vision Site — Design Tokens v2

> 레퍼런스: Be.run 헬스 대시보드 이미지 (2026-06-22 갱신)
> 이전 토큰(에디토리얼·네이비) → 클린 앱 대시보드로 전면 교체

---

## 1. 무드 (Mood)

- **클린 앱 대시보드** — 건강 트래킹 앱처럼 데이터가 시각적으로 살아있는 느낌
- 따뜻한 베이지 배경 + 하얀 카드 + 다크 사이드바의 대비
- 과하지 않게 밝고 정돈된 느낌. "잘 설계된 앱의 홈 화면"
- 키워드: `dashboard` · `clean` · `warm` · `data-driven` · `minimal`

---

## 2. 컬러 (Color)

| 역할 | 이름 | HEX | 용도 |
|------|------|-----|------|
| Background | Warm Beige | `#EDE8E0` | 전체 배경 |
| Card | Pure White | `#FFFFFF` | 카드 배경 |
| Sidebar | Charcoal Black | `#1C1C1C` | 사이드바·다크 위젯 |
| Ink | Near Black | `#1A1A1A` | 주요 텍스트 |
| Muted | Medium Gray | `#8B8B8B` | 보조 텍스트·라벨 |
| Border | Warm Divider | `#E5DFD6` | 구분선·테두리 |
| Accent Yellow | Amber | `#F2C94C` | 강조·하이라이트·진행 |
| Accent Red | Coral | `#E85D4A` | 경고·포인트·버튼 |
| Accent Olive | Warm Tan | `#C4B49A` | 보조 데이터·차트 |
| Active Nav | White | `#FFFFFF` | 사이드바 활성 아이콘 배경 |

- 데이터 블롭: Yellow(#F2C94C) + Red(#E85D4A) + Olive(#C4B49A) 세 가지 겹침
- 카드 그림자: `0 2px 16px rgba(0,0,0,0.06)` — 가볍고 부드럽게

---

## 3. 타이포 (Typography)

- **Primary**: Pretendard / system-ui — 한글·영문 모두 가독성 우선
- **Label/Mono**: JetBrains Mono — 숫자·시간·태그

| 스타일 | 크기 | 굵기 | 용도 |
|--------|------|------|------|
| Page Title | 28–32px | 700 | "Hi, 예사장!" |
| Card Title | 16–18px | 600 | 카드 헤더 |
| Body | 14–15px | 400 | 본문 |
| Data Big | 36–52px | 700 | 숫자·D-day |
| Label | 11–12px | 500 | 태그·카테고리·mono |

---

## 4. 형태 (Shape & Layout)

- **사이드바**: 고정 왼쪽 64px(모바일) / 220px(데스크탑), 배경 `#1C1C1C`
- **카드**: border-radius `20px`, shadow `0 2px 16px rgba(0,0,0,0.06)`
- **소형 요소**: border-radius `10–12px`
- **알약 버튼**: border-radius `100px`
- **그리드**: 카드 2–3컬럼, 거터 16–20px
- **카드 패딩**: 24px

---

## 5. 모션 (Motion)

- **카드 호버**: `translateY(-3px)` + 그림자 강화 (0.2s ease)
- **블롭 플로팅**: CSS `@keyframes` scale + translate 루프 (8–12s, 무한)
  - 3개 블롭이 서로 다른 속도로 떠다니며 겹침
- **카운트업**: 숫자가 0에서 올라오는 애니메이션 (1.4s ease-out-cubic)
- **스태거 입장**: 카드들이 0.1s 간격으로 순차 fadeUp
- **진행 바**: width 0→목표% 애니메이션 (1s ease)
- **시계 초침**: 실시간 업데이트 (1분마다)

---

## 6. 컴포넌트 패턴

- **Stat Card**: 라벨(mono, gray) + 큰 숫자 + 서브텍스트
- **Blob Viz**: 3색 원형 blur 겹침 → D-day·진행률 시각화
- **Row List**: 아이콘/번호 + 이름 + 설명 + 상태 태그 (파이프라인)
- **Schedule Row**: 시간(mono) + 할일 + 현재=빨간 강조
- **Progress Bar**: 얇은 배경 위 컬러 fill, rounded
- **Dark Card**: 사이드바 색(#1C1C1C)으로 칠한 카드 (D-day 카운터용)

---

### 핵심 한 줄
> **따뜻한 베이지 위, 흰 카드들이 데이터를 담고, 다크 사이드바가 구조를 잡는다. 앱처럼 정돈되고, 매일 열고 싶어지는 화면.**
