CustomView 에서 제일 중요한 3가지 함수는 아래 3함수이다. 

- onMeasure
	- 뷰 크기 측정 단계
- onLayout  
	- 뷰 위치, 크기 할당 단계
	- View Group[[View Group]] 을 반드시 구현해주어야 한다.
- onDraw
	- 뷰를 실제로 그리는 단계
	- Canvas [[Canvas]]
	- Paint [[Paint]]

## View Update
- invalidate()
- requestLayout()