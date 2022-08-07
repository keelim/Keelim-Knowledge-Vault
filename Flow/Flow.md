일반적인 Flow 는 콜드 스트림을 갖는다. [[Cold vs Hot]]

## Flow 취소
일반적으로 Flow 자체는 취소를 가지는 로직이 없다. 

## Flow 빌더
flow {}

## Flow Context
플로우는 항상 스코프 안에 있는 컨텍스트를 사용한다. 
## 연산자
### 중간 연산자
- map
- filter
- transform
### 종단 연산자
- reduce
- fold

### 기타 연산자
- flowOn
- buffer
- conflate
- collectLatest
- flatMapConcat
- flattenConcat
- flatMapMerge
- flattenMerge
- flatMapLatest
- catch
- onCompletion
- onEach
- launchIn

### 종류
- StateFlow[[StateFlow]]
- SharedFlow[[SharedFlow]]
- Channel[[Channel]]
