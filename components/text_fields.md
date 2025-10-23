# Text Fields (텍스트 필드)

**시스템 구조** (Import 코드 기준):
```
[Title] (선택적)
  ↓ 6px gap
[TextField 44px]
  ↓ 6px gap
[Guide Message] (선택적)
```

---

## Type 시스템 (2가지)

### **1. Single Line** (기본):
- **용도**: 한 줄 텍스트 입력 (이름, 이메일, 검색 등)
- **높이**: `44px` 고정 ⭐
- **Radius**: `rounded-[8px]` (일반) / `rounded-[24px]` (Chat)
- **구조**: Title → TextField → Guide Message

### **2. Multiple Lines** (Textarea):
- **용도**: 여러 줄 텍스트 입력 (댓글, 메시지, 주소 등)
- **높이**: Flexible ⭐ (최소 `44px`, 콘텐츠에 따라 증가)
- **Radius**: `rounded-[8px]`
- **Scrollbar**: 콘텐츠가 높이를 초과할 때 표시

---

## Title (라벨) - 선택적

### **구조**:
```
[Text + Badge Dot] ←8px→ [글자수 카운터]
```

### **Title Text**:
- **크기**: `14px Regular` ⭐
- **Line-height**: `18px`
- **Font**: WeGothicSans:Regular
- **색상**:
  - Light Mode: `#666666` (기본) / `#fe5b58` (Error)
  - Dark Mode: `#999999`
- **패딩**: `px-[4px] py-0` → **좌우 4px, 상하 0**

### **Badge Dot** (필수 표시):
- **크기**: `4x4` (`size-[4px]`)
- **색상**: `bg-[#fe5b58]` → **빨간색 고정** ⭐
- **Radius**: `rounded-[100px]` (완전한 원)
- **간격**: `gap-[2px]` (Text ↔ Badge Dot)

### **글자수 카운터**:
- **크기**: `14px Regular`
- **Line-height**: `18px`
- **색상**: 
  - Light Mode: `#aeaeae` (기본) / `#cccccc` (Error placeholder)
  - Dark Mode: `#555555`
- **형식**: `12/200` (현재 글자수/최대 글자수)
- **정렬**: `text-right` (우측 정렬)

---

## TextField (입력 영역)

### **기본 설정**:
- **높이**: 
  - Single Line: `44px` 고정 (`h-[44px]`)
  - Multiple Lines: Flexible (최소 `44px`)
- **Radius**: `rounded-[8px]` (일반) / `rounded-[24px]` (Chat)
- **패딩**: `p-[12px]` → **12px 전체** ⭐
- **내부 간격**: `gap-[8px]` (요소 간)

### **구조**:
```
[Select/Leading] ←8px→ [Input Area] ←8px→ [Actions]
     선택적              필수          선택적
```

---

## Input Area (입력 영역)

### **Placeholder**:
- **크기**: `16px Regular` ⭐
- **Line-height**: `22px`
- **Font**: WeGothicSans:Regular
- **색상**:
  - Light Mode: `#cccccc` ⭐
  - Dark Mode: `#3e3e3e`

### **Typing (입력 텍스트)**:
- **크기**: `16px Regular`
- **Line-height**: `22px`
- **색상**:
  - Light Mode: `black`
  - Dark Mode: `white`

### **Caret (커서)**:
- **크기**: `1.5px` width, `14px` height ⭐
- **색상**:
  - Light Mode: `black`
  - Dark Mode: `white`
- **Radius**: `rounded-[100px]`

---

## State 시스템 (5가��)

### **1. Default (기본 - Placeholder)**:
- **Border**: `border border-[#dcdee4] border-solid` ⭐
- **Background**: 투명
- **Text**: `#cccccc` (placeholder)
- **Title**: `#666666`
- **Guide Message**: `#8e8e8e`

### **2. Disabled (비활성)**:
- **Border**: `border border-[#dcdee4] border-solid`
- **Background**: `bg-[#f2f3f7]` ⭐ (연한 회색)
- **Text**: `#8e8e8e` (placeholder)
- **Title**: `#666666`
- **Guide Message**: `#8e8e8e`
- **특징**: 사용자 입력 불가

### **3. Focused (포커스)**:
- **Border**: `border border-[#aeb1b8] border-solid` ⭐
- **Background**: 투명
- **Text**: `black` (입력 중)
- **Title**: `#666666`
- **Guide Message**: `#8e8e8e`
- **Caret**: 표시됨
- **Close Button**: 표시됨 (텍스트가 있을 때)

### **4. Error (오류)**:
- **Border**: `border border-[#fe5b58] border-solid` ⭐ (빨간색)
- **Background**: 투명
- **Text**: `#cccccc` (placeholder) / `black` (입력 중)
- **Title**: `#fe5b58` ⭐ (빨간색)
- **Guide Message**: `#fe5b58` ⭐ (빨간색)
- **용도**: 유효성 검사 실패, 필수 입력 누락

### **5. Success (성공)**:
- **Border**: `border border-[#01d5df] border-solid` (Primary 색상)
- **Background**: 투명
- **Text**: `black`
- **Title**: `#666666`
- **Guide Message**: `#01d5df`
- **용도**: 유효성 검사 통과

---

## Actions (액션 버튼들)

### **Close Button** (X 버튼):
- **크기**: `20x20` 외부, `18x18` 내부 ⭐
- **배경**: `bg-[rgba(0,0,0,0.2)]` (20% 검은색)
- **Icon**: `10x10` X 아이콘 (white)
- **Radius**: `rounded-[100px]` (완전한 원)
- **표시 조건**: 텍스트가 입력된 상태에서만
- **간격**: `gap-[8px]` (Input Area ↔ Close Button)

### **Hidden Typing** (비밀번호 토글):
- **크기**: `24x24`
- **Icon**: 눈 아이콘 (감춤/보임 토글)
- **색상**: `#cccccc`
- **용도**: 비밀번호 입력 필드

### **Text Button** (텍스트 버튼):
- **크기**: `24px` 높이
- **패딩**: `px-[8px] py-0`
- **Radius**: `rounded-[6px]`
- **Border**: `border border-[rgba(0,0,0,0.2)] border-solid`
- **Text**: `12px Bold`, `#3e3e3e`
- **예시**: "Button", "인증"

---

## Guide Message (안내 메시지) - 선택적

- **크기**: `13px Regular` ⭐
- **Line-height**: `17px`
- **Font**: WeGothicSans:Regular
- **색상**:
  - Light Mode: `#8e8e8e` (기본) / `#fe5b58` (Error) / `#01d5df` (Success)
  - Dark Mode: `#777777`
- **패딩**: `px-[4px] py-0` → **좌우 4px, 상하 0**
- **용도**: 입력 규칙 안내, 오류 메시지, 성공 메시지

---

## Multiple Lines 특수 사항

### **Scrollbar**:
- **위치**: `absolute right-0`
- **크기**: `10px` width ⭐
- **패딩**: `px-[2px] py-[4px]`
- **Thumb**:
  - 크기: `60px` 높이 (예시, 콘텐츠에 ��라 변함)
  - 배경: `bg-[rgba(0,0,0,0.2)]` (Light) / `bg-[rgba(255,255,255,0.2)]` (Dark)
  - Radius: `rounded-[3px]`

### **높이 계산**:
- **최소**: `44px` (Single Line과 동일)
- **최대**: 콘텐츠에 따라 자동 증가
- **Overflow**: `overflow-clip` (스크롤바로 처리)

---

## Special Type: Chat (채팅)

### **특징**:
- **Radius**: `rounded-[24px]` ⭐ (완전히 둥근 Pill 형태)
- **패딩**: `px-[16px] py-[12px]` → **좌우 16px, 상하 12px** ⭐
- **Icon Button**: 하트 아이콘 포함 (40px)
- **Home Indicator**: 모바일에서 하단 바 포함

---

## Dark Mode (Fixed Background)

### **색상 변경**:
- **Border**:
  - Default: `#3e3e3e` ⭐
  - Focused: `#555555` ⭐
  - Error: `#fe5b58` (동일)
- **Background**:
  - Default: 투명
  - Disabled: `bg-[#1f1f1f]` ⭐ (어두운 회색)
- **Text**:
  - Placeholder: `#3e3e3e` / `#555555`
  - Typing: `white` ⭐
- **Title**: `#999999` ⭐
- **Guide Message**: `#777777` ⭐
- **Caret**: `white`
- **Close Button**: `bg-[rgba(255,255,255,0.2)]` (20% 흰색)

---

## Select (국가 코드 선택) - 선택적

### **구조**:
```
[+82] ←16px→ [Icon] ←8px→ [Divider]
```

### **Code Text**:
- **크기**: `16px Regular`
- **Line-height**: `22px`
- **색상**: `black`

### **Icon** (드롭다운):
- **크기**: `16x16`
- **색상**: `black`

### **Divider** (구분선):
- **크기**: `1px` width, `18px` height
- **색상**: `#dcdee4`
- **간격**: `gap-[8px]` (Code ↔ Divider)

---

## 간격 시스템

### **외부 간격** (요소 간):
- Title ↔ TextField: `gap-[6px]` ⭐
- TextField ↔ Guide Message: `gap-[6px]` ⭐

### **내부 간격** (TextField 안):
- Select/Leading ↔ Input: `gap-[8px]` ⭐
- Input ↔ Actions: `gap-[8px]` ⭐
- Title Text ↔ Badge Dot: `gap-[2px]`

### **패딩**:
- TextField: `p-[12px]` → **12px 전체** ⭐
- Title: `px-[4px] py-0` → **좌우 4px**
- Guide Message: `px-[4px] py-0` → **좌우 4px**
- Chat Type: `px-[16px] py-[12px]` → **좌우 16px, 상하 12px** ⭐

---

## 고정 크기

| 요소 | 크기 | 비고 |
|------|------|------|
| **TextField 높이** | **44px** ⭐ | Single Line 고정 |
| **Multiple Line 최소** | **44px** | Flexible |
| **Radius** | **8px** | 일반 |
| **Chat Radius** | **24px** | Pill 형태 |
| **Padding** | **12px** | 전체 |
| **Chat Padding** | **16px/12px** | 좌우/상하 |
| **Title 텍스트** | **14px** | Regular |
| **Input 텍스트** | **16px** | Regular |
| **Guide 텍스트** | **13px** | Regular |
| **Caret** | **1.5px** | width |
| **Badge Dot** | **4px** | 크기 |
| **Close Button** | **20px** | 외부 |
| **Scrollbar** | **10px** | width |

---

## 검증 질문

### **기본 구조**:
- [ ] Type이 Single Line 또는 Multiple Lines인가?
- [ ] 높이가 44px(Single) 또는 flexible(Multiple)인가?
- [ ] Radius가 8px(일반) 또는 24px(Chat)인가?
- [ ] 패딩이 12px 전체인가?

### **Title (있는 경우)**:
- [ ] Title 텍스트가 14px Regular, 18px line-height인가?
- [ ] Badge Dot이 4px, #fe5b58 빨간색인가?
- [ ] 글자수 카운터가 14px, #aeaeae인가?
- [ ] Title-TextField 간격이 6px인가?

### **State**:
- [ ] Default border가 #dcdee4인가?
- [ ] Disabled background가 #f2f3f7인가?
- [ ] Focused border가 #aeb1b8인가?
- [ ] Error border와 Title이 #fe5b58 빨간색인가?
- [ ] Success border가 #01d5df인가?

### **Input Area**:
- [ ] Placeholder가 16px Regular, #cccccc인가?
- [ ] Typing 텍스트가 16px Regular, black인가?
- [ ] Caret이 1.5px width, 14px height인가?

### **Actions (있는 경우)**:
- [ ] Close Button이 20px, bg rgba(0,0,0,0.2)인가?
- [ ] Icon이 10px인가?
- [ ] 내부 간격이 8px인가?

### **Guide Message (있는 경우)**:
- [ ] 텍���트가 13px Regular, 17px line-height인가?
- [ ] 색상이 State에 맞는가? (#8e8e8e / #fe5b58 / #01d5df)
- [ ] TextField-Guide 간격이 6px인가?

### **간격**:
- [ ] Title-TextField 간격이 6px인가?
- [ ] TextField-Guide 간격이 6px인가?
- [ ] 내부 요소 간 간격이 8px인가?
- [ ] Title Text-Badge Dot 간격이 2px인가?

### **Dark Mode (있는 경우)**:
- [ ] Default border가 #3e3e3e인가?
- [ ] Focused border가 #555555인가?
- [ ] Disabled background가 #1f1f1f인가?
- [ ] Title이 #999999인가?
- [ ] Guide Message가 #777777인가?
- [ ] Typing 텍스트가 white인가?

---

## 자주 하는 실수

### **기본 크기**:
- ❌ Single Line 높이를 40px로 설정 (정답: **44px**)
- ❌ Radius를 6px로 설정 (정답: **8px** 일반, **24px** Chat)
- ❌ 패딩을 16px로 설정 (정답: **12px** 전체)

### **Title**:
- ❌ Title을 16px로 설정 (정답: **14px** Regular)
- ❌ Badge Dot을 다른 색상으로 (정답: **#fe5b58** 빨간색 고정)
- ❌ Badge Dot 크기를 6px로 (정답: **4px**)
- ❌ Title-TextField 간격을 8px로 (정답: **6px**)

### **State - Border**:
- ❌ Default border를 #aeb1b8로 (정답: **#dcdee4**)
- ❌ Focused border를 #dcdee4로 (정답: **#aeb1b8**)
- ❌ Error border를 #ff0000로 (정답: **#fe5b58**)

### **State - Background**:
- ❌ Default에 배경 추가 (정답: **투���**)
- ❌ Disabled background를 white로 (정답: **#f2f3f7**)

### **Input Area**:
- ❌ Placeholder를 14px로 (정답: **16px** Regular)
- ❌ Placeholder 색상을 #999999로 (정답: **#cccccc**)
- ❌ Caret을 2px로 (정답: **1.5px** width)

### **간격**:
- ❌ 내부 요소 간 간격을 4px로 (정답: **8px**)
- ❌ Title-TextField 간격을 8px로 (정답: **6px**)
- ❌ TextField-Guide 간격을 4px로 (정답: **6px**)

### **Guide Message**:
- ❌ Guide를 14px로 (정답: **13px** Regular)
- ❌ Guide 색상을 #666666로 (정답: **#8e8e8e** 기본, State에 따라 변경)

### **Close Button**:
- ❌ Close Button을 18px로 (정답: **20px** 외부, **18px** 내부)
- ❌ 배경을 30% opacity로 (정답: **20%** rgba(0,0,0,0.2))
- ❌ 항상 표시 (정답: **텍스트가 있을 때만** 표시)

### **Dark Mode**:
- ❌ Dark Default border를 #555555로 (정답: **#3e3e3e**)
- ❌ Dark Focused border를 #3e3e3e로 (정답: **#555555**)
- ❌ Dark Disabled background를 black으로 (정답: **#1f1f1f**)
- ❌ Dark Title을 #666666로 (정답: **#999999**)
- ❌ Dark Typing을 black으로 (정답: **white**)

### **Multiple Lines**:
- ❌ Scrollbar width를 8px로 (정답: **10px**)
- ❌ Thumb radius를 5px로 (정답: **3px**)
- ❌ 최소 높이를 지정 안 함 (정답: **44px** 최소)

### **Chat Type**:
- ❌ Chat Radius를 8px로 (정답: **24px** Pill)
- ❌ Chat 패딩을 12px 전체로 (정답: **16px/12px** 좌우/상하)
