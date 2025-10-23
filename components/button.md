# Button (버튼)

**시스템 구조** (Import 코드 기준):
```
[Leading Icon] ←4px→ [Text] ←6px/4px→ [Trailing Icon + Number]
    선택적              필수            선택적
```

---

## Size 시스템 (6가지)

### **1. XLarge (52px)**:
- **높이**: `max-h-[52px] min-h-[52px]`
- **패딩**: `px-[24px] py-0` → **좌우 24px, 상하 0** ⭐
- **Radius**: `rounded-[8px]`
- **Leading Icon**: 
  - 크기: `20x20`
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `17px Bold`
  - Line-height: `23px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[6px] pr-0` ⭐
  - Icon: `8x16`
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]` (Icon ↔ Number)
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **6px**

### **2. Large (44px)**:
- **높이**: `max-h-[44px] min-h-[44px]`
- **패딩**: `px-[20px] py-0` → **좌우 20px, 상하 0** ⭐
- **Radius**: `rounded-[8px]`
- **Leading Icon**: 
  - 크기: `20x20`
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `16px Bold`
  - Line-height: `22px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[6px] pr-0`
  - Icon: `8x16`
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]`
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **6px**

### **3. Medium (40px)**:
- **높이**: `max-h-[40px] min-h-[40px]`
- **패딩**: `px-[16px] py-0` → **좌우 16px, 상하 0** ⭐
- **Radius**: `rounded-[8px]`
- **Leading Icon**: 
  - 크기: `16x16` ⭐ (20px → 16px로 감소)
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `16px Bold`
  - Line-height: `22px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[6px] pr-0`
  - Icon: `6x12` ⭐ (8x16 → 6x12로 감소)
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]`
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **6px**

### **4. Small (36px)**:
- **높이**: `max-h-[36px] min-h-[36px]`
- **패딩**: `px-[16px] py-0` → **좌우 16px** (Medium과 동일!) ⭐
- **Radius**: `rounded-[8px]`
- **Leading Icon**: 
  - 크기: `16x16`
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `15px Bold` ⭐
  - Line-height: `21px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[6px] pr-0`
  - Icon: `6x12`
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]`
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **6px**

### **5. XSmall (32px)**:
- **높이**: `max-h-[32px] min-h-[32px]`
- **패딩**: `px-[12px] py-0` → **좌우 12px, 상하 0** ⭐
- **Radius**: `rounded-[8px]`
- **Leading Icon**: 
  - 크기: `16x16`
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `14px Bold` ⭐
  - Line-height: `18px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[4px] pr-0` ⭐ (6px → **4px**로 감소)
  - Icon: `6x12`
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]`
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **4px** ⭐ (6px → 4px로 감소)

### **6. XXSmall (24px)**:
- **높이**: `max-h-[24px] min-h-[24px]`
- **패딩**: `px-[8px] py-0` → **좌우 8px, 상하 0** ⭐
- **Radius**: `rounded-[6px]` ⭐ (8px → **6px**로 감소)
- **Leading Icon**: 
  - 크기: `12x12` ⭐ (16px → 12px로 감소)
  - 패딩: `pl-0 pr-[4px]`
- **Text**: 
  - 크기: `12px Bold` ⭐
  - Line-height: `16px` (WeGothicSans)
- **Trailing**:
  - 패딩: `pl-[4px] pr-0`
  - Icon: `5x10` ⭐ (6x12 → 5x10으로 감소)
  - Number: `12px Bold`, `16px` line-height
  - 내부 간격: `gap-[4px]`
- **내부 간격**:
  - Leading → Text: **4px**
  - Text → Trailing: **4px**

---

## 패딩 규칙 요약

| Size | 높이 | 좌우 패딩 | 상하 패딩 | Radius | Leading 패딩 | Trailing 패딩 | Text→Trailing 간격 |
|------|------|-----------|-----------|--------|--------------|---------------|-------------------|
| XLarge | 52px | **24px** | 0 | 8px | pr-[4px] | pl-[6px] | **6px** |
| Large | 44px | **20px** | 0 | 8px | pr-[4px] | pl-[6px] | **6px** |
| Medium | 40px | **16px** | 0 | 8px | pr-[4px] | pl-[6px] | **6px** |
| Small | 36px | **16px** | 0 | 8px | pr-[4px] | pl-[6px] | **6px** |
| XSmall | 32px | **12px** | 0 | 8px | pr-[4px] | pl-[4px] ⭐ | **4px** ⭐ |
| XXSmall | 24px | **8px** | 0 | **6px** ⭐ | pr-[4px] | pl-[4px] | **4px** |

---

## Icon 크기 규칙

| Size | Leading Icon | Trailing Icon |
|------|--------------|---------------|
| XLarge | **20×20** | **8×16** |
| Large | **20×20** | **8×16** |
| Medium | **16×16** ⭐ | **6×12** ⭐ |
| Small | **16×16** | **6×12** |
| XSmall | **16×16** | **6×12** |
| XXSmall | **12×12** ⭐ | **5×10** ⭐ |

---

## Text 크기 규칙

| Size | Text 크기 | Line-height |
|------|-----------|-------------|
| XLarge | **17px Bold** | 23px |
| Large | **16px Bold** | 22px |
| Medium | **16px Bold** | 22px |
| Small | **15px Bold** ⭐ | 21px |
| XSmall | **14px Bold** ⭐ | 18px |
| XXSmall | **12px Bold** ⭐ | 16px |

**Trailing Number (고정)**:
- **모든 사이즈**: `12px Bold`, `16px` line-height
- **내부 간격**: `gap-[4px]` (Icon ↔ Number)

**Icon-Only Button** (원형):
- **허용**: `52×52` (Icon 20px 사용)
- **금지**: `40×40`, `36×36` (Don't Use로 표시됨)

---

## Type 시스템 (5가지)

### **1. Filled Button** (기본):
- **배경**: `bg-[#00cbd5]` (Primary - 민트색) ⭐
- **텍스트**: `text-white`
- **Border**: 없음
- **Font**: **Bold** (WeGothicSans)
- **용도**: 주요 액션, 기본 작업 버튼

### **2. Outlined Button (Color)**:
- **배경**: 투명 (없음)
- **Border**: `border border-[#00cbd5] border-solid` ⭐
- **텍스트**: `text-[#00cbd5]` (Primary 민트색)
- **Font**: **Bold** (WeGothicSans)
- **용도**: 보조 액션, Filled 버튼과 함께 사용

### **3. Outlined Button (Gray)**:
- **배경**: 투명 (없음)
- **Border**: `border border-[rgba(0,0,0,0.2)] border-solid` → **20% 검은색** ⭐
- **텍스트**: `text-black`
- **Font**: **Bold** (WeGothicSans)
- **용도**: 중립적 액션, 취소 버튼

### **4. Ghost Button**:
- **배경**: `bg-[rgba(255,255,255,0)]` (완전 투명) ⭐
- **Border**: 없음
- **텍스트**: `text-[#484848]` (회색) ⭐
- **Font**: **Medium** ⭐ (Bold 아님! 중요)
- **용도**: 최소한의 강조, 텍스트 버튼
- **특징**: 배경/테두리 없이 텍스트만 표시

### **5. Icon Button**:
- **크기**: `52x52` 고정 (`max-h-[52px] max-w-[52px] min-h-[52px] min-w-[52px]`)
- **배경**: `bg-[#00cbd5]` (Primary - 민트색)
- **Icon**: `20x20` (white)
- **Radius**: `rounded-[8px]`
- **용도**: 아이콘만으로 액션 표현
- **제한**: **40px, 36px는 Don't Use** ⭐

---

## Shape 시스템 (2가지)

### **Rectangle** (기본):
- **Radius**: `rounded-[8px]` (XXSmall은 `rounded-[6px]`)
- **용도**: 일반적인 모든 버튼

### **Round** (Pill):
- **Radius**: `rounded-[100px]` → **완전히 둥근 형태** ⭐
- **용도**: 특수 케이스 (Membership, Artist Shop 등)
- **특징**: shadow 효과 자주 사용 (`shadow-[0px_2px_20px_-2px_rgba(0,0,0,0.08)]`)
- **Border**: 
  - 흰 배경: `border-[rgba(0,0,0,0.1)]` (10% 검은색)
  - 색상 배경: border 없음

---

## Color 시스템

### **Primary Color** (Default):
- **색상**: `#00cbd5` (민트색)
- **토큰**: `system/color/button/...`
- **인정**: ✅ **WDS 버튼** ⭐
- **용도**: 기본 버튼 색상

### **Outlined Gray**:
- **Border**: `rgba(0,0,0,0.2)` (20% 검은색)
- **Text**: `#484848` 또는 `black`
- **인정**: ✅ **WDS 버튼**
- **용도**: 중립적 액션

### **Community Color** (Custom):
- **예시**: `#0a84ff` (파란색), 기타 커뮤니티 색상
- **토큰**: `Community/blue/2` 등
- **인정**: ❌ **WDS 버튼 X** ⭐
- **제약**: 공통 Foundation만 활용 (Padding, Radius, Typography 등)
- **용도**: 커뮤니티별 특화 버튼
- **참고**: [커뮤니티 컬러 보기](https://www.figma.com/design/DWEduE6GfxYMlyxKPNJ8jA?node-id=25259-39306)

---

## 배치 규칙 (Horizontal Type)

- **기본 작업 버튼**: 우측에 배치 (예: 확인, 저장)
- **보조 작업 버튼**: 좌측에 배치 (예: 취소)

---

## 공통 규칙

- **상하 패딩**: 모든 버튼 `py-0` (상하 패딩 없음) ⭐
- **Leading → Text 간격**: **4px 고정** (모든 사이즈)
- **Trailing 내부 간격**: **4px 고정** (Icon ↔ Number)
- **정렬**: `flex items-center justify-center`

---

## State 시스템 (추가 Import 필요)

- Enabled (기본)
- Pressed (눌림)
- Loading (로딩 중)
- Disabled (비활성)

---

## 검증 질문

### **Size & Padding**:
- [ ] 높이가 6가지 Size 중 하나인가? (52/44/40/36/32/24)
- [ ] 좌우 패딩이 Size에 맞는가? (24/20/16/16/12/8)
- [ ] **상하 패딩이 0인가?** (py-0) ⭐
- [ ] Small과 Medium의 좌우 패딩이 동일한가? (16px)

### **Shape & Radius**:
- [ ] Shape이 Rectangle 또는 Round인가?
- [ ] Rectangle일 때 radius가 올바른가? (8px 또는 6px for XXSmall)
- [ ] Round일 때 radius가 100px인가?

### **Type**:
- [ ] Type이 5가지 중 하나인가? (Filled/Outlined-color/Outlined-gray/Ghost/Icon)
- [ ] **Filled**: bg-[#00cbd5], text-white, border 없음인가?
- [ ] **Outlined(Color)**: border-[#00cbd5], text-[#00cbd5], bg 없음인가?
- [ ] **Outlined(Gray)**: border-[rgba(0,0,0,0.2)], text-black, bg 없음인가?
- [ ] **Ghost**: bg 투명, border 없음, text-[#484848], **Medium weight**인가? ⭐
- [ ] **Icon Button**: 52x52, bg-[#00cbd5], icon 20px인가?

### **Color**:
- [ ] Primary Color(#00cbd5)를 사용하는가?
- [ ] 커뮤니티 컬러를 사용한다면 **WDS 버튼이 아님**을 인지하는가?
- [ ] 커뮤니티 컬러 사용 시 Foundation 규칙을 따르는가?

### **Icon & Text**:
- [ ] Leading Icon 크기가 Size에 맞는가? (20/20/16/16/16/12)
- [ ] Text 크기가 Size에 맞는가? (17/16/16/15/14/12)
- [ ] Text weight가 Type에 맞는가? (Filled/Outlined: Bold, Ghost: Medium)
- [ ] Trailing Icon 크기가 Size에 맞는가? (8x16/8x16/6x12/6x12/6x12/5x10)
- [ ] Number 텍스트가 12px Bold인가?

### **간격**:
- [ ] Leading → Text 간격이 4px인가?
- [ ] Text → Trailing 간격이 맞는가? (XLarge~Small: 6px, XSmall~XXSmall: 4px)
- [ ] Trailing 내부 간격이 4px인가? (Icon ↔ Number)

### **제약**:
- [ ] Icon-only 버튼을 40px/36px로 만들지 않았는가? (Don't Use)
- [ ] Horizontal Type에서 기본 작업을 우측, 보조 작업을 좌측에 배치했는가?

---

## 자주 하는 실수

### **패딩 관련**:
- ❌ 상하 패딩을 추가 (정답: **py-0**, 상하 패딩 없음)
- ❌ Small의 패딩을 12px로 설정 (정답: **16px**, Medium과 동일)
- ❌ XLarge/Large/Medium/Small의 좌우 패딩을 같게 설정 (정답: **각각 다름**)

### **Icon 크기**:
- ❌ Medium에서 Leading Icon을 20px로 설정 (정답: **16px**)
- ❌ XXSmall에서 Leading Icon을 16px로 설정 (정답: **12px**)
- ❌ Medium에서 Trailing Icon을 8x16으로 설정 (정답: **6x12**)

### **간격**:
- ❌ Text → Trailing 간격을 모든 사이즈에서 6px로 설정 (정답: XSmall부터 **4px**)
- ❌ Leading → Text 간격을 다르게 설정 (정답: **4px 고정**)
- ❌ Trailing 내부 간격을 2px로 설정 (정답: **4px 고정**)

### **Shape & Radius**:
- ❌ Rectangle XXSmall에서 radius를 8px로 설정 (정답: **6px**)
- ❌ Rectangle XSmall에서 radius를 6px로 설정 (정답: **8px**)
- ❌ Round Shape에서 radius를 8px로 설정 (정답: **100px**)

### **Type**:
- ❌ Filled에 border 추가 (정답: **border 없음**)
- ❌ Outlined(Color)에 배경색 추가 (정답: **bg 투명**)
- ❌ Outlined(Gray) border를 10% opacity로 설정 (정답: **20%** opacity)
- ❌ Ghost에 border 추가 (정답: **border 없음**)
- ❌ Ghost 텍스트를 Bold로 설정 (정답: **Medium** weight) ⭐
- ❌ Ghost 텍스트를 black으로 설정 (정답: **#484848** 회색)

### **Color**:
- ❌ 커뮤니티 컬러 버튼을 WDS 버튼으로 표시 (정답: **WDS 버튼 X**)
- ❌ 커뮤니티 컬러 사용 시 임의 패딩/radius 적용 (정답: **Foundation 규칙 준수**)

### **Text**:
- ❌ Large와 Medium의 텍스트 크기를 다르게 설정 (정답: **둘 다 16px**)
- ❌ Small의 텍스트를 16px로 설정 (정답: **15px**)
- ❌ Number 텍스트를 10px로 설정 (정답: **12px Bold 고정**)

### **Icon-Only**:
- ❌ 40px, 36px Icon 버튼 사용 (정답: **Don't Use**, 52px만 허용)

### **배치**:
- ❌ Horizontal Type에서 기본 작업을 좌측에 배치 (정답: **우측**)
- ❌ Horizontal Type에서 보조 작업을 우측에 배치 (정답: **좌측**)
