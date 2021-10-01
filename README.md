# mysql-important

#MYSQL에 관한 것들


- EXPLAIN 꼭 써서 사용.
- 실행 계획 확인
- `EXPLAIN 타입컬럼에 index` 써있는거랑 `Extra 컬럼에 index` 써있는거랑 `매우 큰차이`
- 타입에 있으면 `Full인덱스 스캔이 되기때문에 비추.`
- Extra 컬럼에 있으면 `Covering 인덱스찾음 추천.`
- 5.0 이후 index_merge 최적화


- `정규화`는 무조건 필수! 
- 가장 `작은 데이터 타입`을 쓸것 ( TINYINT )
- 가장 `작은 데이터 타입`을 쓸것 ( TINYINT )
- `인덱스` 걸리는 필드는 `최소한 데이터 크기`
- `IP는 INT UNSIGNED로` 데이터타입할것 (내장 `INET_ATON` 함수사용)
- 스토리지 엔진은 적합한 걸로 사용한다. (아래)
    - 트랜잭션을 지원하며, 커밋, 롤백, 데이터복구 기능 제공 (데이터보호)
    - row-level locking 제공, CRUD 할때 각 row별로 lock을 걸어 multi-thread보다 효율적.
    - 최대 65535 바이트

|엑세스 패턴| 적합한스토리지 엔진|
|---|:---:|
| INSERT만 한다 | MyISAM |
| 갱신빈도가 높다 | InnoDB | 
| 트랜잭션 필요  | InnoDB |
| SELECT COUNT(*) 사용 | MyISAM |


- REPLACE IN TO 사용 / 유니크키로 설정되어있어야 update 됨.


####최적화관련
- EXPLAIN EXTENDED 명령을 실행 한 후에 SHOW WARNINGS 명령을 실행하면 실제 실행되는 최적화된 쿼리를 보여줌


```mysql
# 임시테이블생성
    CREATE 'TEMPOPARY' TABLE t1(f1 INT);
```
- 중복제거 DISTINCT ( GROUP by 보다 빠름)ㅣ



