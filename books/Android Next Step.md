  
## Android Framework
- Android Architecture 개요  
	- Application
	- Application Framework
	- Android Runtime
	- Library
	- Linux Kernel
- Framework Source
- Android Version
	- 호환성 mode
	- 호환성 mode 동작 예시
	- 단말 Version Check
  
## Main Thread와 Handler  
- UI 처리를 위한 Main Thread
- Looper Class
- Message와 MessageQueue  
- Handler Class  
	- Handler 생성자  
	- Handler 동작  
	- Handler 용도  
	- Handler Timing Issue
- UI 변경 Mecanism
- ANR  
	- ANR Time out
	- Framework ANR 판단  
  
## Background Thread
- HandlerThread Class  
- Thread Pool 사용
	- ThreadPoolExecutor Class
	- ScheduledThreadPoolExecutor Class
	- Executors Class
- AsyncTask Class  
	- Background Thread와 UI Thread 구분  
	- Activity 종료 시점과 불일치  
	- AsyncTask 취소  
	- 예외 처리 method 없음  
	- 병렬 실행 시 doInBackground() 실행 순서가 보장되지 않음  
  
4장 Context  
  
5장 Activity  
- 생명주기  
	- Activity 생명주기 Diagram  
	- 생명주기 method 호출 시점  
	- Activity 시작 메서드  
	- Activity 전환 시 생명주기 method 호출  
	- 생명주기 method 사용 시 주의사항  
- 구성 변경 (configuration change)  
	- Resource 반영  
	- 구성 변경으로 인한 Activity 재시작  
	- Framework source 확인  
	- 구성 한정자  
	- data 복구  
	- android:configChanges 속성  
	- Configuration class의 변수 확인  
- Task
	- Task 상태  
	- dumpsys 명령어로 Task 확인  
	- taskAffinity 속성  
	- Task 속성 부여  
- 〈activity-alias〉 선언  
  
## Service  
- Started Service
	- Service 재시작 방식  
	- Multi Thread Issue
	- 외부 Process에서 암시적 Intent로 서비스 시작  
	- IntentService Class 
	- Service 중복 실행 방지  
- Bound Service
	- Remote Binding 
	- Local Binding 
	- Binding의 특성  
	- Messenger Class
  
## Content Provider
- SQLite  
	- sqlite shell  
	- DB Lock 문제  
	- SQLiteOpenHelper 클래스  
- Content Provider  
	- 로컬 프로세스에서 Content Provider 적용 기준  
	- Content Provider 예제  
	- 배치 실행  
- SQLite/ContentProvider 관련 팁  
	- Query 실행 확인  
	- Content Provider 예외 확인  
  
## Broadcast Receiver
- Broadcast Receiver 구현  
- Broadcast Receiver 등록  
	- Broadcast Receiver 정적 등록  
	- Broadcast Receiver 동적 등록  
- 오더드 Broadcast Receiver  
- 스티키 Broadcast Receiver
- LocalBroadcastManager Class
- App Widget
	- App Widget의 특성  
	- AppWidgetProvider Class
	- RemoteViews Class  
	- App Widget Update
	- 유의할 점  
  
## Application  
- App 초기화  
- Application 콜백  
	- ComponentCallbacks2 Interface
	- Application에 등록하는 Callback 
- Process 분리  
	- Process 분리가 필요한 때  
	- 분리된 Process에서 Application은 새로 시작  
	- Process 분리 시 주의할 점  
  
## System Service
- System Service 기본  
- dumpsys 명령어  
- System Service Issue  
	- 빈번한 Remote 호출을 줄여야 함  
	- 전원 관리와 Deep Sleep 
	- Alram 등록과 제거  
  
## 구현 Pattern 
- SingleTone Pattern 
	- SingleTone에 Context를 전달하는 방법  
	- Memory Leak 검증  
- Marker Interface  
- Fragment 정적 생성