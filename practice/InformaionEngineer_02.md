# 정보처리기사

## 2. 요구사항 확인

## 1. 요구사항

### 1-1. 요구사항 개념

> - 문제의 해결 또는 목적 달성을 위하여 고객에 의해 요구되거나, 표준이나 명세 등을 만족하기 위하여 시스템이 가져야 하는 서비스 또는 제약사항이다.
>
> ### 1. 요구사항의 분류 - `기완일`, `신사효유이`
>
> - 요구사항 파악의 기본은 시스템의 요구사항에 대한 파악이다.
> - 요구사항은 기능적 요구사항과 비기능적 요구사항으로 분류된다.
>   - 기능적 요구사항
>     - 시스템이 제공하는 기능, 서비스
>     - 특정 입력, 상황에 대해 시스템이  어떻게 반응하는지
>     - 기능성, 완전성, 일관성
>   - 비기능적 요구사항
>     - 시스템이 수행하는 기능 이외의 사항, 시스템 구축에 대한 제약사항
>     - 품질 속성에 관련
>     - 시스템이 준수해야 할 제약 조건
>     - 신뢰성, 사용성, 효율성, 유지보수성, 이식성
>
> ### 2. 요구사항 개발 프로세스 - `도분명확`
>
> - 요구사항 도출
>   - 요구사항이 어디있는지, 어떻게 수집할 것인지를 파악
>   - 이해관계자가 요구사항을 식별, 개발팀과 고객 사이의 관계 형성
>   - 다양한 이해관계자의 효율적인 의사소통이 중요
>   - 인터뷰, 설문조사, 브레인스토밍, 워크숍
> - 요구사항 분석
>   - 상충되는 요구사항을 해결하고, 소프트웨어의 범위, 소프트웨어가 환경과 어떻게 상호작용하는 지 이해
>   - 시스템 요구사항을 정제
>   - 자료 흐름 지향(DFD) 분석, 객체 지향 분석(UML)
> - 요구사항 명세
>   - 체계적으로 검토, 평가, 승인될 수 있는 문서를 작성하는 단계
>   - 요구사항 명세에서는 시스템 정의, 시스템 요구사항, 소프트웨어 요구사항을 작성
>   - 자연어에 의한 방법, 정형화 기법 사용 방법
> - 요구사항 확인(검증)
>   - 요구사항 문서가 표준에 적합하고 이해 가능하며, 일관성있고 완전한지 검증하는 단계
>   - 동료 검토, 워크 스루, 인스펙션
>
> ### 3. 요구사항 관리 프로세스 - `협기변확`
>
> - 요구사항 협상
>   - 우선순위 설정, 시뮬레이션
>   - 가용한 자원과 수용 가능한 위험 수준에서 구현 가능한 기능을 협상하기 위한 기법
> - 요구사항 기준선
>   - 공식 회의, 형상 관리
>   - 공식적으로 검토되고 합의된 요구사항 명세서
> - 요구사항 변경 관리
>   - CCB, 영향도 분석
>   - 요구사항 기준선을 기반으로 모든 변경을 공식적으로 통제하기 위한 기법
> - 요구사항 확인 및 검증
>   - 확인 및 검증
>   - 구축된 시스템이 이해관계자가 기대한 요구사항에 부합하는지 확인하기 위한 방법

### 1-2 요구사항의 분석 - `분개할협정`

> - 요구사항 분석 기법으로 요구사항 분류, 개념 모델, 요구사항 할당, 요구사항 협상, 정형 분석이 있다.
> - 요구사항 분석 기법을 활용하여 업무 분석가가 정의한 응용 소프트웨어의 요구사항을 확인할 수 있다.
> - 요구사항 분류
>   - 요구사항이 기능인지 비기능인지 확인
>   - 요구사항이 소프트웨어에 미치는 영향의 범위를 파악
>   - 요구사항이 소프트웨어 생명주기 동안 변경이 발생하는지를 확인
> - 개념 모델링
>   - 개념 모델은 문제 도메인의 엔티티들과 개별 관계 및 종속성을 반영
>   - 시나리오로 나타내기 위해 유스케이스 다이어그램을 주로 사용
>   - 대부분의 모델링 표기법은 UML 사용
>
> - 요구사항 할당
>   - 요구사항을 만족시키기 위한 아키텍처 구성요소를 식별하는 활동
>   - 다른 구성요소와 어떻게 상호작용하는지 분석을 통해 추가적인 요구사항의 발견 가능
> - 요구사항 협상
>   - 두 명의 이해관계자가 서로 상충되는 내용을 요구하는 경우, 어느 한쪽을 지지하기보다는 적절한 지점에서 합의하기 위함
> - 정형 분석
>   - 형식적으로 정의된 의미를 지닌 언어로 요구사항을 표현
>   - 정확하고 명확하게 표현
>   - 요구사항분석의 마지막 단계에서 이루어짐

### 1-3. 요구사항의 확인 - `요프모인`

> - 업무 분석가가 요구사항을 이해했는지 확인하는 것이 필요, 요구사항 문서가 기업의 표준에 적합, 이해가능, 일관성, 완전한지 검증
> - 요구사항 검토
>   - 여러 검토자들이 에러, 잘못된 가정, 불명확성, 표준과의 차이를 검토
>   - 고객 중심 프로젝트에는 검토자 그룹에 고객 대표자 1명 이상 포함 필요
>   - 시스템 정의서, 시스템 사양서, 소프트웨어 요구사항 명세서를 완전한 시점에서 검토
> - 프로토타이핑
>   - 새로운 요구사항을 도출하기 위한 수단 및 소프트웨어 요구사항에 대해 소프트웨어 엔지니어가 해석한 것을 확인하기 위한 수단으로 사용
>   - 요구사항이 잘못된 경우 유용한 피드백 제공, 사용자 인터페이스의 동적인 행위가 문서나 그래픽 모델보다 용이
> - 모델 검증
>   - 분석 단계에서 개발된 모델의 품질 검증 필요
>   - 객체 모델의 경우 객체들 사이의 존재하는 의사소통 경로를 검증하기 위한 정적 분석 수행에 유용
> - 인수 테스트
>   - 요구사항의 중요한 속성은 최종 제품을 기준으로 요구사항을 만족시키는지 확인이 가능해야 함
>   - 각각의 요구사항을 어떻게 확인할 것인지에 대한 계획 수립 후, 요구사항을 확인하는 테스트
>
> > - 프로토타이핑 : 사용자가 요구한 주요 기능을 프로토타입으로 구현하여 사용자의 피드백을 통해 개선, 보완하여 완성 소프트웨어를 만들어가는 기법

### 1-4. 요구사항의 확인 프로세스 - `목정비타`

> - 요구사항 목록 확인
>   - 요구사항 목록에서 업무 기능에 대한 요구사항 반영 여부 확인
> - 요구사항 정의서 작성 여부 확인
>   - 요구사항 목록 중 수용인 경우, 요구사항 정의서(유스케이스 명세서)가 작성되었는지 확인
>   - 요구사항 정의서에서 시스템의 동작 방식을 명확하고 구체적으로 기술하고 있는지 검토
> - 비기능적 요구사항의 확인
>   - 시스템 특성, 품질, 제약사항 등 비기능적 요구사항이 명확하게 도출되었는지 검토
>   - 성능, 가용성, 사용 용이성, 유지보수 용이성, 안전성, 보안성 등에 대한 요구사항의 문서화 여부 확인
> - 타 시스템 연계 및 인터페이스 요구사항 확인
>   - 타 시스템 또는 하위 시스템 등과의 모든 인터페이스 요구사항이 정의되어 있는지 확인
>   - 인터페이스 구분, 주기, 방법, 제공자, 요청자 등이 명확하게 정의되어 있는지 확인

## 2. 요구사항의 시스템화 타당성 분석

> - 업무 분석가가 수집하고 요구사항이 개발하고자 하는 응용 소프트웨어에 미칠 영향에 대해서 검토하고 확인해야 한다.

### 2-1. 요구사항의 기술적 타당성 검토

> - 성능 및 용량 산정의 적정성
> - 시스템간 상호 운용성
> - IT 시장 성숙도 및 트렌드 부합성
> - 기술적 위험 분석

### 2-2. 요구사항의 기술적 타당성 분석 프로세스

> - 타당성 분석 결과 기록
> - 타당성 분석 결과의 이해관계자 검증
> - 타당성 분석 결과 확인 및 배포 / 공유

## 3. 비용산정 모델

### 3-1. 비용산정 모델 개념

> - 소프트웨어 규모 파악을 통한 투입자원, 소요시간을 파악하여 실행 가능한 계획을 수립하기 위해 비용을 산정하는 기법이다.

### 3-2. 비용산정 모델 분류

> - 하향식 산정 기법
>   - 경험이 많은 전문가에게 비용산정을 의뢰하거나 여러 전문가와 조정자를 통해 산정하는 방식
>   - 전문가판단
>     - 조직 내에 있는 경험이 많은 두 명 이상의 전문가에게 비용산정을 의뢰
>   - `델파이기법` : 전문가의 경험적 지식을 통한 문제해결 및 미래예측을 위한 기법 = 전문가합의법
>     - 한 명의 조정자와 여러 전문가로 구성
> - 상향식 산정 기법
>   - 세부적인 요구사항과 기능에 따라 필요한 비용을 계산하는 방식
>   - 코드라인 수
>     - 비관치, 낙관치, 기대치를 측정하여 예측을 구함
>   - Man Month
>     - 한 사람이 1개월동안 할 수 있는 일의 양을 기준으로 비용을 산정
>   - COCOMO 모형
>     - 보헴이 개발
>     - 단순형, 중간형, 임베디드형
>   - Putnam 모형
>     - 개발 주기 단계별로 요구할 인력의 분포를 가정
>   - FP 모형
>     - 요구 기능을 증가시키는 인자별로 가중치를 부여
>     - 입력, 출력, 질의, 파일, 인터페이스 개수로 소프트웨어 규모를 표현

### # 퀴즈

> #### 22. (	)은 소프트웨어의 변경 사항을 체계적으로 추적하고 통제하는 관리 기법이다.
>
> #### 23. (	)은 버전 등록 관리에서 저장소의 파일을 받는 행위이다.
>
> #### 24. (	)은 저장소에 새로운 버전의 파일로 갱신하는 행위이다.
>
> #### 25. (	)은 소프트웨어 관리 유형 중 하나로 매일 개발 완료 파일을 약속된 위치의 공유 폴더에 복사하는 방식이다.
>
> #### 26. (	)은 서버와 클라이언트로 구성되어 다수의 인원이 동시에 범용적인 운영체제로 접근가능하여 버전 관리가 가능한 형상 관리 도구이다.
>
> #### 27. (	)은 하나의 서버에서 소스를 쉽고 유용하게 관리할 수 있게 도와주는 관리도구이다.
>
> 22. 소프트웨어 형상 관리
>23. 체크아웃
> 24. 체크인
>25. 공유폴더방식
> 26. CVS
>27. SVN