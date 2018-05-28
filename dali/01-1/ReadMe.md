# CSS-Rendering 1-1

그래픽스 시스템
- 한 줄 요약 그래픽스 시스템은 점을 찍는 작업 

=> x,y width, hegith , color

1. FixedNumber -> 고정되어 있는 숫자로 표현하기 but(이 거는 범용성이 없다. 한 가지에만 적용 가능)
    범용성 고려되는 대표적인 환경적 요인 
   1. 스크린 사이즈 
   2. 크롬 사이즈  크롬 닫기, 스크롤 등등 ui 요소 
   3. 상속 
2. Abstract Caculator (메타포 %, Left, InLine, Float) 추상화된 계산기=> 공식, 함수
3. Components 2번을 이어받는 체계 컴포넌트 example) `<img>, <radio>`
4. FrameWork  컴포넌트들끼리 일정한 규칙과 틀을 가진 것을 프레임워크  더 큰 html 프레임 체계를 하나의 프레임워크라고 볼 수 있다. 



### 렌더링

내가 원하는 모습으로 보다 구체적이고 시각적인 부분으로 보여주는 것 <br>
데이터 -> 그림 
렌더링 시스템

1. 박스 찾기 Geometry caculate ->  Reflow
2. Fragment Fill -> Repaint



pixel도 상대적인 단위 pixelRatio도 고려해야 됨으로 

중립적인 개념이 필요함 

Fragment를 채운다.

영역을 나누고 채운다 



어떻게 고정된 숫자를 사용하지 않고 범용성있게 표현할까? <br>

지오메트리를 어떤식으로 표현할까? <br>

색칠을 할 때 어떤식으로 명령을 내릴까? <br>



### CSS 스펙



CSS사양 ->표준-> 표준을 기준으로 polyfil <br>
css history <br>

1. level1 html -> style 분리하자 
2. level2  ms* / apple/ google  ie 다 호환
   level2+module
   level2.1 include 3  —2.1 사양 
   모듈별로 여러가지로 나뉨 모듈 별로 발전 
   보통 2.1에서 level3가 된 애들을 css3라고 함 공식적으로 css3는 없음 
   
   masking, tranform ,flex*, grid ... 



브라우저 버전별 쓸 수 있는 스택 ! <br>
Other Specfication <br>
크롬> Ie <br>

- wicg 구글이 주 멤버여서 여기 힘이 강함 
- ricg 

Chrom draft ::::<br>

### 기본 배경지식

1. 그래픽스 시스템 
2. 렌더링 시스템 
3. CSS 스펙
   

###  ref

1. CS 보통 개념들 다 상대적  자식-부모 할아버지 입장에서는 부모가 다시 자식이 되고 
2. 고유명사 -> 일반명사에서 그냥 따옴



###  NormalFlow

css 2.1 visual formating model

positioning schemes & normalflow 

NormalFlow

1. BFC (Blcok Formating Context)
2. IFC (Inline Formating Context)
3.  RP (Relatvie Position)

###  Position

- static*
- relative*
- absolute 
- fixed
- Inherit

static, relative일 때만 normalFlow

### RP

RP 는 static을 그리고 relative에서 지시한 만큼 상대적으로 그리기 

static보다 한 층 뜨게 된다.

다시 그리지 않는다. 이미 geometry 로 틀을 잡아 놓고 위에다가 그리기 때문에 

### reference css 속성

단어나 공백 관련 속성
* [words-break](https://css-tricks.com/almanac/properties/w/word-break/)
* [white-space](https://css-tricks.com/almanac/properties/w/whitespace/)

* &nbsp 에 의미
줄 바꿈 없는 공백(non-breaking space, no-break space, 줄여서 NBSP) 또는 단어 잘림 방지 공백, 줄 바꿈하지 않는 공백은 공백 문자의 한 형태로, 현 위치에서 자동 줄 바꿈(워드랩)을 막는 데 쓰인다. 고정 공백이라고도 한다.

### 강의 듣고 스터디하면서  느낌 

1. css 를 좀 더 구체적으로 알게 되면 그래도 다룰 떄 덜 짜증나지 않을까 
2. block, inline정도로만 알았는데 bfc, ifc, rp -> normal flow => geomety cacluate , fragment fill 
이 공부를 잘 하게 되면 브라우저 동작 및 성능 큰 흐름 부터 전체적인 맥락이 기존 보다 훨씬 잘 이해할 수 있을 것 같아서 좋을 것 같다.

### etc

* css 는 모듈단위로 스펙이 발전되고 있구나 
* position relative도 layer처럼 static보다 위에다 그리는 구나
* 강의가 이어지는 부분이여서 부담이 덜 된다면 1주일 1/2 2/2 모두 하는 것이 낫지 않나라는 생각이 든다. 

