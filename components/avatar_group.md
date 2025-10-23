# Avatar Group (아바타 그룹)

**시스템 구조** (Import 코드 기준):
```
[Avatar 1] [Avatar 2] [Avatar 3] [More +N]
  ←겹침→    ←겹침→    ←겹침→
```

---

## Usage Type 시스템 (4가지)

### **1. Default** - 기본 그룹

- **사용처**: 표시되는 아바타의 최대 개수는 3개, 초과분은 숫자로 표시
- **Avatar 크기**: `20x20` (XXXSmall) ⭐
- **겹침 간격**: `mr-[-1px]` → **1px 겹침** ⭐
- **최대 개수**: **3개** 표시
- **Mask**: 왼쪽이 잘린 원형 사용
  - Avatar 3: `mask-size-[16.992px_20px]` (왼쪽 잘림)
  - Avatar 2: `mask-size-[16.992px_20px]` (왼쪽 잘림)
  - Avatar 1: `mask-size-[20px_20px]` (완전한 원)
- **More (초과 표시)**:
  - 크기: `h-[20px]`
  - 패딩: `pl-[8px] pr-[6px]`
  - 텍스트: `+N` (13px Medium, WeGothicSans)
  - Text Shadow: `rgba(0,0,0,0.08) 0px 2px 12px`
  - 겹침: `mr-[-1px]`
- **전체 패딩**: `pl-0 pr-px` (오른쪽 1px)

---

### **2. FanLetter** - 팬레터 그룹

- **사용처**: 좌측 하단에 좋아요 아이콘 표시, 최대 3개 (웹 팬레터 엔드는 제한 없이 Marquee)
- **Avatar 외부**: `28x28` (bg-white, rounded-[14px], p-[2px])
- **Avatar 내부**: `24x24` (XXSmall) ⭐
- **겹침 간격**: `mr-[-8px]` → **8px 겹침** ⭐
- **최대 개수**: **3개** (모바일), **제한 없음** (웹 - Marquee 처리)
- **흰색 테두리**: `bg-white p-[2px] rounded-[14px]` → **2px 흰색 패딩**
- **Mask**: 완전한 원형 `mask-size-[24px_24px]`
- **More (초과 표시)**:
  - Number 컴포넌트: `24x24` 원형
  - 배경: `bg-[#282828]` (어두운 회색)
  - 텍스트: `+N` (10px Bold, WeGothicSans)
  - 외부 wrapping: `bg-white rounded-[14px] size-[28px]`
  - 겹침: `mr-[-8px]`
- **좌측 하단 아이콘**:
  - 위치: `bottom-[-2px] left-[-2px]`
  - 크기: `12x12` (icon_area)
  - Selection 아이콘: `#FE5B58` fill, `opacity-0.2` (20%)
- **전체 패딩**: `pl-0 pr-[8px]`

---

### **3. DM** - 메시지 그룹

- **사용처**: WEB DM 진입 시 하단 플로팅 버튼, 새 메시지 도착 시 최대 10개 표시
- **Avatar 크기**: `20x20` (XXXSmall) ⭐
- **겹침 간격**: `mr-[-1px]` → **1px 겹침** ⭐
- **최대 개수**: **10개** 표시
- **Mask**: 왼쪽이 잘린 원형 `mask-size-[16.992px_20px]`
- **New Badge**:
  - 크기: `12x12` (`min-w-[12px]`)
  - 배경: `bg-[#fe5b58]` (빨간색) ⭐
  - Border: `border border-solid border-white`
  - Radius: `rounded-[20px]` (완전한 원형)
  - 패딩: `pb-[2.5px] pt-[1.5px] px-[4.5px]`
  - 텍스트: `N` (6px Heavy, SF Pro Text)
  - 위치: 마지막 Avatar 우측 상단
  - 겹침: `mr-[-8px]`
- **전체 패딩**: `pl-0 pr-px`
- **전체 높이**: `h-[20px]` (Avatar와 동일), Badge 포함 시 `h-[22px]`

---

### **4. LIVE** - 라이브 참여자 그룹

- **사용처**: 라이브 참여 인원 2명 이상, 32x32 고정 영역에 최대 4개까지 표시
- **고정 영역**: `32x32` ⭐
- **Avatar 크기**: `20x20` (XXXSmall) ⭐
- **겹침 간격**: `mr-[-8px]` → **8px 겹침** ⭐
- **최대 개수**: **2개** (또는 4개까지 가능)
- **배치 방식**: **수직 배치** (Vertical Stack)
  - Avatar 1: `left-0 top-0` (상단)
  - Avatar 2: `left-0 top-[12px]` → **12px 아래** ⭐
- **Mask**: 위/아래가 잘린 원형
  - Avatar 1: 하단이 잘림 (Subtract path)
  - Avatar 2: 상단이 잘림 (Subtract path)
- **전체 패딩**: `pl-0 pr-[8px]`

---

## 공통 규칙

- **Type**: **Circle만** 사용 가능 (모든 Usage)
- **Outline**: `border-[rgba(0,0,0,0.04)]` (Light mode 4%)
- **이미지**: 각 Avatar는 독립적인 이미지 사용
- **방향**: 왼쪽 → 오른쪽 순서로 배치 (LIVE는 위 → 아래)

---

## Overlap 패턴

- **1px 겹침**: Default, DM → `mr-[-1px]`
- **8px 겹침**: FanLetter, LIVE → `mr-[-8px]`

---

## More 컴포넌트 패턴

- **텍스트만** (Default): 13px Medium, text-shadow
- **원형 배경** (FanLetter): 24x24, #282828 배경, 10px Bold
- **Badge** (DM): 12x12, #fe5b58 빨간색, border white, 6px Heavy

---

## 사용처별 설명

- **Default**: 일반적인 그룹 아바타 표시 (3개 제한)
- **FanLetter**: 좋아요한 사용자 표시, 좌측 하단 아이콘, 웹은 Marquee
- **DM**: 새 메시지 발신자 표시 (최대 10개), New Badge 가능
- **LIVE**: 라이브 참여자 표시 (32x32 고정 영역, 수직 배치)

---

## 검증 질문

- [ ] Usage Type이 Default/FanLetter/DM/LIVE 중 하나인가?
- [ ] Avatar 크기가 20px(XXXSmall) 또는 24px(XXSmall, FanLetter)인가?
- [ ] 겹침 간격이 Usage에 맞는가? (1px 또는 8px)
- [ ] 최대 개수가 Usage에 맞는가? (3개/10개/2개/4개)
- [ ] Default/DM에서 겹침이 1px(mr-[-1px])인가?
- [ ] FanLetter/LIVE에서 겹침이 8px(mr-[-8px])인가?
- [ ] FanLetter에서 흰색 테두리가 2px인가? (p-[2px])
- [ ] FanLetter에서 좌측 하단 아이콘이 12x12인가?
- [ ] DM에서 New Badge가 12x12, #fe5b58 빨간색인가?
- [ ] LIVE에서 고정 영역이 32x32인가?
- [ ] LIVE에서 수직 간격이 12px(top-[12px])인가?
- [ ] More 컴포넌트가 Usage에 맞는 스타일인가?
- [ ] Circle Type만 사용하고 있는가?

---

## 자주 하는 실수

### **Overlap 간격**:
- ❌ Default에서 8px 겹침 사용 (정답: **1px** mr-[-1px])
- ❌ FanLetter에서 1px 겹침 사용 (정답: **8px** mr-[-8px])
- ❌ DM에서 8px 겹침 사용 (정답: **1px** mr-[-1px])
- ❌ LIVE에서 1px 겹침 사용 (정답: **8px** mr-[-8px])

### **Avatar 크기**:
- ❌ Default/DM/LIVE에서 24px 사용 (정답: **20px** XXXSmall)
- ❌ FanLetter에서 20px 사용 (정답: **24px** XXSmall + 2px padding = 28px 외부)

### **최대 개수**:
- ❌ Default를 10개 표시 (정답: **3개**)
- ❌ DM을 3개로 제한 (정답: **10개**)
- ❌ LIVE에서 10개 표시 (정답: **2개** 또는 최대 4개)

### **FanLetter 특수 요소**:
- ❌ 흰색 테두리 누락 (정답: **bg-white p-[2px] rounded-[14px]**)
- ❌ 좌측 하단 아이콘 누락 (정답: **12x12 Selection 아이콘 필수**)
- ❌ 웹 팬레터 엔드에서 3개 제한 (정답: **제한 없음, Marquee 처리**)

### **DM Badge**:
- ❌ Badge를 다른 색상으로 (정답: **#fe5b58 빨간색 고정**)
- ❌ Badge 크기를 16px로 (정답: **12x12 고정**)
- ❌ Badge 텍스트를 8px로 (정답: **6px Heavy**)

### **LIVE 배치**:
- ❌ 수평 배치 사용 (정답: **수직 배치**)
- ❌ 고정 영역을 자동으로 (정답: **32x32 고정**)
- ❌ 수직 간격을 16px로 (정답: **12px** top-[12px])

### **Type 제한**:
- ❌ RoundSquare 또는 Square 사용 (정답: **Circle만** 사용 가능)
