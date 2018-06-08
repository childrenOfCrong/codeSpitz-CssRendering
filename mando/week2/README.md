# 2주차

## modern box

box model(margin, border, padding, content)이 모던 브라우저로 넘어오면 outline, box-shadow, box-shadow inset를 포함하여 총 7개를 사용할 수 있다.

* box-shadow: border처럼 사용할 수 있다. 마진과 겹쳐진다. 여러 번 쓸 수 있다.
* box-shadow inset : 보더 안쪽에 그림자 그려준다. 패딩과 겹쳐진다.
* outline: 박스 섀도우와 같은 위치에 그린다. 마찬가지로 크기를 잡아먹지 않는다. 단, box-shadow와는 다르게 border-radius가 적용되지 않는다.

세 특성의 공통점: 프래그먼트단계에서 작동한다. 즉, 지오메트리(크기)에 변경을 주지 않는다.

## BOX-SIZING

`box-sizing: border-box`

디폴트로 content를 기준으로 박스 사이즈가 정해지는데, border-box를 이용하면 border를 기준으로 사이즈가 정해진다.

그림을 그려주는 fragment의 영역은 border박스 까지다: background가 border영역까지 그려지는 이유



## BOX-SHADOW

`box-shadow: 0 0 0 10px #000`

fragment가 다 그려진 이후에 그려지므로 box-shadow가 다른 엘리먼트를 덮게 된다.

**relative를 쓴다면?**

`position; relative`속성은 static을 전부 그려주고 마지막으로 그려주기 때문에 다시 relative 속성을 가진 엘리먼트가 다른 엘리먼트를 덮게 된다.



## BOX-Shadow inset

`box-shadow: inset 0 0 0 10px #000`

여러 박스 쉐도우가 필요한 경우 컴마로 쉽게 구분하면 된다.

`box-shadow: 0 0 0 10px #000 ,inset 0 0 0 10px #000`

**주의**

선언의 반대 순서로 그려진다.

```css
div {
    box-shadow:
        0 0 0 10px #aa0,
        0 0 0 20px #0a0 // 먼저 그려짐
}
```



## BOX-Shadow animation

```css
@keyframes ani {
    from { transform: rotate(0deg)}
    to {}
    /*
    0% {}
    50% {}
    100%{}
    */
}
div {
    animation: ani 5s infinite;
}
```



## OUTLINE

stitched

```css
background: brown;
width: 100px;
height: 100px;
border-radius: 15px;
outline: 7px solid brown;
border: 1px dashed;
box-shadow: 0 0 0 7px brown;
```



## POSITION

**offset이란**

offset: 지오메트리 계산이 다 끝난 후 fixed number로 바뀐 숫자. 참고할 수 있지만 변경할 수 없다.

offset을 요청할 경우 계산을 지오메트리 계산을 다시 하기때문에 레이아웃을 그리는 와중에 다시 요청하지 않는게 좋다. 지오메트리 계산을 끝난 후에 요청하는 것은 괜찮다.



**Offset parent**

>  offset parent: offset의 기준이 되는 것

`position: absolute`의 경우 dom tree의 영향을 받지 않느다.



1. null(오프셋 패런트가 없는 경우)
   * root, html, body
   * position: fixed
   * dom tree 바깥에 있는경우(createNode를 이용해 생성된 노드 등)
2. recursive search(오프셋 페런트를 찾는 과정)
   * parent.position.fixed = null(끝)
   * parent.position.!static = ok
   * body = ok
   * td, th, table = ok
   * ok일 경우 계속 찾으러 위로 올라간다.
   * 즉, position: `abolute` or `relative`인 경우만 부모로 인식한다.
   * 이런 이유때문에static흐름 내에서 absolute를 사용하고 싶다면  relative를 absolute의 컨테이너로 사용한다.



**offset value**

보이는 영역

offsetLeft

offsetTop

offsetWidth

offsetHeight



진짜 컨텐츠의 영역

offsetScrollTop

offsetScrollLeft

offsetScrollWidth

offsetScrollHeight



## Absolute

absolute의 **기본값은 DOM상의 부모**의 위치를 따른다!(static과 같다)

```html
<div style='margin: 100px'>
   <div style='pos: absolute'>
       hi
    </div>
</div>
```

* hi의 위치는 기본값으로 부모의 위치(마진을 적용한)를 offparent르 잡는다
* top을 주기 시작하면 offparent를 다시 찾아 정한다.

