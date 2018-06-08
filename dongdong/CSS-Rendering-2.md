# Modern Box

- Shadow의 거리를 0으로 만들고, border를 하나도 안주면, box-shadow를 border로 사용할 수 있음.

- box-shadow는 geometry로 계산되지 않고, 그림만 그려줌.

- Box-shadow도 Fragment 단계에서만 영향을 끼침.
- box-shadow 속성 중 inset을 주면 border 안에도 그림을 그릴 수 있음.
- box-shadow는 몇 개라도 쓸 수 있음 무지개처럼 그릴 수도 있음.
- 기존에는 border 하나만 쓸 수 있었는데, box-shadow와 box-shadow inset을 사용하면 몇 겹을 사용할 수도 있음.
- outline의 위치는 bodder-box 밖에 그림. geometry의 영향을 끼치지 않는다.

- box-shadow, box-shadow inset, outline 3가지를 보더처럼 쓸 수 있다.

- outline : 박스
- 모던 브라우저에서 box-shadow, box-shadow inset, outline을 사용해서 보더를 만들 수 있당! 오오!

## Box-sizing

- Content Box가 CSS 기본 사이징이다...!

```html
<style>
  div {
    width: 100px;
    height: 100px;
    padding: 10px;
    border: 10px solid #000;
    display: inline-block;
  }
</style>
  <div style="background: red"></div>
  <div style="background: blue"></div>
```

- Stiched 쓰는 법: outline과 border를 쓰면 됨...
- Outline 응용법은 많으니깐, outline box-shadow 많이 나온다!


offset : 

CSS에 속성을 주거나, 태그에 포함관계를 만들어서 지시를 내림.
지시를 내릴 때, 완벽하게 내리지 않고, 추상적으로 내림.
근데, 아무리 추상적으로 내려도 geometry계산이 끝나면 Fixed로 그려짐.
우리가 준 명령을 다 계산한 결과는 숫자로 변환됨. 이 숫자들을 offset이라고 부름.


offset : ~로부터 얼마만큼 떨어진 이라는 뜻.
실제 그림은 브라우저가 우리가 준 요청대로 그리는데, 계산은 브라우저 마음대로 그림.

HTML Rendering System을 실제 그리는 건 브라우저임....
브라우저는 효율적인 계산을 위해 지오메트리 계산을 한 번에 몰아서 하려고 함.

각각 요소들을 움직이는 것만 따로 모아두었다가 한 번에 계산하려고 함. 한 번에 묶어서 계산하는 단위를 frame이라고 함.
Offset은 웬만하면 요청 안하는 게 상책.
Offset은 조회전용일 때는 많이 불러도 상관없음.
우리는 브라우저에게 요청했을 뿐이고, 결과를 보고하는 걸 offset이라고 함.


HTML과 CSS를 연습장에 그려야 한다고 생각해보자.
Offset을 계싼하는 가장 기본적인 로직.
기준점: Offset parent

Offset Parent와 DOM Parent는 별개

Static && Rel





Position: relative를 쓰는 이유? static으로 그리고 있었는데, 특정 영역에 absolute로 그리고 싶을 때, relative를 부모로 만들어서 사용함.



>  offsetLeft | offsetTop | offsetWidth | offsetHeight

> offsetScrollTop | offsetScrollLeft | offsetScrollWidth | offsetScrollHeight



### position: static한테 Left, top을 주면? 개무시

### position: absolute한테 left, top을 주면? offset parent로부터의 거리

### position: relative한테 left, top을 주면? normal flow가 그려졌을 때부터의 거리



left, top => 중의적인 표현을 갖고 있음.

float는 normal flow일 때만 성립한다. 왜 ? BFC일 때만 작동하니깐.







