![[Pasted image 20221106231715.png]]

오프라인 first app 은 기본적으로 data layer 에서 최소 2가지 DataSource 에서 데이터를 얻어온다.
Data layer 는 Reading, Writing 이다. 

로컬과 네트워크 환경을 맞추기 위해서는 Synchronization 이 중요, Synchronization는 pull-based, push-based 가 있다. 

## Conflict resolution
이 상황에서는 last write wins 전략을 사용한다. 
