# spring-redis

## redis 란
- Key-Value 구조의 비정형 데이터를 저장하고 관리
- in-memory 데이터 구조 저장소
- 고성능 키-값 저장소로서 String, list, hash, set, sorted set 등의 자료 구조를 지원하는 NoSQL

### 장점
- 리스트, 배열과 같은 데이터를 처리하는데 유용
- 메모리를 활용하면서 영속적인 데이터 보존
- Message Queue, Shared Memory, Remote Dictionary(RDBMS의 캐시 솔루션 / read 속도가 매우 빠름) 용도로 사용
- Redis Server는 1개의 싱글 쓰레드로 수행되며, 서버 하나에 여러개의 서버를 띄우는 것이 가능



#### 1. Lettuce
- 구현이 간단하다
- spring data redis 를 이용하면 lettuce 가 기본이기때문에 별도의 라이브러리를 사용하지 않아도 된다.
- spin lock 방식이기때문에 동시에 많은 스레드가 lock 획득 대기 상태라면 redis 에 부하가 갈 수 있다.

#### 2. Redisson 
- 락 획득 재시도를 기본으로 제공한다.
- pub-sub 방식으로 구현이 되어있기 때문에 lettuce 와 비교했을 때 redis 에 부하가 덜 간다.
- 별도의 라이브러리를 사용해야한다.
- lock 을 라이브러리 차원에서 제공해주기 때문에 사용법을 공부해야 한다.


```
재시도가 필요하지 않은 lock 은 lettuce 활용하고 재시도가 필요한 경우에는 redisson 를 활용
```
