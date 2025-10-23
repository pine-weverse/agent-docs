# List Item (리스트 아이템)

**시스템 구조** (Native List Item):
```
[Leading] ←12px→ [Content] ←12px→ [Trailing]
  선택적       필수(flexible)     선택적
```

---

## 패턴 유형

- **One Line**: Title만 (높이: 48px minimum)
- **Two Line**: Title + Body (높이: 48px minimum)  
- **Three Line**: Title + Body(2줄) (높이: 자동)

---

## 패딩 시스템

- **Medium** (일반): `px-[16px] py-[12px]` → 좌우 16px, 상하 12px
- **Small** (압축): `px-[16px] py-[6px]` → 좌우 16px, 상하 6px

---

## Leading 옵션

- **없음** (No leading) - Content만 사용
- **Avatar** - 24px / 32px / 40px / 48px 원형
- **CheckBox** - 22px (체크박스 영역 24px)
- **Icon** - 24px (가이드용 Selection 아이콘)
- **Image** - 44px 썸네일 (8px radius)
- **Radio** - 24px 라디오 버튼

---

## Content (필수)

### **Basic** (Two Line):
- Title: 16px Bold, 22px line-height (WeGothicSans)
- Body: 14px Regular, 18px line-height, 2px 상하 패딩
- Title-Body 간격: 2px (`gap-[2px]`)

### **No Body Text** (One Line):
- Title: 16px Bold, 22px line-height만 사용

### **Icon + Body Text**:
- Title: 16px Bold
- Body: 12px 아이콘 + 14px Regular 텍스트 (4px gap)

---

## Trailing 옵션

- **없음** (No Trailing)
- **Icon Button** - 40px 원형, Primary 배경
- **Main Button** - 32px 높이, 텍스트 버튼 (13px Bold)
- **Number Badge** - 16px 높이, 빨간 배경 (999+ 표시)
- **Radio** - 24px 라디오 버튼
- **Text + Icon** - Detail 텍스트 (14px Medium) + 20px 아이콘, 4px gap
- **Toggle** - 52px width, 32px height 토글 스위치

---

## 간격 규칙 (Import 코드 기준)

- **요소 간 간격**: `gap-[12px]` → **12px 고정** ⭐
- **좌우 패딩**: `px-[16px]` → **16px** ⭐
- **상하 패딩 (Medium)**: `py-[12px]` → **12px**
- **상하 패딩 (Small)**: `py-[6px]` → **6px**
- **아이템 최소 높이**: `min-h-[48px]` → **48px**
- **Content 내부 간격**: `gap-[2px]` (Title-Body)
- **Trailing 내부 간격**: `gap-[4px]` (Text-Icon)

---

## Divider (구분선)

- **Small**: 1px 높이, 좌우 16px 마진 (fluid width)
- **Large**: 8px 높이, full width
- **색상**: 
  - Light 모드: `black` fillOpacity 0.04
  - Dark 모드: `white` fillOpacity 0.1

---

## 선택 상태 표현

- 체크 아이콘: Trailing 영역에 배치
- Radio/CheckBox: Leading 또는 Trailing 모두 가능
- 선택된 텍스트: Primary Color (#00B8C1) 적용

---

## 검증 질문

- [ ] Leading + Content + Trailing 구조를 따르는가?
- [ ] 각 영역이 시스템 컴포넌트인가?
- [ ] **요소 간 간격이 12px인가?** (gap-[12px])
- [ ] **좌우 패딩이 16px인가?** (px-[16px])
- [ ] **상하 패딩이 12px(Medium) 또는 6px(Small)인가?** (py-[12px] or py-[6px])
- [ ] 최소 높이가 48px 이상인가? (min-h-[48px])
- [ ] One/Two/Three Line 중 하나의 패턴인가?
- [ ] Title-Body 간격이 2px인가? (gap-[2px])
- [ ] Divider가 있다면 1px(Small) 또는 8px(Large)인가?

---

## 자주 하는 실수

- ❌ 요소 간 간격을 8px로 설정 (정답: **12px**)
- ❌ 좌우 패딩을 20px로 설정 (정답: **16px**)
- ❌ Trailing에 체크 아이콘 대신 Leading에 배치
- ❌ 최소 높이 44px로 설정 (정답: **48px**, 터치 영역 확보)
