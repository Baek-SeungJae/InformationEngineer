# 정보처리기사

## 12. SQL 응용

### 101. SQL의 개념

> ### 1. SQL(Structured Query Language)의 개요
>
> - 1974년 IBM 연구소에서 개발한 SEQUEL에서 유래한다.
> - 국제 표준 DB언어이며, 많은 회사에서 관계형 DB를 지원하는 언어로 채택하고 있다.
> - 관계대수와 관계해석을 기초로 한 혼합 데이터 언어이다.
> - 질의어지만 질의 기능만 있는 것이 아니라 데이터 구조의 정의, 데이터 조작, 데이터 제어 기능을 갖추고 있다.
>
> ### 2. SQL의 분류
>
> - DDL(Date Define Language, 데이터 정의어)
>   - SCHEMA, DOMAIN, TABLE, VIEW, INDEX를 정의하거나 변경, 삭제할 때 사용하는 언어이다.
>   - 논리적 데이터 구조와 물리적 데이터 구조의 사상을 정의한다.
>   - DB관리자나 DB설계자가 사용한다.
>   - DDL의 세 가지 유형
>     - CREATE
>     - ALTER : TABLE에 대한 정의 변경
>     - DROP
> - DML(Data Manipulation Language, 데이터 조작어)
>   - 데이터베이스 사용자가 응용 프로그램이나 질의어를 통하여 저장된 데이터를 실질적으로 처리하는 데 사용되는 언어이다.
>   - 데이터베이스 사용자와 DBMS간의 인터페이스를 제공한다.
>   - DML의 네 가지 유형
>     - INSERT
>     - SELECT
>     - UPDATE
>     - DELETE
> - DCL(Data Control Language, 데이터 제어어)
>   - 데이터의 보안, 무결성, 회복, 병행 수행 제어 등을 정의하는 데 사용되는 언어이다.
>   - DB관리자가 데이터 관리를 목적으로 사용한다.
>   - DCL의 종류
>     - COMMIT
>     - ROLLBACK
>     - GRANT
>     - REVOKE

### 102. DDL

> ### 1. DDL의 개념
>
> - DB 구조, 데이터 형식, 접근 방식 등 DB를 구축하거나 수정할 목적으로 사용하는 언어이다.
> - DDL은 번역한 결과가 데이터 사전이라는 특별한 파일에 여러 개의 테이블로서 저장된다.
>
> ### 2. CREATE SCHEMA
>
> - SCHEMA
>
>   - 데이터베이스의 구조와 제약 조건에 관한 전반적인 명세를 기술한 것
>   - 개체, 속성, 관계 및 데이터 조작 시 데이터들이 갖는 제약조건 등을 정의
>
>   ```SQL
>   CREATE SCHEMA 스키마명 AUTHORIZATION 사용자_id
>   ```
>
>   
>
> ### 3. CREATE DOMAIN
>
> - DOMAIN
>
>   - 하나의 속성이 취할 수 있는 동일한 유형의 원자값들의 집합
>   - ex) 학년을 정의한다면 1~4까지의 값만 갖도록 한다.
>
>   ```SQL
>   CREATE DOMAIN 도메인명 [AS] 데이터타입
>   	[DEFAULT 기본값]
>   	[COSTRAINT 제약조건명 CHECK(범위값)]
>   ```
>
> ### 4. CREATE TABLE
>
> - TABLE
>
>   ```SQL
>   CREATE TABLE 테이블명
>   	(속성명 데이터타입 [DEFAULT 기본값] [NOT NULL],
>       [, PRIMARY KEY (기본키속성명)]
>       [, UNIQUE(대체키속성명)]
>       [, FOREIGN KEY(외래키속성명)
>       	REFERENCES 참조테이블(기본키속성명)]
>       [, CONSTRAINT 제약조건명][CHECK(조건식)])
>   ```
>
> ### 5. CREATE VIEW
>
> - VIEW
>
>   ```SQL
>   CREATE VIEW 뷰명[속성명[, 속성명]]
>   AS SELECT문;
>   ```
>
> ### 6. CREATE INDEX
>
> - INDEX
>
>   ```SQL
>   CREATE [UNIQUE] INDEX 인덱스명
>   ON 테이블명(속성명 [ASC | DESC])
>   [CLUSTER]
>   ```
>
> ### 7. ALTER TABLE
>
> - ALTER문은 TABLE에서만 쓴다.
>
>   ```SQL
>   ALTER TABLE 테이블명 ADD 속성명 데이터타입
>   ALTER TABLE 테이블명 ALTER 속성명 데이터타입
>   ALTER TABLE 테이블명 DROP 속성명 [CASCADE]
>   ```
>
> ### 8. DROP
>
> ```SQL
> DROP TABLE 테이블명 [CASCADE|RESTRICTED]
> ```
>
> - TABLE에는 다른 값이 들어갈 수 있다.
> - CASCADE는 참조중인 모든 개체를 제거한다.
> - RESTRICTED는 제거할 요소를 다른 개체가 참조중이면 제거를 취소한다.

### 103. DCL

> ### 1. DCL의 개념
>
> - 데이터의 보안, 무결성, 회복, 병행 제어 등을 정의하는 데 사용하는 언어이다.
> - DCL은 데이터베이스 관리자(DBA)가 관리를 목적으로 사용한다.
> - DCL에는 GRANT, REVOKE, COMMIT, ROLLBACK, SAVEPOINT 등이 있다.
>
> ### 2. GRANT/REVOKE
>
> - 데이터베이스 관리자가 데이터베이스 사용자에게 권한을 부여하거나 취소하기 위한 명령어이다.
>
> - 사용자 등급 지정 및 해제
>
>   ```SQL
>   GRANT 사용자등급 TO 사용자ID
>   REVOKE 사용자등급 FROM 사용자ID
>   ```
>
>   - DBA, RESOURCE, CONNECT
>
> - 테이블 및 속성에 대한 권한 부여 및 취소
>
>   ```SQL
>   GRANT 권한 ON 개체 TO 사용자 [WITH GRANT OPTION]
>   REVOKE [GRANT OPTION FOR] 권한 ON 개체 FROM 사용자 [CASCADE]
>   ```
>
>   - ALL, SELECT, INSERT, DELETE, UPDATE, ALTER 등
>
>   - WITH GRANT OPTION : 부여받은 권한을 다른 사용자에게 다시 부여할 수 있는 권한을 부여함
>   - GRANT OPTOIN FOR : 다른 사용자에게 권한을 줄 수 있는 권한을 취소함
>   - CASCADE : 연쇄 취소
>
> ### 3. COMMIT
>
> - 트랜잭션이 성공적으로 끝나면 데이터베이스가 새로운 일관성 상태를 가지기 위해 변경된 모든 내용을 데이터베이스에 반영하여야 하는데, 이때 사용하는 명령이 COMMIT이다.
> - DML 이후에 자동으로 COMMIT되도록 AUTO COMMIT 기능을 설정할 수 있다.
>
> ### 4. ROLLBACK
>
> - 아직 COMMIT되지 않은 모든 변경 내역을 취소하고 이전상태로 되돌리는 명령어이다.
> - 일부분만 완료된 트랜잭션은 반드시 Rollback되어야한다.
>
> ### 5. SAVEPOINT
>
> - 트랜잭션 내에 ROLLBACK할 위치인 저장점을 지정하는 명령어이다.
> - ROLLBACK시 지정된 저장점까지의 트랜잭션이 취소된다.

### 104. DML