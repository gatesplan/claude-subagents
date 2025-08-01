# 프로그래밍 AI에이전트 코딩 프로토콜 - 복합 애플리케이션
- 이 문서는 복합 애플리케이션 개발을 담당하는 에이전트가 코드 작성시 지켜야 하는 규칙을 정의한다.
- 이 문서는 에이전트가 *절대* 수정하지 않는다.
- 복합 애플리케이션이란 하나의 완성된 기능을 위해 여러 계층의 기능이 조합되어야 하는 일정 수준 이상의 프로그램이다. 이 문서가 있는 개발 환경은 복합 애플리케이션이다.


## 계층 구조
- 복합 애플리케이션은 크게 6개 계층으로 구분한다.

### 0. 입자층
`Entities`, `Collections`, `Structs`, `Constants`와 같은 가장 작은 단위의 구조를 정의한다.
각 구조는 루트 바로 아래에 해당 작업 디렉터리를 가진다.

### 1. 코어층 (Core)
외부와의 통신을 전담하거나, 저장된 데이터를 입출력하거나, 특정 기능의 가장 작은 단위를 구현하는 등 하드웨어 개입 작업에 의존하는 가장 낮은 단계의 구성요소.

### 2. 서비스 (Service)
응용 계층의 구성요소로, 일정한 목적에 따라 조직한 코어층 이하의 조합 또는 보다 복잡한 동작을 구현한다.
서비스 단계에서 의미있는 하나의 기능 집합을 구현하지만, 서비스 상호간에 의존해서는 안 된다.

### 3. 플러그인 (Plugin)
플러그인 단계에서부터 의존성 역전을 반드시 적용하며, 여러 서비스를 조합하여 의도된 작업을 수행하는 기능을 구현한다.
컨트롤러의 모든 기능이 플러그인을 통해 구현되어야 하는것은 아니나, 행위 기반 캡슐화가 필요할 때 선택적으로 플러그인을 구현하여 동작을 관리한다.
이 계층은 복잡한 어플리케이션에서 동작 자체가 추상화 필요할 때 사용하는 보조 계층에 해당한다.

### 4. 컨트롤러 (Controller)
여러 서비스 또는 플러그인을 제어하여 특수한 목적을 달성하기 위해 만드는 계층.
클라이언트가 상호작용하는 대상이며, 사용자 인터페이스와 연결된다.

### 5. 사용자 인터페이스 (User Interface)
사용자와 상호작용하는 최상위 계층. 여기서부터 프론트엔드 또는 전체 패키지의 엔트리포인트이다.
항상 컨트롤러를 통해 이하 레벨과 상호작용한다.
