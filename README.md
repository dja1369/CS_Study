# CS_Infomation

### why : 개발을 진행하며 단순히 로직만 짜는것이 아닌 어떻게 동작하는지 알고 짜기 위해 공부한것들을 정리한것 

# python
	1. 파이썬의 주요 특징 : 인터프리터 언어이며 동적타이핑 언어이다
	
	2. 파이썬의 삼항연산자 : 파이썬엔 삼항연산자가 없지만 구문에 if나 else를 붙여 비슷한 기능을 하게 할수있다

	3. 컴파일 언어와 인터프리터 언어의 차이점 : 
    컴파일언어는 컴파일러를 통해 구현되며 소스 코드를 사전에 기계어로변환하는 과정을 거쳐 빠르게 컴퓨터에서 
    구동될수 있게 한 방법이고 인터프리터 언어는 인터프리터를 통해 소스코드를 실행시에 각 구문별로 기계어로 변환하여 구현됩니다.
	
	4. 파이썬의 pyc : pyc는 py파일의 컴파일된 버전입니다 플랫폼에 독립적인 바이트코드등을 가지고 있으며 
	  이를 지원하는 모든 플랫폼에서 실행 가능하며 사전에 컴파일 되었기 때문에 py보다 성능의 향상이 있습니다.
	
	5. 파이썬이 객체 지향인 이유 : 
	  객체 지향 프로그래밍의 패러다임을 따르고 있음 이는 클래스와 인스턴스를 중심으로 돌아감
		• 클래스 : 객체를 표현하기 위한것으로 설계 도면 같은것임
		• 인스턴스 : 클래스에 의해 생성된 객체 
		• 캡슐화 : 클래스 내부 변수와 메소드를 하나로 패키징하는것 즉 객체에 선언된 변수나 메소드가 구분없이 접근할수 없도록 하는것
		• 추상화 : 상속시 필요한 메소드의 목록만 구현하고 내부는 구현하지 않아 필요에 따라 오버라이딩 할수 있게끔 만들어둔 클래스 >> 도면이라고 생각.
		• 상속 : 객체가 다른 객체를 상속받아 상속받은 객체의 요소를 사용하는것 
		• 오버라이딩 : 상속받은 메소드를 자식 클래스가 재정의 하는것
		• 오버로딩 : 같은 이름의 메소드 여러개를 가지면서 매개변수의 유형과 개수가 다르게 선언될수 있는것
		• 다형성 : 하나의 객체 혹은 메소드가 여러 타입을 참조할수 있는것 
		• 데이터 숨기기 : 클래스 구현에 대한 자세한 사항을 숨기는것 비록 파이썬은 다른 언어들 처럼 접근 권할을 나눌순 없지만 언더바를 이용하여 제한적으로 차단 가능
	
	6. map 함수의 기능 : map()은 두개의 인수를 받는데 첫 인수는 함수이며 두번째 인수는 iterable을 받음
	
	7. 파이썬 GC : 동적으로 할당한 메모리 영역중 사용되지 않는 영역을 할당 해제하여 반환하는것 
			파이썬 에서는 참조 할때마다 레퍼런스 카운팅을 하여 메모리를 해제 한다.
	8. 파이썬 데코레이터 : 함수를 감싸 추가적인 기능을 함수에 부여 할때 사용한다 
		즉 기본 함수1 에 @decorator를 부여하면 기본함수1에 추가 함수의 기능을 전달해 사용가능하다 
		
	9. 일급 함수 : 파이썬은 모든것을 객체로 취급하는데 이때 함수에 함수를 넣어서 전달이 가능하다 
			즉 함수를 인자로써 취급하는데 이것을 일급 함수라고 한다.
			
	10. 클로저 : 클로저는 외부 함수와 내부함수를 정의했을때 외부 함수가 종료된 후에도 함수가 둘러싼 환경
		즉 지역변수, 코드 등을 유지하다가 함수를 호출했을때 다시 꺼내서 사용하는 함수를 클로저 라고 한다
		이때 지역변수를 가져오기만 하는것이 아닌 변경하고 싶다면 변수에 non local 을 선언하면 값을 변경 가능함
		
	11. lambda와 Def의 차이 : Def는 다중표현을 가지며 함수를 선언하고 이름을 지정해 나중에 호출함
		람다는 함수객체를 구성하고 그 즉시 반환되며 재호출 할수없음.
		
	12. 리스트과 딕셔너리의 차이 : 리스트는 인덱스가 있는 시퀀셜 자료형 으로 각 인덱스에 데이터를 나열한것
		딕셔너리는 해쉬 형 시퀀셜 자료형으로써 키와 값의 쌍으로 구성되어있고 키를 통해 값을 찾을수 있다.
		
	13. 파이썬의 메모리 관리 : 파이썬은 개별적인 힙 영역을 사용해 메모리를 유지하는데 이때 힙 영역은 
	프로그래머는 건드릴수 없고 인터프리터만이 접근 가능합니다.
	
	14. Call by value : 표현식 또는 값이 함수의 각 변수에 바인딩 되는지 여부에 대한 인수 
	파이썬은 그 변수를 함수 수준 변수에서 지역변수로 취급하기에 해당 변수에 대한 변경 사항은 
	로컬로 취급되며 함수 외부에 반영되지 않음.
	
	15. Call by Reference : call by reference와 pass by reference는 서로 바꿔 사용가능함 
	참조로 인수를 전달하면 간단한 복사가 아닌 함수에 대한 암시적 참자로 사용가능 이때 인수에 대한 모든 수정
	사항도 호출자 에게 표현됨.

	16. 파이썬의 generator : iterator를 생성하는 함수이며 yield 키워드를 사용하여 반환함 
	일드는 리턴과 달리 반환후 종료되지않고 그 상태를 유지하며 호출시마다 다음 값을 반환하기에 
	효율적인 메모리 사용이 가능함.
	
	17. 디자인 패턴 
		a. 레이어드 패턴 : 코드를 논리적인 부분으로 나누어 독립된 모듈로 구성 하는것 
		이를 층층히 쌓아 레이어 처럼 개발하는 것이며 수직적으로 구현된다 
		
		Pregentation layer : 사용자와 직접적으로 연결되는 부분 엔드포인트부분에 해당 
			API endpoint정의, 전송된 HTTP request 읽어들임
		
		Business layer : 비스니스 로직 구현 시스템이 구현하는 로직을 이 레이어 에서 구현 
		
		Persistence layer : DB와 관련된 로직을 구현하는 부분 
		
		ApiManager(레이어이어줌) = EngineManager > Logic > DBConnector

# OOP
	SOLID 
	1. 단일 책임의 원칙 : 하나의 클래스는 하나의 역활만 담당해야 한다 
	2. 개방 폐쇄의 원칙 : 확장(상속)에는 열려있고, 수정에는 닫혀있어야한다
	3. 리스코프 치환의 원칙 : 자식 객체는 언제든지 부모 객체로 변환 가능하어야 한다 
	4. 인터페이스 분리의 원칙 : 인터페이스는 클래스가 꼭 필요한 기능만 구현되어야 한다
	5. 의존성 역전의 원칙 : 상위 모듈은 하위 모듈에 의존하면 안되며 추상화에 의존해야 하고 추상화는 세부 사항에 의존하면 안된다.
	
	JWT : Json Web Token으로 로그인 성공시 권한 인가를 위해 사용해주는 토큰임.
	토큰의 유효기간등을 설정하는 방식으로 보안을 유지할수 있음.
	
	TDD : test driven development 테스트코드를 먼저 작성한후 이를 통과하기 위한 코드를 작성하는것
	모듈화가 자연스레 이루어지면서 테스트 커버리지가 높아져 리팩토링과 유지보수가 쉬워진다

	MVC : 모델, 뷰, 컨트롤러가 분리된 형태의 아키텍쳐 이 세가지를 분리하지 않으면 어플의 확장이 어려움
	모델은 데이터처리, 뷰는 사용자 인터페이스처리, 컨트롤러는 비즈니스 로직을 처리함으로써 각각의 요소가 하나의
	역활만 담당하게 됨.

	
# Docker And VM
	Docker 와 VM 의 차이점 : Docker는 하드웨어를 가상화 하지 않고 호스트의 자원을 직접 이용하기에 메모리 접근 파일 시스템, 네트워크 속도가 가상머신에 비해 월등히 빠르다.
	
	
# Data structure

	순차 자료구조 : 시퀀셜 리스트 메모리상에서 일렬로 나열된 데이터 형
	연결 자료구조 : 링크드 리스트 메모리상에선 분산되어있지만 하나의 노드가 다음 노드를 가르키는 포인트가 있음

	삽입 
	순차 : 탐색하려는 위치를 안다면 빠름 몰라도 연결보단 빠름 하지만 데이터의 삽입 삭제는 느리다 
	연결 : 데이터가 메모리에 분산되어있기에 탐색은 느림 하지만 데이터의 삽입 삭제는 빠르다
	
	트리 : 계층구조로 구성된 자료 구조이며 트리의 모든 노드는 하나의 부모노드를 가진다 
	부모노드가 없는 최상단 노드를 루트노드 자식이 하나도 없는 최하단 노드를 리프 노드라고 한다

	힙 : 힙은 이진트리의 한 종류로써 두가지 조건이 성립되는 이진트리를 의미한다 
		1. 완전 이진 트리어야한다 
		2. 부모 노드와 자식 노드간에 크기 관계가 성립해야한다.

	그래프 : 정점과 에지로 이루어진 형태의 자료구조 에지의 방향성과 존재 유무에 따라 유향 그래프 , 
		무향 그래프로 분리 되며 에지가 가중치를 가지고 있다면 가중치 그래프 라고 부른다
		그래프는 행렬과 연결리스트를 활용하여 구현할 수 있는데 행렬의 경우 정점의 존재 여부와 상관없이 항상
		N ^ 2의 공간 복잡도를 가진다.
	
	해쉬 : 임의의 크기를 가진 데이터를 고정된 크기의 값으로 변환하는것 해쉬 함수를 정의하면 배열의 인덱스를 원하는 
		값으로 넣거나 찾을수 있음 즉 키를 이용해 값을 바로 찾아낼수 있음 

# Network
	REST API : REST는 자원, 행위, 표현 등으로 구성된 API아키텍쳐 이며 uri를 통해 자원을 명시하고 get, post, put, del등의 메소드를 통해 해당 자원의 행위를 지정하며 
	코드의 재사용성 및 프론트엔드와 백엔드의 완전한분업이 가능해진다
		1. URI는 정보의 자원을 표현해야한다 
		2. 자원에 대한 행위는 HTTP Method로 표현한다

	GET : 클라이언트가 GET요청시 URI와 Header에만 데이터를 담을수 있기에 크기가 제한적이며 URI에 포함된 데이터는
		그대로 노출된다 대신 캐싱이 간단하므로 노출되어도 상관없거나 단순 조회시에 사용하는게 좋다
		즉 데이터의 변화가 일어나지 않는 경우에 사용한다

	POST : 데이터를 URI, Header, Body에 담아서 전달 가능하므로 GET보다 큰 데이터를 전송할수 있으며
		일반 사용자에게 데이터가 노출되지 않기에 안정적으로 데이터를 전송할수 있다.
		서버상에서 무언가 변경하거나 업데이트시에 사용한다 
		POST는 캐시되지 않으며 브라우저에 기록되지 않는다

	HTTP CODE 
		1XX : 대기, 진행중
		2XX : 성공
		3XX : 요청완료를 위한 추가적인 작업 조치 필요
		4XX : 무언가 잘못됨 (클라이언트 오류)
		5XX : 요청한 서버가 잘못됨(서버 오류)
	
	세션과 쿠키 : HTTP 프로토콜 환경은 커넥트리스(요청을 한후 응답을 받으면 연결을 끊음)
		스테이트리스(통신이 끝나면 상태를 유지하지 않는 특징) 한 특성을 가지는데 이때문에 매번 클라이언트를 확인해야함
		이때 세션과 쿠키를 사용함 세션은 쿠키에 기반하고 있지만 사용자 정보 파일을 브라우저에 저장하는 쿠키와 달리 
		서버측에서 관리함 쿠키는 클라이언트 로컬에 키와 값이 저장되어 들고있는 작은데이터 파일임 
		가장 큰 차이점은 어디서 이 데이터를 관리하느냐이며 세션이 보안성이 더 좋지만 요청속도는 쿠키가 더 빠름 

	TCP와 UDP의 차이 : 
		공통점은 포트 번호를 이용하여 주소를 지정, 데이터 오류 검사를 위한 체크포인트 존재 
		차이점은 
		TCP : 연결형, 가상 회선, 전송 순서 보장, 수신여부 확인, 1:1 통신가능, 신뢰성 높음 대신 느림
		UDP: 비연결형, 데이터그램 방식, 전송 순서 보장 안함, 수신여부 확인 안함, 1:N통신, 신뢰성 낮음 대신 빠름

# DataBase 
	RDB : 관계형 데이터 베이스는 정해진 스키마 가 존재함 
	
	NoSQL : 정해진 스키마가 없음 데이터 구조 변화가 자유롭고 데이터 분산이 용이하지만 
	데이터 중복이 발생하거나 변경시에 오랜시간이 걸리는 단점이 존재함
	
	ORM : 오브젝트 릴레이셔널 매핑 > 객체 와 DB를 연결해주는것 클래스와 테이블의 불일치를 자동으로 매핑해주어
	개발자가 개발에만 집중하게 도와줌. 

# Computer Science
