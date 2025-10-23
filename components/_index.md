# Chord Components Specification Index

Chord Design System의 컴포넌트별 상세 스펙 문서 목록입니다.

# Component Index
- [avartar.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/avatar.md)
- [avatar_group.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/avatar_group.md)
- [badge.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/badge.md)
- [button.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/button.md)
- [dialog.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/dialog.md)
- [list_item.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/list_item.md)
- [tag.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/tag.md)
- [text_field.md](https://raw.githubusercontent.com/pine-weverse/agent-docs/refs/heads/main/components/text_fields.md)

---

## ✅ 완료된 컴포넌트 (상세 스펙 문서화)

### **Button** - [상세 보기](button.md)
- **Size**: 6가지 (XLarge/Large/Medium/Small/XSmall/XXSmall)
- **Type**: 5가지 (Filled/Outlined-Color/Outlined-Gray/Ghost/Icon)
- **Shape**: 2가지 (Rectangle/Round)
- **Color**: Primary/Outlined Gray/Community Color

### **Avatar** - [상세 보기](avatar.md)
- **Size**: 11가지 (Speciality ~ Tiny)
- **Type**: 3가지 (Circle/RoundSquare/Square)
- **Overlays**: Host/Badge Dot/Imoji/Birthday Corn

### **Avatar Group** - [상세 보기](avatar_group.md)
- **Usage Type**: 4가지 (Default/FanLetter/DM/LIVE)
- **Overlap**: 1px / 8px
- **More 표시**: 텍스트/원형/Badge

### **Dialog** - [상세 보기](dialog.md)
- **크기**: 312px 고정
- **Buttons**: 1~3개 (세로/가로 배치)
- **Agree**: 체크박스 옵션
- **Light/Dark Mode**: 별도 스타일

### **List Item** - [상세 보기](list_item.md)
- **구조**: Leading + Content + Trailing
- **패턴**: One Line/Two Line/Three Line
- **패딩**: Medium/Small

### **Tag** - [상세 보기](tag.md)
- **Size**: 2가지 (Small/Medium)
- **Shape**: 2가지 (Rectangle/Round)
- **Type**: 2가지 (Line/Fill)
- **총합**: 8가지

### **Text Fields** - [상세 보기](text_fields.md)
- **Type**: 2가지 (Single Line/Multiple Lines)
- **State**: 5가지 (Default/Focused/Disabled/Error/Success)
- **구조**: Title → TextField → Guide Message
- **Special**: Chat Type (24px Radius)
- **Light/Dark Mode**: 별도 색상 규칙

### **Badge** - [상세 보기](badge.md)
- **Type**: 2가지 (Badge Number/Badge Dot)
- **Badge Number**: 3 Sizes (Large 16px/Medium 14-16px/Small 12px)
- **Badge Dot**: 3 Types (Default/Border 1px/Border 2px)
- **색상**: #fe5b58 빨간색 고정 (Light/Dark 동일)
- **특징**: 999+ 숫자 표시, Pill/Circle 형태

---

## 🚧 작업 중

- CheckBox

---

## 📋 예정 (Chord WDS 22개 컴포넌트)

### 기본 컴포넌트
- Chips
- Dropdown
- FAB (Floating Action Button)
- Loading
- Menu
- Pagination
- Placeholder
- Radio
- Select Number Box
- Slider
- Snackbar
- Snippet
- Stepper
- Tabs
- Thumbnail
- Toast
- Toggle
- Toolbar
- Tooltip

### 레이아웃 컴포넌트
- GNB (Global Navigation Bar)
- Header
- Player Controller

### 모바일 전용
- Bottom Sheet
- Bottom Popup

---

## 📖 사용 방법

1. 검증하려는 컴포넌트의 상세 문서 링크 클릭
2. 시스템 구조, Size/Type/Shape 시스템 확인
3. 검증 질문 체크리스트 활용
4. 자주 하는 실수 섹션 참고

---

## 🔗 관련 문서

- [Guidelines.md](/guidelines/Guidelines.md) - 전체 검증 가이드
- [chord_usage_guide.md](/guidelines/chord_usage_guide.md) - 사용 가이드라인
- [designer_communication_guide.md](/guidelines/designer_communication_guide.md) - 응답 가이드

---

**마지막 업데이트**: 2025-10-22  
**컴포넌트 수**: 8개 완료 / 22개 전체  
**버전**: 0.5.3
