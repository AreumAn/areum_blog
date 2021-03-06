+++
title = "Web 이해하기"
date = 2019-04-17T01:01:18-04:00
weight = 2
chapter = true
pre = "<i class='far fa-window-maximize'></i> "
+++

### 웹 이해하기
***
웹 개발자로 일을 하게 되면서 알아야할 전반적인 상식/지식들이 많이 있습니다.
제가 알아가는 것들과 시간이 없어 나중에 공부해야겠다고 생각하는 개념들을 정말 *_간단하게_* 적어보려고 합니다. 제가 따로 정리도 하겠지만 도움받았던 사이트들 링크를 넣어서 반복 되는 내용 없고 쉽게 정리할 예정입니다.

{{% notice warning %}}
저작권을 잘 몰라서 왠만한 그림은 제가 직접 그립니다. 허접해도 용서를 바랍니다.
{{% /notice %}}


+ [정적 웹사이트와 동적 웹사이트](#web-static-dynamic)
+ [검색의 시대, 웹크롤러(web crawler)](#web-crawler)
+ [Redirection - 301 그리고 302](#web-redirection)
+ [CDN - 컨텐츠 전송 네트워크](#web-cdn)

<a name="web-static-dynamic"></a>
### 정적 웹사이트와 동적 웹사이트
___

#### + [ 정적웹사이트 ]

![static](https://drive.google.com/uc?id=1CfiAGV1gdUZsWI2oj8KIj8PMpsa_jmc3)

웹페이지의 내용이 요청하는 모든 사용자에게 같은, 정적인 정보인 경우.
모든 사용자는 같은 내용의 웹페이지를 서버에 요청하고 응답 받습니다.

예를 들어 작은 식당에서 메뉴를 보여주기 위한 웹사이트를 만든다고 가정해 보면, 이 식당 사이트는 모든 사용자에게 같은 메뉴를 보여줄 것 입니다.
현재 보시고 있는 제 웹사이트도 모두에게 동일한 정보를 보여주는 정적 웹사이트입니다.

이와 같이 사용자/클라이언트가 URL를 통해 서버에 웹페이지를 요청하였을 때, 서버 안에 이미 만들어져 있는 HTML문서를 사용자에게 보내주는 경우 이를 정적 웹페이지라고합니다.
이렇게 구성된 웹사이트를 정적 웹사이트라고 합니다.

#### + [ 동적웹사이트 ]

![dynamic](https://drive.google.com/uc?id=11838Y9_e506TSx2k1ThS7OH9szOOSMiu)

반면에 페이스북이나 구글 이메일 등을 보기 위해 로그인을 하면 각 사용자에 따라 다른 정보와 페이지를 보여 주게 됩니다.
이를 동적이라고 합니다.

사용자/클라이언트가 URL를 통해 서버에 웹페이지를 요청했을 때, 서버는 사용자에 맞는 HTML문서를 만들어서 사용자에게 보내주는 경우 이를 동적 웹페이지 라고합니다.
즉, 모든 사용자는 서로 다른 결과를 서버로부터 응답받게 된다.

이렇게 구성된 웹사이트를 동적인 웹사이트라고 합니다.

<a name="web-crawler"></a>
### 검색의 시대, 웹크롤러(web crawler)
___

#### + 웹크롤러(web crawler)

**인터넷에 있는 웹페이지를 방문해서 자료를 수집하는 일을 하는 프로그램.**

#### + 웹 크롤링(web crawling) = web spidering

**자동화 봇(bot)인 웹크롤러(web crawler)가 정해진 규칙에 따라 여러개의 웹페이지를 브라우징 하는 것**

웹은 기본적으로 HTML 형태로 되어 있습니다. 각 소스들은 보통 개발자들이 거의 일정한 형태로 관리하고 있습니다.
즉, 페이지 마다 규칙이 있습니다. 이런 규칙을 분석해서 우리가 원하는 정보만 뽑아 오는 것을 웹크롤링 작업이라고 할 수 있습니다.


#### + 웹 스크래핑 (web scraping)

웹 사이트 상에서 원하는 부분에 위치한 정보를 컴퓨터로 하여금 자동으로 추출하여 수집하도록 하는 기술


일단 간단히 적었는데, 이 부분은 저도 더 정확한 이해를 위해서 더 공부한 후 정리하도록 하겠습니다.

{{% notice info %}}
[http://www.zinicap.kr/archives/4710](http://www.zinicap.kr/archives/4710)<br />
[https://www.youtube.com/watch?v=gsfmhpsQH08](https://www.youtube.com/watch?v=gsfmhpsQH08)<br />
[https://docs.slimframework.com/routing/helpers/](https://docs.slimframework.com/routing/helpers/)
{{% /notice %}}



<a name="web-redirection"></a>
### Redirection - 301 그리고 302
___

#### + 언제 페이지 이동을 할까?
1. ***기존의 페이지 주소가 다른 주소로 변경 되었을 때***
2. ***로그인, 인증 등 다른 주소로 이동이 필요한 경우***
    - 로그인 후 메인 페이지로 이동
    - 이메일 인증이나 핸드폰 번호 인증 후 인증 확인 페이지로 이동하는 경우
3. ***서로 다른 주소를 하나로 이동시키는 경우***
    - 아래 두 주소를 같은 페이지로 이동

    ```
        https://www.example.com
        https://kr.example.com
    ```
등등등...

#### + 301, 302라는 숫자는 무엇일까?

에러 페이지나 웹사이트가 안될 때 가장 쉽게 접하는게 404에러와 500인데요. 301, 302도 이런 코드 중에 하나입니다. (자주 보지 못했을 뿐..)
이런 코드들을 `HTTP Response Status Code`라고 합니다.

> **HTTP Response Status Code :** <br />
요청에 대한 웹서버의 응답을나타내는 코드. 이 코드를 바탕으로 웹브라우저나 검색엔진 크롤러는 요청을 어떻게 처리해야할지 판단.

<u>**3XX redirection :**</u> 3으로 시작하는 코드는 클라이언트를 지정된 위치로 이동 시키거나 참조하게 하는 등의 동작을 합니다.
***즉, 301과 302의 공통점은 사용자(브라우저)를 새로운 url로 이동 시키는 것*** 임을 알 수 있습니다.

{{% notice info %}}
HTTP response status codes 관련[https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
{{% /notice %}}

#### + 301, 302 차이점

브라우저가 redirection을 만났을 때, 대부분 새로운 url로 이동하지만 검색엔진 크롤러가 redirection 코드(301,302)를 만나면 서로 다르게 동작을 합니다.

> **웹 크롤러가 궁금하다면? [검색의 시대, 웹크롤러(web crawler)](#web-crawler)**

**301(Permanaently Moved)- 영구적으로 옮기는 것.**

- **해당 url이 영구적으로 새로운 url로 변경 되었음을 나타냄. 검색엔진 크롤러는 301 요청을 만나면 컨텐츠가 완전히 새로운 url로 영원히 이동했다고 판단.**
- 검색엔진은 과거 URL의 페이지 랭킹과 평가 점수를 새로운 URL로 이동시킴
- 웹사이트의 도메인을 변경하거나 새로운 url 구조로 개편 했을 때 사용
- 서버 사이드 방법을 이용


**302(Temporarily Moved)- 일시적으로 옮기는 것**

- **요청한 소스가 임시적으로 새로운 url로 이동했음.**
- 검색엔진은 페이지랭킹이나 링크에 대한 점수를 새로운 url로 옮기지 않으며 기존의 url을 그대로 유지. **즉, 검색엔진이 기존 url이 보유한 페이지랭킹 점수는 그대로 유지하도록 하면서 컨텐츠만 새로운 url에서 조회하도록 해야 할 때 유용**
- 일시적인 방법으로 스크립트나 html 태그를 이용한 방법



쉬운 예로 쇼핑몰을 보면, 일시적으로 재고가 없다는 페이지로 이동하는 경우가 있습니다. <br />
_기존 페이지를 A,_ <br />
_재고가 떨어졌다는 알림 페이지를 B라고 한다면,_ <br />
우리가 A로 접속을 할때 B로 페이지 이동이 될 것입니다.<br />

<u>_**302를 이용하게 되면,**_</u> <br />
기존에 A의 페이지 랭킹 점수를 그대로 유지하면서 B페이지를 보여주게 될 것입니다. 나중에 재고가 들어와서 다시 A를 이용한다고 해도 페이지랭킹 점수를 가지고 있기 때문에 기존 랭킹을 유지할 수 있습니다. <br />

<u>_**301로 하게 되면**_</u><br />
페이지 랭킹점수 자체가 모두 B로 이동을 했기때문에 재고가 다시 들어와서 A를 다시 이용하더라도 기존에 페이지 랭킴 점수는 모두 잃었기 때문에 다시 페이지 랭킹을 올리기 위해 더 열심히 일해야겠죠.....


<a name="web-cdn"></a>
### CDN - 컨텐츠 전송 네트워크
___

#### + [ CDN(Content delivery network / Content distribution network) ]

CDN은 컨텐츠를 효율적으로 전달하기위해 제공되는 시스템입니다.
그럼 어떻게 *효율적으로* 전달을 하겠다는 걸까요?

아래 두 그림을 비교해 보면 쉽습니다.

*ISP(Internet Service Provider)): 인터넷 서비스 제공자

![CDN을 사용하지 않았을 때](https://drive.google.com/uc?id=14BlORJMRvapvi632IJDDzHVbYuojHfIJ)
##### CDN을 사용하지 않았을 때


![CDN을 사용](https://drive.google.com/uc?id=1Swjuqo2pzZgroLnKFaEUnoUyLBXxjRV-)
##### CDN을 사용했을 때

첫번째 그림은 하나의 origin 서버에서 각 세계의 요청에 응답을 모두 일일이 해줍니다.<br />
반면에 두번째 CDN을 사용 한 그림을 보면 세계 각국에 캐시 저장소를 만들어 놓습니다.
각 캐시는 text, graphics, script 등 파일들을 저장해 둡니다. 그리고 요청이 있을때 캐시에서 ISP로 요청한 자료를 보내주게 되죠. 서버에 계속 요청 할 필요 없으니 당연히 속도는 빨라지고 End-to-End 딜레이가 줄어들게 되겠죠.

우리나라에서만 사용하는 작은 시스템엔 별로 영향이 없겠지만, 세계 각지에서 접속하는 유튜브, 네플릭스, 구글과 같은 사이트에는 굉장히 유용하겠죠.


{{% notice info %}}
[이미지 출처 바로가기](https://www.netmanias.com/ko/post/blog/5350/cdn/the-advantage-of-the-cdn-content-delivery-network)
{{% /notice %}}

