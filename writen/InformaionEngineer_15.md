# 정보처리기사

## 15. 서버 프로그램 구현

### 121. 개발 환경 구축

> ### 1. 개발 환경 구축의 개요
>
> - 개발 환경 구축은 응용 소프트웨어 개발을 위해 개발 프로젝트 이해하고 소프트웨어 및 하드웨어 장비를 구축하는 것을 의미한다.
> - 개발 환경은 응용 소프트웨어가 운영될 환경과 유사한 구조로 구축한다.
> - 개발 프로젝트의 분석 단계의 산출물을 바탕으로 개발에 필요한 하드웨어와 소프트웨어를 선정한다.
> - 하드웨어와 소프트웨어의 성능, 편의성, 라이선스 등의 비즈니스 환경에 적합한 제품들을 최종적으로 결정하여 구축한다.
>
> ### 2. 하드웨어 환경
>
> - 하드웨어 환경은 사용자와의 인터페이스 역할을 하는 클라이언트 그리고 클라이언트와 통신하여 서비스를 제공하는 서버로 구성된다.
> - 서버는 사용 목적에 따라 웹 서버, 웹 애플리케이션 서버, 데이터베이스 서버, 파일 서버 등으로 나뉜다.
>   - 웹 서버 : 클라이언트로부터 직접 요청을 받아 처리하는 서버로, 저용량의 정적 파일들을 제공한다.
>   - 웹 애플리케이션 서버 : 사용자에게 동적 서비스를 제공하기 위해 웹 서버로부터 요청을 받아 가공을 작업을 수행하거나, 웹 서버와 데이터베이스 서버 또는 웹 서버와 파일 사이에서 인터페이스 역할을 수행한다.
>   - DB 서버 : 데이터베이스와 이를 관리하는 DBMS를 운영하는 서버이다.
>   - 파일 서버 : 데이터베이스에 저장하기에는 비효율적이거나, 서비스 제공 목적으로 유지하는 파일들을 저장하는 서버이다.
>
> ### 3. 소프트웨어 환경
>
> - 소프트웨어 환경은 클라이언트와 서버 운영을 위한 시스템 소프트웨어와 개발에 사용되는 개발 소프트웨어로 구성된다.
> - 시스템 소프트웨어에는 OS, 웹서버, WAS, DBMS등이 있다.
> - 개발 소프트웨어에는 요구사항 관리 도구, 설계/모델링 도구, 구현 도구, 빌드 도구, 테스트 도구, 형상 관리 도구 등이 있다.
>   - 요구사항 관리 도구 : JIRA, IBM DOORS, inteGREAT, Reqtify, Trello
>   - 설계/모델링 도구: DB Designer, PlantUML, ArgoUML
>   - 구현 도구 : 이클립스, 인텔리J, 비쥬얼스튜디오, Netbeans, Node,js
>   - 빌드 도구 : And Gradle, Maven, Jenkins
>   - 테스트 도구 : CppUnit, JUnit, NUnit, SpringTest
>   - 형상관리도구 : GIT, CVS, Subversion, Mercurial
> - 개발 언어 선정 기준
>   - 적정성 : 개발하려는 소프트웨어의 목적에 적합해야 한다.
>   - 효율성 : 코드의 작성 및 구현이 효율적이어야 한다.
>   - 이식성 : 다양한 시스템 및 환경에 적용이 가능해야 한다.
>   - 친밀성 : 개발 언어에 대한 개발자들의 이해도와 활용도가 높아야 한다.
>   - 범용성 : 다른 개발 사례가 존재하고 여러 분야에서 활용되고 있어야 한다.

### 122. 서버 개발

> ### 1. 서버 개발의 개요
>
> - 서버 개발은 웹 애플리케이션의 로직을 구현할 서버 프로그램을 제작하여 웹 애플리케이션 서버에 탑재하는 것을 의미한다.
> - 웹 애플리케이션 서버에 구현된 서버 프로그램은 웹 서버로부터 받은 요청을 처리하여 결과를 반환하는 역할을 수행한다.
> - 서버 개발에 사용되는 프로그래밍 언어에는 Java, JavaScript, Python, PHP, Ruby등이 있다.
> - 각 프로그래밍 언어에는 해당 언어로 서버 프로그램을 개발할 수 있도록 지원하는 프레임워크가 있다.
>
> ### 2. 서버 개발 프레임워크
>
> - 서버 개발 프레임워크는 서버 프로그램 개발 시 다양한 네트워크 설정, 요청 및 응답 처리, 아키텍처 모델 구현 등을 손쉽게 처리할 수 있도록 클래스나 인터페이스를 제공하는 소프트웨어를 의미한다.
> - 서버 개발 프레임워크에 따라 지원하는 프로그래밍 언어가 제한적이므로 선정할 수 있는 프레임워크도 제한적이다.
> - 서버 개발 프레임워크의 대부분은 MVC 패턴을 기반으로 개발되었다.
> - 대표적인 서버 개발 프레임워크의 종류는 다음과 같다.
>   - Spring : JAVA기반, 전자정부 표준 프레임워크의 기반 기술
>   - Node,js : 자바스크립트기반, 비동기 입출력, 이벤트위주의 처리 성능을 갖고 있어 실시간으로 입출력이 빈번한 애플리케이션에 적합하다.
>   - Django : 파이썬기반, 컴포넌트의 재사용과 플러그인화를 강조하여 신속한 개발이 가능하도록 지원
>   - Codeigniter : PHP기반, 인터페이스가 간편하며 서버 자원을 적게 사용
>   - Ruby on Rails : Ruby기반, 테스트를 위한 웹 서버를 지원, DB작업 단순화, 코드길이가 짧아 신속한 개발 가능
>
> ### 3. 서버 프로그램 구현
>
> - 서버 프로그램은 응용 소프트웨어와 동일하게 모듈 및 공통 모듈을 개발한 후, 모듈들을 통합하는 방식으로 구현된다.
> - 모듈은 모듈화를 통해 분리된 시스템의 각 기능들로, 서브 루틴, 서브시스템, 소프트웨어 내의 프로그램, 작업 단위 등과 같은 의미로 사용된다.
> - 모듈 개발 시 기능적 독립성을 고려하여 다른 모듈과의 과도한 상호작용을 배제함으로써 특정 모듈의 수정이 다른 모듈들에게 영향을 미치지 않아야 한다.
> - 모듈의 독립성은 결합도와 응집도에 의해 측정되며, 독립성을 높이려면 모듈의 결합도를 약하게 만들고 응집도를 강하게하며 모듈의 크기를 작게 만든다.
> - 공통 모듈은 여러 프로그램에서 재사용할 수 있는 모듈을 의미하며, 자주 사용되는 계산식이나 매번 필요한 사용자 인증 같은 기능들이 공ㅌ오 모듈로 구성될 수 있다.
>
> ### 4. 프레임워크의 특성
>
> - 모듈화 : 캡슐화, 모듈화로 소프트웨어 품질 향상
> - 재사용성 : 재사용 가능한 모듈을 제공함으로써 생산성 향상
> - 확장성 : 다형성을 가진 인터페이스 확장이 가능하여 다양한 형태와 기능을 가진 애플리케이션 개발 가능
> - 제어의 역흐름 : 개발자가 관리해야 할 객체들의 제어를 프레임워크에 넘김으로써 생산성 향상

### 123. 보안 및 API

> ### 1. 소프트웨어 개발 보안의 개요
>
> - 소프트웨어 개발 보안은 소프트웨어 개발 과정에서 발생할 수 있는 보안 취약점을 최소화하여 보안 위협으로부터 안전한 소프트웨어를 개발하기 위한 일련의 보안 활동을 의미한다.
> - 소프트웨어 개발 보안은 데이터의 기밀성, 무결성, 가용성을 유지하는 것을 목표로한다.
> - 정부에서 제공하는 소프트웨어 개발 보안 가이드를 참고하여 소프트웨어 개발 과정에서 점검해야 할 보안 항목들을 점검한다.
>
> ### 2. 소프트웨어 개발 보안 점검 항목
>
> - 세션 통제
>   - 세션은 서버와 클라이언트의 연결을 말하며, 세션 통제는 세션의 연결과 연결로 인해 발생하는 정보를 관리하는 것
>   - 불충분한 세션 관리, 잘못된 세션에 의한 정보 노출
> - 입력 데이터 검증 및 표현
>   - 입력 데이터에 대한 유효성 검증체계를 갖추고, 검증 실패 시 이를 처리할 수 있도록 코딩하는 것
>   - SQL 삽입, 경로 조작 및 자원 삽입, 크로스사이트 스크립팅(XSS)
> - 보안 기능
>   - 인증, 접근제어, 기밀성, 암호화 등의 기능
>   - 적절한 인증 기능 없는 중요기능 허용, 부적절한 인가
> - 시간 및 상태
>   - 동시 수행을 지원하는 병렬 처리 시스템이나 다수의 프로세스가 동작하는 환경에서 시간과 실행 상태를 관리하여 시스템이 원활히 동작되도록 코딩하는 것
>   - 검사 시점, 사용시점 경쟁조건(TOCTOU), 종료되지 않는 반복문, 재귀함수
> - 에러처리
>   - 소프트웨어 실행 중 발생할 수 있는 오류들을 사전에 정의하여 에러로 인해 발생할 수 있는 문제들을 예방하는 것
>   - 오류 메시지를 통한 정보 누출, 오류 상황 대응 부재
> - 코드 오류
>   - 개발자들이 코딩 중 실수하기 쉬운 형변환, 자원반환 등을 고려하여 코딩하는 것
>   - 널 포인터 역참조, 부적절한 자원 해제
> - 캡슐화
>   - 데이터와 데이터를 처리하는 함수를 하나의 객체로 묶어 코딩하는 것
>   - 잘못된 세션에 의한 데이터 정보 노출, 제거되지 않고 남은 디버그 코드
> - API 오용
>   - API를 잘못 사용하거나 보안에 취약한 API를 사용하지 않도록 고려하여 코딩하는 것
>   - DNS lookup에 의존한 보안 결정, 취약한 API 사용
>
> ### 3. API(Application Programming Interface)
>
> - 응용 프로그램 개발 시 운영체제나 프로그래밍 언어 등에 있는 라이브러리를 이용할 수 있도록 규칙 등을 정의해 놓은 인터페이스
> - 프로그래밍 언어에서 특정한 작업을 수행하기 위해 사용되거나, 운영체제의 파일 제어, 화상 처리, 문자 제어 등의 기능을 활용하기 위해 사용된다.
> - API는 개발에 필요한 여러 도구를 제공하기 때문에 원하는 기능을 쉽고 효율적으로 구현할 수 있다.
> - Windows API, 단일 유닉스 규격(SUS), Java API, 웹 API 등이 있으며, 누구나 무료로 사용할 수 있는 공개된 API를 Open API라고 한다.

### 124. 배치 프로그램

> ### 1.  배치프로그램의 개요
>
> - 배치 프로그램은 사용자와의 상호 작용 없이 여러 작업들을 미리 정해진 일련의 순서에 따라 일괄적으로 처리하는 것을 의미한다.
> - 배치 프로그램이 자동으로 수행되는 주기에 따라 정기 배치, 이벤트성 배치, On-Demand 배치로 구분된다.
>   - 정기 배치 : 일, 주 월과 같이 정해진 기간에 정기적으로 수행된다.
>   - 이벤트성 배치 : 특정 조건을 설정해두고 조건이 충족될 때만 수행된다.
>   - On-Demand 배치 : 사용자 요청 시 수행된다.
> - 배치 프로그램이 갖추어야 할 필수 요소는 다음과 같다.
>   - 대용량 데이터 : 대량의 데이터를 가져오거나, 전달하거나, 계산하는 등의 처리가 가능해야 한다.
>   - 자동화 : 심각한 오류가 발생하는 상황을 제외하고는 사용자의 개입 없이 수행되어야 한다.
>   - 견고성 : 잘못된 데이터나 데이터 중복 등의 상황으로 중단되는 일 없이 수행되어야 한다.
>   - 안정성/신뢰성 : 오류가 발생하면 오류의 발생 위치, 시간 등을 추적할 수 있어야 한다.
>   - 성능 : 다른 응용 프로그램의 수행을 방해하지 않아야 하고, 지정된 시간 내에 처리가 완료되어야 한다.
>
> ### 2. 배치 스케줄러
>
> - 배치 스케줄러는 일괄 처리 작업이 설정된 주기에 맞춰 자동으로 수행되도록 지원해주는 도구이다.
> - 배치 스케줄러는 특정 업무(Job)를 원하는 시간에 처리할 수 있도록 지원한다는 특성 때문에 잡 스케줄러 라고도 불린다.
> - 스프링 배치
>   - Spring Source 사와 Accenture 사가 2007년 공동 개발한 오픈 소스 프레임워크이다.
>   - 스프링 프레임워크의 특성을 그대로 가져와 스프링이 가지고 있는 다양한 기능들을 모두 사용할 수 있다.
>   - 데이터베이스나 파일의 데이터를 교환하는데 필요한 컴포넌트들을 제공한다.
>   - 로그 관리, 추적, 트랜잭션 관리, 작업 처리 통계, 작업 게시자 등의 다양한 기능을 제공한다.
>   - 스프링 배치의 주요 구성 요소와 역할
>     - Job : 수행할 작업 정의
>     - Job Launcher : 실행을 위한 인터페이스
>     - Step : Job처리를 위한 제어 정보
>     - Job Repository : Step의 제어 정보를 포함하여 작업 실행을 위한 모든 정보 저장
> - Quartz
>   - 스프링 프레임워크로 개발되는 응용 프로그램들의 일괄 처리를 위한 다양한 기능을 제공하는 오픈 소스 라이브러리이다.
>   - 수행할 작업과 수행 시간을 관리하는 요소들을 분리하여 일괄 처리 작업에 유연성을 제공한다.
>   - Quartz의 주요 구성 요소와 역할
>     - Scheduler : 실행 환경 관리
>     - Job : 수행할 작업 정의
>     - JobDetail : Job의 상세 정보
>     - Trigger : Job의 실행 스케줄 정의

### 125. 패키지 소프트웨어

> ### 1. 패키지 소프트웨어의 개요
>
> - 패키지 소프트웨어는 기업에서 일반적으로 사용하는 여러 기능들을 통합하여 제공하는 소프트웨어를 의미한다.
> - 기업에서는 패키지 소프트웨어를 구입하여 기업 환경에 적합하게 커스터마이징하여 사용한다.
> - 패키지 소프트웨어를 이용하여 시스템을 구축하는 방식을 패키지 개발 방식이라고 한다.
> - 기능 요구사항을 70% 이상 충족 시키는 패키지 소프트웨어가 있을 때만 사용하는 것이 적합하다.
>
> ### 2. 패키지 소프트웨어의 특징
>
> - 요구사항을 분석하여 업무 특성에 맞게 전용으로 개발되는 소프트웨어와 비교하여 안정성, 라이선스, 샌산성 등에서 차이가 있다.
> - 패키지 소프트웨어는 전문 업체에 의해 품질이 검증되었고, 국제/산업계 표준을 준수하고 있어 안정적인 이용이 가능하다.
> - 소프트웨어에 대한 라이선스가 판매자에게 있기 때문에 시스템 구축 후 기능 추가 및 코드 재사용 등에 제약이 발생한다.
> - 개발 조직을 갖추어야 할 필요성이 없어 비용을 절감할 수 있고, 이미 개발된 소프트웨어를 사용하기 때문에 프로젝트 기간이 단축된다.
> - 기존에 보유하고 있던 시스템과의 상호 연동 및 연계가 어려울 수 있다.
> - 결함이 발생한 경우 판매처의 프로세스에 따라 보완되므로 이용자의 사정에 따라 능동적인 대처를 기대하기는 어렵다.
>
> |               | 패키지 소프트웨어                                      | 전용 개발 소프트웨어             |
> | ------------- | ------------------------------------------------------ | -------------------------------- |
> | 기능 요구사항 | 70% 이상 충족시키는 패키지 소프트웨어가 있는 경우 이용 | 모든 기능 요구사항 반영  가능    |
> | 안정성        | 품질이 검증되었고, 업계 표준 적용                      | 개발자의 역량에 따라 달라짐      |
> | 라이선스      | 판매자                                                 | 회사                             |
> | 생산성        | 개발을 위한 인력과 시간이 절약됨                       | 개발을 위한 인력과 시간이 필요함 |
> | 호환성        | 보장이 안됨                                            | 설계 단계부터 고려하여 개발      |
> | 유지보수      | 결함 발생 시 즉시 대응이 어려움                        | 결함 발생 시 즉시 대응이 가능    |
>
> 