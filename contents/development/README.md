## Development common sense

- [객체 지향 프로그래밍이란?](#객체-지향-프로그래밍이란?)
- [REST API란?](#REST-API란?)
- [HTTP vs HTTPS](#HTTP-vs-HTTPS)
- [Client Side Rendering vs Server Side Rendering](#CSR-vs-SSR)
- [호이스팅?](#호이스팅?)
- [클로져?](#클로저)
- [SEO?](#SEO?)

  <br></br>
  <br></br>
  <br></br>

# 객체 지향 프로그래밍이란?

Object Oriendted Programming
프로그래밍에서 필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 그 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법이다.

### 장점

- 코드 재사용이 용이하다.
- 절차 지향 프로그래밍에서는 코드를 일일히 찾아서 수정해야하는 반면에 객체 지향 프로그래밍에서는 수정해야할 부분이 클래스 내부에 변수 혹은 메서도로 존재하기 때문에 해당 부분만 수정하면 되기에 유지보수가 쉽다
- 대형 프로젝트에 적합하다. 클래스 단위 모듈화시켜서 개발할 수 있으므로 프로젝트 개발 할 때 업무 분담하기 쉽다
  <br></br>

### 단점

- 처리속도가 상대적으로 느리다
- 객체가 많으면 용량이 커질 수 있다
- 설계시 많은 시간과 노력이 필요하다
  <br></br>
  <br></br>

# REST API란?

- Representational State Transfer 라는 용어의 약자로 자원을 이름으로 구분하여 해당 자원의 상태(정보)를 주고 받는 모든 것을 의미
- HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고, HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미
  <br></br>

### REST 구성

- 자원(Resource) - URL
- 행위(Verb) - HTTP METHOD
- 표현(Representations)

URL는 정보의 자원을 표현하고 자원에 대한 행위는 method (GET,POST,PUT,DELETE)로 표현한다.
<br></br>

### REST의 장단점

- 장점
  - HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구출 할 필요가 없다.
  - HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.
  - REST API 메시지가 의도하는 바를 명확하게 나타내므로 의도하는 바를 쉽게 파악할 수 있다.
  - 서버와 클라이언트의 역할을 명확하게 분리한다.
- 단점
  - 표준이 존재하지 않는다.
    <br></br>

### REST가 필요한 이유

- 애플리케이션 분리 및 통합
- 최근의 서버 프로그램은 다양한 브라우저와 안드로이드폰, 아이폰과 같은 모바일 디바이스에서도 통신을 할 수 있어야 한다.
  <br></br>

## RESTful 이란?

RESTful은 일반적으로 REST라는 아키텍처를 구현하는 웹 서비스를 나타내기 위해 사용되는 용어이다. 이해하기 쉽고 사용하기 쉬운 REST API를 만드는 것이 목적이다.
<br></br>
<br></br>

# HTTP vs HTTPS

### HTTP

- HyperText Transfer Protocol
- W3 상에서 정보를 주고 받을 수 있는 프로토콜
- 주로 TCP를 사용하고 HTTP/3부터는 UDP를 사용하며 80번 포트를 사용

### HTTPS

- HyperText Transfer Protocol over Secure Socket Layer, HTTP over TLS, HTTP over SSL, HTTP Secure
- 월드 와이드 웹 통신 프로토콜인 HTTP의 보안이 강화된 버전
- TCP/IP 443번 포트 사용
- 기존 HTTP 레이어에 SSL(TLS) 프로토콜을 얹어 평문 데이터를 암호화
- 인증, 전자상거래와 같은 민감함 트래픽에 이용

### 두 개의 가장 큰 차이점

- SSL 인증서
  사용자가 사이트에 제공하는 정보를 암호화하는데, 쉽게 말해서 데이터를 암호로 바꾼다고 생각하면 이해가 쉽다. 전송된 데이터를 누군가가 훔쳐낸다고 해도 데이터가 암호화되어있기때문에 해독할 수가 없다.

### HTTPS를 사용하는 이유

- 기밀성 <br/>
  HTTPS는 인터넷과 같은 공공매체에서 두 참여자 간의 통신을 보호한다
- 무결성<br/>
  HTTPS는 변조되지 않은 정보로 목적지에 도달하게 한다.
- 인증 <br/>
  HTTPS를 통해 웹사이트의 진위 여부를 확인할 수 있다.

  <br></br>
  <br></br>

# CSR vs SSR

### Client Side Rendering

HTML을 반환 한 후에 자바스크립트만 동작하면서 데이터만 주고 받아서 렌더링을 진행하는 방식
싱글 페이지 어플리케이션이라고도 한다.

#### 장점

- 첫 요청시 한 페이지만 불러온다. 그 이후 필요한 부분만 랜더링해서 읽기에 빠른 인터렉션을 기대할 수 있다.
- 페이지 로딩시 중요하지 않은 리소스의 로딩을 늦춘다.

#### 단점

- 초기 구동속도가 상당히 느리다.
  <br></br>

### Server Side Rendering

서버에서 랜더링 작업하는 방식으로 사용자가 웹 페이지에 접근할 때 서버에 각각의 페이지에 대한 요청을 하며 서버에서 HTML, JS파일 등을 다 다운로드해서 화면에 랜더링하는 방식

#### 장점

- 검색엔지 최적화(SEO) 가능
- 첫 랜딩된 HTML을 client에게 전달해주기때문에 초기 로딩속도를 많이 줄일 수 있다.

#### 단점

- 페이지 이동시 화면이 깜빡 거린다.
- 서버 랜더링에 따른 부하가 발생한다.
- 페이지 요청마다 페이지 새로고침이 발생한다.
  <br></br>
  <br></br>

# 호이스팅?

Hoisting이란 사전적 의미로 끌어 올리기라는 뜻이고 실제로 하는 일도 사전적 의미와 동일하다. 모든 선언(변수, 함수)들을 어느 위치에 호출하던지 간에 자바스크립트는 그 선언들을 스코프의 최상단으로 끌어 올려지는 현상을 이야기한다.

<br></br>
<br></br>

# 클로저

Closure는 내부함수가 외부함수의 지역변수에 접근할 수 있고, 외부함수는 외부함수의 지역변수를 사용하는 내부함수가 소멸 될 때까지 소멸되지 않는 특성을 말합니다.

    function name( first, sur){
        console.log( sur, first);
    }
    name("yeona","kim")

    //이름을 출력해주는 함수 name을 만들었다.

    function firstName( first){
        return function surName( sur){
            console.log(sur, first)
        }
    }

    var myName = firstName("yeona");
    myName("kim")
    //kim yenona가 출력된다.
    //yeona가 함수의 리턴이 끝나기 전까지 계속 상주하고 있었던 것!

<br></br>
<br></br>

# SEO?

검색엔진최적화(Search Engine Optimization, SEO)는 사용자의 검색의도를 명확히 이해하여 고객니즈 기반으로 웹사이트의 기능을 개선, 콘텐츠를 제작하는 방법

우리의 웹페이지는 html document 기반입니다. 페이지에서 title과 discription이 있으니 이러한 정보를 제공하는구나 라고 해당 웹사이트에 대한 정보를 검색엔진에 등록시켜둡니다. 이러한 작업으로 인해 원하는 정보들을 실어 놓은 페이지를 우리가 빠르게 분석할 수 있게 되는 것이고 해당 프로세스가 잘 이뤄질 수 있도록 해주는 것입니다.

react의 경우 CSR로 javascript가 모든 것을 처리해주는 구조입니다. 이 경우 html파일은 빈껍데기나 다름이 없기때문에 SEO 성능이 좋지 못하다고 이야기합니다. 하지만 그렇다면 해결 못하지는 않습니다. react-helmet 라이브러리를 사용하는 방법이 있습니다. SEO의 성능은 HTML 태그중 메타 태그와 직접적인 연관이 있습니다. SSR을 이용할 경우 정적 웹페이지를 이용하여 파일에서는 페이지 별로 이러한 meta태그를 일일이 다룰 수 있지만, CSR에서는 이러한 것이 불가능 하죠. react-helmet을 사용할 경우 이러한 부분을 해결해줄 수가 있습니다. react-helmet 패키지는 동적으로 SEO에 필요한 메타태그들을 쉽게 변경할 수 있게 도와주는 라이브러리 입니다
