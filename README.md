# 객체지향

`자율적인 객체`

객체지향이란 시스템을 상호작용하는 **자율적인 객체들의 공동체**로 바라보고 객체를 이용해 시스템을 분할하는 방법이다. 

객체지향 패러다임의 목적은 현실 세계를 모방하는 것이 아니라 현실 세계에서 사용되는 개념, 용어들을 기반으로 새로운 세계를 창조하는 것이다. 따라서 소프트웨어 세계의 객체는 현실 세계에 존재하는 객체와는 전혀 다른 모습을 보이는 것이 일반적이다.

- **자율적인 객체**란 **상태**와 **행위**를 함께 지니며 스스로 자기 자신을 책임지는 객체를 의미한다.
- 객체는 시스템의 행위를 구현하기 위해 다른 객체와 **협력**한다. 각 객체는 협력 내에서 정해진 역할을 수행하며 역할은 관련된 **책임**의 집합이다.
- 객체는 다른 객체와 협력하기 위해 메시지를 전송하고, **메시지**를 수신한 객체는 메시지를 처리하는 데 적합한 **메서드**를 자율적으로 선택한다.

## 객체지향으로 향하는 걸음

1. 클래스가 아니라 객체를 바라보는 것
2. 객체를 독립적인 존재가 아니라 기능을 구현하기 위해 협력하는 공동체의 존재로 바라보는 것
3. 협력에 참여하는 객체들에게 얼마나 적절한 역할과 책임을 부여할 수 있느냐에 대한 것
4. 이 개념들을 사용하는 프로그래밍 언어라는 틀에 흐트러짐 없이 담아낼 수 잇는 기술을 익히는 것

객체지향 설계는 협력에 참여하기 위해 어떤 객체가 어떤 책임을 수행하고 어떤 객체로부터 메시지를 수신할 것인지를 결정하는 것으로부터 시작된다. 어떤 클래스가 필요하고 어떤 메서드를 포함해야 하는지를 결정하는 것은 책임과 메시지에 대한 대략적인 윤곽을 잡은 후에 시작해도 늦지 않다.

# 객체지향에서 가장 중요한 개념

`객체`, `협력`, `역할`, `책임`

## 객체

`상태`, `행동`, `식별자`

객체란 식별 가능한 개체 또는 사물이다. 객체는 자동차처럼 만질 수 있는 구체적인 사물일 수도 있고, 시간처럼 추상적인 개념일 수도 있다. 객체는 구별 가능한 식별자, 특징적인 행동, 변경 가능한 상태를 가진다. 소프트웨어 안에서 객체는 저장된 상태와 실행가능한 코드를 통해 구현된다.

### 상태

`정적 프로퍼티`, `동적 프로퍼티`, `속성`, `링크`

상태는 특정 시점에 객체가 가지고 있는 정보의 집합으로 객체의 구조적 특징을 표현한다. 객체의 상태는 객체에 존재하는 정적인 프로퍼티와 동적인 프로퍼티 값으로 구성된다. 객체의 프로퍼티는 속성과 다른 객체를 참조하는 링크로 구분할 수 있다.

- 정적 프로퍼티: 변경되지 않고 고정된 프로퍼티(예: 컵의 크기)

- 동적 프로퍼티: 시간이 흐름에 따라 변경되는 프로퍼티 값(예: 330ml)

- 속성: 객체를 구성하는 단순한 값(예: 컵의 크기와 음료 양)

- 링크: 객체와 객체 사이의 의미 있는 연결. 객체 사이에 링크가 존재해야만 요청을 보내고 받을 수 있다.(컵과 빨대의 협력을 가능하게 만드는 연결)

- 왜 상태가 필요할까?

  철수가 영희에게 "지금 밥 먹을래?"라고 묻는다.

  영희는 "아침에 일어나자마자 오믈렛을 먹었고, 운동을 하다가 샤워하고 커피를 마셨어. 출근했는데 선배님이 샌드위치를 주셨지 뭐야. 그리고 점심엔 수진이와 만나서.... 지금은 배고파 ㅎㅎ..."라고 대답했다.

  철수는 영희가 오랫동안 하는 말들을 들어야 했다. 필요했던 것은 '영희가 배고프다'라는 **상태**였을 뿐인데 말이다. 이처럼 상태를 이용하면 과거의 모든 행동 이력을 설명하지 않고도 행동을 쉽게 예측할 수 있다. 즉, 과거에 얽매이지 않고 현재를 기반으로 객체의 행동을 이해할 수 있는 것이다.

- 컵과 빨대만으로 협력이 가능할까?

  예시를 보면서 '컵의 음료를 빨대로 마시려면 사람이 필요한 것 아니야?'라고 생각했을지도 모른다. 처음 이야기했던 대로 객체지향은 현실 세계를 모방하는 것과 차이가 있다. 객체지향에서 객체는 자율적으로 행동한다. 따라서 컵이 빨대에게 음료를 외부로 방출시키겠다고 요청하면 빨대는 스스로 음료를 빨아올리게 된다. 

### 행동

행동이란 외부의 요청 또는 수신된 메시지에 응답하기 위해 동작하고 반응하는 활동이다. 행동의 결과로 객체는 자신의 상태를 변경하거나 다른 객체에게 메시지를 전달할 수 있다. 객체는 행동을 통해 다른 객체와의 협력에 참여하므로 행동은 외부에 가시적이어야 한다. 그러면서도 메시지 송신자는 메시지 수신자의 상태 변경에 대해서는 전혀 알지 못한다. 객체의 행동을 유발하는 것은 외부로부터 전달된 메시지지만 객체의 상태를 변경할지 여부는 객체 스스로 결정하기 때문이다. 송신자가 상태 변경을 기대하더라도 수신자가 자신의 상태를 변경하지 않는다면 송신자가 간섭할 수 있는 어떤 여지도 없다.

객체의 상태는 저절로 변경되지 않는다. 행동은 다른 객체로 하여금 간접적으로 객체의 상태를 변경하는 것을 가능하게 한다.

### 식별자

식별자란 어떤 객체를 다른 객체와 구분하는 데 사용하는 객체의 프로퍼티다. 객체가 식별 가능하다는 것은 객체를 서로 구별할 수 있는 특정한 프로퍼티가 객체 안에 존재한다는 것을 의미한다. 이 프로퍼티를 식별자라고 한다. 모든 객체는 식별자를 가지며 식별자를 이용해 객체를 구별할 수 있다. 값은 식별자를 가지지 않기 때문에 상태를 이용한 동등성 검사를 통해 두 인스턴스를 비교해야 한다. 객체는 상태가 변경될 수 있기 때문에 식별자를 이용한 동일성 검사를 통해 두 인스턴스를 비교할 수 있다.

**값**: 숫자, 문자열, 날짜, 시간, 금액 등과 같이 변하지 않는 모델. 두 개의 숫자 1이 적혀있다면 모든 사람들은 두 숫자가 같은 것으로 간주한다.

**동등성**: 상태를 이용해 두 값이 같은지 판단할 수 있는 성질. 숫자 1의 개념은 시간이 지나도 변하지 않는다.

**동일성**: 상태와 무관하게 식별자를 기반으로 객체가 같은지 판단할 수 있는 성질

## 협력

`요청`, `응답`

협력의 성공은 특정한 역할을 맡은 각 객체가 얼마나 요청을 성실히 이행하는가에 달려 있다. 객체가 다른 객체와 협력하는 유일한 방법은 다른 객체에게 요청을 보내는 것이다. 요청을 수신한 객체는 요청을 처리하기 위해 적절한 방법에 따라 행동한다. 따라서 객체의 행동은 객체가 협력에 참여할 수 있는 유일한 방법이다.

### 요청

객체들은 스스로 해결하지 못하는 문제와 마주치면 문제 해결에 필요한 지식을 알고 있거나 서비스를 제공해줄 수 있는 객체에게 도움을 요청한다.

### 응답

요청을 받은 객체는 주어진 책임을 다하면서 필요한 지식이나 서비스를 제공한다. 즉, 다른 객체의 요청에 응답한다.

## 역할

객체들은 다른 객체와 협력하는 과정 속에서 특정한 역할을 부여받는다. 역할은 어떤 협력에 참여하는 특정한 객체가 협력 안에서 차지하는 책임이나 의무를 의미한다. **역할은 의미적으로 책임이라는 개념을 내포한다**. 특정한 역할은 특정한 책임을 암시한다. 협력에 참여하며 특정한 역할을 수행하는 객체들은 역할에 적합한 책임을 수행하게 된다.

- 여러 객체가 동일한 역할을 수행할 수 있다.
- 역할은 대체 가능성을 의미한다.
- 각 객체는 책임을 수행하는 방법을 자율적으로 선택할 수 있다.
- 하나의 객체가 동시에 여러 역할을 수행할 수 있다.

역할은 협력 내에서 다른 객체로 대체할 수 있음을 나타내는 일종의 표식이다. 협력 안에서 역할은 "이 자리는 해당 역할을 수행할 수 있는 어떤 객체라도 대신할 수 있습니다"라고 말하는 것과 같다. 역할을 대체하기 위해서는 각 역할이 수신할 수 있는 메시지를 동일한 방식으로 이해해야 한다. 

요약하면 역할의 개념을 사용하면 **유사한 협력**을 **추상화**해서 인지 과부하를 줄일 수 있다. 또한 다양한 객체들이 협력에 참여할 수 있기 때문에 협력이 좀 더 유연해지며 다양한 객체들이 동일한 협력에 참여할 수 있기 때문에 재사용성이 높아진다.

## 책임

**요청을 처리하기 위해 객체가 수행하는 행동**

객체 지향에서는 어떤 객체가 어떤 요청에 대해 대답해 줄 수 있거나, 적절한 행동을 할 의무가 있는 경우 해당 객체가 책임을 가진다고 말한다. 책임은 객체에 의해 정의되는 응집도 있는 행위의 집합으로, 객체가 알아야 하는 정보와 객체가 수행할 수 있는 행위에 대해 개략적으로 서술한 문장이다. 결국 어떤 객체에 대한 요청은 그 객체가 요청을 처리할 책임이 있음을 암시한다.

### 책임의 구성

- 하는 것(doing)
  - 객체를 생성하거나 계산을 하는 등의 스스로 하는 것
  - 다른 객체의 행동을 시작시키는 것
  - 다른 객체의 활동을 제어하고 조절하는 것
- 아는 것(knowing)
  - 개인적인 정보에 관해 아는 것
  - 관련된 객체에 관해 아는 것
  - 자신이 유도하거나 계산할 수 있는 것에 관해 아는 것

### 역할과 책임

- 여러 사람이 동일한 역할을 수행할 수 있다.
- 역할은 대체 가능성을 의미한다.
- 책임을 수행하는 방법은 자율적으로 선택할 수 있다.
- 한 사람이 동시에 여러 역할을 수행할 수 있다.

객체는 역할이 암시하는 책임보다 더 많은 책임을 가질 수 있다. 따라서 대부분의 경우에 객체의 타입과 역할 사이에는 일반화/특수화 관계가 성립하는 것이 일반적이다.

### 책임과 메세지

객체는 다른 객체로부터 요청이 전송됐을 경우에만 자신에게 주어진 책임을 수행한다. **객체가 다른 객체에게 주어진 책임을 수행하도록 요청을 보내는 것을 메시지 전송**이라고 한다. 따라서 두 객체 간의 협력은 메시지를 통해 이뤄진다.

책임이 요청을 수신하는 객체 관점에서 무엇을 할 수 있는지를 나열하는 것이라면 메시지는 협력에 참여하는 두 객체 사이의 관계를 강조한 것이다. 책임을 결정한 후 실제로 협력하면서 메시지로 변환할 때는 하나의 책임이 여러 메시지로 분할되는 것이 일반적이다.

자율적인 책임의 특징은 객체가 '어떻게(how)'해야 하는가가 아니라 '무엇(what)'을 해야 하는가를 설명한다는 것이다. 어떻게 해야 하는지는 책임의 수준에서 어느 정도 결정돼 있기 때문에 무엇을 하는지 선택할 수 있는 부분은 크게 제한될 수밖에 없다.

## 객체

`메시지`, `메서드`

실제로 협력에 참여하는 주체는 객체다. 인간의 세계에서 사람이 없으면 역할, 책임, 협력이 아무런 의미가 없는 것처럼 객체가 존재하지 않는 객체지향 세계 역시 아무런 의미가 없다. 객체는 다른 객체와의 협력을 통해 기능을 구현하기 때문에 협력의 품질을 결정하는 것은 객체의 품질이다. 

메서드란 메시지를 수신했을 때 책임을 수행하는 방법을 의미한다.

객체의 품질을 위해서 다음과 같은 두 가지 덕목을 갖춰야 한다.

- 객체는 충분히 '협력적'이어야 한다. 다른 객체의 요청에 충실히 귀 기울이고, 다른 객체에게 적극적으로 도움을 요청할 정도로 열린 마음을 지녀야 한다. 객체는 다른 객체의 명령이 복종하는 것이 아니라 요청에 응답할 뿐이며, 어떤 방식으로 응답할지는 객체 스스로 판단하고 결정한다. 심지어 요청에 응할지 여부도 객체 스스로 결정할 수 있다.
- 객체는 충분히 '자율적'이어야 한다. 자기 스스로의 원칙에 따라 어떤 일을 하거나 자기 스스로를 통제하여 절제하여야 한다

### 예시: **카페 - 커피 주문**

**협력**

- 손님, 캐셔, 바리스타 사이의 암묵적인 협력 관계

**역할**

- 커피를 주문하는 손님
- 주문을 받는 캐셔
- 커피를 제조하는 바리스타

**책임**

- 커피를 주문할 수 있는 책임을 수행하는 손님
- 손님의 주문을 받는 책임을 수행하는 캐셔
- 주문된 커피를 제조하는 책임을 수행하는 바리스타

# 인터페이스

`공용 인터페이스`, `사적 인터페이스`

- 인터페이스란?

  인터페이스는 어떤 두 사물이 마주치는 경계 지점에서 서로 상호작용할 수 있게 이어주는 방법이나 장치를 의미한다. 텔레비전을 시청하기 위해 가장 많이 사용하는 인터페이스는 텔레비전의 리모컨이며, 엘레베이터를 타고 원하는 층에 도착하기 위해서는 엘레베이터의 버튼을 눌러야만 한다. 개발자들은 미리 약속된 어플리케이션 프로그래밍 인터페이스(API)를 통해 다른 사람이 작성한 코드와 상호작용한다. 사람이건 사물이건 세계에 존재하는 그 어떤 대상과 상호작용하고 싶다면 그 대상이 제공하는 인터페이스의 사용법을 익혀야 한다.

  일반적으로 인터페이스는 다음과 같은 세 가지 특징을 지닌다.

  1. 인터페이스의 사용법을 익히기만 하면 내부 구조나 동작 방식을 몰라도 쉽게 대상을 조작하거나 의사를 전달할 수 있다(예: 자동차의 핸들, 변속기, 브레이크의 사용법을 익히면 조향장치나 엔진의 구조를 몰라도 자동차를 운전할 수 있다).
  2. 인터페이스 자체는 변경하지 않고 단순히 내부 구성이나 작동방식만을 변경하는 것은 인터페이스 사용자에게 어떤 영향도 미치지 않는다(예: 자동차의 엔진이나 타이어를 교체했다고 해서 자동차 운전법을 다시 익히지 않아도 된다).
  3. 대상이 변경되더라도 동일한 인터페이스를 제공하기만 하면 아무런 문제 없이 상호작용할 수 있다(예: 자동차 운전법을 알면 다른 자동차의 운전법을 다시 익힐 필요가 없다).

객체의 인터페이스는 객체가 수신할 수 있는 메시지의 목록으로 구성되며 객체가 어떤 메시지를 수신할 수 있는지가 객체가 제공하는 인터페이스의 모양을 만든다.

인터페이스는 외부에서 접근 가능한 공개된 **공용 인터페이스**와 내부에서만 접근 가능한 **사적인 인터페이스**로 구분된다. 모든 인터페이스는 메시지 전송을 통해서만 접근할 수 있다. 단지 메시지 송신자가 다른 객체인지 아니면 객체 자신인지만 다를 뿐이다. 객체지향 패러다임 안에서는 자기 스스로에게 뭔가를 요청하는 경우에도 메시지를 전송해야 한다. 객체지향에서 모든 상호작용은 메시지를 통해서만 이뤄저야 하며 자기 자신과의 상호작용 역시 예외가 아니다.

객체가 협력에 참여하기 위해 수행하는 메시지가 객체의 공용 인터페이스 모양을 결정한다. 객체가 책임을 수행하게 하는 것은 객체에게 전송되는 메시지다. 책임은 객체가 메시지를 수신했을 때 수행해야 하는 객체의 행동이며, 실제로 객체의 공용 인터페이스를 구성하는 것은 객체가 외부로부터 수신할 수 있는 메시지의 목록이다. 

## 인터페이스의 구현과 분리

### 객체 관점에서 생각하는 방법

`추상화`, `구현`

- 좀 더 **추상적인 인터페이스**
  → 예) 진라면 끓여줘 → 라면 끓여줘: 추상적인 수준의 인터페이스는 수신자의 자율성을 보장할 수 있다.
- 최소 인터페이스
- 인터페이스와 구현 간에 차이가 있다는 점을 인식

**구현**

객체지향 세계에서 내부 구조와 작동 방식을 가리키는 고유의 용어는 구현이다. 객체를 구성하지만 공용 인터페이스에 포함되지 않는 모든 것이 구현에 포함된다.

객체는 `상태`를 가진다. 상태는 객체에 포함되지만 객체 외부에 노출되는 공용 인터페이스의 일부는 아니다. 따라서 상태를 어떻게 표현할 것인가는 객체의 구현에 해당된다.

객체는 `행동`을 가진다. 행동은 메시지를 수신했을 때만 실행되는 일종의 메시지 처리 방법이다. 이 처리 방법을 메서드라고 한다. 메서드를 구성하는 코드 자체는 객체 외부에 노출되는 공용 인터페이스의 일부는 아니기 때문에 객체의 구현 부분에 포함된다.

### 인터페이스와 구현의 분리 원칙

`인터페이스와 구현의 분리 원칙`, `캡슐화`

인터페이스와 구현의 분리 원칙은 소프트웨어의 변경을 관리하기 위한 것이다. 

훌륭한 객체란 구현을 모른 채 인터페이스만 알면 쉽게 상호작용할 수 있는 객체를 의미한다. 이것은 객체를 설계할 때 객체 외부에 노출되는 인터페이스와 객체의 내부에 숨겨지는 구현을 명확하게 분리해서 고려해야 한다는 것을 의미한다. 이를 **인터페이스와 구현의 분리 원칙**이라고 한다.

결론적으로 객체 설계의 핵심은 두 개의 분리된 요소로 분할해 설계하는 것이다. 그것이 바로 외부에 공개되는 인터페이스와 내부에 감춰지는 구현이다. 객체 내부에 속하는 상태와 메서드 구현을 수정하더라도 객체 내부에 영향을 미쳐서는 안 된다. 객체 외부에 영향을 미치는 변경은 객체의 공용 인터페이스를 수정할 때뿐이다.

- 인터페이스와 구현의 분리 원칙이 왜 중요할까?

  소프트웨어는 자주 변경되기 때문이다. 객체지향 세계에서 어떤 객체를 수정했을 때 어떤 객체가 영향을 받는지 판단하는 것은 어렵다. 객체의 모든 것이 외부에 공개돼 있다면 아무리 작은 부분을 수정하더라도 변경에 의한 파급효과가 거대할 것이다. 
  인터페이스와 구현의 분리 원칙은 객체를 자율적인 존재로 만드는 데도 기여한다. 자율적인 객체는 외부와 상관없이 메시지를 처리하는 메서드를 스스로 선택할 수 있어야 한다. 이것은 외부에 영향을 주지 않고도 메서드를 자유롭게 변경할 수 있어야 한다는 것을 의미한다. 따라서 적절한 구현을 선택하고 이를 인터페이스 뒤로 감추는 것은 객체의 자율성을 향상시킬 수 있는 가장 기본적인 방법이다.

# 기능과 구조

객체지향 세계를 구축하기 위해서는 사용자에게 제공할 기능과 기능을 담을 안정적인 구조라는 재료가 준비돼 있어야 한다. 기능은 사용자가 자신의 목표를 달성하기 위해 사용할 수 있는 시스템의 서비스다. 구조는 시스템의 기능을 구현하기 위한 기반으로, 기능 변경을 수용할 수 있도록 안정적이어야 한다.

## 기능과 구조의 표현 기법

`유스케이스`, `도메인`

- 구조는 사용자나 이해 관계자들이 도메인에 관해 생각하는 개념과 개념들 간의 관계로 표현한다.
- 기능은 사용자의 목표를 만족시키기 위해 책임을 수행하는 시스템의 행위로 표현한다.

일반적으로 기능을 수집하고 표현하기 위한 기법을 **유스케이스 모델링**이라고 하고 구조를 수집하고 표현하기 위한 기법을 **도메인 모델링**이라고 한다. 두 가지 모델링 활동의 결과물을 각각 **유스케이스**와 **도메인 모델**이라고 한다.

# 객체지향 설계 기법

올바른 객체를 설계하기 위해서는 먼저 견고하고 깔끔한 협력을 설계해야 한다. 협력을 설계한다는 것은 설계에 참여하는 객체들이 주고받을 요청과 응답의 흐름을 결정한다는 것을 의미한다. 이렇게 결정된 요청과 응답의 흐름은 객체가 협력에 참여하기 위해 수행될 책임이 된다.

일단 객체에게 책임을 할당하고 나면 책임은 객체가 외부에 제공하게 될 행동이 된다. 협력이라는 문맥에서 객체가 수행하게 될 적절한 책임. 즉 행동을 결정한 후에 그 행동을 수행하는 데 필요한 데이터를 고민해야 한다. 그리고 객체가 협력에 참여하기 위해 필요한 데이터와 행동이 어느 정도 결정된 후에 클래스의 구현 방법을 결정해야 한다. 결과적으로 클래스와 데이터는 협력과 책임의 집합이 결정된 후에야 무대 위에 등장할 수 있다.

객체지향이 올바른 객체에 올바른 책임을 할당하는 것과 관련된 모든 것이라면 협력이라는 문맥 안에서 객체를 생각하는 것은 올바른 객체지향 애플리케이션을 구현하는 것과 관련된 모든 것이다. 일단 협력이라는 견고한 문맥이 갖춰지면 우리의 초점은 협력을 위해 필요한 책임의 흐름으로 옮겨진다. 그리고 협력에 필요한 책임을 결정하고 객체에게 책임을 할당하는 과정을 얼마나 합리적이고 적절하게 수행했는지가 객체지향 설계의 품질을 결정한다.

객체의 행위에 초점을 맞추기 위해서는 협력이라는 실행 문맥 안에서 책임을 분배해야 한다. 각 객체가 가져야 하는 상태와 행위에 대해 고민하기 전에 그 객체가 참여할 문맥인 협력을 정의하라. 객체지향 시스템에서 중요한 것은 충분히 자율적인 동시에 충분히 협력적인 객체를 창조하는 것이다. 이 목표를 달성할 수 있는 가장 쉬운 방법은 객체를 충분히 협력적으로 만든 후에 협력이라는 문맥 안에서 객체를 충분히 자율적으로 만드는 것이다.

## 책임-주도 설계(Responsibility-Driven Design)

객체지향 설계는 애플리케이션의 기능을 구현하기 위한 협력 관계를 고안하고, 협력에 필요한 역할과 책임을 식별한 후 이를 수행할 수 있는 적절한 객체를 식별해 나가는 과정이다. 책임-주도 설계는 객체의 역할, 책임, 협력을 고안하기 위한 방법과 절차를 제시한다.

### 설계 절차

- 시스템이 사용자에게 제공해야 하는 기능인 시스템 책임을 파악한다.
- 시스템 책임을 더 작은 책임으로 분할한다.
- 분할된 책임을 수행할 수 있는 적절한 객체 또는 역할을 찾아 책임을 할당한다.
- 객체가 책임을 수행하는 중에 다른 객체의 도움이 필요한 경우 이를 책임질 적절한 객체 또는 역할을 찾는다.
- 해당 객체 또는 역할에게 책임을 할당함으로써 두 객체가 협력하게 된다.

## 디자인 패턴(Design Pattern)

디자인 패턴은 전문가들이 반복적으로 사용하는 해결 방법을 정의해 놓은 설계 템플릿의 모음이다. 또한 디자인 패턴은 책임-주도 설계의 결과를 표현한다.

만약 특정한 상황에 적용 가능한 디자인 패턴을 잘 알고 있다면 책임-주도 설계의 절차를 순차적으로 따르지 않고도 시스템 안에 구현할 객체들의 역할과 책임, 협력 관계를 빠르고 손쉽게 포착할 수 있을 것이다. 즉, 디자인 패턴은 책임-주도 설계의 결과물인 동시에 지름길이다.

## 테스트-주도 개발(Test-Driven Development)

테스트를 먼저 작성하고 테스트를 통과하는 구체적인 코드를 추가하면서 애플리케이션을 완성해나가는 방식이다. 테스트는 테스트-주도 개발을 통해 얻을 수 있는 별도의 보너스 같은 것이며, 실제 목적은 구체적인 코드를 작성해나가면서 역할, 책임, 협력을 식별하고 식별된 역할, 책임, 협력이 적합한지를 피드백받는 것이다.

# 참고

[객체지향의 사실과 오해](https://book.naver.com/bookdb/book_detail.nhn?bid=9145968)

