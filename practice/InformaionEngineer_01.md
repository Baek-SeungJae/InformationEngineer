# 정보처리기사

## 1. 현행 시스템 분석

## 1. 현행 시스템 파악

### 1-1. 현행 시스템 파악 개념

> - 현행 시스템이 어떤 `하위 시스템`으로 구성되었는지, `제공 기능`, `연계 정보`는 무엇인지, `어떤 기술 요소`를 사용하는지를 파악하는 활동
> - `SW & HW`, `네트워크 구성`을 함께 파악한다.

### 1-2. 현행 시스템 파악 절차 - 3단계

> - `구성` / `기능` / `인터페이스` 파악
>
>   - 현행 시스템 구성 현황
>
>     - 기간 업무와 지원 업무로 구분
>     - 각 업무에 속하는 정보시스템들의 명칭, 주요 기능을 명시
>     - 조직 내 존재하는 모든 정보 시스템의 현황 파악이 가능해야 함
>
>   - 기능 현황
>
>     - 단위 업무 시스템이 현재 제공하고 있는 기능
>     - 주요기능과 하부기능으로 구분하여 계층형으로 표시
>
>   - 인터페이스 현황
>
>     - 단위 업무 시스템이 다른 시스템과 주고받는 데이터의 종류, 형식, 프로토콜, 연계유형, 주기
>
>     - 데이터 형식(XML, 고정포맷, 가변포맷)
>
>     - 통신규약(TCP/IP, X.25 등)
>
>     - 연계유형(EAI)
>
>       > - IP : 인터넷 프로토콜 : 패킷 전달 여부를 보증하지 않고 `보낸 순서와 받는 순서가 다를` 수 있다.
>       > - TCP : 전송 제어 프로토콜 : `IP 위에서` 동작하는 프로토콜 `데이터 전달을 보증`하고, `보낸 순서대로 받게`한다.
>       > - X.25 : ITU-T 의 X 표준, Frame Relay의 근간을 이루는 프로토콜 : 패킷망에서 회선 종단과 단말 사이에 이루어지는 상호작용을 규정
>
> - `아키텍처` 및 `SW 구성` 파악
>   
>   - 현행 시스템 아키텍처
>   
>     - 기간 업무를 수행하기 위한 계층별 기술 요소를 최상위 수준에서 파악
>   
>     - 단위 업무 시스템별로 아키텍처가 다른 경우에는 가장 핵심이 되는 기간 업무 처리 시스템을 기준으로 파악
>   
>   - 소프트웨어 구성
>   
>     - 단위 업무 시스템의 업무 처리를 위해 설치되어 있는 소프트웨어들의 제품명, 용도, 라이선스, 적용 방식, 라이선스 수 파악
>     - 상용 소프트웨어의 경우에는 라이선스 적용 방식의 기준과 보유한 수량파악이 중요
>
> - `HW` 및 `네트워크 구성` 파악
>   - 시스템 하드웨어 구성파악
>   
>     - 단위 업무 시스템들이 운용되고 있는 서버의 주요 사양(CPU, 처리 속도, 메모리 크기, 하드디스크의 용량 등)과 수량, 이중화 구현 여부를 파악
>     - 이중화는 기간 업무의 서비스 기간, 장애 대응 정책에 따라 필요성 여부가 결정됨
>     - 인프라 구축 기술 난이도 및 비용 증가 가능성이 존재함
>   
>   - 네트워크 구성 파악
>   
>     - 업무 처리 시스템을 위해 어던 네트워크 장비를 사용하여 어떻게 구성되어 있는 지 파악
>   
>     - 네트워크 구성도의 작성을 통해 서버의 위치, 서버 간의 네트워크 연결 방식을 파악할 수 있도록 표현
>   
>       > - IPS : 침입 차단 시스템 : 네트워크에 대한 공격을 실시간으로 차단하고, 유해 트래픽에 대한 조치를 능동적으로 처리
>       > - 라우터 : OSI 3계층 장비 : 스위치를 연결하여 네트워크간 비용 소모가 최적화된 경로를 설정하고 결정된 경로를 따라 트래픽을 전달하는 역할 (ex: RIP)

### 1-3. 소프트웨어 아키텍처

> - 소프트웨어 아키텍처의 개념
>   
>   - 여러가지 소프트웨어 구성 요소와 그 구성요소가 가진 특성 중에서 외부에 드러나는 특성
>   - 구성 요소간의 관계를 표현하는 시스템의 구조나 구조체
>   - 소프트웨어를 설계하고 전개하기 위한 지침이나 원칙
>   
> - 소프트웨어 아키텍처 프레임워크
>
>   - 소프트웨어 집약적인 시스템에서 아키텍처가 표현해야 하는 내용 및 이들간의 관계를 제공하는 아키텍처 기술 표준
>   - 구성요소
>     - 아키텍처 명세서
>       - 아키텍처를 기록하기 위한 산출물
>       - 이해관계자들의 시스템에 대한 관심을 관점에 맞추어 작성한 뷰로 표현
>       - 개별 뷰, 뷰 개괄 문서, 인터페이스 명세 등
>     - 이해관계자
>       - 시스템 개발에 관련된 모든 사람과 조직
>       - 고객, 사용자, 개발자, PM, 유지보수자, 마케팅 담당자
>     - 관심사
>       - 시스템에 대한 이해관계자들의 서로 다른 의견과 목표
>       - 기능, 신뢰성, 보안, 사용성
>       - 유지보수 용이성
>       - 적인 비용과 인력
>     - 관점
>       - 개별 뷰를 개발할 때 토대가 되는 패턴이나 양식
>       - 이해관계자들이 서로 다른 역할이나 책임으로 시스템이나 산출물들에 대해 보고싶은 관점
>       - 서로 관련 있는 관심사들의 집합이라는 관점에서 전체 시스템을 표현
>       - 시스템에 대한 아키텍처 설명에는 하나 이상의 뷰로 구성
>     - 뷰
>       - 서로 관련 있는 관심사들의 집합이라는 관점에서 전체 시스템을 표현
>       - 시스템에 대한 아키텍처 설명에는 하나 이상의 뷰로 구성
>     - 근거
>       - 아키텍처 결정 근거
>       - 회의 결과, 보고 결과
>
> - 소프트웨어 아키텍서 4 + 1 뷰 - `유논프구배`
>
>   - 고객의 요구사항을 정리해 놓은 시나리오를 4개의 관점에서 바라보는 소프트웨어 적인 접근 방법
>
>   - 4개의 분리된 구조로 구성되는 개념을 제시하고, 4개 구조가 충돌되지 않는지 요구사항을 충족시키는지 유스케이스로 검토한다.
>
>   - 유스케이스 뷰
>
>     - 아키텍처를 도출하고 설계하는 작업을 주도하는 뷰
>     - 다른 뷰를 검증하는데 사용
>
>   - 논리 뷰
>
>     - 설계 모델의 추상화이며, 주요 설계 패키지와 서브 시스템, 클래스를 식별하는 뷰
>     - 시스템 기능적인 요구사항 지원
>     - 클래스와 이들 간 관계에 대한 집합을 보여주는 클래스 다이어그램으로 표현
>
>   - 프로세스 뷰
>
>     - `런타임` 시의 시스템의 태스크, `스레드`, `프로세스`와 이들 사이의 상호작용 등의 관계를 표현
>     - 성능이나 가용성 같은 비기능적 요구사항을 고려
>
>   - 구현 뷰
>
>     - 개발환경 안에서 정적인 소프트웨어 모듈(소스코드, 데이터파일, 컴포넌트, 실행파일 등)의 구성을 표현
>     - 개발자 관점에서 소프트웨어의 구현과 관리적인 측면을 컴포넌트 다이어그램으로 표현
>     - 컴포넌트 뷰라고도 함
>
>   - 배포 뷰
>
>     - 물리적인 노드의 구성과 상호 연결 관계를 배포 다이어그램으로 표현하는 뷰
>     - 다양한 실행 파일과 다르런타임 컴포넌트가 해당 플랫폼 또는 컴퓨팅 노드에 어떻게 매핑되는가를 보여주며, 가용성, 신뢰성, 성능, 확장성 등의 시스템의 비기능적인 요구사항을 고려
>
>     > - 런타임 : 컴퓨터 프로그램이 실행되고 있는 동안의 동작 상태
>     > - 스레드 : 프로세스의 실행 부분을 담당하는 실행의 기본 단위(프로세스에서 실행 개념만 분리)
>     > - 프로세스 : 운영체제가 관리하는 실행단위로 프로세서에 의해 처리되는 PCB를 가진 시스템 프로그램
>
> - 현행 시스템 분석서 작성 및 검토
>
>   - 현행 시스템 관련 자료 수집
>     - 현행 시스템 관련 자료 수집을 위해 자료의 특성에 따라 3개의 팀을 구성한다.
>     - 정보 시스템 구성 / 기능 및 인터페이스 자료 수집팀
>       - 정보시스템 구성도
>       - 정보시스템 기능 구성도
>       - 정보시스템 인터페이스 현황
>     - 현행 시스템 아키텍처 및 소프트웨어 자료 수집팀
>       - 현행 시스템 아키텍처 구성도
>       - 소프트웨어 구성도
>     - 하드웨어 및 네트워크 자료 수집팀
>       - 하드웨어 구성도
>       - 네트워크 구성도
>     - 수집 자료의 성격에 따라서 팀을 명확하게 구분해야 한다.
>
>   - 수집 자료의 분석
>
>     - 수집된 정보를 취합 / 정제하고, 중복되거나 유효하지 않은 정보들은 삭제한다.
>     - 불명확한 부분은 체크한 후 분석 및 설계 단계를 통해 구체적으로 조사한다.
>     - 현행 시스템의 이슈 및 문제점을 파악한다.
>     - 정보 시스템 구성 / 기능 및 인터페이스 자료 수집팀
>       - 정보시스템 구성/ 기능 구성도
>         - 정보시스템의 구분
>         - 정보시스템 명
>         - 주요 기능
>         - 정보시스템의 기능 구성
>       - 정보시스템 인터페이스 현황
>         - 송수신 시스템
>         - 연계방식 및 연계 주기
>         - 연동 데이터 형식
>         - 주요 연동 데이터
>
>     - 현행 시스템 아키텍처 및 소프트웨어 자료 수집팀
>       - 현행 시스템 아키텍처 구성도
>         - 운영체제의 종류
>         - 적용 `프레임워크`
>         - 계층별 적용 기술
>         - 데이터 연동 방식
>         - 데이터 저장소
>         - 외부 시스템 연계 방식
>       - 소프트웨어 구성도
>         - 단위 시스템별 필요 소프트웨어의 제품명 및 용도
>         - 라이선스 적용 방식
>         - 라이선스 수
>     - 하드웨어 및 네트워크 자료 수집팀
>       - 하드웨어 구성도
>         - 단위 시스템별 서버 제품명 및 용도
>         - CPU / 메모리 / HDD 용량 및 수량
>         - 이중화 적용 여부
>       - 네트워크 구성도
>         - 네트워크 장비의 용도 및 제품명
>         - 수량 및 주요사양
>         - 장비 위치 및 연동 `프로토콜`
>
>     > - 프레임워크 : 소프트웨어의 구체적인 부분에 해당하는 설계와 구현을 재사용이 가능하게끔 클래스들을 제공하는 틀이다.
>     > - 프로토콜 : 서로 다른 시스템에 있는 두 개체 간의 데이터 교환을 원활히 하기 위한 일련의 통신 규약이다.
>
> - 분석한 결과를 기반으로 산출물 작성 - `현기인아소하네`
>
>   - 각 취득 자료를 분석한 결과를 기반으로 산출물을 작성한다.
>   - 현행 시스템의 이슈나 문제점을 산출물에 상세하게 포함하여 작성한다.
>     - 정보시스템 구성 현황
>     - 정보시스템 기능 구성도
>     - 인터페이스 현황
>     - 아키텍처 구성도
>     - 소프트웨어 구성도
>     - 하드웨어 구성도
>     - 네트워크 구성도 
>
> - 산출물에 대한 검토 수행
>
>   - 팀별로 작성된 산출물을 상호 검토하여 의견을 제시한다.
>   - 다른 팀의 검토 의견을 반영하여 산출물을 수정하고 최종 완료한다.

## 2. 개발 기술 환경 정의

### 2-1. 개발 기술 환경 현행 시스템 분석

> - 운영체제 현행 시스템 분석
>
>   - 운영체제의 개념
>     - 컴퓨터 시스템이 제공하는 모든 하드웨어, 소프트웨어를 사용할 수 있도록 해주고, 사용자와 하드웨어간의 인터페이스를 담당하는 프로그램
>     - 사용자가 컴퓨터를 좀 더 쉽게 사용하기 위해 지원하는 소프트웨어
>   - 운영체제 현행 시스템 분석
>     - 품질 측면과 지원 측면을 고려한다.
>     - 품질 측면
>       - 신뢰도
>         - 장기간 시스템 운영 시 운영체제의 장애 발생 가능성
>         - 운영체제의 버그로 인한 재기동 여부
>       - 성능
>         - 대규모 및 대량 파일작업(배치 작업) 처리
>         - 지원 가능한 메모리크기
>     - 지원 측면
>       - 기술 지원
>         - 공급사들의 안정적인 기술 지원
>         - 오픈 소스 여부
>       - 주변 기기
>         - 설치 가능한 하드웨어
>         - 다수의 주변 기기 지원 여부
>       - 구축 비용
>         - 지원 가능한 하드웨어 비용
>         - 설치할 응용 프로그램의 라이선스 정책 및 비용
>         - 유지 및 관리 비용
>   - 운영체제 종류 및 특징
>     - 대표적으로 PC, 모바일 운영체제로 나뉜다.
>     - PC
>       - 윈도우 : 중 / 소규모 서버, 일반 PC 등 유지, 관리 비용 장점
>       - 유닉스 : 대용량 처리, 안전성 높은 엔터프라이즈급 서버
>       - 리눅스 : 중 / 대규모 서버 대상, 높은 보안성 제공
>     - 모바일
>       - 안드로이드 : 다양한 기기와의 호환성
>       - IOS : 높은 보안성과 고성능
>
> - 네트워크 현행 시스템 분석
>
>   - 네트워크의 개념
>
>     - 컴퓨터 장치들의 노드 간 연결(데이터링크)을 사용하여 서로에게 데이터를 교환할 수 있도록 하는 기술
>
>     - 데이터 링크들은 광케이블과 같은 유선 매체 또는 와이파이(Wi-Fi)와 같은 무선 매체를 통해 확립된다.
>
>   - OSI 7Layer (5~7:데이터 4:세그먼트 3:패킷 2:프레임 1:비트)
>
>     - 네트워크 통신에서 생긴 여러 가지 충돌 문제를 완화하기 위해 국제 표준화 기구(ISO)에서 제시한 네트워크
>     - 응용계층
>       - 사용자와 네트워크 간 응용 서비스 연결, 데이터 생성
>       - HTTP, FTP
>     - 표현계층
>       - 데이터 형식 설정과 부호교환, 암/복호화
>       - JPEG, MPEG
>     - 세션계층
>       - 연결 접속 및 동기제어
>       - SSH, TLS
>     - 전송계층
>       - 신뢰성있는 통신 보장
>       - 데이터 분할, 재조립, 흐름제어, 오류제어, 혼잡제어
>       - TCP, UDP
>     - 네트워크 계층
>       - 단말 간 데이터 전송을 위한 최적화된 경로 제공
>       - IP, ICMP
>     - 데이터링크 계층
>       - 인접 시스템간 데이터 전송, 전송오류 제어
>       - 동기화, 흐름제어 등
>       - 오류검출 / 재전송
>       - 이더넷
>     - 물리 계층
>       - 0과 1의 비트 정보를 회선에 보내기 위한 전기적 신호 변환
>       - RS-232C
>
>   - 네트워크 현행 시스템 분석
>
>     - 현행 시스템이 구성된 네트워크 구조를 네트워크 구성도를 통해 분석한다.
>     - 네트워크 구성도를 통해 서버위치, 서버간 연결방식을 파악할 수 있다.
>     - `백본망`, `라우터`, `스위치`, `게이트웨이`, `방화벽` 등을 대상으로 분석한다.
>     - 네트워크 분석 시 물리적인 위치 관계 파악, 조직 내 보안 취약성 분석 및 대응이 가능하다.
>     - 네트워크 장애 발생 추적 및 대응 등의 다양한 용도로 활용할 수 있다.
>
>     > - 백본망 : 다양한 네트워크를 통해 상호 연겨하는 컴퓨터 네트워크의 일부로서, 각기 다른 LAN이나 부분망 간에 정보를 교환하기 위한 경로를 제공하는 망
>     > - 라우터 : 3계층장비, 최적화경로를 찾고 이 경로를 따라 패킷을 전송
>     > - 스위치 : 2계층장비, MAC주소 기반으로 빠르게 데이터를 전달
>     > - 게이트웨이 : 컴퓨터 네트워크에서 서로 다른 통신망, 프로토콜을 사용하는 네트워크 간의 통신을 가능하게 하는 네트워크 장비
>     > - 방화벽 : 외부로부터 불법 침입과 내부의 불법 정보 유출을 방지, 내/외부 네트워크의 상호간 영향을 차단
>
> - DBMS 현행 시스템 분석
>   - DBMS의 개념
>     - 데이터의 집합을 만들고, 저장 및 관리하는 기능을 제공하는 응용 프로그램
>   - 기능
>     - 중복제어, 접근통제, 인터페이스 제공, 관계표현 등을 제공
>   - DBMS 현행 시스템 분석
>     - 가용성
>       - 장기간 시스템을 운영할 때 장애 발생 가능성
>       - 백업 및 복구 편의성
>       - DBMS 이중화 및 복제 지원 여부
>     - 성능
>       - 대규모 데이터 처리 성능
>       - 대량 거래 처리 성능
>       - 다양한 튜닝 옵션 지원 여부
>       - 비용 기반 최적화 지원 및 설정의 최소화 지원 여부
>     - 상호 호환성
>       - 설치 가능한 운영체제 종류
>       - 다양한 운영체제에서 지원되는 JDBC, ODBC
>     - 기술 지원
>       - 공급 업체들의 안정적인 기술 지원 여부
>       - 다수의 사용자 간의 정보 공유 여부
>       - 오픈 소스 여부
>     - 구축 비용
>       - 라이선스 정책 및 비용
>       - 유지 및 관리 비용
>
> - 미들웨어의 현행 시스템 분석
>   - 미들웨어의 개념
>     - 미들웨어는 분산 컴퓨팅 환경에서 응용 프로그램과 프로그램이 운영되는 환경 간에 원만한 통신이 이루어질 수 있도록 제어해주는 소프트웨어이다.
>     - 운영체제와 소프트웨어 애플리케이션 사이에 위치하고 있다.
>     - 대표적인 미들웨어는 WAS이다.
>   - WAS의 개념
>     - 서버 계층에서 애플리케이션이 동작할 수 있는 환경을 제공하고 안정적인 트랜잭션 처리와 관리, 다른 이기종 시스템과의 애플리케이션 연동을 지원하는 서버이다.
>   - 
>
> 



### # 퀴즈

> #### 1. (	)은 개발이 완료된 제품 소프트웨어를 고객에게 전달하기 위한 형태의 문서이다.
>
> #### 2. (	)은 소프트웨어 설계에서 기능 단위로 분해하고 추상화 되어 재사용 및 공유가능한 수준으로 만들어진 단위이다.
>
> #### 3. (	)은 모듈을 이용하여 소프트웨어의 성능을 향상시키거나 시스템의 디버깅, 시험, 통합, 수정을 용이하도록 하는 소프트웨어 설계 기법이다.
>
> #### 4. (	)은 소스코드 파일을 컴퓨터에서 실행할 수 있는 소프트웨어의 단위로 변환하는 과정이다.
>
> #### 5. (	)은 조직의 최종 사용자인 고객과 잘 정리된 릴리즈 정보를 공유하는 문서이다.
>
> #### 6. (	)은 배포를 위한 패키징 시에 디지털 콘텐츠의 지적 재산권을 보호하고 관리하는 기능을 제공하며, 안전한 유통과 배포를 보장하는 도구이다.
>
> #### 7. (	)은 콘텐츠 및 프로그램과 같이 복제가 용이한 저작물에 대해 불법 복제 및 배포 등을 막기 위한 기술적인 방법이다.
>
> #### 8. (	)은 저작권 관리에서 콘텐츠를 메타 데이터와 함께 배포 가능한 단위로 묶는 기능을 수행한다.
>
> #### 9. (	)은 저작권 관리에서 원본을 안전하게 유통하기 위한 전자적 보안 장치이다.
>
> #### 10. (	)은 저작권 관리에서 키 관리 및 라이선스 발급 관리를 수행한다.
>
> 1. 제품 소프트웨어 패키징
> 2. 모듈
> 3. 모듈화
> 4. 빌드
> 5. 릴리즈 노트
> 6. 제품 소프트웨어 패키징 도구
> 7. 저작권 보호 기술
> 8. 패키저
> 9. 보안 컨테이너
> 10. 클리어링 하우스
>
> #### 11. (	)은 공개키 암호 방식 기반으로 디지털 인증서를 활용하는 소프트웨어, 하드웨어, 사용자, 정책 및 제도 등을 총칭하는 암호 기술이다.
>
> #### 12. (	)은 디지털 저작물에 특정한 번호를 부여하는 일종의 바코드 시스템으로서 디지털 저작물의 저작권 보호 및 정확한 위치 추적이 가능한 시스템이다.
>
> #### 13. (	)은 디지털 콘텐츠 / 웹 서비스 권리 조건을 표현한 XML 기반의 마크업 언어이다.
>
> #### 14. (	)은 멀티미디어 관련 요소 기술들이 통일된 형태로 상호 운용성을 보장하는 멀티미디어 표준 규격이다.
>
> #### 15. (	)은 다양한 미디어 포맷에 따라 각종 콘텐츠를 작성, 수집, 배급하는 콘텐츠 생산에서 활용, 폐기까지 전 공급 과정을 관리하는 기술이다.
>
> #### 16. (	)은 역공학을 통한 공격을 막기 위해 프로그램의 소스코드를 알아보기 힘든 형태로 바꾸는 기술이다.
>
> #### 17. (	)은 커널 암호화 방식으로 데이터베이스 파일을 직접 암호화하고, 접근 제어와 감사기록 기능이 추가된 데이터베이스 보안 강화 기술이다.
>
> #### 18. (	)은 한 번의 시스템 인증을 통하여 여러 정보시스템에 재인증 절차 없이 접근할 수 있는 통합 로그인 기술이다.
>
> #### 19. (	)은 제품 소프트웨어 개발단계부터 적용한 기준이나 패키징 이후 설치 및 사용자 측면의 주요 내용 등을 기록한 문서이다.
>
> #### 20. (	)은 사용자가 제품을 구매한 후 최초 설치 시 참조하는 매뉴얼이다.
>
> 11. PKI
> 12. DOI
> 13. XrML
> 14. MPEG-21
> 15. CMS
> 16. 코드 난독화
> 17. Secure DB
> 18. SSO
> 19. 제품 소프트웨어 매뉴얼
> 20. 제품 소프트웨어 설치 매뉴얼
>
> #### 21. (	)은 개발된 컴포넌트 또는 패키지에 대해 제품화하고 배포 정보를 포함한 문서이다.
>
> 21. 제품 소프트웨어 배포본