# Effective_kotlin

## 좋은 Code

### 안정성

- 가변성 제한
- 변수 scope 최소화
- platform type 사용 자제 (?)
- inferred type return X
- 예외로 코드 제한
- 표준 오류 사용(사용자 오류 자제)
- null 과 Failiure 사용
- 적절하게 null 처리
- use 사용, resource 관리
- unit test

### 가독성

- 가독성 목표 설계
- 연산자 overload시 의미에 맞게
- Unit? return  X
- 변수type 명확하게
- Receiver 명시적 참조
- Property는 동작이 아닌 상태
- 이름있는 Argument
- Coding convention 지켜라

## Code 설계

### 재사용성

- kmowledge 반복 사용 X
- 일반적인 algorithm 반복 구현 X
- 일반적인 property pattern → property delegate
- Generics
- Type Parameter Shadowing X
- Generics Type variance 한정자(공변성) 활용
- 공통 module 추출해서 여러 platform X

### 추상화 설계

- 추상화 level 통일
- Code 보호는 → 추상화
- API 안정성 확인
- 외부 API 는 wrap 해서 사용
- 가시성 최소화
- 문서로 규약 정의
- 추상화 규약

### 객체 생성

- Item 대신 Factory 함수 사용
- 기본 생성자에 있는 이름있는 옵션 Argument 사용 (Java로 만들어진 것은 안됨)
- 복잡한 객체 생성하기 위한 DSL 정의

### Class 설계

- 상속보다는 컴포지션
- data 결합 표현 data 한정자 사용
- 연산, action 전달은 고차 함수
- 태그 class 보다 class 계층
- equals 규약
- hashCode 규약
- compareTo 규약
- API 필수적이지 않는 부분은 확장 함수 추출
- Member 확장 함수 사용 X

## 효율성

### 비용줄이기

- 불필요한 객체 생성 X
- 함수 type parameter 함수 inline
- inline class
- 사용하지 않는 객체 reference는 제거

### 효율적인 Collection 처리

- 하나 이상의 처리 단계를 가지는 경우 Sequence 사용
- Collection 처리 단계 수 제한
- 성능 중요 부분은 기본 자료형 배열
- mutable collection 사용 고려
