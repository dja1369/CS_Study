# OOP
##	SOLID 
###  1. 단일 책임의 원칙 : 하나의 클래스는 하나의 역활만 담당해야 한다 
    22.09.01
    SPR를 지키기 위해선 기본적으로 하나의 객체는 하나의 책임만을 가지고 있어야 한다 
    즉 Service라는 클래스가 A팀의 요청에 대해 변경된다 가정하고 
    B팀 의 요청에 의해 변경되는 클래스라면 이는 SRP를 위반하고 있을 가능성이 높다 
    (즉 한 클래스가 두 로직을 담당하고 있다면 두 역활을 담당하고 있다는 말이다.)
    핵심은 한개의 클래스는 한개의 역활만 담당해 변경이 예측될수 있는 범위로 한정 되어야 한다
    한 클래스가 다양하고 막중한 책임을 가져선 안되기에... 
    
    e.g. 
    class Service:  # 이 코드는 어떨까? 하나의 클래스가 여러 역활을 수행하고 있다
                    # 예를 들어 결제, 항의, 여러기능들..
        def pay: # 결제 기능 담당
            pass
        def blame: # 불만 기능 담당
            pass
        def ....

    위 코드의 문제점은 결제 기능을 수정하고 싶다면 서비스클래스를 수정하고 블레임 기능도 서비스 클래스를 수정해야만 한다. 
    한마디로 두가지 역활을 가지고 있는것이다 이러한 경우의 문제점은 단순히 결제 기능에 문제가 생겨 pay 메소드를 수정하면 서비스 클래스를 새로 배포해야 한다는것이다 
    이런 경우 service클래스는 여러 역활을 담당하게 되어 문제가 생긴다.

    이를 해결하기 위해선 간단하게 한다면 기능별로 클래스를 만들어 분리하면 된다
    간단하게 표현하자면 (임의 구현이므로 생성자는 제외했음)
    class service(metaclass=ABCMeta):
        @abstractmethod
        def pay(): # 결제 기능 담당
            pass
        @abstractmethod
        def blame(): # 불만 기능 담당
            pass
        @abstractmethod
        def somemethod(): # 여러 기능 담당
            pass
    
    class pay(service):
        def pay():
            # logic 
        def blame():
            pass
        def somemethod():
            pass
    class blame(service):
        def pay():
            pass
        def blame():
            # logic
        def somemethod():
            pass    
        ...

    이 예제는 간단하고 여러 문제점이 있지만 본질적인 목표인 역활의 분리를 해냈다 필요하다면 이제 객체를 생성해 기능을 호출해 로직을 구성하면 될것이다. 
    물론 실제 비즈니스 로직은 더 복잡하고 어려울것 이다.
    그럼 자 이제 무엇이 다음 문제일까? 
    단일 책임 원칙은 지켜냈지만 상속 과정중 쓰이지 않는 죽은 코드가 발생했다 이제 이를 해결 하기 위해서 ISP 인터페이스 분리 원칙이 필요하다고 생각한다.
    
		 	
        
###	2. 개방 폐쇄의 원칙 : 확장(상속)에는 열려있고, 수정에는 닫혀있어야한다
    22.09.13
    OCP 개방 폐쇄 원칙 이것은 쉽게 말해 새로운 요구사항이 생길시 코드를 수정하는것이 아닌 추가하는 방식으로 초기에 구상하여 
    로직을 캡슐화해 유지보수가 쉽게끔 하라는 것 이라고 생각한다 
    즉 새로운 기능을 추가하다가 기존의 로직이 변경되었다면 이는 기존 로직이 잘못 디자인된 경우라고 볼수있다
    만약 새로운 요구사항이 추가될시 기존의 로직에 새로운 코드를 덧붙여 작성하게끔 디자인 해야한다
    e.g.
    # OOP를 지키지 못한 코드 
    class message(metaclass=ABCMeta):
        def __init__(self, data: dict):
            self.date = data
    
    class FirstTypeMessage(message):
        """ FirstTypeMessage에 대한 처리"""
    
    class SecondTypeMessage(message):
        """ SecondTypeMessage에 대한 처리"""

    class ThirdTypeMessage(message):
        """ ThirdTypeMessage에 대한 처리"""
    
    class MessageClassifier:
        def __init__(self, data: dict):
            self.data = data
        
        def classification(self):
            if(self.data["type"] == 1):
                return FirstTypeMessage(self.data)
            elif(self.data["type"] == 2):
                return SecondTypeMessage(self.data)
            else:
                return ThirdTypeMessage(self.data)
    위의 예제는 어떠한가 특정 타입별로 메세지를 다르게 처리하기 위해 수신받은 데이터의 타입별로 분류해 타입별 클래스에 반환하고 있다 
    물론 위 코드가 동작하는데는 무리가 없겠지만 만약 새로운 메세지 처리 타입이 생긴다면? 
    MessageClassifier클래스 classification함수에 elif로 새로운 로직을 추가해줘야 할것이다. 
    그럼 OOP를 적용해 이를 해결해보자

    e.g.  
    class message(metaclass=ABCMeta):
        def __init__(self, data: dict):
            self.date = data
        
        @abstractmethod    
        def grade_vaildation(data: dict):
            pass 

    
    class FirstTypeMessage(message):
        """ FirstTypeMessage에 대한 처리"""
        def grade_vaildation(data: dict):
            return data["type"] == 1  
    
    
    class SecondTypeMessage(message):
        """ SecondTypeMessage에 대한 처리"""
        def grade_vaildation(data: dict):
            return data["type"] == 2
    
    
    class ThirdTypeMessage(message):
        """ ThirdTypeMessage에 대한 처리"""    
        def grade_vaildation(data: dict):
            return data["type"] == 3
    

    class MessageClassifier:
        def __init__(self, data: dict):
            self.data = data
         
        def classification(self):
            for message_type in Message.__subclasses__():
                try:
                    if message_type.grade_vaildation(self.data):
                        return message_type(self.data)
                except Exception as e:
                    continue
    단순하게 설명하자면 메세지 클래스를 상속받는 모든 클래스를 가져와 검증하는 함수를 호출하고 수신받은 데이터가 동일하면 
    True를 반환해 메세지별 처리 로직이 작동하게 된다 
    자 이렇게 수정하면 새로운 메세지 타입이 생겨도 메시지 클래스를 상속받아 새로 구현(확장)하면 될것이다
    물론 완벽한 예제가 아니기에 틀릴수도 있지만 우선적으로 이렇게 구현하면 기존의 로직을 수정할 일이 없어지기에 
    유지보수 및 안정성에서 좋은 이점이 생길것이다.


###	3. 리스코프 치환의 원칙 : 자식 객체는 언제든지 부모 객체로 변환 가능하어야 한다
    22.09.13
    LSP 리스코프 치환 원칙은 부모객체와 자식 객체는 언제든지 서로 치환(대체)이(가) 가능해야 한다는것 이다 
    쉽게말해 사각형을 상속받는 정사각형과 직사각형 객체는 언제든지 부모의 역활을 대체 할 수 있음을 알수있다 
    이를 지키기 위해 기본적인 제약 조건이 있다면 
    1. 자식 클래스는 부모 클래스에 정의된 것 보다 조건을 엄격하게 만들면 안된다.
    2. 자식 클래스는 부모 클래스에 정의된 것 보다 조건을 약하게 만들면 안된다. 
    이 두가지만 지킨다면 LSP는 쉽게 지킬수 있다고 생각한다 하지만 실제로 로직의 구현시에는 
    여러 추가 기능과 반환값이 달라지는 경우가 있기에 솔직히 이 원칙은 항상 고민을 하며 지켜야 할것 같다.

###	4. 인터페이스 분리의 원칙 : 인터페이스는 클래스가 꼭 필요한 기능만 구현되어야 한다
    22.09.13
    ISP 인터페이스 분리 원칙 이것은 1번의 단일 책임 원칙에서 이어지는데 
    e.g.
    class service(metaclass=ABCMeta):
        @abstractmethod
        def pay(): # 결제 기능 담당
            pass
        @abstractmethod
        def blame(): # 불만 기능 담당
            pass
        @abstractmethod
        def somemethod(): # 여러 기능 담당
            pass
    

    class pay(service):
        def pay():
            # logic 
        def blame():
            pass
        def somemethod():
            pass


    class blame(service):
        def pay():
            pass
        def blame():
            # logic
        def somemethod():
            pass    
        ...
    이러한 로직이 있다고 가정하면 추상화 하였을때 상속하여 구현할때 필요없는 메소드 까지 같이 구현하거나 
    죽은 코드가 생성되게 된다 즉 이러한 죽은 코드를 방지하고자 좀더 세세한 단위로(최소 단위)로 분리해 
    인터페이스를 구현 하자는 원칙이다.
    물론 이 원칙에서도 조심해야 할 사항이 있는데 이는 "성급한 추상화" 이다 
    만약 물건을 잡는 손을 구현 한다면 이 클래스는 물건을 잡는다는 행위의 주체를 세분화 하고자 
    손가락과 손을 든다 로 추상화를 하였다면 두가지의 추상화된 클래스를 받을것이다 
    이는 기능을 최소 단위로 분리한듯 보이지만 물건을 잡기 위해서는 반드시 손을 들고 손가락을 펼쳐야 하기 때문에
    물건을 집는다는 행위를 구성함에 있어선 둘을 분리할 필요가 없다 오히려 더 복잡한 상속관계만을 만들어 낼 뿐이다.
    그렇기에 인터페이스를 분리 할 때는 반드시 명확한 기준을 가지고 분리해야만 한다고 생각한다. 

###	5. 의존성 역전의 원칙 : 상위 모듈은 하위 모듈에 의존하면 안되며 추상화에 의존해야 하고 추상화는 세부    사항에 의존하면 안된다.
    22.09.13
    DIP 의존성 역전 원칙은 단순히 생각하면 추상화(고수준)가 세부로직(저수준)에 의존하면 안되고
    상위 모듈과 하위 모듈 모두 추상화에 의존해야 한다는 의미 라고 생각한다.
    
    e.g. 너무나도 좋은 예시가 있어 빌려왔다 refs.https://doorbw.tistory.com/240?category=677823
    class EventStreamer():    
        def __init__(self, parsed_data: str, client: Syslog):
            self.parsed_data = parsed_data        
            assert client is Syslog, "Client is not Syslog"        
            self.client = client            
        def stream(self):       
            self.client.send(self.parsed_data)
    class Syslog():    
        def send(data: str):        
            print(f"Syslog send: {data}")       
            pass    
    class OtherClient():    
        def send(data: str):
            print(f"OtherClient send: {data}")       
            pass  
            
    streamer1 = EventStreamer("for Syslog data!", Syslog)streamer1.stream()streamer2 = EventStreamer("for OtherClient data!", OtherClient)streamer2.stream()
    위의 코드는 예제를 위해서 assert를 통해 강제성을 부여하였지만 파이썬 같은 동적언어가 아닌 
    정적 언어에서는 타입이 지정되기에 에러를 반환할것이다.
    즉 들어오는 파라미터가 syslog가 아닐수도 있음에도 syslog를 직접적으로 참조하기에 문제가 발생하는것이다.
    이를 해결하기 위해선 Syslog와 OtherClient 클래스를 추상화 하는 인터페이스를 만들고  
    추상화 클래스와 관계를 맺고 추상화 타입을 정의하여 의존성을 역전 시킬수 있다
    DIP 미적용 EventStreamer > Syslog "" EventStreamer < Syslog, OtherClient
    DIP 적용 EventStreamer > 추상화 < Syslog, OtherClient
    그리하여 EventStreamer객체는 추상화 인터페이스와 관계를 가질뿐 실제 구체적인 저수준 로직에 대한 의존성이 사라지게 된다.