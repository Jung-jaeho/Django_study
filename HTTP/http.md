# 4주차
 HTTP = HyperText Transfor Protocol

------

## 목차
### 1) HTTP 소개
### 2) HTTP Request Message
### 3) HTTP Response Message
### 4) 마무리


## 1) HTTP 소개
**HTTP란?**

-  HTTP는 클라이언트와 서버 사이에서 request와 response를 하는 프로토콜
-  클라이언트(웹 브라우저)가 HTTP를 통하여 서버로 요청을 하면(CSS,HTML,IMAGE..) 웹 서버는 클라이언트에게 응답하는 방식
-  클라이언트와 서버가 컨텐츠를 주고 받기 위해서는 알아 들을 수 있는 메세지가 필요하고 그것에 해당하는 공통의 약속에 메시지

![http_client_server](./img/http_client_server.png)


### 결론  
웹브라우저가 하는 역할은 사용자가 요청한 정보를 웹서버에게 대신 물어봐 주는(요청헤더를 이용해서) 기능이다. 웹서버는 자기가 가지고 있는 정보를 보내주면서 응답헤더를 만들어주는 기계이다. 그러면 웹브라우저는 응답한 정보를 화면에 그려주는 역할이다.

### 정리  
  1) HTTP -> 클라이언트와 서버 사이에 통신을 해주는 프로토콜  
  2) Client -> 요청자  
  3) Web server -> 요청을 받고 응답해주는 곳  
  4) Web browser -> client와 Server의 통역사(?) 역할   



## 2) HTTP Request Message

**HTTP Request Message**  
-  Web Browser와 Web Server가 서로 주고받는 메시지에 대해서 자세히 알아보자  
  (Brower -> Server)
  
![Request message](./img/Request_message.png)
  
### 1. Request line

  * Web browser와 web server가 어떤 방식으로 통신할 것인지 설명  
     * Get : 우리가 데이터를  web Server로부터 가져올 때 쓰는 것(질문)
     * HTTP/1.1 : 현재 Web browser가 현재 사용하고 있는 버전이다. 그래서 이 버전을 통해서 적당한 방식으로 통신을 하는 것이다.
     * HOST : 우리가 요청하는 Web site에 Web server 주소  
     * PORT : 사진에는 없지만 HOST/8080 적혀있는 경우가 있다. 쉽게 생각하면 HOST는 "재호네 집"이고 POST는 "재호방"이라고 보면 된다.
     * USER-AGENT : 요청하는 Web browser가 어떤 Web browser인지 나타낸다.
     * Accept Encoding : 데이터 양이 많을 때 압축하는 방식
     * If-Modified-Since : 내가 가지고 있는 파일에 대한 수정날짜


## 3) HTTP Response Message
-   Web Server와 Web Browser가 서로 주고받는 메시지에 대해서 자세히 알아보자  
  (Server -> Brower)   
  ![Response_format](./img/Response_format.jpg)

* STATUS LINE
  * version(HTTP version)
  * status(상태) : 서버가 응답했을 때 상태 (ex 2XX,3XX,404..)
  * phrase :사람이 이해하기 쉽도록 풀어쓴 부분 (ex OK,ERROR ..)
  
* HEADER
   * Content-type : Web server가 응답할때 타입(이파일은 text이며 html로 해석한다. 이미지파일 이면 image/jpeg 이다.)
   * Contnet-Length : Size를 보여준다.(단위 byte)
   * Content Encoding : 압축방식




## 4) 마무리
  
  ### (1) Web browser Request

![request](./img/request.png)  
  Web Browser는 이렇게 생긴 코드를 Web Server에게 요청한다.
  (여기서 GET이 아닐 경우는 아래에 더 추가하면 된다.)  


### (2) Web browser Response
![response](./img/response.png)  
 Web server가 응답할때는 헤더+요청받은 내용(HTML,jpg, ..)을 입력하여 Web browser에게 주면  Web browser는 헤더와 본문은 참조해서 사용자에게 보여준다.

 ### (3) Get vs Post(추가설명)

 Get 방식 (URL에 넣는 방식)
www.example.com?id=mommoo&pass=1234 

URL에 붙이고 HTTP 패킷의 헤더에 포함되어서 서버로 요청하는 방식이다.
따라서 get방식은 body에 특별한 내용이 안들어간다. 

URL형태로 표현되므로, 특정 페이지를 다른사람 에게 접속하게 할 수 있다. 
또한 간단한 데이터를 넣도록 설계되어, 데이터를 보내는 양의 한계가 있다.

POST 방식 (BODY에 넣는 방식)
POST 방식은 GET 방식과 달리, 데이터 전송을 기반으로 한 요청 메서드이다.
GET방식은 URL에 데이터를 붙여서 보내는 반면, POST방식은 URL에 붙여서 보내지 않고
BODY에다가 데이터를 넣어서 보낸다.  
따라서, 헤더필드중 BODY의 데이터를 설명하는 Content-Type이라는 헤더 필드가
들어가고 어떤 데이터 타입인지 명시한다.
