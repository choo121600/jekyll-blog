---
layout: post
type: tech
date: 2022-01-01 05:43
category: MySQL
title: MySQL 기본 명령어
tech-header: true
hash-tag: [MySQL]
---


## 수식어
---
- SHOW -> DB, Table을 보기
- CREATE -> DB, Table을 생성
- USE -> DB 사용
- SELECT -> data를 보기
- INSERT -> 레코드 삽입
- UPDATE -> 데이터 업데이트
- DELETE -> 레코드 삭제
- DROP -> DB, Table 삭제
- ALTER -> 정보 수정

## 응용
#### DB 생성
```
$ CREATE DATABASE 데이터베이스이름;
```

#### DB 사용
```
$ USE 데이터베이스이름;
```

#### Table 생성
```
$ CREATE TABLE 테이블명({
    필드명 형식 공란허용여부 자동증가여부,
    ...
});
```
#### 데이터 삽입
```
$ INSERT INTO 테이블명(필드명, ...) VALUES ('데이터1', '데이터2', ...);
```

#### 데이터 모두 보기
```
    $ SELECT * FROM 테이블명
```

#### 데이터 일부 수정
```
    $ UPDATE 테이블명 SET 수정필드명="변경값" WHERE 조건필드명="조건값"
```

#### 데이터 일부 삭제
```
    $ DELETE FROM 테이블명 WHERE 필드명="값"
```