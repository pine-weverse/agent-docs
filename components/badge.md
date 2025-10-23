# Badge (배지)

**시스템 구조** (Import 코드 기준):
```
Type 1: Badge Number (숫자 표시)
Type 2: Badge Dot (점 표시) - 스펙 대기 중
```

---

## Badge Number (숫자 배지)

### **용도**:
- 읽지 않은 알림 개수 표시
- 새로운 콘텐츠 개수 표시 ("999+")
- "New" 표시 (단일 문자 "N")

---

## Size 시스템 (3가지)

### **1. Large** (숫자 표시 - "999+"):
- **높이**: `16px` (자동) ⭐
  - 계산: 12px 텍스트 + 16px line-height
- **패딩**: `px-[4px] py-0` → **좌우 4px, 상하 0** ⭐
- **최소 너비**: 자동 (콘텐츠에 따라 증가)
- **폰트**: 
  - 크기: `12px Medium` ⭐
  - Line-height: `16px`
  - Font: WeGothicSans:Medium
  - 색상: `white`
- **Radius**: `rounded-[20px]` → **Pill 형태** ⭐
- **배경**: `bg-[#fe5b58]` → **빨간색 고정** ⭐
- **내용**: "1", "99", "999+", "NEW" 등

### **2. Medium** (단일 문자 - "N"):
- **높이**: `14~16px` (자동)
  - 계산: 12px 텍스트 + 1px 상하 패딩 + 16px line-height
- **패딩**: `px-[3.5px] py-px` → **좌우 3.5px, 상하 1px** ⭐
- **최소 너비**: 자동 (약 14px)
- **폰트**: 
  - 크기: `12px Medium`
  - Line-height: `16px`
  - Font: WeGothicSans:Medium
  - 색상: `white`
- **Radius**: `rounded-[20px]`
- **배경**: `bg-[#fe5b58]`
- **내용**: "N", "★" 등 단일 문자

### **3. Small** (최소 크기 - "N" with border):
- **크기**: `12×12px` (고정) ⭐ (`size-full` 또는 `min-w-[12px]`)
- **패딩**: `px-[4.5px] pt-[1.5px] pb-[2.5px]` → **비대칭 패딩** ⭐
- **Border**: `border border-white border-solid` → **1px 흰색** ⭐
- **폰트**: 
  - 크기: `6px Heavy` ⭐ (매우 작음!)
  - Line-height: `normal`
  - Font: **SF_Pro_Text:Heavy** ⭐ (WeGothicSans 아님!)
  - 색상: `white`
- **Radius**: `rounded-[20px]`
- **배경**: `bg-[#fe5b58]`
- **내용**: "N" (단일 문자만)
- **용도**: 공지사항 모듈 등 매우 작은 인디케이터

---

## 고정 스타일

### **색상** (모든 Size 공통):
- **배경**: `#fe5b58` (빨간색) → **변경 불가** ⭐
- **텍스트**: `white` → **변경 불가**
- **Border**: `white` (Small만 해당)

### **Shape** (모든 Size 공통):
- **Radius**: `rounded-[20px]` → **Pill 형태** ⭐
- **정렬**: `flex items-center justify-center` (중앙 정렬)

---

## Size별 비교표

| Size | 높이 | 패딩 (좌우/상하) | 폰트 | 폰트 크기 | Line-height | Border | 용도 |
|------|------|------------------|------|-----------|-------------|--------|------|
| **Large** | 16px | 4px / 0px | WeGothicSans Medium | **12px** | 16px | 없음 | "999+" 숫자 표시 |
| **Medium** | 14-16px | 3.5px / 1px | WeGothicSans Medium | **12px** | 16px | 없음 | "N" 단일 문자 |
| **Small** | **12px** | 4.5px / 1.5-2.5px | **SF_Pro_Text Heavy** ⭐ | **6px** ⭐ | normal | **1px white** | 매우 작은 "N" |

---

## 사용 규칙

### **텍스트 콘텐츠**:
- **Large**: 숫자 (1~999+), 짧은 텍스트 (NEW, HOT 등)
- **Medium**: 단일 문자 (N, ★, ! 등)
- **Small**: 단일 문자 "N"만 (공간 제약)

### **999+ 규칙**:
- 999 이하: 숫자 그대로 표시 ("1", "99", "999")
- 1000 이상: "999+" 표시 (고정)

### **숫자 정렬**:
- `text-center` (중앙 정렬)
- `text-nowrap` (줄바꿈 없음)

---

## 배치 위치

### **Avatar 위 배치**:
```
Avatar (40px) 기준:
- 위치: absolute, top-0, right-0
- Badge 오프셋: -2px (Avatar 경계 약간 넘어감)
```

### **Icon 위 배치**:
```
Icon Button (24px) 기준:
- 위치: absolute, top-0, right-0
- Badge 오프셋: -4px
```

### **List Item Trailing**:
```
List Item 우측 영역에 배치
- 간격: gap-[12px] (Content ↔ Badge)
```

---

## Dark Mode (Fixed Background)

### **색상 변경 없음** ⭐:
- **배경**: `#fe5b58` (동일)
- **텍스트**: `white` (동일)
- **Border**: `white` (동일)
- **이유**: 빨간색 배지는 Light/Dark 모두 동일한 강조색 사용

---

## 접근성 고려사항

### **Small (12px, 6px ��트)**:
- ⚠️ **터치 타겟 최소 기준 미달** (44×44px 권장)
- ✅ **읽기 전용 인디케이터**로만 사용 (클릭 불가)
- ✅ **보조 정보**: 스크린 리더를 위한 `aria-label` 제공 필요
  - 예: `aria-label="새 알림 3개"`

### **Large/Medium**:
- ✅ 12px 폰트는 가독성 확보
- ✅ 충분한 대비 (빨간 배경 + 흰 텍스트)

---

## 검증 질문

### **Size 선택**:
- [ ] Large (16px)를 사용하는가? (999+ 숫자 표시용)
- [ ] Medium (14-16px)를 사용하는가? (N 단일 문자용)
- [ ] Small (12px)를 사용하는가? (매우 작은 인디케이터, border 포함)

### **스타일**:
- [ ] 배경이 #fe5b58 빨간색인가?
- [ ] 텍스트가 white인가?
- [ ] Radius가 20px (Pill 형태)인가?
- [ ] 중앙 정렬이 적용되었는가?

### **패딩**:
- [ ] Large일 때 px-[4px] py-0인가?
- [ ] Medium일 때 px-[3.5px] py-px인가?
- [ ] Small일 때 px-[4.5px] pt-[1.5px] pb-[2.5px]인가?

### **폰트**:
- [ ] Large/Medium은 WeGothicSans:Medium, 12px인가?
- [ ] Small은 SF_Pro_Text:Heavy, 6px인가? ⭐
- [ ] Line-height가 Large/Medium은 16px, Small은 normal인가?

### **Border (Small만)**:
- [ ] Small일 때 1px white border가 있는가?

### **콘텐츠**:
- [ ] 999 초과 시 "999+"로 표시하는가?
- [ ] 텍스트가 중앙 정렬되고 줄바꿈이 없는가?

### **배치**:
- [ ] Avatar/Icon 위에 absolute 배치 시 적절한 오프셋이 있는가?
- [ ] List Item에서 gap-[12px] 간격이 있는가?

### **접근성 (Small 사용 시)**:
- [ ] 읽기 전용 인디케이터로만 사용하는가? (클릭 불가)
- [ ] aria-label이 제공되는가?

---

## 자주 하는 실수

### **Size 혼동**:
- ❌ Large에서 패딩을 6px로 설정 (정답: **4px**)
- ❌ Medium에서 패딩을 4px로 설정 (정답: **3.5px**)
- ❌ Small에서 대칭 패딩 사용 (정답: **비대칭** pt-1.5px, pb-2.5px)

### **폰트**:
- ❌ Small에서 WeGothicSans 사용 (정답: **SF_Pro_Text:Heavy**)
- ❌ Small에서 폰트 크기를 8px로 (정답: **6px**)
- ❌ Large/Medium에서 폰트를 Bold로 (정답: **Medium**)

### **색상**:
- ❌ 배경을 Primary (#00cbd5)로 변경 (정답: **#fe5b58 고정**)
- ❌ Dark 모드에서 색상 변경 (정답: **Light/Dark 동일**)

### **Border**:
- ❌ Large/Medium에 border 추가 (정답: **Small만** 1px white)
- ❌ Small에서 border를 다른 색으로 (정답: **white 고정**)

### **Radius**:
- ❌ Radius를 24px로 설정 (정답: **20px**)
- ❌ Rectangle 형태 사용 (정답: **Pill 형태만** 사용)

### **높이**:
- ❌ Large 높이를 20px로 고정 (정답: **16px 자동**)
- ❌ Small 높이를 16px로 설정 (정답: **12px**)

### **콘텐츠**:
- ❌ 1000 이상 숫���를 "1000"으로 표시 (정답: **999+**)
- ❌ Small에 여러 문자 입력 (정답: **"N" 단일 문자만**)

### **배치**:
- ❌ Avatar 중앙에 배치 (정답: **top-right, 약간 넘어감**)
- ❌ List Item에서 간격 없이 배치 (정답: **gap-[12px]**)

### **접근성**:
- ❌ Small (12px)를 클릭 가능한 버튼으로 사용 (정답: **읽기 전용만**)
- ❌ aria-label 없이 사용 (정답: **스크린 리더용 레이블 필수**)

---

## WDS vs 커스텀 판단

### **✅ WDS Badge Number로 인정**:
- Large (16px, 999+): ✅ 표준 사용
- Medium (14-16px, N): ✅ 표준 사용

### **⚠️ Small (12px)는 특수 케이스**:
- **크기**: 12×12px (매우 작음)
- **폰트**: SF_Pro_Text Heavy, 6px
- **Border**: 1px white
- **용도**: 공지사항 모듈 등 매우 제한적
- **권장**: 가능하면 Medium (14-16px) 사용 권장
- **접근성**: 터치 타겟 기준 미달, 읽기 전용만 사용

---

## Badge Dot (점 배지)

### **용도**:
- 최소한의 알림 표시 (읽지 않은 콘텐츠 있음)
- "New" 인디케이터 (숫자 없이)
- Avatar/Icon/List Item 위 상태 표시
- 공간 제약이 있을 때 Badge Number 대신 사용

---

## Type 시스템 (3가지)

### **1. Default** (Border 없음):
```tsx
<div className="bg-[#fe5b58] rounded-[100px] size-full" />
```

- **Shape**: Circle → `rounded-[100px]` ⭐
- **배경**: `bg-[#fe5b58]` → **빨간색 고정** ⭐
- **크기**: `size-full` → **부모 크기에 맞춤** ⭐
- **Border**: 없음
- **용도**: 기본 알림 인디케이터 (어두운/일반 배경)

### **2. With Border 1px** (얇은 테두리):
```tsx
<div className="bg-[#fe5b58] relative rounded-[100px] size-full">
  <div 
    aria-hidden="true" 
    className="absolute border border-solid border-white inset-0 pointer-events-none rounded-[100px]" 
  />
</div>
```

- **Shape**: Circle → `rounded-[100px]`
- **배경**: `bg-[#fe5b58]` → **빨간색 고정**
- **크기**: `size-full` → **부모 크기에 맞춤**
- **Border**: `border border-solid border-white` ⭐
  - **1px** 흰색 테두리
  - `absolute inset-0` (내부에서 border 렌더링)
  - `pointer-events-none` (이벤트 차단 방지)
  - `aria-hidden="true"` (스크린 리더 제외)
- **용도**: 흰색/밝은 배경, **작은 크기** (6px~8px)

### **3. With Border 2px** (두꺼운 테두리):
```tsx
<div className="bg-[#fe5b58] relative rounded-[100px] size-full">
  <div 
    aria-hidden="true" 
    className="absolute border-2 border-solid border-white inset-0 pointer-events-none rounded-[100px]" 
  />
</div>
```

- **Shape**: Circle → `rounded-[100px]`
- **배경**: `bg-[#fe5b58]` → **빨간색 고정**
- **크기**: `size-full` → **부모 크기에 맞춤**
- **Border**: `border-2 border-solid border-white` ⭐
  - **2px** 흰색 테두리 (더 강조)
  - `absolute inset-0` (내부에서 border 렌더링)
  - `pointer-events-none` (이벤트 차단 방지)
  - `aria-hidden="true"` (스크린 리더 제외)
- **용도**: 흰색/밝은 배경, **큰 크기** (10px~12px), 강조 필요

---

## Size 시스템

### **크기 조절 방식**:
Badge Dot은 `size-full`을 사용하여 **부모 컨테이너 크기**에 맞춥니다.

**일반적인 크기**:
- `2px` → 최소 크기 (아주 작은 인디케이터)
- `4px` → 작은 크기
- `6px` → 기본 크기 ⭐ (가장 많이 사용)
- `8px` → 중간 크기
- `10px` → 큰 크기
- `12px` → 최대 크기

**부모 컨테이너 설정 예시**:
```tsx
{/* 6px Dot */}
<div className="size-[6px]">
  <BadgeDot />
</div>

{/* 12px Dot */}
<div className="size-[12px]">
  <BadgeDot />
</div>
```

### **권장 크기**:
- **Avatar (40px 이상)**: 8px~12px
- **Icon (24px)**: 6px~8px
- **List Item**: 6px
- **공간 제약 큰 경우**: 4px

### **Type별 권장 크기 조합** ⭐:
| 크기 | 권장 Type | 이유 |
|------|----------|------|
| **2px~4px** | Default | Border가 너무 작아서 보이지 않음 |
| **6px~8px** | Default 또는 **Border 1px** | 밝은 배경에서 1px border 적합 |
| **10px~12px** | Default 또는 **Border 2px** | 밝은 배경에서 2px border 강조 |

---

## Type별 비교표

| Type | 배경 | Border | 크기 조절 | 권장 크기 | 용도 | 배경 색상 |
|------|------|--------|----------|----------|------|----------|
| **Default** | #fe5b58 | 없음 | 부모 size | 2px~12px | 기본 인디케이터 | 어두운/일반 배경 |
| **Border 1px** | #fe5b58 | 1px white | 부모 size | **6px~8px** | 밝은 배경 (작은 크기) | 흰색/밝은 배경 |
| **Border 2px** | #fe5b58 | **2px white** | 부모 size | **10px~12px** | 밝은 배경 (큰 크기, 강조) | 흰색/밝은 배경 |

---

## 사용 규칙

### **Type 선택** ⭐:
| 배경 | 크기 | 권장 Type | 이유 |
|------|------|----------|------|
| 어두운/일반 | 모든 크기 | **Default** | Border 불필요, 대비 충분 |
| 밝은/흰색 | 2px~4px | **Default** | Border가 너무 작아 보이지 않음 |
| 밝은/흰색 | 6px~8px | **Border 1px** | 얇은 테두리로 시인성 확보 |
| 밝은/흰색 | 10px~12px | **Border 2px** | 두꺼운 테두리로 강조 |

### **Size 선택**:
- **공간에 따라**: 큰 요소(Avatar) = 큰 Dot, 작은 요소(Icon) = 작은 Dot
- **중요도에 따라**: 중요한 알림 = 큰 Dot, 보조 알림 = 작은 Dot
- **기본값**: 6px ⭐

### **Badge Number vs Badge Dot 선택**:
| 상황 | 권장 | 이유 |
|------|------|------|
| 개수 표시 필요 | Badge Number | "999+" 등 숫자 표시 |
| 개수 불필요 | Badge Dot | 공간 절약, 미니멀 |
| 공간 여유 있음 | Badge Number | 더 많은 정보 제공 |
| 공간 제약 있음 | Badge Dot | 최소 공간 (2px~12px) |
| 중요도 높음 | Badge Number | 숫자로 강조 |
| 중요도 낮음 | Badge Dot | 부드러운 알림 |

---

## 배치 위치

### **Avatar 위 배치**:
```tsx
<div className="relative">
  <Avatar size={40} />
  {/* Badge Dot - top-right에 배치 */}
  <div className="absolute top-0 right-0 size-[8px]">
    <BadgeDot />
  </div>
</div>
```

**오프셋**:
- Avatar 경계에서 약간 넘어가도록 배치
- `top-0 right-0` (경계 기준)
- 필요 시 `-translate-x-[2px] -translate-y-[2px]` 미세 조정

### **Icon 위 배치**:
```tsx
<div className="relative">
  <Icon size={24} />
  {/* Badge Dot - top-right에 배치 */}
  <div className="absolute -top-[2px] -right-[2px] size-[6px]">
    <BadgeDot />
  </div>
</div>
```

### **List Item Trailing**:
```tsx
<ListItem>
  <ListItem.Leading>...</ListItem.Leading>
  <ListItem.Content>...</ListItem.Content>
  <ListItem.Trailing>
    {/* Badge Dot */}
    <div className="size-[6px]">
      <BadgeDot />
    </div>
  </ListItem.Trailing>
</ListItem>
```

---

## 고정 스타일

### **색상** (Type 공통):
- **배경**: `#fe5b58` (빨간색) → **변경 불가** ⭐
- **Border**: `white` (With Border만) → **변경 불가**

### **Shape** (Type 공통):
- **Radius**: `rounded-[100px]` → **Circle 형태** ⭐
- **크기 조절**: `size-full` (부모에 맞춤)

---

## Dark Mode (Fixed Background)

### **색상 변경 없음** ⭐:
- **배경**: `#fe5b58` (동일)
- **Border**: `white` (동일)
- **이유**: 빨간색 배지는 Light/Dark 모두 동일한 강조색 사용

**With Border Type (1px/2px 모두)**:
- Dark 모드에서도 white border 유지 (1px 또는 2px)
- 시인성 확보를 위해 Light/Dark 동일

---

## 접근성 고려사항

### **최소 크기 (2px~6px)**:
- ⚠️ **터치 타겟 최소 기준 미달** (44×44px 권장)
- ✅ **읽기 전용 인디케이터**로만 사용 (클릭 불가)
- ✅ **보조 정보**: 스크린 리더를 위한 설명 필요
  - 부모 요소에 `aria-label` 제공
  - 예: `aria-label="새 알림 있음"`

### **시인성**:
- **Default**: 어두운 배경에서 잘 보임
- **Border 1px**: 밝은 배경, 작은 크기(6px~8px)에서 시인성 확보
- **Border 2px**: 밝은 배경, 큰 크기(10px~12px)에서 강조 및 시인성 확보
- **권장**: 배경색 대비 5:1 이상 (자동 충족됨)

### **Dot 자체 접근성**:
```tsx
{/* ✅ 권장: 부모에 aria-label */}
<div aria-label="새 알림 있음" className="relative">
  <Icon />
  <div className="absolute -top-[2px] -right-[2px] size-[6px]">
    <BadgeDot />
  </div>
</div>

{/* ❌ 잘못된 예: Dot에 aria-label */}
<div className="size-[6px]" aria-label="알림">
  <BadgeDot /> {/* 너무 작아서 스크린 리더가 읽기 어려움 */}
</div>
```

---

## 검증 질문

### **Type 선택**:
- [ ] Default (Border 없음)를 사용하는가?
- [ ] With Border 1px를 사용하는가? (6px~8px 크기)
- [ ] With Border 2px를 사용하는가? (10px~12px 크기)
- [ ] 배경 색상과 크기에 따라 적절한 Type을 선택했는가?

### **Size 선택**:
- [ ] 부모 컨테이너로 크기를 조절하는가? (`size-full`)
- [ ] 2px~12px 범위 내 크기인가?
- [ ] 기본 크기 6px를 고려했는가?
- [ ] 배치 위치(Avatar/Icon/List)에 맞는 크기인가?

### **스타일**:
- [ ] 배경이 #fe5b58 빨간색인가?
- [ ] Shape이 Circle (`rounded-[100px]`)인가?
- [ ] Border 1px일 때 `border border-solid border-white`를 사용하는가?
- [ ] Border 2px일 때 `border-2 border-solid border-white`를 사용하는가?
- [ ] Border가 `absolute inset-0`로 렌더링되는가?

### **배치**:
- [ ] Avatar/Icon 위에 absolute 배치 시 top-right 위치인가?
- [ ] 적절한 오프셋이 있는가?
- [ ] List Item Trailing에 배치 시 적절한 간격이 있는가?

### **접근성**:
- [ ] 읽기 전용 인디케이터로만 사용하는가? (클릭 불가)
- [ ] 부모 요소에 aria-label이 제공되는가?
- [ ] 배경 대비가 충분한가? (Default vs With Border)

### **Badge Number vs Dot 선택**:
- [ ] 숫자 표시가 필요한가? → Badge Number
- [ ] 최소 공간만 사용하는가? → Badge Dot
- [ ] 중요도가 높은가? → Badge Number
- [ ] 부드러운 알림인가? → Badge Dot

---

## 자주 하는 실수

### **Type 혼동**:
- ❌ 밝은 배경, 6px~8px에서 Default 사용 (정답: **Border 1px**)
- ❌ 밝은 배경, 10px~12px에서 Border 1px 사용 (정답: **Border 2px**)
- ❌ 어두운 배경에서 With Border 사용 (정답: **Default**)
- ❌ Border를 직접 Dot div에 추가 (정답: **absolute 자식 div로 border**)
- ❌ 큰 크기(12px)에 1px border 사용 (정답: **2px border가 더 적합**)

### **Size 설정**:
- ❌ Dot에 직접 `size-[6px]` 설정 (정답: **부모에 설정, Dot은 size-full**)
- ❌ width/height 따로 설정 (정답: **size-[Npx]로 정사각형**)
- ❌ 20px 이상 사용 (정답: **2px~12px 범위**)

### **색상**:
- ❌ 배경을 Primary (#00cbd5)로 변경 (정답: **#fe5b58 고정**)
- ❌ Dark 모드에서 색상 변경 (정답: **Light/Dark 동일**)
- ❌ Border를 다른 색으로 (정답: **white 고정**)

### **Shape**:
- ❌ `rounded-full` 사용 (정답: **rounded-[100px]**)
- ❌ Rectangle 형태 사용 (정답: **Circle만**)

### **배치**:
- ❌ Avatar 중앙에 배치 (정답: **top-right**)
- ❌ absolute 없이 inline 배치 (정답: **absolute 배치**)
- ❌ z-index 없이 Avatar 뒤에 가려짐 (정답: **z-10 등 추가**)

### **접근성**:
- ❌ 작은 Dot (4px)를 클릭 가능한 버튼으로 사용 (정답: **읽기 전용만**)
- ❌ Dot 자체에 aria-label 추가 (정답: **부모 요소에 추가**)
- ❌ 스크린 리더 설명 없이 사용 (정답: **부모에 aria-label**)

### **With Border 구현**:
- ❌ Dot div에 직접 border 추가 (정답: **absolute 자식 div로 border**)
- ❌ `pointer-events-auto` 사용 (정답: **pointer-events-none**)
- ❌ `aria-hidden="false"` 또는 생략 (정답: **aria-hidden="true"**)
- ❌ border div를 `rounded-full`로 (정답: **rounded-[100px]**)
- ❌ Border 1px와 2px 혼동 (정답: **크기에 따라 선택**)

---

## WDS vs 커스텀 판단

### **✅ WDS Badge Dot으로 인정**:
- Default (Border 없음): ✅ 표준 사용
- With Border 1px (white): ✅ 표준 사용 (6px~8px)
- With Border 2px (white): ✅ 표준 사용 (10px~12px)
- 크기: 2px~12px 범위 ✅

### **❌ 커스텀으로 분류**:
- **다른 색상 배경**: Primary (#00cbd5), 회색 등
  - Badge Dot은 빨간색 (#fe5b58)만 사용
  - 다른 색상 필요 시 커스텀 인디케이터
- **크기 12px 초과**: 14px, 16px 등
  - Badge Dot 범위를 벗어남
  - Badge Number Small (12px) 고려
- **Shape 변경**: Rectangle, Rounded Rectangle
  - Badge Dot은 Circle만 사용
  - 다른 Shape 필요 시 커스텀

### **⚠️ 경계 케이스**:
- **12px Dot vs Badge Number Small (12px)**:
  - Dot: 단순 상태 표시 (숫자/텍스트 없음)
  - Number: "N" 텍스트 + border (더 강조)
  - 용도에 따라 선택
