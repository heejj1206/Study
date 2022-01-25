# RESTful
[작성자: 노희재]
&nbsp;   
&nbsp;   

💡 REST, REST API, RESTful

다들 한 번씩은 들어봤을 이 용어들은 각각 어떤것을 의미하는 걸까요?
     
&nbsp;   
&nbsp;   
&nbsp;   

## **REST 란?**

‘REpresentational State Transfer’ 의 줄임말.

하나의 아키텍처로 볼 수 있으며,

API 설계의 중심에 리소스가 있고 HTTP Method 를 통해 리소스를 처리하도록 설계하는 것입니다.

*즉, RESTful 이란 용어는*

REST 의 기본 원칙을 성실히 지킨 서비스 디자인을 표현하는 말이라고 할 수 있습니다.

&nbsp;
&nbsp;
&nbsp;   
&nbsp;   

## **API 란?**

‘Application Programming Interfaces’ 의 줄임말.

Application Software 를 구축하고 통합하는 정의 및 프로토콜 세트로,

사용자나 클라이언트가 얻으려 하는 리소스 사이의 조정자로 생각하면 됩니다.

ex) 날씨 서비스용 API 에서 사용자는 우편번호를 제공하고,

생산자는 해당 지역의 기온을 응답하도록 지정 할 수 있다.

&nbsp;   
&nbsp;
&nbsp;   
&nbsp;   

## **그렇다면 RESTful 하게 API 를 설계한다는 것은 어떤 걸 의미하는 걸까요?**

1. 리소스와 행위를 직관적으로 분리한다.
    - 리소스는 URI 에 명사로 표현한다.
    - 행위는 리소스에 대한 CRUD 를 HTTP Method 로 표현한다.
    
    ex) URL : [h](https://heejj.com/v2/book)ttp://heejj.com/user/1, HTTP Method : DELETE (O)
    
     URL : http://heejj.com/user/1/delete, HTTP Method : POST (X)
     &nbsp;   
     &nbsp;   
    
    | CRUD | HTTP Method |
    | --- | --- |
    | CREATE | POST |
    | READ | GET |
    | UPDATE | PUT, PATCH |
    | DELETE | DELETE |
    
    &nbsp;   
    &nbsp;   
    
2. Header 와 Body 를 명확하게 분리해서 사용한다.
    - 리소스에 대한 내용은 Body 에 담는다.
    - HTTP 요청/응답에 필요한 정보들은 Header 에 담는다.
        - 요청 시간
        - MIME 타입
        - API 정보
        - 등등

&nbsp;   

3. API 버전을 관리한다.
    - API 의 Base URL 이 변경될 수도 있음에 유의해야 한다.
    - 특정 API 를 변경할 때는 반드시 하위호환성을 보장해야 한다.
    
    &nbsp;    
    
4. Stateless
    - Stateless 란?
        - 무상태.
        - 클라이언트와 서버 관계에서 서버가 클라이언트의 상태를 보존하지 않음을 뜻한다.
        
    - Stateless 를 지키는 방법 = 멱등성을 지킨다.
        - 멱등성이란? 연산을 여러번 적용하더라도 결과가 달라지지 않는 성질
        - 고로, *Stateless 를 지키는 방법은*
            
            클라이언트가 서버에게 몇번의 응답을 요청한다고 해도 늘 같은 답이 돌아와야 한다.
            
        - 이를 위해서 서버는 클라이언트의 행동이 서버의 상태를 변경하게 하면 안된다.
        - 서버는 각각의 요청을 완전히 별개의 것으로 처리하여
            
            이전 요청이 다음 요청에 연관되지 않게 하기 때문에
            
            처리 방식에 일관성을 부여하기 때문에 서버의 부담이 줄어든다.
            
            = 두가지 행동을 하나의 API 로 처리하지 않는다.
            
&nbsp;   
&nbsp;   
&nbsp;   

# 👋  마치는 

RESTful 을 공부하며 느낀 점은

어떻게 보면 RESTful 은 비교적 쉽게 이해 할 수 있는 개념이지만

이 개념을 이해하기 위해 알아야 하는 지식들이 더 어려웠습니다.

저는 Stateless 관련 부분이 가장 복잡하다고 느껴졌는데요,

중요한 내용이라고 하니 다들 더 많은 내용을 찾아보시면 좋을 것 같습니다!

&nbsp;   
&nbsp;   
