# 01_Start_Django

### 1. Intro

- framework
  
  - 서비스 개발에 필요한 기능들을 미리 구현해서 모아 놓은 것.
  
  - 소프트웨어 생산성과 품질을 높임.

- www(World WIde Web)
  
  - 전 세계에 퍼져 있는 거미줄 같은 연결망

- Client - Server
  
  - 오늘날 대부분 웹서비스는 클라이언트-서버 구조 기반
    
    <img title="" src="01_Start_Django_assets/2022-10-10-16-59-19-image.png" alt="" width="328">
  
  - Client - 서비스를 요청하는 주체. (웹사용자의 인터넷 연결장치, 웹 브라우저)
    Server - 요청에 대해 서비스를 응답하는 주체. (웹페이지, 사이트, 앱 등을 저정하는 컴퓨터)
  
  -  어떠한 자원(resource)를 요청(request)하는 쪽을 Client, 자원을 제공하는 쪽을 서버(Server)라고 함.

- Web browser
  
  - 웹페이지는 HTML문서 파일 하나. 즉, 웹페이지 코드를 받으면 우리가 보는 화면처럼 바꿔주는 것이 바로 웹 브라우저.
  
  - Static web page 
    
    - 모든 사용자에게 동일한 페이지 전달
  
  - Dynamic web page 
    
    - 사용자의 요청에 따라 웹페이지에 추가적인 수정 후 클라이언트에게 전달되는 웹페이지
    
    - 웹페이지의 내용을 바꿔주는 주체 == server
      서버에서 동작하고 있는 프로그램이 웹페이지를 변경. 이렇게 사용자의 요청을 받아 적절한 응답을 만들어주는 프로그램을 쉽게 만들도록 도와주는 프레임워크가 Django.

---

### 2. Design_Pattern

- 각기 다른 기능의 다양한 응용 소프트웨어 개발시 공통적인 설계 문제, 해결책 사이에도 공통점이 있음, 이러한 유사점을 패턴
  
  자주 사용되는 소프트웨어의 구조를 건축 공법처럼 일반적인 구조화를 해둔것. (Client - Server 구조도 소프트웨어 디자인 패턴 중 하나.)

<br>

- MTV 패턴
  
  - Model - Template - View
  
  - Model
    
    - 데이터와 관련된 로직 관리. 응용프로그램의 데이터 구조 정의, 데이터베이스 기록을 관리.
  
  - Template
    
    - 화면 상 사용자 인터페이스 구조와 레이아웃을 정의.
  
  - View
    
    - Model & Template과 관련된 로직 처리 후 응답 반환. (client 요청에 대한 처리를 분기하는 역할.)
    
    - ex) 데이터 필요시 model에 접근해 데이터를 가져오고, 가져온 데이터를 template로 보내 화면 구성 후 응답으로 만들어 클랑이언트에게 반환.
      
      <img src="01_Start_Django_assets/2022-10-10-17-34-09-image.png" title="" alt="" width="295">
  
  - MVC 디자인 패턴을 기반으로 조금 변형된 패턴. (Model - View - Controller)
    
    <img src="01_Start_Django_assets/2022-10-10-18-27-50-image.png" title="" alt="" width="244">

---

### 3. Django_start

- 포로젝트 생성
  
  ```git
  # django 3.2버전 설치
  $ pip install django==3.2.13
  # 패키지 목록생성
  $ pip freeze > requirements.txt
  # 프로젝트 생성(마지막 dot 중요, 붙이지 않을 경우 프로젝트 디렉토리 새로 생성)
  $ django-admin startproject <프로젝트이름> .
  # 서버실행
  $ python manage.py runserver
  ```

- 프로젝트 구조
  
  <img src="01_Start_Django_assets/2022-10-10-18-55-08-image.png" title="" alt="" width="121">
  
  - __init__.py : python에게 이 디렉토리를 하나의 python 패키지로 다루도록 지시. (추가코드 x)
  
  - asgi.py : Asychronous Server Gateway Interface, Django 애플리케이션 비동기식 웹서와 연결 및 소통을 도움. (추후 배포시 사용)
  
  - settings.py : Django 프로젝트 설정을 관리.
  
  - urls.py : 사이트 url과 적절한 views의 연결 지정.
  
  - wsgi.py : Web Server Gateway Interface, Django애플리케이션이 웹서버와 연결 및 소통 도움. (추후 배포시 사용)
  
  - manage.py : Django프로젝트와 다양한 상호작용하는 커맨드라인 유틸리티
    
    ```git
    # manage.py Usage
    $ python manage.py <command> [opitons]
    ```

<br>

- 애플리케이션(앱) 생성
  
  ```git
  # appname은 복수형작성 권장.
  $ python manage.py startapp <appname>
  ```

- 애플리케이션 구조
  
  <img src="01_Start_Django_assets/2022-10-10-19-06-58-image.png" title="" alt="" width="133">
  
  - admin.py :  


