# csnote
면접을 위한 전공지식 CS노트의 저장소 및 오타 공지사항입니다.
 - ebook의 경우 페이지번호가 단말기마다 다릅니다. 페이지의 기준은 인쇄본 1쇄를 기준으로 말씀을 드립니다. 
 - 현재 5쇄까지 아래의 내용이 모두 반영되어있습니다. 
 - 추후 반영되는 사항은 [new] 키워드를 붙입니다.

# 오탈자 및 추가 및 변경 사항
1쇄와는 달리 달라진 점이 있습니다. 해당 부분은 다음과 같습니다. 

MVC패턴 예제 - React.js에서 Spring으로 바뀔 예정입니다. MVC패턴을 React.js로 구현할 수 있지 MVC 패턴의 예로는 미흡한 부분이 있어서 수정할 예정입니다.

## 싱글톤 코드 수정[new]
ch1/2.js


## 143, 148, 150, 182페이지  
> before

SDD

> after

SSD


## 17페이지 
> before

싱글톤패턴은 하나의 클래스에 오직 하나의 인스턴스만 가지는 패턴입니다. 보통 데이터베이스 연결모듈에 많이 사용합니다.

> after

싱글톤 패턴(singleton pattern)은 하나의 클래스에 오직 하나의 인스턴스만 가지는 패턴입니다. 하나의 클래스를 기반으로 여러 개의 개별적인 인스턴스를 만들 수 있지만 그렇게 하지 않고 하나의 클래스를 기반으로 단 하나의 인스턴스를 만들어 이를 기반으로 로직을 만드는데 쓰이며 보통 데이터베이스 연결모듈에 많이 사용합니다.

## 18페이지 
> before

앞의 코드에서 볼 수 있듯이 obj와 obj2는 다른 인스턴스를 가집니다.  

> after

앞의 코드에서 볼 수 있듯이 obj와 obj2는 다른 인스턴스를 가집니다. 
이 또한 new Object라는 클래스에서 나온 단 하나의 인스턴스니 어느정도 싱글톤패턴이라 볼 수 있습니다만 실제 싱글톤패턴은 보통 다음과 같은 코드로 구성됩니다. 

## 20페이지 
> before

`public static synchronized Singleton getInstance()`

> after

`public static Singleton getInstance()` 

> before

자바로는 다음과 같이 할 수 있습니다. 

> after 

자바로는 다음과 같이 중첩 클래스를 이용해서 만드는 방법이 가장 대중적입니다.
더 깊게 알고 싶은 분은 필자의 유투브 채널인 큰돌의 터전 - 'JAVA로 싱글톤 패턴을 구현하는 7가지 방법' 영상을 참고 하시길 바랍니다.

## 24페이지 설명 변경
> before

의존성 주입은 의존성 주입원칙을 지키며 만들어야 하며 원칙은 다음과 같습니다
 - 상위 모듈은 하위 모듈에서 어떠한 것도 가져오지 않아야 합니다. 둘 다 추상화에 의존해야 하며, 이때 추상화는 세부 사항에 의존하지 말아야 합니다. 

> after

의존성 주입 원칙

의존성 주입은 "상위 모듈은 하위 모듈에서 어떠한 것도 가져오지 않아야 합니다. 
또한 둘 다 추상화에 의존해야 하며, 이 때 추상화는 세부사항에 의존하지 말아야 합니다." 라는 의존성 주입원칙을 지켜주면서 만들어야 합니다. 

## 27페이지 설명 변경
> before

또한, CoffeeFactory를 보면 static으로 createCoffee() 정적 메서드를 정의한 것을 알
수 있는데, 정적 메서드를 쓰면 클래스의 인스턴스 없이 호출이 가능하여 메모리를 절약
할 수 있고 개별 인스턴스에 묶이지 않으며 클래스 내의 함수를 정의할 수 있는 장점이 있
습니다. 

> after

또한, CoffeeFactory 클래스를 보면 static 키워드를 통해 createCoffee() 메서드를 정적메서드로 선언한 것을 볼 수 있는데 이렇게 정적메서드로 정의하게 되면 클래스를 기반으로 객체를 만들지 않고 호출이 가능하며 해당 메서드에 대한 메모리 할당을 한번만 할 수 있는 장점이 있습니다.


## 29페이지 설명 변경
> before

상수의 집합을 정의할 때 사용되는 타입이다. 상수나 메서드 등을 집어넣어서 관리하며 코드를 리팩터링할 때
해당 집합에 관한 로직 수정 시 이 부분만 수정하면 되므로 코드 리팩터링 시 강점이 생긴다.

> after

상수의 집합을 정의할 때 사용되는 타입이다. 예를 들어 월, 일, 색상 등의 상수값을 담는다. 자바에서의 Enum은 다른 언어보다 더 활용되어 쓰이며 상수뿐만 아니라 메서드를 집어넣어서 관리할 수 있다. Enum을 기반으로 상수집합을 관리한다면 코드를 리팩터링할 때 상수집합에 대한 로직 수정 시 이 부분만 수정하게 된다는 장점, 본질적으로 스레드세이프(thread safe)하기 때문에 싱글톤 패턴을 만들 때 도움이 된다. 참고로 enum으로 만드는 싱글톤 패턴은 필자의 유투브 채널, 큰돌의 터전 - 'JAVA로 싱글톤 패턴을 구현하는 7가지 방법' 영상을 참고하시길 바랍니다. 

## 40페이지 설명 변경
> before 

프록시 객체의 target 동작을 가로채서 정의할 동작들이 정해져 있는 함수 

> after

target 동작을 가로채고 어떠한 동작을 할 것인지가 설정되어 있는 함수

## 40페이지 설명 변경
> before 

new Proxy로 선언한 객체의 a와 b라는 속성에 특정 문자열을 담아서 handler에 “name이
라는 속성에 접근할 때는 a와 b라는 것을 합쳐서 문자열을 만들어라.”를 구현했습니다. 이
렇게 p라는 변수에 name이라는 속성을 선언하지 않았는데도 p.name으로 name 속성에 접근
하려고 할 때, 그 부분을 가로채 문자열을 만들어 반환하는 것을 볼 수 있습니다.
자바스크립트 

> after

new Proxy()로 a와 b 속성을 가지고 있는 객체와 handler 함수를 매개변수로 넣고 p라는 변수를 선언했습니다. 이 후 p의 name 속성을 참조하니 a와 b라는 속성밖에 없는 객체가 handler의 “name이라는 속성에 접근할 때 a와 b를 합쳐서 문자열을 만들라” 는 로직에 따라 어떠한 문자열을 만드는 것을 볼 수 있습니다. 이렇게 name 속성 등 어떠한 속성에 접근할 때 그 부분을 가로채서 어떠한 로직을 강제할 수 있는게 프록시 객체입니다.  

## 45페이지 설명 변경
> before 

이를 통해 익명 사
용자의 직접적인 서버로의 접근을 차단하고 간접적으로 한 단계를 더 거침으로써 보안성
을 더욱 강화할 수 있습니다.

> after

이를 통해 익명 사용자의 직접적인 서버로의 접근을 차단하고 간접적으로 한 단계를 더 거치게 만듦으로써 보안을 강화할 수 있습니다.  


## 46페이지 설명 변경
> before 

CDN 말고도 CloudFlare를 통해 누릴 수 있는 이점은 많습니다. 대표적으로 DDOS 공격
방어, HTTPS 구축이 있습니다. 이 모든 것은 웹 서버 앞단에 두어 ‘프록시 서버’로 쓰기
때문에 가능한 것입니다.

> after

CloudFlare는 웹 서버 앞단에 프록시 서버로 두어 DDOS 공격방어, HTTPS 구축에 쓰입니다. 
또한, 서비스를 배포해보면 해외에서 무언가 의심스럽고 많은 트래픽이 발생하기도 하고 이 때문에 많은 클라우드 서비스 비용이 발생할 수도 있는데 CloudFlare가 의심스러운 트래픽인지를 먼저 판단해 CAPTCHA 등을 기반으로 이를 일정부분 막아주는 역할도 수행합니다. 

## 49페이지 설명 변경
> before 

참고로 127.0.0.1이란 루프백 IP로, 본인 PC의 IP를 뜻합니다. localhost나 127.0.0.1을
입력하면 DNS를 타지 않고 바로 본인 PC로 연결됩니다.
 

참고로 CORS에 대한 자세한 설명은 필자가 만든 영상(https://bit.ly/3KfzrBh)을 참고하
기 바랍니다.


이터레이터 패턴(iterator pattern)은 이터레이터(iterator)를 사용하여 컬렉션(collection)의
요소들에 접근하는 디자인 패턴입니다.


> after

참고로 127.0.0.1이란 루프백(loopback) IP로, 본인 PC 서버의 IP를 뜻합니다. localhost나 127.0.0.1을 주소창에 입력하면 DNS를 거치지 않고 바로 본인 PC 서버로 연결됩니다.


CORS에 대한 자세한 설명은 필자의 유투브 채널, 큰돌의 터전 - 'CORS ' 영상을 참고하시길 바랍니다. 


이터레이터 패턴(iterator pattern)은 이터레이터(iterator)를 사용하여 컬렉션(collection)의 요소들에 접근하는 디자인 패턴입니다. 이를 통해 순회할 수 있는 여러 가지 자료형의 구조와는 상관없이 이터레이터라는 하나의 인터페이스로 순회가 가능합니다.

## 50페이지 설명 변경
> before

이를 통해 순회할 수 있는 여러 가지 자료형의 구조와는 상관없이 이터레이터라는 하나의
인터페이스로 순회가 가능합니다.

> after

앞의 그림은 이터레이터라는 똑같은 배로 동그라미로 이루어진 컬렉션이든 마름모로 이루어진 컬렉션이든 순회할 수 있는 것을 보여줍니다.


## 52페이지 설명 변경
> before

a와 b는 다른 모듈에서 사용할 수 있는 변수나 함수인 privat 범위를 ...(생략)

> after

a와 b는 다른 모듈에서 사용할 수 없는 변수나 함수이며 private 범위를 가집니다. c와 d는 다른 모듈에서 사용할 수 있는 변수나 함수이며 public 범위를 가집니다. 참고로 위와 같은 노출모듈패턴을 기반으로 만든 자바스크립트 모듈 방식으로는 CJS(CommonJS) 모듈 방식이 있습니다. 

## 54페이지 설명 변경
> before

MVC 패턴의 예 리액트
MVC 패턴을 이용한 대표적인 라이브러리로는 리액트(React.js)가 있습니다. 
리액트는 유저 인터페이스를 구축하기 위한 라이브러리입니다. ‘가상 DOM’을 통해 실제
DOM을 조작하는 것을 추상화해서 성능을 높였습니다.
대표적인 특성으로는 불변성(immutable)이 있습니다. 예를 들어 state는 setState를 통
해서만 수정이 가능하고, props를 기반으로 해서 만들어지는 컴포넌트인 pureComponent
가 있습니다. 단방향 바인딩이 적용되어 있고, 자유도가 높고, 메타(페이스북)가 운영하고
있으며 넷플릭스, 트위터, 드롭박스, 우버, 페이팔, 마이크로소프트 등에서 사용됩니다.
참고로 ‘가상 DOM’에 대한 자세한 설명은 필자가 만든 영상(https://bit.ly/3hDX620)을
참고하기 바랍니다.

> after

MVC 패턴을 이용한 대표적인 프레임워크로는 자바 진영에서 유명한 스프링(Spring) 이 있습니다. 

Spring의 WEB MVC는 웹서비스를 구축하는데 편리한 기능들을 많이 제공합니다. 예를 들어 @RequestParam, @RequestHeader, @PathVariable 등의 애너테이션을 기반으로 사용자의 요청값들을 쉽게 분석할 수 있으며 사용자의 어떠한 요청이 유효한 요청인지를 쉽게 거를 수 있습니다. 예를 들어 숫자를 입력해야 하는데 문자를 입력하는 사례 같은 것을 말이죠. 또한 재사용가능한 코드, 테스트, 쉽게 리디렉션할 수 있게 하는 등의 장점이 있습니다. 
스프링에 대한 자세한 설명은 필자의 유투브 채널, 큰돌의 터전 - 'Spring과 MVC패턴' 영상을 참고하시길 바랍니다. 


## 68페이지 설명 변경
> before

네트워크란 노드(node)와 링크(link)가 서로 연결되어 있거나 연결되어 있지 않은 집합체를 의미합니다. 

> after

네트워크란 노드(node)와 링크(link)가 서로 연결되어 있으며 리소스를 공유하는 집합을 의미합니다.
 

## 69페이지 설명 변경
> before

처리량(throughput)이란 링크를 통해 전달되는 단위 시간당 데이터양을 말합니다.  


단위로는 bps(bits per second)를 씁니다. 초당 전송 또는 수신되는 비트 수라는 의미입
니다.
처리량은 사용자들이 많이 접속할 때마다 커지는 트래픽, 네트워크 장치 간의 대역폭, 네
트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받습니다.
네트워크란 노드(node)와 링크(link)가 서로 연결되어 있거나 연결되어 있지 않은 집합체를 의미합니다. 

> after

처리량(throughput)은 링크 내에서 성공적으로 전달된 데이터의 양을 말하며 보통 얼만큼의 트래픽을 처리했는지를 나타냅니다. 많은 트래픽을 처리한다 = 많은 처리량을 가진다. 라는 의미입니다.
단위로는 bps(bits per second)를 씁니다. 초당 전송 또는 수신되는 비트 수라는 의미입니다. 처리량은 사용자들이 많이 접속할 때마다 커지는 트래픽, 네트워크 장치 간의 대역폭, 네트워크 중간에 발생하는 에러, 장치의 하드웨어 스펙에 영향을 받습니다.
앞의 그림을 보면 트래픽이 있는데 트래픽은 특정시점에 링크 내의 “흐르는” 데이터의 양을 말합니다. 예를 들어 서버에 저장된 파일(문서,이미지,동영상 등)을 클라이언트(사용자)가 다운로드 시 발생되는 데이터의 누적량을 뜻합니다. 트래픽과 처리량을 헷갈릴 수 있는데 이렇게 이해하면 됩니다. 
 - 트래픽이 많아졌다. = 흐르는 데이터가 많아졌다. 
 - 처리량이 많아졌다. = 처리되는 트래픽이 많아졌다.   

## 82페이지 설명 변경

> before

전송(transport) 계층은 송신자와 수신자를 연결하는 ... (생략)

> after

전송(transport) 계층은 송신자와 수신자를 연결하는 통신 서비스를 제공하며 연결 지향 데이터 스트림 지원, 신뢰성, 흐름 제어를 제공할 수 있으며 애플리케이션과 인터넷 계층 사이의 데이터가 전달될 때 중계 역할을 합니다. 대표적으로 TCP와 UDP가 있습니다. 

## 99페이지 오타
> before

로드밸런서로는 L7 스위치뿐만 아니라.. (생략)

> after

로드밸런서로는 L7 스위치뿐만 아니라 L4스위치도 있습니다. L4 스위치는 전송 계층

## 106페이지 설명 및 오타 변경
> before

IP주소를 통해 통신하는 과정을 홉바이홉... (생략) 

> after

IP주소를 통해 통신하는 과정을 홉바이홉통신이라고 합니다. 
여기서 홉(hop)이란 영어 뜻 자체로는 건너뛰는 모습을 의미합니다. 이는 통신망에서 각 패킷이 여러 개의 라우터를 건너가는 모습을 비유적으로 표현한 것입니다. 앞의 그림처럼 수많은 서브네트워크 안에 있는 라우터의 라우팅테이블의 IP를 기반으로 패킷을 전달하고 또 전달해나가며 라우팅을 수행하며 최종 목적지까지 패킷을 전달합니다.

> before

IPv6는 64비트를 16비트 단위로

> after

IPv6는 128비트를 16비트 단위로

## 109페이지 오타
> before

클래스 기반 할당 방식(CIDR)

> after

클래스 기반 할당 방식(classful network addressing)

## 117페이지 설명 추가 
> before

하지만 Base64 문자열로 변환할 경우... (생략)

> after

하지만 Base64 문자열로 변환할 경우 37% 정도 크기가 더 커지는 단점이 있습니다. 자세한 설명은 필자가 만든 영상을 참고하세요. 
 - https://youtu.be/-bxZyTfhoH0 

## 132페이지 Q&A 1개추가  

www.naver.com을 주소창에 입력하면 어떻게 될까요? 

https://www.youtube.com/watch?v=5MM8NDzWHdE 에 영상을 올려놨습니다. 

## 137페이지 오타 및 설명변경
> before

1은 유저모드라고 설정되며, 유저모드일 경우에는 시스템콜을 못하게 막아서 한정된 일만 가능하게 합니다.

> after

1은 유저모드라고 설정됩니다. 

## 143페이지 오타

> before

보조기억장치 : HDD, SDD를 일컬으며 휘발성, 속도낮음, 기억 용량이 많습니다. 


> after

보조기억장치 : HDD, SDD를 일컬으며 비휘발성, 속도낮음, 기억 용량이 많습니다. 

## 149페이지 설명 변경
> before

스와핑

만약 가상 메모리에는 존재하지만 실제 메모리인... (생략)

> after

스와핑

만약 가상 메모리에는 존재하지만 실제 메모리인 RAM에는 현재 없는 데이터나 코드에 접근할 경우 페이지 폴트가 발생합니다. 이 때 메모리의 당장 사용하지 않는 영역을 하드디스크로 옮기고 하드디스크의 일부분을 마치 메모리처럼 불러와쓰는 것을 스와핑(swapping)이라고 합니다. 이를 통해 마치 페이지폴트가 일어나지 않은 것처럼 만듭니다.

페이지 폴트 

페이지 폴트(page fault)란 프로세스의 주소 공간에는 존재하지만 지금 이 컴퓨터의 RAM에는 없는 데이터에 접근했을 경우에 발생합니다. 페이지폴트와 그로 인한 스와핑은 다음 과정으로 이루어집니다.

## 151 페이지 설명 변경
> before

PFF(Page Fault Frequency)는 페이지 폴트 빈도를 조절하는 방법으로 상한선과 하한선을 만드는 방법입니다. 만약 상한선에 도달한다면 페이지를 늘리고 하한선에 도달한다면 페이지를 줄이는 것이죠. 

> after

PFF(Page Fault Frequency)는 페이지 폴트 빈도를 조절하는 방법으로 상한선과 하한선을 만드는 방법입니다. 만약 상한선에 도달한다면 프레임을 늘리고 하한선에 도달한다면 프레임을 줄이는 것이죠.  


## 153 페이지 설명 변경
> before 
페이지드 세그멘테이션(paged segmentation)은 공유나 보안을 의미 단위의 세그먼트로 나
누고, 물리적 메모리는 페이지로 나누는 것을 말합니다.
 

> after

페이지드 세그멘테이션(paged segmentation)은 프로그램을 의미 단위인 세그먼트로 나눠 공유나 보안 측면에 강점을 두고 임의의 길이가 아닌 동일한 크기의 페이지 단위로 나누는 것을 말합니다.  


## 163페이지 설명 변경
> before
 
### 스택
스택에는 지역변수, 매개변수, 함수가 저장되고 컴파일 시에 크기가 결정되며 ‘동적’인 특
징을 갖습니다.
스택 영역은 함수가 함수를 재귀적으로 호출하면서 동적으로 크기가 늘어날 수 있는데,
이때 힙과 스택의 메모리 영역이 겹치면 안 되기 때문에 힙과 스택 사이의 공간을 비워 놓
습니다.


### 힙
힙은 동적 할당할 때 사용되며 런타임 시 크기가 결정됩니다. 예를 들어 벡터 같은 동적
배열은 당연히 힙에 동적 할당됩니다. 힙은 ‘동적’인 특징을 가집니다.


### 데이터 영역
데이터 영역은 전역변수, 정적변수가 저장되고, 정적인 특징을 갖는 프로그램이 종료되면
사라지는 변수가 들어 있는 영역입니다.


데이터 영역은 BSS 영역과 Data 영역으로 나뉘고, BSS 영역은 초기화가 되지 않은 변수
가 0으로 초기화되어 저장되며 Data 영역(Data segment)은 0이 아닌 다른 값으로 할당된
변수들이 저장됩니다.

### 코드 영역
코드 영역은 프로그램에 내장되어 있는 소스 코드가 들어가는 영역입니다. 이 영역은 수
정 불가능한 기계어로 저장되어 있으며 정적인 특징을 가집니다.

> after

### 스택과 힙
스택과 힙은 동적할당이 되며 동적할당은 런타임단계에서 메모리를 할당받는 것을 말합니다. 
스택은 지역변수, 매개변수, 실행되는 함수에 의해 늘어들거나 줄어드는 메모리 영역입니다. 함수가 호출될 때마다 호출될 때의 환경 등 특정 정보가 스택에 계속해서 저장됩니다. 
또한, 재귀함수가 호출된다고 했을 때 새로운 스택 프레임이 매번 사용되기 때문에 함수 내의 변수 집합이 해당 함수의 다른 인스턴스 변수를 방해하지 않습니다. 
힙은 동적으로 할당되는 변수들을 담습니다. malloc(), free() 함수를 통해 관리할 수 있으며 동적으로 관리되는 자료구조의 경우 힙영역을 사용합니다. 예를 들어 vector는 내부적으로 힙영역을 사용합니다.    

### 데이터 영역과 코드 영역
이 영역은 정적할당되는 영역입니다. 정적할당은 컴파일단계에서 메모리를 할당하는 것을 말합니다. 데이터 영역은 BSS segment와 Data segment, code / text segment 로 나뉘어서 저장됩니다.
BSS segment는 전역변수 또는 static, const로 선언되어있고 0으로 초기화 또는 초기화가 어떠한 값으로도 되어 있지 않은 변수들이 이 메모리 영역에 할당되며 Data segment은 전역변수 또는 static, const 로 선언되어있고 0이 아닌 값으로 초기화된 변수가 이 메모리 영역에 할당됩니다.
code segment는 프로그램의 코드가 들어갑니다.



## 164페이지 설명 변경
> before

프로세스 스케줄링 상태 : '준비', .... (생략)

> after

프로세스 스케줄링 상태 : '준비', '일시중단' 등 프로세스가 CPU에 대한 소유권을 얻은 이후의 프로세스의 상태

## 173페이지 설명 변경

> before

공유자원에 접근할 때 순서 등의 이유로 ... (생략)

> after

임계 영역

임계영역(critical section)은 둘 이상의 프로세스, 스레드가 공유자원에 접근할 때 순서 등의 이유로 결과가 달라지는 코드 영역을 말합니다. 
임계 영역을 해결하기 위한 방법은 크게 뮤텍스, 세마포어, 모니터 세 가지가 있으며, 이 방법 모두 상호 배제, 한정 대기, 융통성이란 조건을 만족합니다. 
이 방법에 토대가 되는 메커니즘은 잠금(lock)입니다. 예를 들어 임계 영역을 화장실이라고 가정하면 화장실에 A라는 사람이 들어간 다음 문을 잠급니다. 그리고 다음 사람이 이를 기다리다 A가 나오면 화장실을 쓰는 방법입니다.

## 174페이지 설명 변경
> before

뮤텍스(mutext)는 공유 자원을 ... (생략)

> after

뮤텍스

뮤텍스(mutex)는 프로세스나 스레드가 공유 자원을 lock()을 통해 잠금 설정하고 사용한 후에는 unlock()을 통해 잠금해제하는 객체입니다. 잠금이 설정되면 다른 프로세스나 스레드는 잠긴 코드 영역에 접근할 수 없고 해제는 그와 반대입니다. 또한 뮤텍스는 잠금 또는 잠금해제라는 상태만을 가집니다. 

## 175페이지 설명 변경
> before

프로세스가 공유 자원에 접근하면... (생략)

> after

프로세스나 스레드가 공유자원에 접근하면 세마포어에서 wait() 작업을 수행하고 프로세스나 스레드가 공유자원을 해제하면 세마포어에서 signal() 작업을 수행합니다. 세마포어에는 조건 변수가 없고 프로세스나 스레드가 세마포어 값을 수정할 때 다른 프로세스나 스레드는 동시에 세마포어 값을 수정할 수 없습니다. 

바이너리 세마포어

바이너리 세마포어는 0과 1의 두가지 값만 가질 수 있는 세마포어입니다. 구현의 유사성으로 인해 뮤텍스는 바이너리 세마포어라고 할 수 있지만 엄밀히 말하면 뮤텍스는 잠금을 기반으로 상호배제가 일어나는 "잠금 메커니즘"이고, 세마포어는 신호를 기반으로 상호 배제가 일어나는 "신호 메커니즘"입니다. 
여기서 신호 메커니즘은 휴대폰에서 노래를 듣다가 친구로부터 전화가 오면 노래가 중지되고 통화 처리 작업에 관한 인터페이스가 등장하는 것을 상상하면 됩니다.


## 180페이지 설명 변경[new]

> before

라운드 로빈(RR, Round Robin)은 현대 컴퓨터가 쓰는 스케줄링인 우선순위 스케줄링
(priority scheduling)의 일종으로 각 프로세스는 동일한 할당 시간을 주고 그 시간 안에 끝
나지 않으면 다시 준비 큐(ready queue)의 뒤로 가는 알고리즘입니다.

> after

라운드 로빈(RR, Round Robin)은 현대 컴퓨터가 쓰는 선점형 알고리즘 스케줄링 방법으로 각 프로세스는 동일한 할당 시간을 주고 그 시간 안에 끝
나지 않으면 다시 준비 큐(ready queue)의 뒤로 가는 알고리즘입니다.
 
 
## 180페이지 설명 변경[new]

> before

이는 오래된 작업일수록 ‘우선순위를 높이는 방법(aging)’을 통해 단점을 보완한 알고리즘
을 말합니다.

> after

이는 오래된 작업일수록 ‘우선순위를 높이는 방법(aging)’을 통해 단점을 보완한 알고리즘
을 말합니다.
참고로 우선순위는 앞서 설명한 SJF와 우선순위를 말하는 것 뿐만 아니라 FCFS를 활용하여 만들기도 하며 선점형, 비선점형적인 우선순위 스케줄링 알고리즘을 말하기도 합니다. 

## 181페이지 오타  

RB > RR

## 182페이지 오타
> before

HDD, SDD를 일컬으며 휘발성,

> after

HDD, SDD를 일컬으며 비휘발성, 

## 186페이지 오타
> before

NoSQL 데이터베이스의 구조는... (생략)

> after

MongoDB 데이터베이스의 구조는 도큐먼트 - 컬렉션 - 데이터베이스로 이루어져 있습니다.

## 191페이지 설명 변경
> before

그렇기 때문에 지정된 형태에 ... (생략)

> after

그렇기 때문에 CHAR의 경우 유동적이지 않은 길이를 가지 데이터의 경우 효율적이며 유동적인 길이를 가진 데이터는 VARCHAR로 저장하는 것이 좋습니다.

## 191페이지 설명 변경
> before
 
CHAR는 테이블을 생성할 때 선언한 길이로 고정되며 길이는 0에서 255 사이의 값을 가
집니다. 레코드를 저장할 때 무조건 선언한 길이 값으로 ‘고정’해서 저장됩니다. 

> after

CHAR는 고정 길이 문자열이며 길이는 0에서 255 사이의 값을 가집니다. 레코드를 저장할 때 무조건 선언한 길이 값으로 ‘고정’해서 저장됩니다. 예를 들어 CHAR(100)으로 선언한 후 10글자를 저장해도 100바이트로 저장되게 됩니다. 


## 210페이지 오타[new]
 > BEFORE

### REPEATABLE_READ
REPEATABLE_READ는 하나의 트랜잭션이 수정한 행을 다른 트랜잭션이 수정할 수 없
도록 막아주지만 새로운 행을 추가하는 것은 막지 않습니다. 따라서 이후에 추가된 행이
발견될 수도 있습니다. 
 

### READ_COMMITTED
READ_COMMITTED 는 가장 많이 사용되는 격리 수준이며 MySQL8.0, PostgreSQL,
SQL Server, 오라클에서 기본값으로 설정되어 있습니다. READ UNCOMMITTED 와
는 달리 다른 트랜잭션이 커밋하지 않은 정보는 읽을 수 없습니다. 즉, 커밋 완료된 데이
터에 대해서만 조회를 허용합니다.
하지만 어떤 트랜잭션이 접근한 행을 다른 트랜잭션이 수정할 수 있습니다. 예를 들어 트
랜잭션 A가 수정한 행을 트랜잭션 B가 수정할 수도 있습니다. 이 때문에 트랜잭션 A가 같
은 행을 다시 읽을 때 다른 내용이 발견될 수 있습니다.

 > AFTER

### REPEATABLE_READ
REPEATABLE_READ는 하나의 트랜잭션이 수정한 행을 다른 트랜잭션이 수정할 수 없
도록 막아주지만 새로운 행을 추가하는 것은 막지 않습니다. 따라서 이후에 추가된 행이
발견될 수도 있습니다.이는 MySQL8.0의 innoDB 기본값이기도 합니다.

### READ_COMMITTED
READ_COMMITTED 는 가장 많이 사용되는 격리 수준이며 PostgreSQL,
SQL Server, 오라클에서 기본값으로 설정되어 있습니다. READ UNCOMMITTED 와
는 달리 다른 트랜잭션이 커밋하지 않은 정보는 읽을 수 없습니다. 즉, 커밋 완료된 데이
터에 대해서만 조회를 허용합니다.
하지만 어떤 트랜잭션이 접근한 행을 다른 트랜잭션이 수정할 수 있습니다. 예를 들어 트
랜잭션 A가 수정한 행을 트랜잭션 B가 수정할 수도 있습니다. 이 때문에 트랜잭션 A가 같
은 행을 다시 읽을 때 다른 내용이 발견될 수 있습니다. 
