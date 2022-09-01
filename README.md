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
		yield는 리턴과 달리 반환후 종료되지않고 그 상태를 유지하며 호출시마다 다음 값을 반환하기에 
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
	SOLID -> 자세한 사항은 OOP 폴더로.
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
	Docker 와 VM 의 차이점 : Docker는 하드웨어를 가상화 하지 않고 호스트의 자원을 직접 이용하기에 메모리 접근 파일 시스템, 
	네트워크 속도가 가상머신에 비해 월등히 빠르다.
	
	
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
	REST API : REST는 자원, 행위, 표현 등으로 구성된 API아키텍쳐 이며 uri를 통해 자원을 명시하고 
	get, post, put, del등의 메소드를 통해 해당 자원의 행위를 지정하며 코드의 재사용성 및 프론트엔드와 백엔드의 완전한분업이 가능해진다
	이러한 방식(Rest API)이 제공된다면 RestFul 하다고 할수있다
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
	
	
	Socket : 프로세스가 네트워크로 데이터를 내보내거나 받기위한 창구 역활을함 
		(서로 떨어져있는 두 호스트를 연결해주는 도구로써 인터페이스의 역활을 함)
		프로세스가 데이터를 받기위해선 소켓을 열어 데이터를 써보내거나 소켓으로부터 
		데이터를 읽어와야함. (이때 연결된 통로로 패킷을 교환한다)
		소켓은 IP, Port, Protocol 으로 정의된다.
		• Protocol : 어떤 시스템이 다른 시스템과 통신을 원활하게 수용하도록 해주는 통신 규약 및 약속
		• IP : 전 세계 컴퓨터에 부여된 고유의 식별 주소 
		• Port : 네트워크상에서 통신하기 위해서 호스트 내부적으로 프로세스가 할당 받아야 하는 고유한 주소. 
		(프로세스 식별용 이기에 같은호스트 내부에선 서로 다른 프로세스가 같은 값을 가질수 없음)
		• Server Socket : 클라이언트 소켓의 연결요청을 대기하고 요청이 오면 클라이언트 소켓을 생성하여 통신을 가능케 한다
		• Client Socket : 실제로 데이터 송수신이 일어나는곳
	
	특징 
	• Server - Client 구조를 가지며 처음 데이터를 보내는쪽이 Client가 되고 받는쪽이 Server가 된다.
	• Socket은 송수신을 한뒤 연결이 끊어지는것이 아니라 연결이 유지되어 실시간으로 송수신 할수있다.


	Socket 종류
	• TCP(스트림)
		○ 양방향으로 바이트 스트림(순서가 있는 데이터의 연속적인 흐름)을 전송, 연결지향성
		○ 오류수정, 전송처리, 흐름제어 보장
		○ 송신된 순서에 따라 중복되지 않게 데이터를 수신 -> 오버헤드가 발생
		○ Overhead : 어떤 처리를 하기 위해 들어가는 간접적인 처리시간 - 메모리등을 말함
		○ 소량의 데이터 보다 대량의 데이터 전송에 적합  Ex)파일 전송
		○ 각자의 호스트가 독립된 회선을 이용하는 Full-Duplex(전이중) 보장
		○ 중개 장치를 거치지않고 직접적으로 연결되는 Point To Point(점대점) 보장
		○ 연결 과정시 3HandShake 연결 해제시 4HandShake과정을 거친다 
		
		3-handshake C(Client) , S(Server) SYN(싱크로나이즈드 시퀀스 넘버) ACK(아놀리지드먼트 넘버)
		C:연결 요청 > S:연결 확인 수신및 C포트오픈요청 송신 > C: 연결 확인 송신. 
		
		4-handshake
		C:종료 요청 > S:종료 요청 수신및 통신 종료 대기 > S: 종료 요청 송신 > C: 종료 요청 수신 S: 일정시간 대기 
		
		
	• UDP(데이터그램) 
		○ 전송을 우선시한 독립적인 통신 방법
		○ 비연결형 소켓, 연결을 위한 논리적인 경로가 없기에 패킷들은 각각의 다른 경로로 전송됨
		○ 최소한의 오류만을 검출하고 패킷을 제대로 수신하였는지 체크를 하지 않아 신뢰성 보장X
		○ 과정이 적은 대신 그만큼 네트워크에 부하가 적고 속도가 빠르다
		○ 전송 데이터의 크기에 제한이 있음. (Over한 Packet들은 나누어져서 보내짐.)
		○ 1 : 1로 연결되는 TCP와 달리 다 : 다 가능
		○ 신뢰성보단 연속성이 중요한 통화, 메시지 등에 주로 사용됨 
		
	SSL(Secure Sockets Layer)
		• 암호화 기반의 통신 프로토콜 HTTP에 SSL이 결합된다면 이를 HTTPS 라고 부른다
		• Html 텍스트 기반의 통신규약. 인터넷에서 데이터를 주고 받을수 있는 프로토콜, Html문서를 주고받는데 쓰이는 통신규약.
		• SSL인증서를 통해 클라이언트와 서버 간의 통신을 보증한다.
			○ SSL 인증서에는 공개키, CA(인증서 발급자) 도메인 등등의 정보가 담겨있음
		• 암호화된 데이터를 주고받는다, 주로 대칭키(공개키) 방식, 비대칭키(비밀키) 암호화 방식 사용
		• 대칭키(Symmertric Key) : 하나의 Key로 암호화와 복호화를 모두 하는 방식 
		• 비대칭키(Asymmertric Key) : 두 개의 키로 암호화와 복호화를 하는 방식 Ex) A 로 암호화 > B 로 복호화, B 로 암호화 > A 로 복호화
		• HTTPS에선 실제전송 데이터의 암호화시 대칭키, 키 교환에선 비대칭키 암호화를 사용.
		• SSL통신과정은 HandShark라는 과정을 거친다. ( handshake -> 데이터전송 -> 세션종료 )
			1. Client -> Server 
				i. 클라이언트는 랜덤데이터를 만들어 서버에 보낸다.
				ii. 클라이언트에서 사용 가능한 암호화 방식들을 서버에 보낸다.
			2. Server -> Client
				i. 서버 또한 랜덤데이터를 만들어 클라이언트에 보낸다.
				ii. 클라이언트가 보낸 암호화방식들 중에 사용할 방식을 선정하여 클라이언트에 보낸다.
				iii. 이떄 SSL인증서도 같이 동봉되어 보내진다.
			3. Client -> CA
				i. 서버에게 받은 인증서를 CA를 통해 확인한다(신뢰성 검증)
				ii. 공인된 CA라면(브라우저에 저장된CA 리스트)에서 발급된 인증서라면 인증서의 공개키로 복호화 할수있다 
				제대로된 인증서 라면 공인CA의 비밀키로 암호화 되었기 때문이다.
				iii. 공인된 CA가 아닌 사설 CA에서 발급받은 인증서라면 리스트에 존재하지 않기에 경고문이 뜬다 
	• 세션(Session) : 실제로 서버와 클라이언트가 데이터를 주고받는 단계 
		○ 정보를 상대방에게 전송하기 전에 세션 키 값을 이용해서 대칭키 방식으로 암호화
	
	Router
		• 네트워크간 데이터 전송을 위해 패킷이 대상에 도달 할수 있는 가장 작은 경로를 선택하는데 사용됨
		• 데이터를 다른 통신망으로 통신할수 있도록 도와주는 인터넷 접속 장비이다.
	특징	
		• 패킷의 중계전달 : 라우터는 인접한 라우터에서 전달받은 패킷의 수신처 주소를 조사하여 최적 경로를 선택하고 
						새로운 패킷을 중계한다 이를 각 라우터마다 반복함으로써 패킷이 최종 목적지까지 도달한다
		• 라우터 계층위치 : OSI 7Layer에서 라우터는 네트워크 계층에서 동작한다, 정보를 이동시킬뿐만 아니라 
						어떤 경로를 택할 것인지도 결정 한다.
		• 경로 선택 방식
			○ 정적 라우팅 : 목적지 주소까지의 경로를 직접 설정하는 방식
			○ 동적 라우팅 : 라우팅 프로토콜에 의해 경로가 자동적으로 설정되는 방식
		• 우회경로 구성, 로드밸런싱(라우터로 부터 나오는 여러 케이블들의 트래픽을 고르게 분산시켜줌)

	라우터 종류(개인)
	• 코어 라우터: 서비스 제공자 또는 클라우드 제공자가 주로 사용하는 라우터이다. 
				코어 라우터는 추가 라우터나 스위치를 연결할 수 있도록 최대 대역폭을 제공한다.
	• 엣지 라우터: 인터넷을 비롯한 외부 네트워크와 연결되는 네트워크 가장 바깥쪽의 연결 지점이다. 
				게이트웨이 라우터라고도 불린다. 최대한 많은 대역폭을 제공하도록 최적화 
				되어있고, 최종 사용자에게 데이터를 배포하기 위해 다른 라우터와 연결된다.
	• 분산 라우터: 유선 연결을 통해 엣지 라우터에서 데이터를 수신한 다음 일반적으로 와이파이를 통해 최종 사용자에게 전송한다. 
				보통 사용자나 추가 라우터 연결을 위한물리적 연결부도 포함되어 있다.
	• 무선 라우터: 무선 라우터에는 엣지 라우터와 분산 라우터의 기능이 모두 포함되어 있다. 
				보통 홈 네트워크와 인터넷 액세스용으로 사용된다.
	• 가상 라우터: 일부 라우터 기능을 클라우드에서 가상화하여 서비스로 제공할 수 있는 소프트웨어다.




	Switch
		• 같은 네트워크 내부에서 데이터 전송을 수행하는 기기
		• 도착한 패킷을 저장하고 처리하여 목적지 주소를 판별하고 전송중 패킷의 충돌이 발생하지 않도록 패킷을 특정 대상으로 전달함.
		• 스위치 계층위치 : OSI 7Layer에서 스위치는 L2, L3, L4, L7가 있는데 숫자의 위치의 계층에서 작동한다
		• L2 스위치 : 동일 네트워크 간의 연결 만 가능 .
		. L3 스위치 : 서로 다른 네트워크간의 연결 이 가능 .
		. L4 스위치 : 서버나 네트워크 간의 로드밸런싱 용도 .
		. L7 스위치 : 데이터 안의 실제 내용을 기반으로 한 로드밸런싱 .
	
### OSI 7 Layer
	L1 (물리 계층) : 실제 장치들을 연결하기 위한 전기적, 물리적 세부 사항들이 정의된다

	L2 (데이터 링크 계층) : 노드 와 노드간 신뢰성 있는 전송을 보장하기 위한 계층으로 오류 제어와 흐름 제어가 필요하다 

	L3 (네트워크 계층) : 여러 노드를 거칠 때마다 경로를 찾아주는 역활을 하는 계층으로 데이터를 네트워크를 통해 전달하고, 
					  그 과정에서 QoS(Quality Of Service)를 제공하기 위한 기능적, 절차적 수단을 제공한다.

	L4 (전송 계층) :  끝 과 끝의 사용자들이 신뢰성 있는 데이터를 주고 받을 수있도록
	 				하며 특정 연결의 유효성을 제어한다. 
					일부 프로토콜은 상태 개념 이 있고 ( Stateful ), 연결 기반 ( Connection Oriented )이다. 
					이는 Transport Layer 의 패킷들의 전송이 유효한지 확인하고 전송이       
				    실패한 패킷들을 다시 전송한 다는 것을 뜻한다. 
					가장 잘 알려진 프로토콜로 TCP 가 있다 

	L5 (세션 계층) : 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법을 제공한다. 연결, 체크, 종료 

	L6 (표현 계층) : 코드 간의 번역을 담당한다.  인코딩이나 암호화 등의 동작이 이 계층에서 이루어진다.

	L7 (응용 계층) : 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행한다. Telnet이 이에 해당한다

	

# DataBase 
	#### DB를 사용하는 이유 : 
		DB 존재 이전엔 파일 시스템을 이용하여 데이터를 관리 하였음 이는 각각의 파일 단위로 
		저장되기에 이를 처리하기 위한 독립적인 애플리케이션과 상호 연동이 되어야하는데 
		이때 문제점으로 데이터 종속성과 데이터 무결성이 발생함 
	특징
	1. 데이터의 독립성 
		a. 물리적 독립성 : DB 사이즈를 늘리거나 성능 향상을 위해 데이터 파일을 늘리거나 
						새로 추가해도 관련된 응용 프로그램을 수정할 필요가 없음
		b. 논리적 독립성 : DB는 논리적인 구조로 다양한 응용 프로그램의 논리적 요구를 만족가능
	2. 데이터의 무결성 : 데이터의 유효성 검증으로 잘못된 데이터를 무결성 상태 유지 
	3. 데이터의 보안성 : 인가된 사용자들만 DB나 내부 자원에 접근가능케해 보안구현 가능 
	4. 데이터의 일관성 : 연관된 정보를 논리적인 구조로 관리함으로써 
					 어떤 하나의 데이터만 바꿨을때 생길수 있는 데이터의 불일치성을 배제할수있다 
	5. 데이터의 비중복 : DB는 데이터를 통합해서 관리함으로써 자료의 중복을 해결할수있다.
	
	
	정규화
		정규화란 한 데이터를 변경했을때 이를 특정 릴레이션에만 적용되고 
		나머지에는 변경이 되지 않았을때 
		어느것이 정확한 데이터인지 파악할수 없는 상황을 막기위해 진행되는 과정이다.
		즉 중복을 최소화 하기 위해 데이터를 구조화 하는 작업임 

	제 1 정규형 : 속성의 도메인이 오로지 원자값 즉 더이상 분해되지 않는값으로 이루어진것

	제 2 정규형 : 릴레이션이 제 1 정규형에 속하고 기본키가 아닌 모든 속성이 기본키에 완전함수 종속 되는것

	제 3 정규형 : 릴레이션이 제 2 정규형에 속하고 기본키가 아닌 모든 속싱이 기본키에 이행적 함수 종속이 되지 않는것.

	인덱스
		인덱스 : 데이터가 어디에 있는지 번호등으로 순서를 매겨둔것 즉 색인을 의미함
			비록 추가적인 데이터가 들기에 저장 성능은 떨어지겠지만 읽기 속도는 월등히 빨라짐
		DBMS는 인덱스를 항상 최신의 정렬된 상태로 유지해야 원하는 값을 빠르게 찾을수 있음 
		
		Insert : 새로운 데이터에 대한 인덱스 추가 
		Delete : 삭제하는 데이터의 인덱스를 사용하지 않음 처리 
		Update : 기존 인덱스를 사용하지 않음 처리하고 갱신된 데이터에 인덱스 추가 

		장점 : 데이블 조회 속도 향상 및 성능 증가 
			전반적인 시스템의 부하 감소

		단점 : 인덱스를 관리하기 위해 10%정도의 추가 저장공간 필요 
			인덱스를 관리하기 위한 추가 작업 소요 
			인덱스를 잘못 사용할경우 오히려 성능 저하 발생

		결국 Create, Delete, Update가 빈번한 속성에 인덱스를 걸게되면 인덱스가 비대해져 오히려 성능이 감소하므로
		적절하게 설정해야한다 

		사용법 : alter 테이블 add index 인덱스명(컬럼명)

		인덱스 구성에 사용되는 자료구조 

		Hash Table : 해쉬 테이블은 key, value로 데이터를 저장하는 자료구조중 하나로 빠른 검색시에 유용하다 
			즉 고유한 key값을 이용해 인덱스를 생성하고 이 인덱스를 데이터에 매칭해두어 찾아낸다 
			하지만 DB 인덱스에선 제한적으로 사용되는데 이는 해시가 =(등호) 연산에만 특화되어 
			값이 조금이라도 달라지면 다른 해시값을 생성하기에 부등호 연산이 자주 사용되는 DB검색에는 적합하지 않다

		B+Tree : B+Tree는 DB의 인덱스를 위해 자식 노드가 2개 이상인 B-Tree를 개선시킨 자료 구조 이다 
		
		특성 
			1. 리프노드만 인덱스와 데이터(value)를 가지고 있고 나머지 노드들은 인덱스(key) 만을 갖는다
			2. 리프노드는 Linkedlist로 연결되어있다 
			3. 데이터 노드의 크기는 인덱스 노드의 크기와 같지 않아도된다 
		
		DB검색은 부등호를 이용한 순차 검색이 자주 발생될수 있다 
		이러한 이유로 Btree의 리프 노드들을 Linkedlist로 연결하여 순차 검색을 용이하게 하는등 index에 맞게 최적화함
	
	KEY
	기본키(Primary_Key) : 한 테이블의 각 row(행) 을 유일하게 식별해주는 column(열) 각 테이블마다 primaryKey가 존재해야 함 
				NULL과 중복은 허용치 않음

	외래키(foreign_Key) : 한 테이블의 필드 즉 column중 다른 테이블의 행을 식별가능해야함
	
	RDB : 관계형 데이터 베이스는 정해진 스키마 가 존재함 
		스키마(Schema) : DB의 테이블 구조 및 형식, 관계등의 정보를 기술한것 
			1. 관계형 DB를 사용하여 데이터를 저장할때 가장 먼저 할일은 데이터의 공통 속성을 식별하여 
			column으로 정의하고 테이블을 만드는것 
			2. 통상적으로 하나의 테이블이 아닌 여러 개의 테이블로 만들고, 각 테이블의 구조, 형식, 관계 등을 정의함.
			이를 스키마라고 하며, 일종의 DB의 설계도임
## 트랜잭션 격리
	동시에 여러 트랜잭션이 처리될 때 트랜잭션 끼리 얼마나 고립되어 있는가
	즉 특정 트랜잭션이 다른 트랜잭션에 변경한 데이터를 볼 수 있는가를 허용한 정도

	격리성 관련 동시성 이슈 (트랜잭션 T1, T2)
			a. Dirty Read
				T1이 데이터에 접근해 값을 1에서 2로 변경한후 아직 Commit 하지 않은 상태에서
				T2가 데이터를 읽게되면 T2는 2라는 데이터를 가져온다 
				이때 T1이 RollBack할 경우 T2가 가진 데이터는 꼬이게 된다.
			b. Non-Reapeatable Read
				T1이 데이터를 Read올때 T2가 데이터에 접근해 값을 변경하거나 삭제후 커밋하면
				T1은 이미 삭제되거나 변경된후의 데이터를 조회하게 된다 
				즉 데이터의 일관성이 유지되지 않고 서로 다른 결과를 출력한다 있는가를
			c. Phantom Read
				T1중에 특정 조건으로 데이터를 검색하여 결과를 얻는다
				이때 T2가 접근해 해당 조건의 데이터의 일부를 추가/삭제하면 
				T1은 종료되지 않았음으로 이를 반영하게 된다 
				이때 T2가 RollBack하면 데이터가 꼬이게 된다.
## 격리 수준
	1. 격리 수준 
	a. Read Uncommited
		한 트랜잭션의 변경된 내용을 Commit, Rollback과 상관없이 다른 트랜잭션이 읽을수 있게 함.
		a. 특징
			i. Lock유지에 드는 리소스 적음
			ii. DeadLock.에 빠질 위험이 가장 적고 성능이 빠름 
		b. 주의
			i. Dirty Read 발생 가능성 존재 
			ii. 데이터 정합성에 문제가많음 -> 되도록 사용하지 않는게 이상적
			iii. 갱신되지 않을 과거의 자료에 사용시 권장됨
			iv. 몇몇 행이 조회되지 않아도 될만큼 거대한 데이터를 집계시 권장됨
			v. 트랜잭션 도중에 값을 얻어낼 수 있으므로 복잡한 함수나 프로시저에 디버깅 용으로 사용되기도 함
	
	b. Read Commited
		Commit이 완료된 데이터만 조회가 가능하게 함 
		a. 특징
			i. 다른 트랜잭션에서의 변경 사항이 커밋 되지 않은 경우 실제 테이블값이 아닌 Undo 영역의 백업 데이터에서 값을 가져옴 
			ii. Commit된 결과만 가져오기때문에 Dirty Read 발생 X 
			iii. RDB에서 대부분 기본적으로 사용됨
		
		b. 주의
			i. Non-repeatable Read 발생 가능
			ii. 잠금이 발생하기에 속도나 성능에 있어서 느릴수 있음
			iii. 트랜잭션 간 고립성 완전 보장 안함 즉 정확도가 중요하면 더 높은 격리 필요
	
	c. Repeatable Read
		트랜잭션이 시작되기전 Commit된 데이터만 조회 가능하게함
		a. 특징
			i. Mysql 에서 기본적으로 사용
			ii. 자신의 트랜잭션 보다 먼저 일어난 트랜잭션의 변경점 부터 보게됨
			iii. Undo 영역에 백 해두고 실제 레코드 값 변경 
			iv. 트랜잭션이 범위 내 에서 조회한 데이터의 일관성 보장
			v. 이미 존재하는 영역에 대해서만 보장 
		b. 주의
			i. 다른 사용자는 트랜잭션 영역에 해당되는 데이터에 대한 수정이 불가능
			ii. 잠금의 범위가 넓어져 성능과 속도 저하
			iii. Phantom Read 발생 가능 
	
	d. Serializable
		a. 가장 단순하면서 엄격한 격리수준
		b. Insert 되는 데이터도 고려하여 격리성 유지 
		c. 완벽한 읽기 일관성 
		d. 한 트랜잭션이 특정 테이블을 조회할경우 다른 트랜잭션은 해당 테이블의 데이터를 추가, 변경, 삭제할 수 없음(성능 저하)
		e. 모든것이 순차적으로 진행되 Phantom Read 발생 X
		f. 거의 사용되지 않음.

	
	
## JOIN

![image](https://user-images.githubusercontent.com/62789342/180370740-f77ae906-4da3-41eb-b553-90d47fc75ae1.png)

## basic syntax
	SELECT : 데이블 컬럼 조건
	- AS : 특정 컬럼의 데이터를 표시하되 표시할 컬럼명을 변경 

	USE : e.g USE DBNAME; (DB선택)

	FROM : 테이블 명 조건

	ORDER BY : 정렬할 기준 
		- DESC : 내림차순
		- ASC : 오름차순

	WHERE : 조건문으로 맞는값 검색
		- AND, OR 부가 속성 

	LIKE : 부분적으로 일치하는 컬럼 검색
		- e.g LIKE 'TE%';(TE로시작하는 조건), LIKE '%TE%';(TE가 들어간 조건) , LIKE 'TE__';(TE로 시작하고 2글자가 붙을경우.)

	LIMIT : 결과중 일부만 가져오기 
		- e.g LIMIT 10;(결과중 처음부터 10개만 가져옴), LIMIT 50, 10;(결과중 50번째부터 10개만 가져옴.)

	조건 조합의 순서
	SELECT > FROM > WHERE > ORDER BY > LIMIT

	
	NoSQL : 정해진 스키마가 없음 데이터 구조 변화가 자유롭고 데이터 분산이 용이하지만 
	데이터 중복이 발생하거나 변경시에 오랜시간이 걸리는 단점이 존재함
	
	ORM : 오브젝트 릴레이셔널 매핑 > 객체 와 DB를 연결해주는것 클래스와 테이블의 불일치를 자동으로 매핑해주어
	개발자가 개발에만 집중하게 도와줌. 

# Computer Science
	뮤텍스와 세마포어 : 
		둘다 멀티 프로그래밍 환경에서 공유 자원에 대한 접근을 제한 하는것이지만 
		뮤텍스는 한 스레드, 프로세스에 의해 소유될수 있는 키값을 기반으로 하지만 
		세마포어는 현재 공유자원에 대해 접근할수 있는 스레드, 프로세스 수를 나타내는 값을 기반으로 한다.

		데드락 : 두개이상의 작업이 서로가 가진 자원을 요구해 교착상태에 빠져있는것 이를 해결하기 위해선 
		둘중 하나의 작업을 중단 시켜 교착상태를 제거한다

		MSA : 마이크로 서비스 아키텍쳐는 개별 서비스 단위로 나뉘어 개발하는 방식 
		MA : 모놀리식 아키텍쳐는 하나의 거대한 아키텍쳐로 개발하는것이다

		오버헤드 : 어떤 처리를 하기위해 들어가는 간접적인 처리 시간, 메모리 등을 말함

	
	
	CORS : 도메인 또는 포트가 다른 서버의 자원을 요청하는 매커니즘으로 한 쪽에서 실행중인 웹 어플이 
		다른 출처의 선택한 자원에 접근 할 수 있는 권한을 부여하도록 브라우저에 알려주는것

	웹 동작방식 
		1. 사용자가 브라우저에 URL 입력
		2. 브라우저는 DNS를 통해 서버의 진짜 주소를 찾아냄 e.g. IP (DNS : 도메인 네임 시스템 기계가 읽을수 있도록 변환)
		3. HTTP프로토콜을 이용해 HTTP요청이 생성됨
		4. TCP/IP 연결을 통해 HTTP요청이 서버로 전송됨
		5. 서버는 HTTP 프로토콜을 활용해 HTTP 응답 메세지를 생성함
		6. TCP/IP 연결을 통해 요청한 컴퓨터로 전송
		7. 도착한 HTTP응답 메세지는 웹페이지 데이터로 변환되며 이는 웹 브라우저롤 통해 사용자에게 출력됨.\
