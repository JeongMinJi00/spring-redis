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
