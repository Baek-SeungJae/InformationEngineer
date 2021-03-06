# 정보처리기사

## 3. 애플리케이션 설계

### 20. 소프트웨어 아키텍쳐

> ### 1. 개요
>
> - 소프트웨어의 기본 골격이 되는 구조.
> - 소프트웨어를 구성하는 요소들 간의 관계를 표현하는 시스템의 구조, 구조체
> - 소프트웨어 개발 시 적용되는 원칙과 지침이며, 이해관계자들의 의사소통 도구로 활용된다.
> - 소프트웨어 아키텍처의 설계는 좋은 품질을 유지하면서 사용자의 비기능적 요구사항으로 나타난 제약을 반영하고, 기능적 요구사항을 구현하는 방법을 찾는 과정이다.
> - 애플리케이션의 분할 방법, 모듈에 할당된 기능, 모듈간의 인터페이스를 결정한다.
> - 모듈와 추상화 단계적분해, 정보은닉
>
> ### 2. 모듈화
>
> - 성능을 향상시키거나 시스템의 수정 및 재사용, 유지관리가 용이하도록 시스템의 기능들을 모듈 단위로 나누는 것
> - 자주 사용되는 계산식이나 사용자 인증 같은 공통 모듈로 구성하여 프로젝트의 재사용성을 향상 시킬 수 있다.
> - 모듈의 크기를 너무 작게 나누면 개수가 많아져 모듈 간의 통합 비용이 많이 들고, 너무 크게 나누면 개수가 적어 통합 비용은 적게 들지만 모듈 하나의 개발비용이 많이든다.
>
> ### 3. 추상화
>
> - 전체적이고 포괄적인 개념을 설계한 후 차례로 세분화하여 구체화 시켜 나가는 것
> - 인간이 복잡한 문제를 다룰 때 가장 기본적으로 사용하는 방법.
> - 완전한 시스템을 구축하기 전에 그 시스템과 유사한 모델을 만들어서 여러가지 요인들을 테스트 할 수 있다.
> - 최소의 비용으로 실제 상황에 대처할 수 있고, 시스템의 구조 및 구성을 대략적으로 파악할 수 있게 해준다.
>   - 과정 추상화 : 자세한 수행 과정을 정의하지 않고 전반적인 흐름만 파악할 수 있게 설계
>   - 데이터 추상화 : 데이터의 세부 속성이나 용도를 정의하지 않고, 데이터 구조를 대표할 수 있는 표현으로 설계
>   - 제어 추상화 : 이벤트 발생의 정확한 절차나 방법을 정의하지 않고, 대표할 수 있는 표현으로 대체
>
> ### 4. 단계적 분해
>
> - Niklaus Wirth에 의해 제안된 하향식 설계 전략. 문제를 상위 중요 개념으로부터 하위의 개념으로 구체화 시키는 분할 기법
> - 추상화의 반복으로 세분화
> - 소프트웨어의 기능 -> 구체화 -> 알고리즘 -> 자료구조 식으로 상세한 내용을 뒤로 미루어 진행
>
> ### 5. 정보은닉
>
> - 모듈 내부에 포함된 절차, 자료들의 정보가 감추어져 다른 모듈이 접근하거나 변경하지 못하도록 하는 기법
> - 어떤 모듈이 기능을 활용하는데 다른 모듈과 데이터를 주고받아야 할 때 인터페이스를 통해 주고받는다.
> - 모듈을 독립적으로 수행할 수 있고 하나의 모듈이 변경되어도 다른 모듈에 영향을 주지 않으므로, 수정, 시험, 유지보수가 용이하다.
>
> ### 6. 소프트웨어 아키텍처의 품질 속성
>
> - 시스템
>   - 성능 : 사용자의 요청과 같은 이벤트가 발생했을 때, 이를 적절하고 빠르게 처리하는 방법
>   - 보안 : 허용되지 않은 접근을 막고, 허용된 접근에는 적절한 서비스를 제공한다.
>   - 가용성 : 장애없이 정상적으로 서비스를 제공
>   - 기능성 : 사용자가 요구한 기능을 만족스럽게 구현
>   - 사용성 : 소프트웨어를 사용하는데 헤매지 않고 명확하고 편리하게 구현
>   - 변경 용이성 : 처음 설계한 목표와 다른 하드웨어나 플랫폼에서도 동작가능 해야함
>   - 확장성 : 시스템의 용량, 처리능력을 확장시켰을 때 효과적으로 활용할 수 있도록 구현
>   - 기타 : 테스트 용이성, 배치성, 안정성
> - 비즈니스
>   - 시장 적시성 : 정해진 시간에 맞춰 프로그램을 출시
>   - 비용과 혜택 : 개발 비용을 더 투자하여 유연성이 높은 아키텍처를 만들 것인지를 결정, 유지보수 개발비의 trade-off
>   - 예상 시스템 수명 : 시스템을 얼마나 오랫동안 사용할 것인지를 고려, 변경용이성, 확장성을 함께 고려
>   - 기타 : 목표 시장, 공개 일정, 기존 시스템과 통합
> - 아키텍처
>   - 개념적 무결성 : 전체 시스템과 시스템을 이루는 구성요소들 간의 일관성
>   - 정확성, 완결성 : 요구사항와 요구사항을 구현하기 위해 발생하는 제약사항들을 모두 충족 시켜야 함
>   - 구축 가능성 : 모듈 단위로 구분된 시스템을 적절하게 분배하여 유연하게 일정을 변경할 수 있도록 하는 것
>   - 기타 : 변경성, 시험성, 일치성, 대체성
>
> ### 7. 소프트웨어 아키텍처 설계 과정
>
> - 설계 목표 : 시스템의 개발 방향을 명확히 하기 위해 비즈니스 목표, 우선순위 등의 요구사항을 분석하여 전체 시스템의 설계 목표를 설정한다.
> - 시스템 타입 결정 : 시스템과 서브시스템의 타입을 결정하고, 설계 목표와 함께 고려하여 아키텍처 패턴을 적용한다.
> - 아키텍처 패턴 적용 : 아키텍처 패턴을 참조하여 시스템의 표준 아키텍처를 설계한다.
> - 서브시스템 구체화 : 서브시스템의 기능 및 서브시슽메 간의 상호작용을 위한 동작과 인터페이스를 정의한다.
> - 검토 : 아키텍처가 설계 목표에 부합하는지, 요구사항이 잘 반영 되었는지, 설계의 기본원리를 만족하는지 등을 검토한다.

### 21. 아키텍처 패턴

> ### 1. 개요
>
> - 아키텍처를 설계할 때 참조할 수 있는 전형적인 해결 방식, 예제를 의미한다.
> - 아키텍처 패턴은 소프트웨어 시스템의 구조를 구성하기 위한 기본적인 윤곽을 제시한다.
> - 서브시스템들과 그 역할이 정의되어 있으며, 서브시스템 사이의 관계와 여러 규칙, 지침 등이 포함되어 있다.
> - 아키텍처 스타일, 표준 아키텍처라고도 한다.
>
> - 장점
>   - 시행착오를 줄여 개발 시간을 단축시키고 고품질의 제품을 생산한다.
>   - 검증된 구조이므로 안정적으로 개발할 수 있다.
>   - 이해관계자들이 공통된 아키텍처를 공유할 수 있어 의사소통이 간편해진다.
>   - 시스템 구조를 이해하는 것이 쉬워 개발에 참여하지 않은 사람도 유지보수가 가능하다.
>   - 시스템 특성을 개발 전에 예측할 수 있다.
>
> ### 2. 레이어 패턴
>
> - 시스템을 계층으로 구분한다.
> - 상위 계층은 하위 계층의 서비스 제공자가 되고, 하위 계층은 클라이언트가 된다.
> - 마주보는 두 개의 계층만 상호작용이 이루어진다. -> 변경 작업이 용이하다.
> - 특정 계층만 교체해 시스템을 개선하는 것이 가능하다.
> - OSI
>
> ### 3. 클라이언트 서버 패턴
>
> - 하나의 서버컴포넌트와 다수의 클라이언트 컴포넌트로 구성된다.
> - 사용자는 클라이언트와 의사소통만 하고 클라이언트가 서버에 요청한다.
> - 서버는 클라이언트의 요청에 대비해 항상 대기 상태를 유지해야 한다.
> - 클라이언트나 서버는 요청과 응답을 받기 위해 동기화 되는 경우를 제외하고는 서로 독립적이다.
>
> ### 4. 파이프 필터 패턴
>
> - 데이터 스트림 절차의 각 필터 컴포넌트로 캡슐화하여 파이프를 통해 전송하는 패턴이다.
> - 재사용성이 좋고 추가가 쉬워 확장이 용이하다.
> - 필터 컴포넌트를 재배치하여 다양한 파이프라인을 구축하는 것이 가능하다.
> - 데이터 변환, 버퍼링, 동기화 등에 사용
> - UNIX의 쉘
>
> ### 5. MVC패턴
>
> - 모델 : 서브시스템의 핵심 기능과 데이터를 보관
> - 뷰 : 사용자에게 정보를 표시
> - 컨트롤러 : 사용자로부터 받은 입력을 처리
> - 별로의 컴포넌트로 분리되어 있으므로 서로 영향을 받지 않고 개발 작업을 수행할 수 있다.
> - 한개의 모델에 대해 여러개의 뷰를 필요로하는 대화영 애플리케이션에 적합하다.
>
> ### 6. 기타
>
> - 마스터슬레이브
> - 브로커
> - 피어투피어
> - 이벤트버스
> - 블랙보드
> - 인터프리터

### 22. 객체지향

> ### 1. 개요
>
> - 현실 세계의 개체를 하나의 객체로 만들어 객체들을 조립해서 작성하는 기법
> - 구조적 기법의 문제점으로 인한 위기의 해결책으로 채택
>   - 유지보수x
>   - 추가적인 요구사항에 대응x
>   - 재사용x
>   - 유사한 소프트웨어를 개발할 때도 비슷한 비용 필요
> - 객체지향은 재사용성, 확장성, 고품질 소프트웨어를 빠르게 개발할 수 있다.
> - 객체 지향은 복잡한 구조를 단계적으로 표현하고 멀티미디어 데이터를 병렬처리할 수 있다.
> - 현실세계를 모형화 하므로 쉽게 이해할 수 있다.
> - 객체, 클래스, 캡슐화, 상속, 다형성이 있다.
>
> ### 2. 객체
>
> - 데이터와 데이터를 처리하는 함수를 묶어놓은(캡슐화한) 하나의 모듈이다.
>   - 데이터 : 객체가 가지고 있는 정보로 속성이나 상태, 분류 등 = 속성, 상태, 변수, 상수, 자료구조
>   - 함수 : 객체가 수행하는 기능, 객체가 갖는 데이터를 처리하는 알고리즘 = 메소드, 서비스, 동작, 연산
>
> - 객체는 독립적으로 식별 가능한 이름을 가지고있다.
> - 객체가 가질 수 있는 조건을 상태라고 하는데, 일반적으로 시간에 따라 변한다.
> - 객체와 객체는 상호 연관성에 의한 관계가 형성된다.
> - 객체가 반응할 수 있는 메시지의 집합을 행위라고 하며, 객체는 행위의 특징을 나타낼 수 있다.
> - 객체는 일정한 기억장소를 가지고 있다.
> - 객체의 메소드는 다른 객체로부터 메시지를 받았을 때 정해진 기능을 수행한다.
>
> ### 3. 클래스
>
> - 공통된 속성, 연산을 갖는 객체의 집합, 객체의 일반적인 타입
> - 클래스는 각각의 객체들이 갖는 속성과 연산을 정의하고 있는 틀
> - 각각의 객체를 인스턴스라고 하며, 새로운 객체를 생성하는 것을 인스턴스화 라고 한다.
> - 동일 클래스에 속한 객체들은 공통된 속성과 행위를 가지고 있으면서, 그 정보는 서로 달라서 동일 기능을 하는 여러 객체를 나타낸다.
> - 최상위 클래스는 상위클래스를 갖지 않는 클래스를 의미한다.
> - 슈퍼클래스는 부모, 서브클래스는 자식 관계를 나타낸다.
>
> ### 4. 캡슐화
>
> - 데이터와 데이터를 처리하는 함수를 하나로 묶는 것
> - 캡슐화된 객체는 인터페이스를 제외한 세부 내용이 은닉되어 외부에서 접근할 수 없고, 외부 모듈 변경에 의한 파급효과가 적다.
> - 재사용이 용이하다.
> - 메시지를 주고받을 때 상대 객체의 세부 내용은 알 필요가 없으므로 인터페이스가 단순해지고, 객체 간의 결합도가 낮아진다.
>
> ### 5. 상속
>
> - 상속은 이미 정의된 상위 클래스(부모 클래스)의 모든 속성과 연산을 하위 클래스(자식 클래스)가 물려받는 것이다.
> - 상속을 이용하면 하위 클래스는 상위 클래스의 모든 속성과 연산을 자신의 클래스 내에서 정의하지 않고도 사용할 수 있다.
> - 상위 클래스의 속성과 연산을 하위 클래스가 사용할 수 있기 때문에 소프트웨어의 reuse를 높이는 중요한 개념이다.
> - 다중상속 : 한 개의 클래스가 두 개 이상의 상위 클래스로부터 속성과 연산을 상속받는 것이다.
>
> ### 6. 다형성
>
> - 메시지에 의해 객체가 연산을 수행하게 될 때 하나의 메시지에 대해 각각의 고유한 방법으로 응답할 수 있는 능력
> - 동일메소드명 다른 매개변수

### 23. 모듈

> ### 1. 개요
>
> - 모듈화를 통해 분리된 시스템의 각 기능 : 서브루틴, 서브시스템, 소프트웨어 내의 프로그램, 작업 단위
> - 모듈은 단독으로 컴파일이 가능하며, 재사용할 수 있다.
> - 소프트웨어를 구성하는 각 모듈의 기능이 서로 독립됨, 하나의 기능만 수행하고 다른 모듈과 과도한 상호작용을 배제한다.
> - 독립성이 높은 모듈일수록 모듈을 수정하더라도 다른 모듈들에게 거의 영향을 미치지 않는다.
> - 결합도, 응집도에 의해 독립성이 측정된다. 결합도는 낮게, 응집도는 높게하는게 좋은 것
>
> ### 2. 결합도(coupling)
>
> - 모듈 간에 상호 의존하는 정도 또는 두 모듈 사이의 연관 관계를 의미한다.
> - 다양한 결합으로 모듈을 구성할 수 있으나 결합도가 약할수록 품질이 높고, 강할수록 품질이 낮다.
> - 결합도가 강하면 시스템 구현 및 유지보수 작업이 어렵다.
>   - 자료결합도 : 모듈 간의 인터페이스가 자료 요소로만 구성될 때, 데이터만 옮겨다닌다.
>   - 스탬프결합도 : 모듈간에 배열이나 레코드 등 자료구조가 전달되는 결합, 자료구조의 변화로 영향을 미칠 수 있다.
>   - 제어결합도 : 어떤 모듈의 논리적인 흐름을 제어하기 위해 제어요소를 전달하는 결합도
>   - 외부결합도 : 이 모듈에서 선언한 데이터를 외부의 다른 모듈에서 참조할 때의 결합도
>   - 공통결합도 : 공유되는 공통 데이터 영역을 여러 모듈이 사용할 때의 결합도
>   - 내용결합도 : 한 모듈이 다른 모듈의 내부기능, 내부자료를 직접참조하고 수정할 때의 결합도
>
> ### 3. 응집도(cohesion)
>
> - 정보은닉의 개념을 확장한 것
> - 명령어의 호출문 등이 내부요소들 끼리만 연결되어 있을 때 응집도가 높다고 표현
>   - 기능적 응집도 : 모든 기능 요소들이 단일 문제와 연관되어 수행될 경우
>   - 순차적 응집도 : 하나의 활동의로 나온 출력데이터를 다음 활동의 입력으로 사용
>   - 교환(통신)적 응집도 : 동일한 입력과 출력을 사용하여 다른 기능을 수행하는 구성
>   - 절차적 응집도 : 다수의 관련 기능을 가질 때 모듈 안의 구성 요소들이 그 기능을 순차적으로 수행
>   - 시간적 응집도 : 특정 시간에 처리되는 몇 개의 기능을 모다 하나의 모듈로 작성하는 경우
>   - 논리적 응집도 : 유사한 성격을 갖거나 특정 형태로 분류되는 처리요소로 하나의 모듈 형성
>   - 우연적 응집도 : 모듈 내부의 각 구성 요소들이 서로 관련 없는 요소로만 구성된 경우
>
> ### 4. 팬인/팬아웃
>
> - 팬인 : 어떤 모듈을 제어하는 모듈의 수
> - 팬아웃 : 어떤 모듈에 의해 제어되는 모듈의 수
> - 시스템의 복잡도를 알 수 있다.
> - 팬인이 높으면 재사용측면에서 잘 설계 되어있을 수 있으나, 단일장애점이 발생할 수 있으므로 주의한다.
> - 팬아웃이 높으면 불필요하게 다른 모듈을 호출하지 않는지 검토해야 한다.
> - 시스템 복잡도를 낮추려면 팬인은 높게, 팬아웃은 낮게 설계해야 한다.

### 24. 공통모듈

> ### 1. 개요
>
> - 여러 프로그램에서 공통적으로 사용할 수 있는 모듈
> - 자주 사용되는 계산식이나 매번 필요한 사용자 인증과 같은 기능들이 공통모듈로 구성될 수 있다.
> - 모듈의 재사용성 확보와 중복 개발 회피를 위해 설계 과정에서 공통 부분을 식별하고 명세를 작성할 필요가 있다.
> - 공통 모듈을 구현할 때는 다른 개발자들이 해당 기능을 명확히 이해할 수 있도록 다음 명세 기법을 준수해야 한다.
>   - 정확성 : 해당 기능이 필요하다는 것을 알 수 있도록 정확히 작성한다.
>   - 명확성 : 해당 기능을 이해할 때 중의적으로 해석되지 않도록한다.
>   - 완전성 : 시스템 구현을 위해 필요한 모든 것을 기술한다.
>   - 일관성 : 공통 기능들 간 상호 충돌이 발생하지 않도록 작성한다.
>   - 추적성 : 기능에 대한 요구사항의 출처, 관련 시스템 등 관계를 파악할 수 있도록 작성한다.
>
> ### 2. 재사용
>
> - 비용과 개발 시간을 절약하기 위해 이미 개발된 기능들을 파악하고 재구성하여 새로운 시스템 또는 기능 개발에 사용하기 적합하도록 최적화 시키는 작업이다.
> - 재사용을 위해서 누구나 이해할 수 있고 사용이 가능하도록 사용법을 공개해야 한다.
> - 재사용되는 대상은 외부 모듈과의 결합도는 낮고 응집도는 높아야 한다.
> - 규모에 따른 분류
>   - 함수와 객체 : 클래스나 메소드 단위의 소스 코드를 재사용한다.
>   - 컴포넌트 : 컴포넌트 자체에 대한 수정 없이 인터페이스를 통해 통신하는 방식으로 사용한다.
>   - 애플리케이션 : 공통된 기능들을 제공하는 애플리케이션을 공유하는 방식으로 재사용한다.
>
> ### 3. 효과적인 모듈 설계 방안
>
> - 결합도는 줄이고 응집도는 높여 독립성과 재사용성을 높인다.
> - 모듈의 제어 영역 안에서 그 모듈의 영향 영역을 유지시킨다. =>팬인 / 팬아웃과 연결되는 내용
> - 복잡도와 중복성을 줄이고 일관성을 유지시킨다.
> - 모듈의 기능은 예측가능해야하고, 지나치게 제한적이면 안된다.
> - 유지보수가 용이해야한다.
> - 모듈 크기는 시스템의 전반적인 기능과 구조를 이해하기 쉬운 크기로 분해한다.
> - 하나의 입구와 하나의 출구를 갖도록 한다.
> - 인덱스 번호나 기능 코드들이 전반적인 처리 논리 구조에 예기치 못한 영향을 끼치면 안된다.

### 25. 코드

> ### 1. 개요
>
> - 코딩의 코드가 아니다…
> - 컴퓨터를 이용하여 자료를 처리하는 과정에서 분류, 조합 및 집계를 편리하게 하기 위한 기호이다.
> - 코드는 정보를 신속, 정확, 명료하게 전달할 수 있다.
> - 일정한 규칙에 따라 작성되며, 정보 처리 효율과 처리된 정보의 가치에 많은 영향을 미친다.
> - 주빈번호, 학번, 전화번호 등이 있다.
> - 식별, 분류, 배열기능
>
> ### 2. 코드의 종류
>
> - 순차코드(Sequence Code) : 발생순서, 크기순서등 일정 기준에 따라 차례로 번호부여
> - 블록코드(Block Code) : 공통성이 있는 것끼리 블록으로 구분 후 일련번호 부여
> - 10진코드(Decimal Code) : 0~9까지 10진분할을 반복하여 대분류 중분류 소분류
> - 그룹 분류 코드(Group Classification Code) : 일정 기준에 따라 대분류, 중분류, 소분류 각 그룹 안에서 일련 번호 부여
> - 연상 코드(Mnemonic Code) : 대상화 항목의 명칭이나 약호와 관계있는 숫자, 문자, 기호를 이용하여 분류
> - 표의 숫자 코드(Significant Digit Code) : 대상 항목의 성질 즉, 길이 넓이 부피 등 물리적 수치를 코드에 대입
>
> - 합성코드(Combined Code) : 하나의 코드로 수행하기 어려운 경우 2개 이상의 코드를 조합
>
> ### 3. 코드 부여 체계
>
> - 코드 부여 체계는 이름만으로 개체의 용도와 적용 범위를 알 수 있도록 코드를 부여하는 방식
> - 각 개체의 유일한 코드를 부여하여 개체의 식별, 추출을 용이하게 한다.
> - 코드를 부여하기 전에 각 시스템의 고유한 코드와 개체를 나타내는 코드등이 적용되어야 한다.
> - 코드 부여 체계를 담당하는 자는 코드의 자릿수와 구분자, 구조 등을 상세하게 명시해야 한다.

### 26. 디자인 패턴

> ### 1. 개요
>
> - 디자인 패턴은 각 모듈의 세부적인 패턴이나 모듈들 간의 인터페이스와 같은 코드를 작성하는 수준의 세부적인 구현 방안을 설계할 때 참조할 수 있는 전형적인 해결방식, 예제이다.
> - 재사용할 수 있는 기본형 코드들이 포함되어 있다.
> - '바퀴를 다시 발명하지 마라' : 문제가 발생하면 새로 해결책을 구상하는 것 보다 기존 패턴을 참고하는 것이 효율적이다.
> - 디자인 패턴은 한 패턴에 변형을 가하거나 특정 요구사항을 반영하면 유사한 형태의 다른 패턴으로 변화되는 특징이 있다.
> - GoF라고 불리는 에릭감마, 리차드헬름, 랄프존슨, 존블라시디스가 처음으로 구체화 하였다.
> - 수많은 디자인 패턴들 중에서 가낭 일반적인 사례에 적용될 수 있는 패턴들을 분류하여 정리함으로써 지금까지도 소프트웨어 공학이나 현업에서 가장 많이 사용되는 디자인 패턴이다.
> - 생성패턴5개, 구조패턴7개 행위패턴 11개
>
> ### 2. 생성패턴
>
> - 객체의 생성과 관련
> - 객체의 생성과, 참조 과정을 캡슐화하여 객체가 생성되거나 변경되더라도 프로그램의 구조에 영향을 주지 않도록하여 프로그램에 유연성을 더한다.
>   - 추상팩토리 : 구체적인 클래스에 의존하지 않고 인터페이스를 통해 서로 연관하는 객체의 그룹을 생성해 추상적으로 표현한다. 연관된 서브클래스를 묶어 한번에 교체할 수 있다.
>   - 빌더 : 작게 분리된 인스턴스를 건축하듯이 조합하여 객체를 생성한다, 동일한 객체 생성에서도 서로 다른 결과를 만들어낼 수 있다.
>   - 팩토리메소드 : 객체 생성을 서브 클래스에서 처리하도록 분리하여 캡슐화한 패턴인다, 상위클래스에서 인터페이스만 정의하고 실제 생성은 서브클래스에서 한다.
>   - 프로토타입 : 원본 객체를 복제해 객체를 생성하는 패턴이다. 일반적인 방법으로 객체를 생성하며, 비용이 클 때 사용한다.
>   - 싱글톤 : 하나의 객체를 생성하면 생성된 객체를 어디서든 참조할 수 있지만 여러 프로세스가 동시에 참조할 수는 없다. 클래스 내에서 인스턴스가 하나뿐임을 보장하며, 불필요한 메모리낭비를 줄인다.
>
> ### 3. 구조 패턴
>
> - 클래스나 객체들을 조합하여 더 큰 구조로 만들 수 있게 해주는 패턴
>   - 어댑터 : 호환성이 없는 클래스들의 인터페이스를 다른 클래스가 이용할 수 있도록 변환
>   - 브리지 : 구현부에서 추상층을 분리하여 독립적으로 확장할 수 있도록 구성한 패턴
>   - 컴포지트 : 여러 객체를 가진 복합 객체와 단일 객체를 구분없이 다루고자 할 때 사용하는 패턴, 디렉터리 안에 디렉터리가 있듯이 복합 객체 안에 복합 객체가 포함되는 구조
>   - 데코레이터 : 객체간의 결합을 통해 능동적으로 기능들을 확장할 수 있는 패턴, 부가적인 기능을 추가하기 위해 다른 객체를 덧붙이는 방식
>   - 퍼싸드 : 복잡한 서브 클래스를 피해 더 상위에 인터페이스를 구성함으로써 서브 클래스의 기능을 간편하게 사용할 수 있도록 하는 패턴이다. 서브클래스들 사이의 인터페이스를 통합하는 Wrapper객체가 필요하다.
>   - 플라이웨이트 : 인스턴스가 필요할 때마다 매번 생성하는 것이 아니고 가능한 한 공유해서 사용함으로써 메모리를 절약하는 패턴이다.
>   - 프록시 : 접근이 어려운 객체와 여기에 연결하려는 객체 사이에서 인터페이스 역할을 수행하는 패턴이다, 네트워크 연결, 대용량 객체로의 접근 등에 이요한다.
>
> ### 4. 행위 패턴
>
> - 행위패턴은 클래스나 객체들이 서로 상호작용 하는 방법이나 책임 분배 방법을 정의하는 패턴이다.
>   - 책임연쇄(Chain of Responsibility) : 요청을 처리할 수 있는 객체가 둘 이상 존재하여 한 객체가 처리하지 못하면 다음 객체로 넘어가는 형태, 객체들이 chain으로 엮여있어 해결될 때 까지 책임이 넘어간다.
>   - 커맨드(Command) : 요청을 객체의 형태로 캡슐화하여 재이용하거나 취소할 수 있도록 요청에 필요한 정보를 로그에 남기는 패턴
>   - 인터프리터(Interpreter) : 언어에 문법을 정의하는 패턴이다. SQL이나 통신 프로토콜 같은 것을 개발 할 때 사용
>   - 반복자(Iterator) : 자료구조와 같이 접근이 잦은 객체에 대해 동일한 인터페이스를 사용하도록 하는 패턴
>   - 중재자(Mediator) : 수 많은 객체들 간의 복잡한 상호작용을 캡슐화하여 객체로 정의하는 패턴
>   - 메멘토(Memento) : 특정 시점에서의 객체 내부 상태를 개체화 함으로써 이후 요청에 따라 객체를 해당 시점의 상태로 돌릴 수 있는 기능을 제공하는 패턴
>   - 옵저버(Observer) : 한 객체의 상태가 변화하면 객체에 상속되어 있는 다른 객체들에게 변화된 상태를 전달하는 패턴이다.
>   - 상태(State) : 객체의 상태에 따라 동일한 동작을 다르게 처리해야 할 때 사용하는 패턴
>   - 전략(Strategy) : 동일한 계열의 알고리즘을 개별적으로 캡슐화하여 상호 교환할 수 있게 정의하는 패턴
>   - 템플릿 메소드 : 상위 클래스에서 골격을 정의하고 하위 클래스에서 세부처리를 구체화하는 구조의 패턴
>   - 방문자(Visitor) : 각 클래스들의 데이터 구조에서 처리 기능을 분리하여 별도의 클래스로 구성하는 패턴