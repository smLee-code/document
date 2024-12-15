# Springboot Basic

## 개발 환경

- SpringBoot 3.4.0 (3.0 이상)
- JDK 23 (17 이상)
- Gradle - Groovy

### IntelliJ Settings

- Settings - Build, Execution, Deployment - Build Tools - Gradle

  Build and run using 및 Run tests using 옵션 : Gradle -> IntelliJ IDEA 변경
  (속도 이슈)

---

## 라이브러리

- Gradle은 의존관계가 있는 라이브러리를 함께 다운로드 한다.

ex)
- 
-

--- 

## View 환경설정

- resources/static/index.html 파일 -> 도메인 메인 화면으로 기능 (정적 페이지)

### 필요한 정보 찾는 방법 (메뉴얼 검색)

ex) Welcome Page에 관한 정보

1. spring.io 웹페이지
2. Projects - Springboot - Learn 
3. 해당 버전의 Reference Doc. 
4. 좌측 search 에서 'Welcome Page' 검색
5. 설명을 자세히 읽어본다.

### Thymeleaf 템플릿 엔진

-

---

## 빌드 및 실행

1. 터미널에서 프로젝트 폴더로 이동
2. ./gradlew build 입력 (빌드)
3. cd build/libs 입력 (build/libs 폴더로 이동)
4. java -jar 프로젝트명-0.0.1-SNAPSHOT.jar 입력 (실행 확인)
5. ./gradlew clean (빌드 삭제) / ./gradlew clean build (빌드 삭제후 다시 빌드)


---

## 스프링 웹 개발 기초

### 웹 개발 방식

1. 정적 컨텐츠
  
   - 서버에서 추가 작업 없이 파일을 웹 브라우저에 그대로 내려주는 것

2. MVC 및 템플릿 엔진

   - 서버에서 프로그래밍 작업을 하여 html을 동적으로 바꿔서 내려주는 것

3. API

   - 안드로이드, 아이폰 클라이언트 개발시 서버에서 json 데이터 포맷으로 내려주는 것
   - html 자체가 아니라 html을 그리기 위한 데이터만 주고 받는다. (주로 서버간에 사용)

### 웹 브라우저 작동 방식

  localhost:8080/ABC123 이라는 주소로 접근할 경우

1. 내장된 톰캣 서버로 ABC123 전달

2. ABC123 관련 컨트롤러 탐색 (톰캣이 알아서 처리)

3. 관련 컨트롤러가 없다면 static 폴더의 ABC123.html 파일을 찾아서 화면에 띄운다. (정적 컨텐츠)

4. 관련 컨트롤러가 있다면 해당 메소드를 실행한다. viewResolver에게 return에 해당하는 html 파일을 찾도록 한다. 그 파일을 실행한다. (MVC 방식)

5. 만약 그 컨트롤러에 @ResponseBody 어노테이션이 붙어있다면, httpMessageConverter가 동작한다. (API 방식)

    - return이 문자일 경우 StringConverter (StringHttpMessageConverter) 가 동작하여 바로 html에 바로 넣어서 띄운다.
    - return이 객체일 경우 JsonConverter (MappingJackson2HttpMessageConverter) 가 동작하여 json 형식으로 바꿔서 띄운다.

### MVC

- Model, View, Controller
- Model1 방식 (이전) : View에 모든걸 다 하는 방식
- MVC 방식 (현재) : Model, View, Controller를 분리하는 방식 (각각의 역할 별로 분리) - 일종의 웹 개발용 디자인 패턴이다.

### API

