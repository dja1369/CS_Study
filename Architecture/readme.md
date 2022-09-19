# Architecture

<hr>

<img width="413" alt="스크린샷 2022-09-19 오후 9 12 42" src="https://user-images.githubusercontent.com/62789342/191014687-409855f8-9e1e-48b2-8d66-cec06c6a05ff.png">

# 1. 현재 상황
    굉장히 많은 메소드가 Main.py에 집중되어 있음 
    이는 초기 아키텍쳐를 구상하지 않고 코드를 작성했기에 발생하였음 
    이후 아키텍쳐에 대한 스터디를 진행하여 이를 적용하고 개선하고자 리팩토링을 논의함

# 2. 고려할 아키텍쳐 리스트


## A. Layered architecture 

<img width="414" alt="스크린샷 2022-09-19 오후 9 12 52" src="https://user-images.githubusercontent.com/62789342/191014726-dad2cb80-c0b0-4605-bb2d-32b7c724b453.png">

    표현계층(View) = 표현
    비즈니스계층(B,L), 응용계층(application) = 제어
    영속성계층(DAO), 도메인계층(Domain) = 행위
    DB(mysql, oracle..), 인프라계층 = 구현 기술
    계층으로 나누어 구별하는 아키텍쳐
    기본적으로 레이어드 아키텍쳐에선 모든 계층은 수직적(Top-Down)으로 구성된다 
    이는 레이어드 아키텍쳐의 주요 특징중 하나이며 이런 구조로 인해 특정 레이어는 
    바로 하위 레이어에만 연결되게 되고 각 레이어가 격리되는 효과가 일어나   
    캡슐화를 이룸과 동시에 단일책임을 갖는다 
    따라서 특정 레이어는 다른 레이어에 영향을 주지 않고 변경 가능하다
    


## B. Domain Driven Design 
<img width="641" alt="스크린샷 2022-09-19 오후 9 13 05" src="https://user-images.githubusercontent.com/62789342/191014755-82307ab5-d1e3-442b-be90-d4404a92f47b.png"> 
<img width="644" alt="스크린샷 2022-09-19 오후 9 13 14" src="https://user-images.githubusercontent.com/62789342/191014768-c698213a-a50a-463f-92ff-1630662f5e3a.png">

    Domain : 소프르웨어로 해결하고자 하는 대상 
    즉 설계를 해결하고자 하는 대상별로 나누어 구현하는것이며 도메인의 구별 기준은 
    개개인마다 달라질수 있다
    하지만 설계시 최대한 표현력이 나타나게끔 해야하며 단순히 속성만 나열하는것이 아닌 
    실제 행위를 통해 도메인이 기능이 나타나도록 설계 해야 한다.


## C. hexagonal architecture 
<img width="665" alt="스크린샷 2022-09-19 오후 9 13 26" src="https://user-images.githubusercontent.com/62789342/191014788-a2dc2e92-cc53-4c7d-a569-08b0ce00797d.png"> 
<img width="700" alt="스크린샷 2022-09-19 오후 9 13 35" src="https://user-images.githubusercontent.com/62789342/191014804-595cf4ff-4c1c-4835-b807-4f7742241fc6.png">

    헥사고날 아키텍처는 내부(도메인)와 외부(인프라)로 구분된다
    내부 영역 : 순수한 비즈니스 로직을 표현하며 캡슐화된 영역 -> 기능적 요구사항에 따라 먼저 설계
    외부 영역 : 내부 영역에서 기술을 분리하여 연결시켜주는 영역(기술 : nginx, DB, Redis...)
    핵심 가치로는 포트와 어댑터가 존재한다 
    
    포트 : 내부 비즈니스 영역을 외부로 노출한 API
        InboundPort : 내부 영역 사용을 위해 노출된 API
        OutboundPort : 내부 영역이 외부 영역을 사용하기 위한 API
    
    어댑터 : 외부 세계와 포트 간 교환을 조정함
        InboundAdapter : 외부 애플리케이션/서비스와 내부 비즈니스 영역(인바운드 포트) 간의 데이터 교환 조정
        OutboundAdapter : 내부 비즈니스 영역(아웃바운드 포트)과 외부 애플리케이션/서비스간 데이터 교환 조정

## 3. 최종 선택 
    현재 시급한 사안은 기존의 뭉쳐져 있는 함수들을 분리하는게 우선사항이라고 파악됨
    또한 개별로 하나의 아키텍쳐를 적용하기엔 부족하거나 오버 엔지니어링이라는 의견이 존재하였음 
    그리하여 차후 신규 입사자와 서비스의 확장성를 고려하여 ** Layered architecture in DDD ** 를 차용하기로 결정

## 4. 폴더 구조 
<img width="371" alt="스크린샷 2022-09-19 오후 9 13 49" src="https://user-images.githubusercontent.com/62789342/191014836-599babc4-6a34-40d5-b0f3-11fa4b53d035.png">

    우선적으로 Main.py에 존재하는 함수를 파악하여 기능에 따라 Db, Web, View, Control, Compact로 도메인 별로 구분 짓고
    아래의 파일 구조는 추상화 > 구현부 | 라우트(Get, Post)별로 구분 하여 아키텍쳐를 설계함 


    
    
