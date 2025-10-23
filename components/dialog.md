# Dialog (다이얼로그)

**시스템 구조** (Import 코드 기준):
```
[Scrim Overlay 50% 검은색]
    ↓
[Dialog 312px]
  ├─ [Text] (Title + Description)
  └─ [DialogButtons]
       ├─ [Agree] (선택적)
       └─ [Buttons] (1~3개)
```

---

## Dialog 기본 설정

- **크기**: `w-[312px]` → **312px 고정** ⭐
- **Radius**: `rounded-[16px]` → **16px** ⭐
- **패딩**:
  - Light Mode: `pb-[16px] pt-[24px] px-[16px]` → **상단 24px, 하단 16px, 좌우 16px** ⭐
  - Dark Mode: `pb-[16px] pt-[24px] px-0` → **좌우 0** ⭐ (Material 내부에서 px-[16px])
- **내부 간격**: `gap-[24px]` (Text ↔ DialogButtons) ⭐
- **정렬**: `flex flex-col items-center justify-center`

---

## Scrim Overlay (배경 오버레이)

- **배경**: `bg-[rgba(0,0,0,0.5)]` → **50% 검은색** ⭐
- **위치**: `absolute inset-0`
- **용도**: Dialog 뒤 화면 어둡게 처리

---

## Light Mode / Dark Mode

### **Light Mode**:
- **배경**: `bg-white`
- **패딩**: `pb-[16px] pt-[24px] px-[16px]`

### **Dark Mode**:
- **배경**: `bg-[#282828]` ⭐
- **패딩**: `pb-[16px] pt-[24px] px-0` (좌우 0)
- **Material 영역**:
  - 패딩: `px-[16px] py-0` (Text 영역에만 좌우 패딩)

---

## Text 영역 (Title + Description)

### **구조**:
```
[Title]
  ↓ 12px gap
[Description]
```

**간격**: `gap-[12px]` (Title ↔ Description) ⭐

### **Title**:
- **크기**: `19px Bold` ⭐
- **Line-height**: `25px`
- **Font**: WeGothicSans:Bold
- **정렬**: `text-center`
- **너비**: `w-[312px]` (Dialog와 동일)
- **색상**:
  - Light Mode: `text-black`
  - Dark Mode: `text-white`
- **최대 줄 수**: **3줄** → 이후 "..." 처리 ⭐
- **Overflow**: `-webkit-box css-7x2tr0` (ellipsis 처리)

### **Description**:
- **크기**: `16px Regular` ⭐
- **Line-height**: `22px`
- **Font**: WeGothicSans:Regular
- **정렬**: `text-center`
- **너비**: `w-full`
- **색상**:
  - Light Mode: `text-[#282828]` ⭐
  - Dark Mode: `text-[#dddddd]` ⭐
- **최대 줄 수**: **5줄** → 이후 "..." 처리 ⭐
- **Overflow**: `-webkit-box css-jco31q` (ellipsis 처리)

---

## DialogButtons 영역

### **구조**:
```
[Agree] (선택적)
  ↓ 16px gap
[Buttons] (1~3개)
```

- **크기**: `w-[280px]` → **280px 고정** ⭐ (Dialog 312px - 좌우 패딩 32px)
- **간격**:
  - Agree ↔ Buttons: `gap-[16px]` ⭐
  - Buttons 내부: `gap-[6px]` ⭐

---

## Agree (체크박스 옵션) - 선택적

### **구조**:
```
[Checkbox 24px] ←6px→ [Text]
```

### **Checkbox**:
- **크기**: `24x24` → **24px** ⭐
- **내부 체크박스**: `22x22`, `rounded-[100px]` (원형)
- **배경** (선택 시):
  - Light Mode: `bg-[#01d5df]` ⭐
  - Dark Mode: `bg-[#01d5df]`
- **Icon**: 16x16 white checkmark (SVG)
- **Border**: 없음 (선택 안 됨 시 border 표시)

### **Text**:
- **크기**: `15px Regular` ⭐
- **Line-height**: `21px`
- **Font**: WeGothicSans:Regular
- **색상**: `text-[#484848]` (Light/Dark 동일) ⭐
- **최대 줄 수**: **2줄** → 이후 "..." 처리 ⭐
- **Overflow**: `-webkit-box css-zgugll` (ellipsis)

**간격**: `gap-[6px]` (Checkbox ↔ Text) ⭐

---

## Buttons (1~3개)

### **배치 방식** (2가지):

#### **1. 세로 형태** (Vertical) - 기본:
- **배치**: `flex flex-col gap-[6px]` ⭐
- **사용처**: 버튼 1~3개 모두 가능
- **간격**: `gap-[6px]` (버튼 간)
- **버튼 크기**: `w-[280px]` 고정
- **높이**: `44px` (Large) ⭐

#### **2. 가로 형태** (Horizontal):
- **배치**: `flex gap-[6px] items-center` ⭐
- **사용처**: **버튼 2개일 때만** ⭐
- **간격**: `gap-[6px]` (버튼 간)
- **버튼 크기**: `basis-0 grow` → **동일한 너비로 분할**
- **높이**: `44px` (Large)
- **배치 순서**:
  - 좌측: Outlined Gray (보조 작업)
  - 우측: Filled (기본 작업)

---

## Button Type 조합 규칙

### **버튼 1개**:
- **Type**: Filled ⭐
- **예시**: "확인" (Primary 액션)

### **버튼 2개** (택1 - 세로 또는 가로):

**세로 형태**:
```
[Filled Button]     ← 기본 작업 (상단)
[Outlined Gray]     ← 보조 작업 (하단)
```

**가로 형태**:
```
[Outlined Gray]  [Filled Button]
   보조 (좌측)      기본 (우측)
```

### **버튼 3개** (세로만):
```
[Filled Button]     ← 기본 작업 (최상단)
[Outlined Gray]     ← 보조 작업 (중간)
[Ghost Button]      ← 최소 강조 (최하단)
```

---

## Button 스타일 (Light Mode)

### **Filled** (주요 액션):
- **배경**: `bg-[#00cbd5]` (Primary 민트색) ⭐
- **텍스트**: `text-white`
- **Font**: 16px Bold, 22px line-height
- **Border**: 없음
- **패딩**: `px-[20px] py-0` (Large 44px 규칙)

### **Outlined Gray** (보조 액션):
- **배경**: 투명
- **Border**: `border border-[rgba(0,0,0,0.2)] border-solid` ⭐
- **텍스트**: `text-black`
- **Font**: 16px Bold, 22px line-height
- **패딩**: `px-[20px] py-0`

### **Ghost** (최소 강조):
- **배경**: `bg-[rgba(255,255,255,0)]` (완전 투명)
- **Border**: 없음
- **텍스트**: `text-[#484848]` ⭐
- **Font**: 16px **Medium** ⭐ (Bold 아님!)
- **패딩**: `px-[20px] py-0`

---

## Button 스타일 (Dark Mode)

### **Filled** (주요 액션):
- **배경**: `bg-[#01d5df]` ⭐ (약간 다른 민트색)
- **텍스트**: `text-black` ⭐ (Light와 반대)
- **Font**: 16px Bold, 22px line-height
- **Border**: 없음

### **Outlined** (보조 액션):
- **배경**: 투명
- **Border**: `border border-[rgba(255,255,255,0.2)] border-solid` ⭐ (흰색 20%)
- **텍스트**: `text-white` ⭐
- **Font**: 16px Bold, 22px line-height

### **Ghost** (최소 강조):
- **배경**: `bg-[rgba(255,255,255,0)]` (완전 투명)
- **Border**: 없음
- **텍스트**: `text-[#bbbbbb]` ⭐ (밝은 회색)
- **Font**: 16px **Medium** ⭐

---

## 간격 시스템 (Margin)

### **외부 여백** (Dialog 밖):
- **좌우**: **16px** (화면 양쪽)
- **상하**: 중앙 정렬 (`translate-x-[-50%] translate-y-[-50%]`)

### **내부 여백** (Dialog 안):
- **상단**: `pt-[24px]` → **24px** ⭐
- **하단**: `pb-[16px]` → **16px** ⭐
- **좌우** (Light): `px-[16px]` → **16px** ⭐
- **좌우** (Dark): `px-0` (Material 영역에서 px-[16px])

### **요소 간 간격**:
- Text ↔ DialogButtons: `gap-[24px]` ⭐
- Title ↔ Description: `gap-[12px]` ⭐
- Agree ↔ Buttons: `gap-[16px]` ⭐
- Buttons 내부 (세로): `gap-[6px]` ⭐
- Buttons 내부 (가로): `gap-[6px]` ⭐
- Checkbox ↔ Text: `gap-[6px]` ⭐

---

## 텍스트 최대 줄 수

| 영역 | 최대 줄 수 | 처리 |
|------|-----------|------|
| **Title** | **3줄** ⭐ | "..." ellipsis |
| **Description** | **5줄** ⭐ | "..." ellipsis |
| **Agree Text** | **2줄** ⭐ | "..." ellipsis |

---

## 고정 크기

| 요소 | 크기 | 비고 |
|------|------|------|
| **Dialog 너비** | **312px** ⭐ | 고정 |
| **Buttons 영역** | **280px** ⭐ | Dialog 312px - 좌우 32px |
| **Button 높이** | **44px** ⭐ | Large 사이즈 |
| **Checkbox** | **24px** | 외부 영역 |
| **Checkbox 내부** | **22px** | 실제 체크박스 |
| **Checkmark Icon** | **16px** | SVG |
| **Dialog Radius** | **16px** ⭐ | 고정 |

---

## 검증 질문

### **Dialog 기본**:
- [ ] Dialog 너비가 312px인가?
- [ ] Dialog radius가 16px인가?
- [ ] Scrim 배경이 rgba(0,0,0,0.5)인가?
- [ ] 내부 간격(Text ↔ Buttons)이 24px인가?

### **패딩**:
- [ ] 상단 패딩이 24px인가?
- [ ] 하단 패딩이 16px인가?
- [ ] 좌우 패딩이 Light 16px / Dark 0(Material 16px)인가?

### **Text 영역**:
- [ ] Title이 19px Bold, 25px line-height인가?
- [ ] Description이 16px Regular, 22px line-height인가?
- [ ] Title-Description 간격이 12px인가?
- [ ] Title 최대 3줄, Description 최대 5줄인가?
- [ ] Light Title이 black, Dark가 white인가?
- [ ] Light Description이 #282828, Dark가 #dddddd인가?

### **DialogButtons**:
- [ ] DialogButtons 너비가 280px인가?
- [ ] Agree-Buttons 간격이 16px인가?
- [ ] Buttons 간 간격이 6px인가?

### **Agree**:
- [ ] Checkbox 크기가 24px(외부), 22px(내부)인가?
- [ ] Checkbox 배경이 #01d5df인가?
- [ ] Checkbox Icon이 16px인가?
- [ ] Checkbox-Text 간격이 6px인가?
- [ ] Text가 15px Regular, 21px line-height인가?
- [ ] Text 색상이 #484848인가?
- [ ] Text 최대 2줄인가?

### **Button 배치**:
- [ ] 버튼 1개일 때 Filled만 사용하는가?
- [ ] 버튼 2개일 때 세로(Filled+Outlined) 또는 가로인가?
- [ ] 가로일 때 좌측 Outlined, 우측 Filled인가?
- [ ] 버튼 3개일 때 세로만 사용하는가?
- [ ] 버튼 3개일 때 Filled+Outlined+Ghost 순서인가?

### **Button 스타일 (Light)**:
- [ ] Filled가 bg-[#00cbd5], text-white인가?
- [ ] Outlined가 border-[rgba(0,0,0,0.2)], text-black인가?
- [ ] Ghost가 bg 투명, text-[#484848], **Medium** weight인가?

### **Button 스타일 (Dark)**:
- [ ] Filled가 bg-[#01d5df], text-black인가?
- [ ] Outlined가 border-[rgba(255,255,255,0.2)], text-white인가?
- [ ] Ghost가 text-[#bbbbbb]인가?

### **Button 크기**:
- [ ] 모든 버튼이 44px 높이인가? (Large)
- [ ] 세로일 때 버튼 너비가 280px인가?
- [ ] 가로일 때 버튼이 basis-0 grow인가?
- [ ] 버튼 패딩이 px-[20px] py-0인가?

### **텍스트 제한**:
- [ ] Title이 3줄 초과 시 ellipsis 처리되는가?
- [ ] Description이 5줄 초과 시 ellipsis 처리되는가?
- [ ] Agree Text가 2줄 초과 시 ellipsis 처리되는가?

---

## 자주 하는 실수

### **Dialog 크기**:
- ❌ Dialog 너비를 300px로 설정 (정답: **312px**)
- ❌ Dialog radius를 12px로 설정 (정답: **16px**)
- ❌ Scrim 배경을 60%로 설정 (정답: **50%** rgba(0,0,0,0.5))

### **패딩**:
- ❌ 상단 패딩을 16px로 설정 (정답: **24px**)
- ❌ 하단 패딩을 24px로 설정 (정답: **16px**)
- ❌ Dark Mode에서 좌우 패딩 16px 직접 적용 (정답: **px-0, Material 내부에서 적용**)

### **간격**:
- ❌ Text-Buttons 간격을 16px로 설정 (정답: **24px**)
- ❌ Title-Description 간격을 16px로 설정 (정답: **12px**)
- ❌ Agree-Buttons 간격을 12px로 설정 (정답: **16px**)
- ❌ Buttons 간 간격을 8px로 설정 (정답: **6px**)

### **Title/Description**:
- ❌ Title을 16px로 설정 (정답: **19px Bold**)
- ❌ Description을 14px로 설정 (정답: **16px Regular**)
- ❌ Title line-height를 22px로 설정 (정답: **25px**)
- ❌ Light Description을 black으로 설정 (정답: **#282828**)
- ❌ Dark Description을 white로 설정 (정답: **#dddddd**)
- ❌ Title 최대 줄 수를 5��로 설정 (정답: **3줄**)
- ❌ Description 최대 줄 수를 3줄로 설정 (정답: **5줄**)

### **Agree**:
- ❌ Checkbox 크기를 20px로 설정 (정답: **24px** 외부, **22px** 내부)
- ❌ Checkbox 배경을 #00cbd5로 설정 (정답: **#01d5df**)
- ❌ Checkbox-Text 간격을 8px로 설정 (정답: **6px**)
- ❌ Text를 16px로 설정 (정답: **15px Regular**)
- ❌ Text 색상을 black으로 설정 (정답: **#484848**)
- ❌ Text 최대 줄 수를 3줄로 설정 (정답: **2줄**)

### **Button 배치**:
- ❌ 버튼 2개를 항상 세로로 배치 (정답: **세로 또는 가로** 가능)
- ❌ 가로일 때 좌측 Filled, 우측 Outlined (정답: **좌측 Outlined, 우측 Filled**)
- ❌ 버튼 3개를 가로로 배치 (정답: **세로만** 가능)
- ❌ 버튼 3개 순서를 Ghost-Outlined-Filled로 (정답: **Filled-Outlined-Ghost**)

### **Button 스타일**:
- ❌ Light Filled를 bg-[#01d5df]로 (정답: **#00cbd5**)
- ❌ Dark Filled를 text-white로 (정답: **text-black**)
- ❌ Light Outlined border를 10% opacity로 (정답: **20%**)
- ❌ Dark Outlined border를 10% opacity로 (정답: **20%**)
- ❌ Ghost를 Bold로 설정 (정답: **Medium** weight)
- ❌ Dark Ghost를 #484848로 설정 (정답: **#bbbbbb**)

### **Button 크기**:
- ❌ 버튼 높이를 40px로 설정 (정답: **44px** Large)
- ❌ DialogButtons 너비를 300px로 설정 (정답: **280px**)
- ❌ 세로 버튼을 가변 너비로 (정답: **280px 고정**)
- ❌ 가로 버튼을 고정 너비로 (정답: **basis-0 grow**)
