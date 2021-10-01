##mysql 쿼리 프로파일링

- mysql 쿼리 프로파일링관련 
    - 쿼리가 처리되는 동안 각 단계별 작업에 시간이 얼마나 걸렸는지 확인.
    
- 기본적으로 활성화가 되어있지 않기때문에 사용시 먼저 프로파일링 기능 활성화
- mysql 5.1 이상부터 지원

#### 프로파일링 설정 On/Off 확인
 ```sql
show variables LIKE '%profiling%';
```

#### 프로파일링 On 으로 설정
```sql
SET profiling = 1;
```


#### 사용된 쿼리 전체 확인
```sql
show profiles;
```

#### 프로파일링 히스토리 크기 확인
```sql
show variables LIKE '%profiling_history_size%';
```
- *_profiling_* 은 모두저장되는게 아니고 *_profiling_history_size_*에 설정된 만큼 저장됨.
- 기본값으로 **__15 rows__** 쿼리에 대해서 저장되며 최대 100까지 설정가능함.


#### 프로파일링 FOR QUERY (상세조회)

```sql
show profile for query 1;
```

- for query [쿼리번호]를 사용.
- 쿼리번호는 show profiles에서 조회된 Query_ID임


#### 프로파일링 상세조회 (CPU, MEMORY, DISK)

```sql
show profile cpu for query 1;
```

- CPU 키워드 대신 BLOCKID, MEMORY, SOURCE 키워드도 사용 가능
