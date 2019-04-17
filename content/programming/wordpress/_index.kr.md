+++
title = "Wordpress"
date = 2019-04-08T01:40:06-04:00
weight = 10
chapter = true
pre = "<i class='fab fa-wordpress'></i> "
+++

### 워드프레스
***
디자인 에이전시에서 1년정도 파트타임으로 간단한 워드프레스 사이트들을 만들었습니다.
너무 기초적인 설명은 제외하고 제가 일하면서 가장 기본이 되고 자주 사용했던 부분을 정리해보고자 합니다.
그래도 혹시나 궁금하신 부분 메일주시면 추가하도록하겠습니다.

+ [워드프레스 간단한 소개](#wp-section01)
+ [중요파일들 및 구조](#wp-section02)
+ [자주 수정되는 부분](#wp-section03)
+ [child theme vs theme](#wp-section07)
+ [로컬에 세팅하기](#wp-section04)
+ [도커에 설치하기](#wp-section05)
+ [유용한 플러그인들](#wp-section06)


<a name="wp-section01"></a>
### 워드프레스 간단한 소개
___
워드프레스를 open-source CMS(Content management system)라고 합니다.
쉽게 말해 오픈소스는 공짜로 쓸 수 있는 것이다. CMS를 직역하면 컨텐츠 관리 시스템입니다. 컨텐츠를 어떻게 관리할건데? 웹사이트로 만들어서 관리한다고 하는게 가장 쉬울 것 같습니다.

워드프레스는 쉽게 웹사이트를 설치해서 만들어 주는 시스템이라고 보는게 가장 쉬운 표현일 것 같네요.

저 같은 경우는 godaddy, 1 and 1, siteground 등 호스팅회사를 이용해서 워드프레스 사이트를 만들었습니다.(wordpress에서 제공하는 호스팅을 이용하지 않았습니다)

<a name="wp-section02"></a>
### 중요파일들 및 구조
___
https://en-ca.wordpress.org/download/
일할 때 보통 구글에서 영어로 검색해서 위에 사이트가 나왔네요..
여튼 구글에서 워드프레스 파일 단운로드 하면 다운 받을 수 있는 페이지가 나옵니다.
다운받아서 압축을 풀면 wordpress라는 폴더가 생기고 아래와 같은 파일들이 나옵니다.

![wp-files](https://drive.google.com/uc?id=1_y73KWYmrG9e-MguSIcqR5Oq_D11LrJm)
##### 워드프레스 파일 안에 구조들

위에 그림에서 보듯이 기본적인 워드프레스 파일 구조는 3개의 폴더와 파일들로 구성되어있습니다.
```
1. `wp-admin`
2. `wp-content` : 개발 시에 가장 많이 수정하게 되는 폴더
3. `wp-includes`
`기본설정 파일들(폴더 밖)`
```

기본 워드프레스 파일에는 `wp-config.php`가 없는데요.
`wp-config-sampe.php` 를 복사해서 `wp-config.php`라는 파일을 만들어줍니다.

- ***wp-config.php***<br>
`wp-config.php`는 DB에 접속하기 위한 정보나 업로드용량 제한 등을 수정할 때 쓰입니다.
기본적으로 한번이라도 워드프레스를 직접 설치해 본 적 있는 사람들은 반드시 알아야하는 파일이기도 합니다.

- ***version.php***<br>
해당 파일의 `$wp_version = '5.1.1';`를 통해서 워드프레스 버전을 소스에서 알아 볼 수 있습니다. 수정할 일은 없지만 플러그인 등을 구입할때 워드프레스와 php버전이 맞는 것을 사용해야합니다. 그때 워드프레스 버전을 알아보기 쉽겠죠.
_참고로 소스보기를 통해 아래 내용을 체크해 볼 수도 있습니다.
```
<meta name=”generator” content=”WordPress 5.1.1″>
```

- ***wp-content 폴더***<br>
해당 폴더는 테마와 플러그인이 설치되는 폴더입니다.
용량이 너무 큰 플러그인들도 있었고 오래된 버전의 플러그인을 쓰고 싶을 때도 있었기때문에 주로 직접 파일을 FTP로 호스팅 하는 서버에 업로드했습니다.
1.***wp-content/themes*** : 테마가 설치되는 폴더입니다.<br>
2.***wp-content/plugins*** : 플러그인이 설치 되는 폴더입니다.

_어드민 페이지에서 테마와 플러그인을 업로드 하고 싶은 경우_
- 어드민페이지: 도메인/wp-admin<br>
- 테마: 외모(apperance) > 테마(theme)<br>
- 플러그인: 플러그인 메뉴<br>

<a name="wp-section07"></a>
### child theme vs theme
___
두개의 차이점은 워드프레스를 하는 회사에 개발자로 취업하고 싶다면 면접시 꼭 준비해야하는 부분이기도 합니다.
유료테마의 경우 child theme을 기본적으로 제공합니다.

테마를 그대로 쓴다면 문제가 없겠지만, 고객의 요구사항에 따라서 일정 부분을 수정해야하는 경우가 발생하는데요. 뭐 그렇게 계속 수정된 부모테마를 쓴다면 문제가 없지만.

유지보수와 보안을 위해 부모테마의 버전을 업데이트 하게 되면 기존에 우리가 수정한 부분은 모두 날라가게 됩니다.

![lost](https://drive.google.com/uc?id=1qtyAhsay2XTcfyld_L7ZR222moKwnqSE)
##### 하...상상도 하기 싫다

그렇다고 수정을 안 할 수도 없고... 업데이트를 계속 안할 수도 없고....

그 대안이 바로 child 테마입니다. 수정은 자식테마를 계속 해주고 부모테마를 업데이트 해주면 테마는 업데이트 되고 저희가 수정한 부분도 남아 있게 됩니다.

<a name="wp-section03"></a>
### 자주 수정되는 부분
___

- 워드프레스 메모리 256M로 리밋 늘리기 : `wp-config.php`

```
define( 'WP_MEMORY_LIMIT', '256M' );
```

- 파일 업로드 크기 늘리기 : 아래 세가지 방법이 있습니다.
_* 파일 변경 전에 호스팅 회사의 cpanel에 들어가서 php설정을 변경하는 부분이 있는지 먼저 확인하는 것을 추천드립니다._

    ***1. 본인이 사용하는 테마의 functions.php***

    ```php
    @ini_set( 'upload_max_size' , '64M' );
    @ini_set( 'post_max_size', '64M');
    @ini_set( 'max_execution_time', '300' );
    ```
    ***2. php.ini***

    ```
    upload_max_filesize = 64M
    post_max_size = 64M
    max_execution_time = 300
    ```

    ***3. .htaccess***
    ```
    php_value upload_max_filesize 64M
    php_value post_max_size 64M
    php_value max_execution_time 300
    php_value max_input_time 300
    ```


<a name="wp-section04"></a>
### 로컬에 세팅하기
___

<a name="wp-section05"></a>
### 도커에 설치하기
___

<a name="wp-section06"></a>
### 유용한 플러그인들
___
<!-- lazy loading, cdn, 다중언어
css, js 추가하는 프로그램
도메인 설정: https://support.google.com/a/answer/33353?hl=ko&ref_topic=4445319
g suit 인증 : https://wpforms.com/how-to-securely-send-wordpress-emails-using-gmail-smtp/
-->


