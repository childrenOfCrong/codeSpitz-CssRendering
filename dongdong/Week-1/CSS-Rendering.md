## Abstract calculator(%, LEFT, BLOCK, INLINE, FLOAT)

#### 퍼센트를 사용한다는 것은?

> 실제로 화면에 그려질 때 환경을 인식해서 숫자로 변경.

즉, %는 공식이자, 함수임. 숫자 체계가 아니라, 공식이자 수식이다. 수식은 그림을 그리는 순간마다 다시 함수로 돌려서 숫자체계로 변환함. 직접 숫자체계를 사용하면 빠르지만, 반응형에 사용할 수 없기 때문에 %를 비롯한 메타포들을 사용한다.(Abstract calculator)



Graphics system은 원시적인 숫자로 기술하는 그래픽 시스템을 넘어 함수를 통해서 어떻게 계산할지 기술하는 방식으로 발전함. 근데, 단지 그것 만으로는 복잡한 그래픽을 그릴 수 없음. 추상화된 그래픽스 시스템 체계를 이어받는 공통점을 갖고 있는 애들을 만듬. 이를 컴포넌트라고 부름. 컴포넌트들이 일정한 규칙과 형태를 지키는 형태로 구성되어 있다면 이를 프레임워크라고 부름.



컴퓨터 사이언스에 나오는 모든 것들은 상대적이며, 어떤 레벨에 따라서 하드웨어로 보였던 게 어떤 레벨에서는 소프트웨어로 보이기도 하고, 어떤 레벨에서는 소프트웨어로 보였던 게 어떤 레벨에서는 하드웨어로 보이기도 함. 



## Graphics system

그래픽스 시스템이란, 한마디로 점 찍는 방법이다. 점을 여러개 찍거나 특정한 패턴, 색상으로 화면을 구성할 수 있다.



## Rendering System

어떠한 대상의 있으면 내가 원하는 모습으로 다시 그려내는 것을 렌더링이라고 한다. 즉, 어떤 체계를 통해서 그림이 표현됨.

### 렌더링 시스템은 2단계를 통해서 그려짐.

1. Geometry calcualter : Geometry를 계산하는 과정 (Re-flow).
2. Fragment Fill (단편 조각) : Geometry 안에 채우는 과정 (Re-paint).

>  pixel ratio 라는 단어가 중립적이지 않다. 
>
> 중립적인 단어가 필요한데, 이를 Fragment라고 함.
>
> 렌더링은 Geometry를 계산하고 Fragment를 채운다. 



## CSS Specifications

CSS란? 

1. 어떻게 하면 고정된 숫자가 아닌 계산된 체계로 그래픽을 표현할까
2. 지오메트리를 어떻게 표현할까? 색칠을 할 때 어떤 식으로 명령을 내릴까에 대한 언어임.



Q. float: right를 이용해 화면의 오른쪽에 붙힌다는 행위는 무엇인가?

>  부모의 width를 계산하고 자식의 width를 계산해서, 부모의 width - 자식의 width한 자리를 자식의 left로 삼는다!



CSS에서는 굉장히 풍부한 메타포가 많음. 각각 메타포에 대해 이해해야 원하는 레이아웃을 그릴 수 있음. CSS를 배운다는 건 CSS에 나오는 속성 또는 값이 구체적으로 발현될 때는 어떻게 표현되는지 이해하는 데 있음. CSS는 일관성없고 복잡해서, 체계가 다양하다.



---

## CSS 체계의 변천과정

1. CSS Level 1 → A4 용지 한장 짜리 
2. CSS Level 2 → MS가 제안한 스펙이 많음.
3. CSS Level 2 + Module → 그림에 관한 걸 하나의 스펙으로 관리하는 건 무리. 관심분야 별로 모아서, 모듈별로 관리하자.
4. CSS Level 2.1 → CSS의 모든 모델들이 2로 고정됨. CSS 레벨이 존재하는 단계. CSS 2.1 사양이라고 불려도 됨. 모듈별로 어떤 분과는 Level3를 발표하고, 어떤 분과들은 확정적이라 레벨이 올라갈 일이 없게 됨.
5. CSS Level3는 2.1 중 레벨업한 모듈들만 Level3라고 부르는 것이지 공식적으로 CSS 3는 존재하지 않음.



> CSS Module level로 바뀜. (transforms masking, compositioning, flexbox, effects,  grid 등 각 모듈들이 발전하는 형태로 변함. CSS 사양의 세계는 모듈들은 모듈들 나름대로 업데이트 중임. 기존 사양들도 재검토됨.)



## Normal Flow

#### positioning schemes & normalflow

Position: static | relative | absolute | fixed | inherit

>  Position은 특정 geomatry의 추상적인 left - top을 결정하는 시스템을 의미한다.

position: static | relative 일때만 포지션이 적용된다. 나머지는 normal flow에 들어가지 못함.

position: absolute | fixed는 normal flow가 아니며, 크기 고정이 안되고, 예외상황을 발생시킬 수 있으니 주의!

#### normal flow의 2가지 공식 

1. Block Formatting Context
2. Inline Formatting Context
3. Relatvie Position : Normal Flow의 일부이지만, position model에서 정의하고 있다.

실제로 normal flow를 계산하는 방법은 BFC(Block Formatting Context)와 IFC(Inline Formatting Context)임



#### Block & Inline ?

>  BFC와 IFC는 어떻게 한 줄을 먹는지, 어떻게 한 줄을 그리는지에 대한 원리임. 

Block : 부모의 가로길이를 가득 채운 한 줄. 그 줄에 무엇이 들어갈 지 고민할 필요가 없음.

BFC에서 고민해야 할 건 ? 다음 번 블록이 나올 때 Y의 위치만 신경 쓰면 됨. (두번째 Block는 상위 block의 height가 떨어지는 위치에 그리면 됨.)

IFC에서 고민해야 할 건 ? 첫 번째 IFC 요소의 가로길이만큼 떨어진 자리에 X가 결정됨. 

inline 요소가 밑으로 내려갈 때는, inline 요소들의 width의 합이 상위 inline 요소의 width값을 넘을 때 내려감.

얼마만큼 내려가야 하는가? 지금 inline을 구성하고 있는 요소 중 가장  height가 큰 요소가 line-height가 되어서 line-height만큼 Y값이 내려옴.

> 

다만,IFC영역이 생성되도, Block이 오면 즉시, IFC 영역이 종료되고 다음번 block요소가 만들어짐.



#### RP

Relative는 static으로 그려도 상대적으로 위치를 이동시킴.

Relative는 오직 Element만 상대적으로 그릴 뿐이지, Geometry는 Static으로 계산된다.
