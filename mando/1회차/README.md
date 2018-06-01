# 1회차

css는 5세대 언어

* 5세대 언어: 선언만 하면 작성해 주는 언어: 선언형 언어(많은 부분 자동화)



비트맵: 0과1(비트)만으로 표현하는 방식

트루칼라: 4바이트(r,g,b,a)

16비트 트루칼라도 있음



fixed number체계: 확정된 값에 그림을 그리는 체계

* 다양한 디스플레이에 대응할 수 없어진다



abstract calculator: 위의 단점을 보완한 체계

* %, left, inline, block 등 추상화된 단계를 이용
* 다양한 디스플레이에 적용 가능



component: 여러 추상적인 아이템을 묶어서 언제든지 활용할 수 있는 것으로 묶어놓은 것



framework: component가 일관성 있는 분류, 체계를 갖고있는 것



그래픽스: 그림을 그림으로 표현

렌더링: 그림이 아닌 것을 그림으로 표현



리플로우geometery calculater: 영역을 지정하는(계산하는)과정

리페인트fragment fill: 영역(fragment)을 채우는 과정

현대 렌더링 시스템은 위의 과정이 이뤄진다.



지오메트리 변화는 많은 컴퓨팅적 소비를 유발한다



## css spec

1. css level1
2. css level2
3. css level2 + module
4. css 2.1 : css level2 + module : 모듈 별 스펙이 따로 존재
5. module level: css의 통합 레벨이 올라가는 대신 각각의 모듈의 레벨이 올라가기 시작





## normal flow

노말플로우의 렌더링 원칙(세 가지 알고리즘 원리)

* block formatting context(BFC)
* inline formatting context(IFC)
* relatvie positioning(RP)

### position

* static: 노말플로우의 영향
* relative: 노말플로우의 영향
* absolute
* fixed
* inherit



### 과정

BFC영역에서 블록 엘리먼트들이 만들어 질 때

* 다음 블록엘리먼트는 BFC덕분에 y값(이전 엘리먼트의 height)을 가지고 태어남
* BFC는 이렇게 다음 블록엘리먼트가 가져야할 그래픽정보를 계산하는 역할

IFC영역

* IFC덕에 다음 인라인 엘리먼트가 x값(이전 엘리먼트의 width)을 가지고 태어남
* 줄바꿈이 일어나게 되면 다음 엘리먼트가 계산된 x,y가 갖도록 해줌


특정상황에서는 또 다른 BFC영역이 발생하도록 css가 행동



### BFC

상위의 block요소를 타고 타고 들어가서 width를 가져온다



### IFC

> 모든 div의 overflow속성은 auto다: auto란 말은 브라우저의 속성이 맡긴다는 뜻. 브라우저의 속성은 visible이다

visible 속성에서는 inline 엘리먼트의 크기가 상위 block엘리먼트의 width보다 커지면 뚫고 나간다.

하지만 케리지 리턴(`\n`)이나 스페이스 등 공백문자를 넣어주면 IFC가 공백문자로 나뉘어진 텍스트 노드를 개별 width를 갖는 엘리먼트 비슷하게 인식한다. 따라서 상위 width를 넘어가는 텍스트 노드를 아래로 내려줌



### RP

normal flow를 계산한 후 relative를 계산해서 렌더링함

> relative: static으로 그리고 나서 static으로 그려진 normal flow에서 상대적으로 그릴 위치

static 속성과 relative속성 둘 다 존재하면 relative가 뜨면서 static을 가림

**지오메트리 계산은 전부 static에서 했기 때문에 나머지 엘리먼트의 배치는 바뀌지 않는다. 상대적으로 relative엘리먼트만 움직인다**



지금까지 normal flow 아래에서 작동하는 방식을 봤다. absolute나 fixed는 normal flow가 아님으로 크기가 고정이 안되거나 다른 예외상황을 발생시킬 수 잇으니 알고있자!