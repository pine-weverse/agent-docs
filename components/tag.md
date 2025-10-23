# Tag (태그)

**시스템 구조** (Import 코드 기준):
```
[Icon 10px] ←2px→ [Text 10px Bold]
```

---

## Size 시스템

### **Small**:
- 높이: `h-[16px]`
- 좌우 패딩: `px-[4px]`
- 상하 패딩: `py-0` (없음)

### **Medium**:
- 높이: `h-[20px]`
- 좌우 패딩: `px-[6px]`
- 상하 패딩: `py-0` (없음)

---

## Shape 시스템

### **Rectangle**:
- Small: `rounded-[4px]`
- Medium: `rounded-[6px]`

### **Round**:
- 모든 사이즈: `rounded-[24px]` (완전히 둥근 pill 형태)

---

## Type 시스템

### **Line** (Stroke/Outlined):
- Border: `border border-[#01d5df]` (Primary color)
- Border opacity: `opacity-40` (40%)
- 텍스트: `text-[#01d5df]` (Primary color)
- 아이콘: Primary color fill
- 배경: 투명

### **Fill**:
- Background: `bg-[#01d5df]` (Primary color)
- Background opacity: `opacity-[0.85]` (85%)
- 텍스트: `text-white`
- 아이콘: white fill
- Border: 없음

---

## 내부 간격

- 아이콘 ↔ 텍스트: `gap-[2px]` → **2px** ⭐
- 아이콘 크기: `size-[10px]` → **10px**
- 텍스트: **10px Bold** (WeGothicSans), `leading-[13px]`
- 정렬: `flex items-center justify-center` (세로/가로 중앙)

---

## 8가지 조합

1. Small + Rectangle (4px) + Line
2. Small + Rectangle (4px) + Fill
3. Small + Round (24px) + Line
4. Small + Round (24px) + Fill
5. Medium + Rectangle (6px) + Line
6. Medium + Rectangle (6px) + Fill
7. Medium + Round (24px) + Line
8. Medium + Round (24px) + Fill

---

## 검증 질문

- [ ] 높이가 16px(Small) 또는 20px(Medium)인가?
- [ ] 좌우 패딩이 4px(Small) 또는 6px(Medium)인가?
- [ ] 상하 패딩이 0인가? (py-0)
- [ ] Rectangle일 때 radius가 4px(Small) 또는 6px(Medium)인가?
- [ ] Round일 때 radius가 24px인가?
- [ ] 아이콘-텍스트 간격이 2px인가? (gap-[2px])
- [ ] 아이콘 크기가 10px인가?
- [ ] 텍스트가 10px Bold, 13px line-height인가?
- [ ] Line 타입일 때 border opacity가 40%인가?
- [ ] Fill 타입일 때 background opacity가 85%인가?
- [ ] Line 타입의 텍스트가 Primary color인가?
- [ ] Fill 타입의 텍스트가 white인가?

---

## 자주 하는 실수

- ❌ Small에서 패딩을 6px로 설정 (정답: **4px**)
- ❌ Medium에서 패딩을 4px로 설정 (정답: **6px**)
- ❌ Rectangle Small에서 radius를 6px로 설정 (정답: **4px**)
- ❌ Rectangle Medium에서 radius를 4px로 설정 (정답: **6px**)
- ❌ 아이콘-텍스트 간격을 4px로 설정 (정답: **2px**)
- ❌ 상하 패딩을 추가 (정답: **0**, py-0)
- ❌ Line 타입에서 border를 100% opacity로 설정 (정답: **40%**)
- ❌ Fill 타입에서 background를 100% opacity로 ��정 (정답: **85%**)
