### 플로트
- left
- right 
- none
- inherit

플로트 속성의 종류에는 위에 4가지가 있고 
(NormalFlow, IFC, BFC, RP)
플로트 속성을 부여하면 NewBFC를 그리고 새로운 레이어 같은 개념 붕 뜬다.(새로운 bfc 영역 생성  - 레이어 처럼  영역 넓이는 cotent 넓이까지 )
플로트는 LineBox로 그려진다. 인라인요소는 가드한다.
라인박스 -플로트 요소만 신경씀 ㅇㅇㅇ
라인박스 플로트가 자치하지 않는 나머지 영역

레프트보다 왼쪽에는 못 그림 !

LineBox 

### OverFlow geometry기준

- visible  
- hidden  내 geometry 넘어가면 안 보이게
- scroll 내 geometry 넘어가면 스크롤 생기게 
- inherit
- auto == visible  -> geometry가 크기에 따라 변한다 
  
고전 layOut  모든 브라우저 지원 
Grid 
Flex

### OverFLow-x, y

transform 
- visible 
- hidden 
- scroll 
- clip 
- auto 

### Text OverFLow

HIDDEN / SCROLL 을 가질 때만 새로운 BFC를 만든다. 
NEWBFC-FIRST LINE BOX BOUND 

New BFC

Float over normal flow 

Text inline guard

Line box 
