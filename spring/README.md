### 1. Spring 정의
  - 자바 엔터프라이즈 개발을 편리하게 해주는 오픈 소스 경량급 어플리케이션 프레임워크
  - POJO (Plain Old Java Object) 기반의 엔터프라이즈 어플리케이션 개발을 쉽고 편하게 할 수 있도록 한다.
  - 개발하는데 필요한 하부구조를 포괄적으로 제공하므로 개발에 집중할 수 있다.
  - 전자 정부 표준 프레임워크의 기반 기술
  
### 2. 컨테이너란? (Container)
  - 컨테이너는 보통 인스턴스의 라이프사이클을 관리하며 생성된 인스턴스에게 추가 기능을 제공하는 것  
  작성한 코드의 처리과정을 위임받은 독립적인 존재
  - 컨테이너는 개발자가 작성한 코드를 참조한 뒤 객체의 생성과 소멸을 컨트롤한다.
  
### 3. IoC란? (Inversion Of Control)
  - 모든 객체에 대한 생성부터 라이프사이클 관리까지의 제어권이 바뀐 것을 의미
  - Servlet에 제어를 위임하여 Bean을 관리

### 4. Framework와 Library의 차이
  - IOC의 개념이 적용되었는지 유무
  - 라이브러리는 코드로 어플리케이션의 흐름을 직접 제어한다.   
    (필요한 기능이 있을 때 능동적으로 라이브러리를 사용)
  - 프레임워크에서는 반대로 코드가 프레임워크에 의해 사용된다.  
    (프레임워크가 흐름을 주도하고 개발자가 만든 코드를 어플리케이션에서 사용하도록 한다.)
    
### 5. DI란? (Dependency Injection)
  - Spring Framework에서 지원하는 IoC의 형태
  - Framework에 의해 동적으로 주입되므로 여러 객체간의 결합이 줄어든다.
  - 즉, 객체를 직접 생성하는 것이 아닌 외부에서 생성한 후 주입시키는 방식
  - 컨테이너가 Bean 객체를 생성하고 종속성 주입을 수행
  - 개발자가 설정만 (xml, annotaion 등) 하면 컨테이너가 알아서 처리한다.
  - 생성자를 통한 전달 (Constructor Injection)
  - 메소드를 통한 전달 (Setter Injection)
  - 멤버 변수를 통한 전달 (Field Injection)
  - 장점  
        1. 종속성이 감소  
        2. 재사용성이 증가  
        3. 일부 인터페이스의 다른 구현이 필요할 경우 코드 변경할 필요 없이  
        &nbsp;&nbsp;&nbsp;&nbsp;해당 구현을 사용하도록 컴포넌트를 구성할 수 있다.  
        4. 코드가 읽기 쉬워진다

### 6. AOP란? (Aspect Oriented Programming)
  - 관점 지향 프로그래밍의 약자
  - 기존의 OOP에서 `로그`, `트랜잭션`, `자원해제`, `성능테스트` 등 처럼  
  공통적으로 반복되는 중복코드를 해결하기 위해 사용
  - 비지니스 로직에 집중하고 실행 시 비지니스 로직 앞, 뒤 혹은 원하는 지점에 공통 관심사를 수행할 수 있도록함
 
 ### 7. MVC 패턴에 대한 설명
  - MVC란?  
    사용자 인터페이스를 효과적으로 데이터 모형과 관련시키기 위한 방법론 또는 설계 방식
  - MVC 패턴의 목적은 코드의 재사용성과 개발에 소용되는 시간을 단축시키기 위함
  - MVC 구성요소
    - Model : 논리적 데이터 기반 구조를 표현
    - View : Model의 데이터를 기반으로 사용자 인터페이스 내의 구성요소들을 표현 (사용자들에게 보여지는 화면)
    - Controller : Model과 View를 연결하고 있는 클래스, Model과 View의 사이에서 정보 교환하는 역할
    
### 8. Spring MVC 처리 순서
  1. URL Request
  2. DispatcherServlet
  3. HandlerMapping
  4. Controller
  5. ModelAndView
  6. DispatcherServlet
  7. ViewResolver
  8. View
  9. Response
  
### 9. Filter와 Interceptor 차이
  - 실행 시점의 차이
  - Filter : DispatcherServlet 앞에서 처리, WebApplication에 등록
  - Interceptor : DispatcherServlet과 Handler 사이, Spring Context에 등록
  - Application 전역으로 처리해야할 것은 Filter로 상세한 처리 (인증, 권한 등)은 Interceptor에서 처리
  
### 10. Spring legacy와 Spring Boot의 차이
  - Spring Boot의 경우 웹 컨테이너 (Tomcat)을 내장하고 있고 최소한의 설정으로 쉽게 Spring Application을 만들기 위한 목적으로 설계된 Spring 프로젝트 
  - Dependency 문제가 간편하게 해결되고 빠르게 어플리케이션을 만들수 있는 장점이 있음.  
    ('starter-pack'이라는 dependeny를 통해 설정할 수 있음)
  - Spring Boot는 기본으로 Embeded Tomcat을 사용하게 되어 있다.