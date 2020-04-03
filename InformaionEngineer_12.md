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

>### 1. DML의 개념
>
>- 데이터베이스 사용자가 응용 프로그램이나 질의어를 통해 저장된 데이터를 실질적으로 관리하는데 사용되는 언어이다.
>- DML은 데이터베이스 사용자와 데이터베이스 관리 시스템 간의 인터페이스를 제공한다.
>- DML의 유형
>  - INSERT
>  - SELECT
>  - DELETE
>  - UPDATE
>
>### 2. INSERT INTO~
>
>```sql
>INSERT INTO 테이블명 (속성명1, 속성명2,) VALUES (데이터1, 데이터2)
>```
>
>- 튜플을 삽입할 때 사용한다.
>- 속성과 데이터 개수는 일치해야 한다.
>- 모든 속성을 사용할 때는 속성명을 생략할 수 있다.
>- SELECT문을 이용해서 다른 테이블의 검색 결과를 삽입할 수 있다.
>
>### 3. DELETE FROM~
>
>```sql
>DELETE FROM 테이블명 [WHERE 조건]
>```
>
>- 조건을 안쓰면 모든 레코드를 삭제한다.
>- 모든 레코드를 삭제하더라도 테이블 구조는 남아있으므로 DROP과는 다르다.
>
>### 4. UPDATE ~ SET ~
>
>```sql
>UPDATE 테이블명
>SET 속성명 = 데이터
>[WHERE 조건]
>```
>
>- 조건이 일치하는 튜플에서 속성에 해당하는 값을 데이터로 고친다.

### 105. DML - SELECT1

> ### 1. 일반형식
>
> ```SQL
> SELECT [PREDICATE] [테이블명.]속성명 [AS 별칭] [,[테이블명.]속성명 [AS 별칭]]
> [,그룹함수(속성명)[AS 별칭]]
> [, Window함수 OVER (PARTITION BY 속성명1, 속성명2...) ORDER BY 속성명3, 속성명4, ...]
> FROM 테이블명[,테이블명, ...]
> [WHERE 조건]
> [GROUP BY 속성명, 속성명, ..]
> [HAVING 조건]
> [ORDER BY 속성명 [ASC | DESC]]
> ```
>
> - SELECT절
>   - PREDICATE : 불러올 튜플 수를 제한할 명령어를 기술한다.
>     - ALL : 모든 튜플을 검색, 주로 생략
>     - DISTINCT : 중복된 튜플이 있으면 첫번째 한개만 검색
>     - DISTINCTROW : 중복된 튜플을 제거하고 한 개만 검색하지만 선택된 속성의 값이 아닌 튜플 전체를 대상으로 한다.
>   - 속성명
>     - 모든 속성을 검색할 때는 *를 사용한다.
>     - 두개 이상의 테이블을 대상으로 검색할 때는 테이블명.속성명으로 표현한다.
>   - AS
>     - 속성 및 연산의 이름을 다른 제목으로 표시하기 위해 사용된다.
> - FROME절
>   - 질의에 의해 검색될 데이터를 포함하는 테이블명
> - WHERE절
>   - 검색할 조건을 기술
> - OREDER BY절
>   - 특정 속성을 기준으로 정렬하여 검색할 때 사용
>   - 속성명
>     - 정렬의 기준이 되는 속성명
>   - ASC | DESC : 내림차순 오름차순을 정의 생략하면 오름차순
> - 연산자
>   - 연산자 우선순위는 산술>관계>논리
>   - % : 모든 문자를 대표
>   - _: 문자 하나를 대표
>   - \# : 숫자 하나를 대표
>
> ### 2. 기본 검색
>
> ```sql
> SELECT * FROM 사원 
> SELECT DISTINCT 주소 as addr
> SELECT 부서+'부서의 '
> ```
>
> ### 3. 조건 지정 검색
>
> ```sql
> SELECT * FROM 사원 WHERE 부서='기획'
> 
> WHERE 주소 = '서울' OR 주소 = '부산'
> WHERE 주소 IS NULL
> WHERE 이름 LIKE '김%'
> WHERE 생일 BETWEEN #01/01/69# AND #12/31/73#
> ```
>
> ### 4. 정렬 검색
>
> ```sql
> SELECT * FROM 사원 ORDER BY 부서 ASC, 이름 DESC
> ```
>
> ### 5. 하위 질의
>
> ```sql
> SELECT 이름, 주소
> FROM 사원
> WHERE 이름 = (SELECT 이름 FROM 여가활동 WHERE 취미 = '나이트댄스')
> #취미가 나이트댄스인 사원의 이름과 주소를 검색
> 
> SELECT 이름, 주소
> FROM 사원
> WHERE 이름 NOT IN (SELECT 이름 FROM 여가활동)
> #여가활동을 안하는 사원의 이름과 주소를 검색
> ```
>
> ### 6. 복수 테이블 검색
>
> ```sql
> SELECT 사원.이름, 사원.부서, 여가활동.취미, 여가활동.경력
> FROM 사원, 여가활동
> WHERE 여가활동.경력 >=10 AND 사원.이름 = 여가활동.이름
> # 이름으로 조인, 여가경력이 10년이상인 컬럼을 조회
> ```

### 106. DML - SELECT2

> ### 1. 일반 형식
>
> ```sql
> SELECT [PREDICATE] [테이블명.]속성명 [AS 별칭] [,[테이블명.]속성명 [AS 별칭]]
> [,그룹함수(속성명)[AS 별칭]]
> [, Window함수 OVER (PARTITION BY 속성명1, 속성명2...) ORDER BY 속성명3, 속성명4, ...]
> FROM 테이블명[,테이블명, ...]
> [WHERE 조건]
> [GROUP BY 속성명, 속성명, ..]
> [HAVING 조건]
> [ORDER BY 속성명 [ASC | DESC]]
> ```
>
> - 그룹함수 : GROUP BY 절에 지정된 그룹별로 속성을 집계할 함수를 기술
>   - STDDEV : 표준편차
>   - VARIANCE : 분산
>   - ROLLUP(속성명, 속성명) : 속성을 대상으로 그룹별 소계
>   - CUBE(속성명, 속성명) : ROLLUP과 유사한 형태이나 인수로 주어진 대상으로 모든 조합의 그룹별 소계를 구한다.
> - WINDOW 함수 : GROUP BY절을 이용하지 않고 속성의 값을 집계할 함수를 기술
>   - PARTITION BY : WINDOW 함수가 적용될 범위로 사용할 속성을 지정한다.
>   - ORDER BY : PARTITION 안에서 정렬 기준으로 사용할 속성을 지정한다.
>   - ROW_NUMBER() : 윈도우별로 레코드에 대한 일련번호 반환
>   - RANK() : 윈도우별로 순위를 반환하며, 공동순위를 반영
>   - DENSE_RANK() : 윈도우별로 순위를 반환하며, 공동순위를 무시
> - GROUP BY절 : 특정 속성을 기준으로 그룹화하여 검색할 때 사용한다.
> - HAVING 절 : GROUP BY와 함께 사용되며, 그룹에 대한 조건을 지정한다.
>
> ### 2. WINDOW 함수 이용 검색
>
> ```sql
> SELECT 상여내역, 상여금, ROW_NUMBER() OVER(PARTITION BY 상여내역 ORDER BY 상여금 DESC)
> FROM 상여금
> ```
>
> ### 3. 그룹 지정 검색
>
> ```sql
> SELECT 부서, AVG(상여금)
> FROM 상여금
> GROUP BY 부서
> 
> SELECT 부서, COUNT(*)
> FROM 상여금
> WHERE 상여금 >= 100
> GROUP BY 부서
> HAVING COUNT(*) >=2
> ```
>
> ### 4. 집합 연산자를 이용한 통합 질의
>
> ```sql
> SELECT 속성명1, 속성명2
> FROM 테이블명
> UNION | UNION ALL | INTERSECT | EXCEPT
> SELCET 속성명, 속성명2
> FROM 테이블명
> ```
>
> - 두 개의 SELECT 문에 기술한 속성들은 개수와 데이터 유형이 서로 동일해야 한다.
> - 집합연산자
>   - UNION : 중복된 행은 한번만 출력하는 합집합
>   - UNION ALL : 중복된 행도 계속 출력하는 합집합
>   - INTERSECT : 공통된 행만 출력
>   - EXCEPT : 첫 번째 SELECT문에서 두번째 SELECT 문의 결과를 제외한 행을 출력

### 107. DML - JOIN

> ### 1. JOIN의 개념
>
> - 2개의 테이블에 대해 연관된 튜플을 결합하여, 새로운 릴레이션을 반환한다.
> - 일반적으로 FROM절에 기술하지만, 릴레이션이 사용되는 어느 곳에서나 사용할 수 있다.
>
> ### 2. INNER JOIN
>
> - 일반적으로 EQUI JOIN과 NON-EQUI JOIN으로 구분된다.
>
> - 조건이 없는 INNER JOIN을 수행하면 CROSS JOIN과 동일한 결과를 얻을 수 있다.
>
> - EQUI JOIN
>
>   - WHERE절에서 =로 비교하는 연산이라고 생각해도 된다.
>   - JOIN후에 동일한 컬럼이 2번 나타나게 되는데 중복을 제거하는 방법을 NATURAL JOIN이라고 한다.
>   - 연결고리가 되는 공통 속성을 JOIN속성이라고 한다.
>
>   ```sql
>   WHERE 학생.학과코드 = 학과.학과코드
>   
>   FROM 학생 NATURAL JOIN 학과
>   
>   FROM 학생 JOIN 학과 USING(학과코드)
>   # 모두 같은 결과를 나타낸다.
>   ```
>
> - NON-EQUI JOIN
>
>   - =조건이 아닌 > < 연산자를 이용하는 JOIN 방법이다.
>
>   ```sql
>   SELECT 학번, 이름, 성적, 등급
>   FROM 학생, 성적등급
>   WHERE 학생.성적 BETWEEN 성적등급.최저 AND 성적등급.최고
>   ```
>
> ### 3. OUTER JOIN
>
> - 릴레이션에서 JOIN조건에 만족하지 않는 튜플도 결과로 출력하기 위한 JOIN 방법
> - LEFT OUTER JOIN
>   - INNER JOIN의 결과를 구한 후, 우측 항 릴레이션과 맞지 않는 좌측 항에 있는 튜플들에 NULL 값을 붙여 INNER JON 결과에 추가한다.
> - RIGHT OUTER JOIN
>   - INNER JOIN의 결과를 구한 후, 좌측 항 릴레이션과 맞지 않는 우측 항에 있는 튜플들에 NULL 값을 붙여 INNER JON 결과에 추가한다.
> - FULL OUTER JOIN
>   - LEFT, RIGHT 방식을 합쳐 양쪽에 NULL 값을 붙인다.
>
> ### 4. SELF JOIN
>
> - 같은 테이블에서 2개의 속성을 연결하여 EQUI JOIN하는 방법이다.
>
> ```sql
> SELCET A.학번, A.이름, B.이름 as 선배
> FROM 학생 A JOIN 학생 B
> ON A.선배 = B.학번;
> ```

