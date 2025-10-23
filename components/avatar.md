# Avatar (아바타)

**시스템 구조** (Import 코드 기준):
```
[Avatar Image] + [Outline (선택)] + [Badge/Host (선택)]
```

---

## Type 시스템

- **Circle**: `rounded-[100px]` → 완전한 원형 ⭐
- **RoundSquare**: `rounded-[12px]` → 둥근 모서리 사각형 (RoundSquare 사용)
- **Square**: `rounded-[12px]` → 둥근 모서리 사각형 (일반 이미지)

---

## Size 시스템 (11가지)

1. **Speciality**: `128x128` - 특수 화면 전용, 시스템 관리자 논의 필요
2. **3XLarge**: `96x96` - 페이지 내 아바타 강조 표시
3. **2XLarge**: `72x72` - 사용자 프로필 페이지, 아바타 전시
4. **XLarge**: `64x64` - 아바타를 버티컬 리스트로 표시
5. **Large**: `56x56` - 아바타를 버티컬 리스트로 표시
6. **Medium**: `48x48` - DM 전시, DM 리스트, 멀티 프로필, 리스닝파티
7. **Small**: `40x40` - DM 리스트, 멀티 프로필 리스트
8. **XSmall**: `32x32` - 피드 포스트, 댓글, 리스닝파티
9. **XXSmall**: `24x24` - 대댓글, 검색, Chip
10. **XXXSmall**: `20x20` - 네비게이션(프로필), Tab바
11. **Tiny**: `16x16` - 합동 라이브, 특수 화면만, 시스템 관리자 논의 필요

---

## Outline (선택적)

- **삭제 가능** (필수 아님)
- **Light Mode**: `border border-[rgba(0,0,0,0.04)]` → **4% 검은색** 테두리
- **Dark Mode**: `border border-[rgba(255,255,255,0.1)]` → **10% 흰색** 테두리
- Circle: `rounded-[100px]`
- RoundSquare/Square: `rounded-[12px]`

---

## Host (오버레이 아바타)

- **크기**: `24x24` 고정 (XXSmall 사이즈)
- **위치**: `absolute bottom-0 right-[-4px]` → 오른쪽 하단, **-4px 오프셋** ⭐
- **Border**: `border-2 border-solid border-white` → **2px 흰색 테두리** (Light)
- **Border**: `border-2 border-solid border-black` → **2px 검은색 테두리** (Dark)
- **Shape**: `rounded-[100px]` (항상 원형)
- **용도**: RoundSquare 타입에서 호스트 표시 (합동 라이브 등)

---

## Badge Dot (알림 뱃지)

### **사용처**: 
RoundSquare 타입 아바타 오른쪽 상단

### **크기 시스템** (Avatar 크기별):

#### **72px+ Avatar** (2XLarge 이상):
- Badge: `20x20` (`rounded-[333.333px]`)
- Border: `border-[3.333px] border-solid border-white` (Light)
- Position: `mr-[-20px]`

#### **64px Avatar** (XLarge):
- Badge: `16x16` (`rounded-[266.667px]`)
- Border: `border-[2.667px] border-solid border-white` (Light)
- Position: `mr-[-16px]`

#### **40px 이하 Avatar** (Small, XSmall):
- Badge: `10x10` (`rounded-[166.667px]`)
- Border: `border-[1.667px] border-solid border-white` (Light)
- Position: `mr-[-10px]`

### **공통**:
- **배경**: `bg-[#fe5b58]` ��� **빨간색 고정** ⭐
- **Dark Mode Border**: `border-black` (검은색 테두리)
- **용도**: 알림, 온라인 상태, 업데이트 표시

---

## Imoji (이모지 오버레이)

- **사용처**: DM에서 사용하는 아바타
- **Type**: **Circle만** 사용 가능
- **Size**: Medium(48px), XLarge(64px)에서 제공 ⭐
- **Imoji 크기**: `24x24` 고정
- **위치**: `absolute bottom-[-6px] right-[-6px]` → **-6px 오프셋** ⭐
- **배경 원형**:
  - Light Mode: `white` circle, `12px` radius
  - Dark Mode: `#282828` circle, `12px` radius
  - Drop Shadow: `dy="2" stdDeviation="6" opacity 0.08`
- **Emoji 텍스트**:
  - 크기: `13px` (SF Pro Text Regular)
  - 위치: `bottom-[18.5px] right-[12px]`
  - Transform: `translate-x-[50%] translate-y-[100%]`
  - Blur 효과: 중첩 (opacity 80% blur + 100% 선명)
- **조합 가능**: Medium, XLarge에서 Birthday Corn과 함께 표시 가능

---

## Birthday Corn (생일 꼬깔 오버레이)

- **사용처**: 아티스트 생일에 보여주는 UI
- **Type**: **Circle만** 사용 가능
- **Size**: Speciality ~ XXSmall 모든 사이즈 제공 ⭐

### **Birthday Corn 크기** (Avatar 크기별):
- Speciality (128px): `48x48` icon_area, left-[84px] top-[-16px]
- 2XLarge (72px): `32x32` icon_area, left-[46px] top-[-12px]
- XLarge (64px): `24x24` icon_area, left-[42px] top-[-8px]
- Large (56px): `20x20` icon_area, left-[38px] top-[-6px]
- Medium (48px): `20x20` icon_area, left-[32px] top-[-6px]
- Small (40px): `16x16` icon_area, left-[26px] top-[-4px]
- XSmall (32px): `16x16` icon_area, left-[20px] top-[-5px]
- XXSmall (24px): `12x12` icon_area, left-[15px] top-[-4px]

### **공통**:
- **회전**: `rotate-[38.348deg]` → **38.348도 회전** ⭐
- **SVG Gradient**:
  - Radial: #69FFFF → #1D9696 (청록색)
  - Linear: #FD9BFF → #985D99 (핑크색)
- **조합 가능**: Medium, XLarge에서 Imoji와 함께 표시 가능

---

## Type × Size 조합 (33가지)

- Circle: 11가지 Size 모두 사용 가능
- RoundSquare: 주로 Medium 이상 Size에서 사용 (Host 오버레이 포함)
- Square: 주로 Medium 이상 Size에서 사용 (썸네일, 브랜드 아이콘)

---

## 사용처 가이드

- **Speciality (128px)**: 리스닝파티 카드, 엔딩 화면 - 특수 케이스만
- **3XLarge (96px)**: 위버스 메인 추천 스타홈, 라이브 종료 화면
- **2XLarge (72px)**: 프로필 페이지
- **XLarge (64px)**: 글로벌홈, 샵홈 아티스트 리스트
- **Large (56px)**: 글로벌홈, 샵홈 아티스트 리스트
- **Medium (48px)**: DM 전시/리스트, 멀티 프로필, 리스닝파티 음원 연동
- **Small (40px)**: DM 리스트, 멀티 프로필 리스트
- **XSmall (32px)**: 피드 포스트 카드, 댓글, 리스닝파티(음원사)
- **XXSmall (24px)**: 대댓글, 검색(최근 검색 아티스트), Chip
- **XXXSmall (20px)**: 네비게이션(프로필), Tab바
- **Tiny (16px)**: 합동 라이브 프로필 - 특수 케이스만

---

## 검증 질문

- [ ] Type이 Circle/RoundSquare/Square 중 하나인가?
- [ ] Size가 11가지 중 하나인가? (128/96/72/64/56/48/40/32/24/20/16)
- [ ] Circle일 때 `rounded-[100px]`인가?
- [ ] RoundSquare/Square일 때 `rounded-[12px]`인가?
- [ ] Outline이 있다면 Light mode 4%, Dark mode 10% opacity인가?
- [ ] **Host** 오버레이가 24px 크기인가?
- [ ] Host 위치가 `right-[-4px]`인가?
- [ ] Host border가 2px white (Light) / black (Dark)인가?
- [ ] **Badge Dot** 배경이 `#fe5b58` 빨간색인가?
- [ ] Badge Dot 크기가 Avatar 크기에 맞는가? (20px/16px/10px)
- [ ] Badge Dot border가 Avatar 크기별로 맞는가? (3.333px/2.667px/1.667px)
- [ ] Badge Dot 위치가 Avatar 크기에 맞는가? (mr-[-20px]/-16px/-10px)
- [ ] **Imoji**를 사용한다면 Circle + Medium/XLarge인가?
- [ ] Imoji 크기가 24px인가?
- [ ] Imoji 위치가 `bottom-[-6px] right-[-6px]`인가?
- [ ] Imoji 배경이 Light white / Dark #282828인가?
- [ ] **Birthday Corn**을 사용한다면 Circle Type인가?
- [ ] Birthday Corn 크기가 Avatar 크기에 맞는가?
- [ ] Birthday Corn이 38.348도 회전되어 있는가?
- [ ] Speciality/Tiny 사용 시 시스템 관리���와 논의했는가?

---

## 자주 하는 실수

### **기본 Type/Size**:
- ❌ Circle을 `rounded-[50%]`로 설정 (정답: **`rounded-[100px]`**)
- ❌ RoundSquare를 `rounded-[8px]`로 설정 (정답: **`rounded-[12px]`**)
- ❌ 정의되지 않은 Size 사용 (정답: **11가지 중 하나만**)
- ❌ Speciality/Tiny를 일반 화면에 사용 (정답: **특수 케이스만**, 논의 필요)

### **Outline**:
- ❌ Outline을 항상 추가 (정답: **선택적**, 없어도 됨)
- ❌ Light mode Outline을 10%로 설정 (정답: **4%**)
- ❌ Dark mode Outline을 4%로 설정 (정답: **10%**)

### **Host**:
- ❌ Host를 `right-0`에 배치 (정답: **`right-[-4px]`**, -4px 오프셋)
- ❌ Host border를 1px로 설정 (정답: **2px**)

### **Badge Dot**:
- ❌ Badge Dot을 다른 색상으로 설정 (정답: **`#fe5b58` 빨간색 고정**)
- ❌ 모든 Avatar에 같은 Badge 크기 사용 (정답: **Avatar 크기별로 다름** - 20px/16px/10px)
- ❌ Badge border를 고정 크기로 사용 (정답: **Avatar 크기별로 다름** - 3.333px/2.667px/1.667px)
- ❌ Badge 위치를 고정으로 사용 (정답: **Avatar 크기별로 다름** - mr-[-20px]/-16px/-10px)

### **Imoji**:
- ❌ Imoji를 Circle 외 Type에 사용 (정답: **Circle만** 사용 가능)
- ❌ Imoji를 Small 이하에 사용 (정답: **Medium, XLarge만** 제공)
- ❌ Imoji 위치를 -4px로 설정 (정답: **-6px** 오프셋)
- ❌ Imoji를 Avatar 크기별로 다르게 (정답: **24px 고정**)

### **Birthday Corn**:
- ❌ Birthday Corn을 Circle 외 Type에 사용 (정답: **Circle만** 사용 가능)
- ❌ Birthday Corn을 회전 없이 배치 (정답: **38.348도 회전** 필수)
- ❌ 모든 Avatar에 같은 Corn 크기 사용 (정답: **Avatar 크기별로 다름**)
- ❌ Birthday Corn을 임의 위치에 배치 (정답: **Avatar 크기별로 정확한 left/top 값** 있음)
