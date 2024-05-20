# MongoDB

## RDBMS 용어와 비교

| RDBMS | | MongoDB |
| --- | --- | --- |
| Database | | Database |
| Table | | Collection |
| Tuple / Row | | Document |
| Column | | Key / Field |
| Table Join | | Embedded Documents |
| Primary Key | | Primary Key (_id) |

- Document 기반의 데이터베이스 <-> RDBMS는 Row 단위의 레코드 기반
- 각각의 Document에는 _id 라는 ObjectID 타입의 값을 가짐
- BASE(Basically Available, Soft state, Eventually consistent): 가용성을 우선시

## MongoDB 실습

> 실습 환경  
> MongoDB: 7.0.2  
> Mongosh: 2.0.2  

## 서버 준비 및 접속

```bash
> mongod # 서버 준비
> mongosh # 서버 접속 (또 다른 cmd 창)
```

## 데이터베이스 생성 use

```bash
> use mongodb_test
switched to db mongodb_test
```

```bash
> db # 현재 사용 중인 데이터베이스 확인
mongodb_test
```

```bash
> show dbs # 데이터베이스 리스트 확인
admin   40.00 KiB
config  60.00 KiB
local   72.00 KiB
```

리스트에서 만든 데이터베이스를 보려면 최소 1개의 `Document`를 추가

```bash
> db.book.insert({'name':'MongoDB Test', 'author':'seongmin'});
admin         40.00 KiB
config        60.00 KiB
local         72.00 KiB
mongodb_test   8.00 KiB
```

## 데이터베이스 제거 db.dropDatabase()

```bash
> mongodb_test> db.dropDatabase();
{ ok: 1, dropped: 'mongodb_test' }
```



