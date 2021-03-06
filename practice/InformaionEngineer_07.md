# 정보처리기사

## 7. 데이터 조작 프로시저 최적화

## 1. 데이터 조작 프로시저 성능 개선

### 1-1. 쿼리 성능 개선(튜닝)의 개념

> - 데이터베이스에서 프로시저에 있는 SQL 실행 계획을 분석, 수정을 통해 최소의 시간으로 원하는 결과를 얻도록 프로시저를 수정하는 작업이다.
>- SQL 성능 개선을 통해 데이터 조작 프로시저의 성능 개선이 가능하다.

### 1-2. 쿼리 성능 개선 절차

> - 문제있는 SQL 식별
>
>   - 모니터링 도구인 APM등을 활용
>
>     > - APM : 안정적인 시스템 운영을 위해 부하량, 접속자 파악 및 장애진단 등을 목적으로 하는 성능 모니터링 도구를 의미한다.
>
> - 옵티마이저 통계 확인
>
>   - 옵티마이저는 개발자가 작성한 SQL을 가장 빠르고 효율적으로 수행할 최적의 처리 경로를 생성해주는 핵심 모듈
>
> - SQL문 재구성
>
>   - 범위가 아닌 특정 값 지정으로 범위를 줄여 처리속도를 빠르게 함
>   - 옵티마이저가 비정상적인 실행계획을 수립할 경우, 힌트로서 옵티마이저의 접근 경로 및 조인 순서를 제어
>
> - 인덱스 재구성
>
>   - 성능에 중요한 액세스 경로를 고려하여 인덱스 생성
>   - 실행계획을 검토하여 기존 인덱스의 열 순서를 변경/추가
>
> - 실행계획 유지관리
>
>   - 데이터베이스 버전 업그레이드, 데이터전환 등 시스템 환경의 변경 사항 발생시에도 실행계획이 유지되고 있는지 관리

### 1-3. 옵티마이저 통계 확인

> ### 1. 옵티마이저의 개념 - `CBO vs RBO`
>
> - SQL을 가장 빠르고 효율적으로 수행할 최적의 처리경로를 생성해주는 DBMS 내부의 핵심엔진이다.
> - 옵티마이저가 생성한 SQL 처리경로를 실행계획이라고 부른다.
>
> ### 2. 옵티마이저의 유형
>
> - RBO - Rule Based Optimizer
>   - 통계 정보가 없는 상태에서 사전 등록된 규칙에 따라 질의 실행 계획을 선택하는 옵티마이저
>   - 규칙(우선순위)기반
>   - 인덱스구조, 연산자, 조건절 형태
>   - 사용자가 원하는 처리경로로 유도되기 쉬움
> - CBO - Cost Based Optimizer
>   - 통계 정보로부터 모든 접근 경로를 고려한 질의실행 계획을 선택하는 옵티마이저
>   - 비용(수행 시간) 기반
>   - 레코드 개수, 블록 개수, 평균 행 길이, 컬럼 값의 수, 컬럼 값 분포, 인덱스 높이, 클러스터링 팩터 등
>   - 옵티마이저의 이해도가 낮아도 성능 보장 가능
>
> ### 3. SQL 수행과정 내 옵티마이저 역할
>
> - 쿼리변환
>
>   - SQL을 좀 더 일반적이고 표준화된 형태로 변환
>
> - 비용 산정
>
>   - 쿼리 명령어 각 단계의 선택도, 카디널리티, 비용을 계산
>   - 궁극적을 ㅗ실행계획 전체에 대한 총 비용 계산
>
> - 계획 생성
>
>   - 하나의 쿼리를 수행 시 후보군이 될 만한 실행계획들을 생성해내는 역할
>
>   > - 선택도 : 전체 대상 레코드 중에서 특정 조건에 의해 선택될 것으로 예상되는 레코드 비율
>   > - 카디널리티 : 튜플의 개수
>   > - 힌트 : 실행하려하는 SQL문에 사전에 정보를 주어서 SQL문 실행에 빠른 결과를 가져오는 효과를 만드는 문법
>
> ### 4. 힌트 사용
>
> - SQL 성능 개선의 핵심 부분으로 옵티마이저의 실행 계획을 원하는대로 변경할 수 있게 한다.
>
> - 옵티마이저가 항상 최선의 실행계획을 수립할 수 없어 명시적인 힌트를 통해 실행 계획을 변경한다.
>
>   ```SQL
>   /*+ RULE*/ 규칙기반 접근 방식을 사용하도록 지정
>   /*+ CHOOSE*/ 오라클 옵티마이저 디폴트 값에 따름
>   /*+ INDEX(테이블인덱스명)*/ 지정된 인덱스를 강제적으로 사용하도록 지정
>   /*+ USE_HASH(테이블명)*/ 지정된 테이블들의 조인이 Hash Join 형식으로 일어나도록 유도
>   /*+ USE_MERGE(테이블명)*/ 지정된 테이블들의 조인이 Sort Merge 형식으로 일어나도록 유도
>   /*+ USE_NL(테이블명)*/ 지정된 테이블들의 조인이 Nested Loop 형식으로 일어나도록 유도
>   
>   ```
>
>   > - 해시조인 : 해싱함수 기법을 활용하여 조인을 수행
>   > - 정렬합병조인 : 조인 대상 범위가 넓을 경우 임의 접근을 줄이기 위한 경우나 연결고리에 마땅한 인덱스가 존재하지 않을 경우 사용
>   > - 중첩반복조인 : 2개 이상의 테이블에서 하나의 집합을 기준으로 순차적으로 상대방 Row를 결합하여 원하는 결과를 조합

### 1-4. SQL문 재구성

### 1-5. 인덱스 재구성

> - 재구성에 대해 다양한 사례가 존재하므로 범위가 너무 넓다. 넘어감.

### # 퀴즈

> #### 29. 요구사항 검증 방법에는 요구사항 목록 확인, (	), 비기능적 요구사항의 확인, 타 시스템 연계 및 인터페이스 요구사항 확인 등이 있다.
>
> #### 30. (	)은 성능 및 용량 산정의 적정성, 시스템 간 상호 운용성, IT 시장 성숙도 및 트렌드 부합성, 기술적 위험 분석의 4단계를 거친다.
>
> #### 31. 요구사항의 기술적 타당성 검토 중 (	)은 요구사항에서 목표시스템이 조직 내외 타 시스템과의 연동을 요구하는 경우, 상호 운용이 가능한지 여부를 판단하는 것이다.
>
> #### 32. (	)은 다른 목적을 지닌 2개 이상 시스템들이 상호 간 정보 및 서비스를 교환하면서 효과적으로 운용될 수 있는 시스템의 능력이다.
>
> #### 33. 요구사항의 기술적 타당성 분석 프로세스 중 타당성 분석 겨로가에 이견이 있는 경우 (	)의 중재 하에 합의 도출
>
> #### 34. 분석 클래스의 스테레오 타입 중 (	)은 시스템과 외부 액터와의 상호작용을 담당하는 클래스이다.
>
> 29. 요구사항 정의서 작성 여부 확인
>30. 요구사항의 기술적 타당성 검토
> 31. 시스템 간 상호 운용성
>32. 상호 운용성
> 33. 프로젝트 관리자
>34. 경계(boundary)