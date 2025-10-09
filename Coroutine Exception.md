## launch catching
- try catch 를 하는 경우 launch 밖에서 처리하면 exception 을 가지고 올 수 없다. 
- launch 안에서 처리해야 한다.

### async catching
- async 는 await 를 호출하는 시점에서 throw 를 뱉는다.

### coroutineScope
- coroutineScope 안에서 launch 를 여러 개를 실행할때, 하나의 launch 가 실패한다면 다른 launch 취소된다.

### supervisorScope
- 이를 하고 싶지 않다면 supervisorScope 를 사용하면 된다.하지만 cancel 를 막는 것이기 때문에 여타 Throw 를 막진 않는다. 

### CoroutineExceptionHandler
- launch, async. scope 등에서 넣어줄 수 있으면 글로벌하게 처리할 수 있다. 