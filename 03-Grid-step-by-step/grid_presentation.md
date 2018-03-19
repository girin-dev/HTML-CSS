
# Grid for layout
곽규원
* `HOW TO CREATE A CSS GRID STEP-BY-STEP`

---

# Grid란?
수평선과 수직선이 교차해서 이루어진 집합체  
css에서 레이아웃을 잡기 위해 추천되는 방식  

가능환경
IE 10(부분지원), Edge 12, Chrome 57, Safari 10.1 이상 등
Opera mini, Opera for Android, qq, baidu 사용 불가(2018년 3월 현재, https://caniuse.com/)
---

## 적용을 위한 container의 attribute
1. display: grid
    * block-level의 그리드
2. display: inline-grid
    * inline-level의 그리드

---

## fr 단위
* grid container grid를 위한 fraction unit(파편 조각)
* 그리드 컨테이너에 남아있는 사용가능한 공간의 일정 비율(상대적)
* repeat() 표기법
```css
.wrapper {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    /* grid-template-columns: 1fr 1fr 1fr */
}
```
---

# grid 
* grid-template-columns(세로 열)
* grid-template-rows(가로 행)
* 잠재적 그리드
`grid-template-columns`를 이용하여 세로 열의 트랙만을 정의하였을 경우, 가로 행은 그리드가 알아서 새로운 행을 생성하도록 함.
* 명시적 그리드
`grid-template-columns`, `grid-template-rows`를 이용해서 직접 정의한 행과 열로 이루어진 그리드. 이때 정의한 그리드 외부에 콘텐츠가 늘어나면 그리드가 잠재적으로 새로운 행과 열을 만들게 됨.

---

* grid-auto-rows와 grid-auto-columnns
잠재적 그리드에서 생성된 트랙의 크기를 지정할 수 있음.
* `minmax()`
rows, columns의 값으로 넣어 그리드 크기의 최소, 최대값을 정해줄 수 있다.

---

## grid item 간 간격 조정
* grid-gap
* grid-column-gap
* grid-row-gap

---

## grid item 포지셔닝(위치)
* grid positioning
    * grid-column
    * grid-row  
```css
.item-1 {
    grid-column: 3; 
	grid-row: 2;
}
```
명확한 위치를 적시하지 않으면 다른 grid item들의 위치에 영향을 줄 수 있음(잠재적 그리드의 영향)

---

## grid item 사이징(크기)
좌상 첫줄부터 1로 시작하는 오름차순으로 순서가 매겨져 있음
* grid sizing
    * grid-column-start / grid-row-end / grid-column
    * grid-row-start / grid-row-end / grid-row
```css
.item-1 {
	grid-column-start: 1;
    	grid-column-end: 4;
        /* grid-column: 1/4; */
}
```

---

## grid item 이름붙이기와 그 활용
* grid-area
* grid-template-areas
```css
.container {
	grid-template-areas: "header header header"
    			     "side-1 main side-2"
			     "footer footer footer";
}
.item {
	grid-area: header;	
}
```

---

## grid는 중첩해서 사용 가능하다.
* grid nesting 가능한 속성


