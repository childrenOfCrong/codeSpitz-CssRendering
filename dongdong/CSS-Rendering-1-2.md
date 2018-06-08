# Float

> Left | Right | None | Inherit

Float: BFC, IFC가 아니라, line box 공식으로 그려진다.

Normal Flow : IFC, BFC, Relative 공식으로 그려진다.



## BFC + Float

```html
<div style="width: 500px">
  <div style="height: 50px; background: red"></div>
  <div style="
              width: 200px; 
              heigth: 150px; 
              float: left; 
              background: rgba(0,255,0,0.5);"></div>
  <div style="
              height: 50px; 
              background:skyblue;"></div>
</div>
```

![bfc-float](/Users/dongwoolee/Documents/Dev/codeSquad/codeSpitz-CssRendering/dongdong/bfc-float.png)



기존 BFC 박스(빨간색)가 있었는데도 불구하고, Float가 등장하는 순간 새로운 BFC 영역이 등장.

Float는 추가적인 BFC 박스를 만드는 역할을 한다.

새로 만든 BFC 영역의 공간은 Float영역이 만들어진 공간부터 inline영역이 차지하는 공간 끝까지이다.





## Text, Inline Guard

```html
<div style="width:500px">
  <div style="height: 50px; background: red"></div>
  <div style="width: 200px; height: 150px; float:left; background:rgba(0,255,0,0.5)"></div>
  Hello
  <div style="height: 50px; background: skyblue">
    World
  </div>
  !!
</div>
```

![inline-guard](/Users/dongwoolee/Documents/Dev/codeSquad/codeSpitz-CssRendering/dongdong/inline-guard.png)

"Hello"는 inline으로 들어왔으니, 초록색 박스에 그려져야 하는데, float는 inline에 가드 역할을 하니깐 가드 밖에 그려짐.

SkyBlue는 Block 요소이므로 박스 자체는 다 그려짐. 그러나 skyblue 안에 있는 inline요소는 DOM의 포함관계와 상관없이 inline요소로 작동해서 초록색 박스 밖에 그려짐. 일단 Float가 만들어지면, inline은 못들어감. **Float는 인라인 요소에 대해서 가드로 작동한다.** Block요소는 Float될 뿐, 그림은 다 그려짐. div는 다 그려지고, inline만 가드됨.



## Line Box

- 라인박스를 계산할 때는 플로트만 신경씀.
- 전체 영역에서 플로트가 들어가면, 들어간 플로트만큼 라인박스가 줄어듬. 
- 즉, 플로트가 들어가서 남은 영역만 라인박스가 됨.
- 라인박스는 가로 뿐만 아니라 세로도 봄.
- Float는 inline 요소의 가드역할을 하지만 Block 요소는 가드하지 않음.
- 각 라인박스의 하단 경계면에 맞추어 다음 라인박스가 그려짐.



# Overflow

> CSS2.1 Visual Formatting Model
>
> Visible | Hidden | Scroll | Inherit | Auto

Visible: 보일 때 까지 커진다.(일반적인 브라우저는 visible이 auto)

Hidden: 내 geometry를 넘어가는 영역이 생기면 자름.

Scroll: 내 geometry를 벗어나는 영역이 발생하면 스크롤바를 만듬.

Inherit:

Auto(디폴트): 내부의 크기가 커지면 부모도 같이 커진다. 즉, Geometry의 크기가 직접 변함

* overflow가 hidden || scroll 일 때는 값을 가진 요소로부터 새로운 BFC를 즉시 생성. 

  
