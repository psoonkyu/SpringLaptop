# SpringLaptop
노트북 스프링 프로젝트 백업

Elipse 설정(STS)

general - server - server environment - tomcat 등록(기존 서버 제거)

general - editors - texteditors - spelling - encoding - other UTF-8

general - web browser - use external web browser - chorome

Json - Json files - encoding - UTF-8

web - css files - UTF-8

web - HTML files - UTF-8

web - jsp files - UTF-8

XML - XML files - UTF-8


Maven : 원격저장소에 있는 필요한 라이브러리 파일들을 자동으로 받아주는 기능
*원격저장소(MavenRepository)

필요한 파일의 등록은 Maven 의 설정파일인 pox.xml 에 <dependency>를 등록해서 받아옴

maven.apache.org
다운받아서 압축풂

tomcat server 더블클릭 - serve modules without publishing 체크

port 번호 9090 으로 되어있는지 확인 아니면 tomcat conf 에서 8080 에서 9090 으로 변경


X 누르고 Save


메이븐이 jar 파일을 받아오다가 손상된경우는 제대로 다시 받아올수 없기때문에 repagitory 가서 받은다음 지워줘야한다. 그래서 localrepository 를 편한 폴더로 지정함

maven폴더 conf - settings.xml 편집(VS CODE)

52번째줄  <localRepository>/path/to/local/repo</localRepository> 에 주석 해제
<localRepository>c:\dev\apache-maven-3.6.0\repository</localRepository> 로변경

STS 에서
windows - preperence - maven - userSettings - usersetting - browse
C:\work\apache-maven-36\conf\settings.xml 지정
그러면 아래 Local Repository 가 변경됨
apply 저장

git 설정
window - preferences - team - Ignored resources
Add pattern
*/target/* 등록 OK
apply 저장

----------------------------
Spring legacy project

Spring MVC project

package 에 3단계로 써줌 ex) com.kh.spring

finish 누르면 다운받느라 걸림

폴더설명
프로젝트 아이콘
M maven
S pring

src/main/java - 기존 src 역활, 기존 class(servlet) 위치
HomeController.java 스프링이 자동으로 생성하는 관리자

src/main/resource - 자바관련된 설정파일 , mapper config Mybatis 파일 log4j.xml 로그찍는넘

src/test/java - Junit 단일 테스트 가능, 실제작업과 관련없음
src/test/resource - 

JRE
MAven dependencies - 메이븐이 받아온 jar 파일

src - main - webapp (올리는 위치) - resources (CSS 나 이미지 폴더)
                                  - WEB-INF (외부에서 접근이 불가능한 경로)
					    - views 뷰 넣는 위치(home.jsp 있음)
                                            - spring 스프링에 관련된 환경설정 폴더 						servlet-context.xml 프로그램별 설정 root-context.xml 공용설정

target - web\WEB-INF\CLASSES 역활

--------------------
실행해보면 500 에러뜸 JSTL 로드불량
그래서 WEB-INF\lib 폴더 만들어서 라이브러리 넣어줌

pom.xml
<java-version>1.8</java-version> 로변경
<org.springframework-version>5.0.6.RELEASE</org.springframework-version>

141 줄
<source>1.8</source>
<target>1.8</target>

프로젝트에서 properites - java build path - Libraries - JRE system Library 를 두번눌러 JDK 1.8로 변경

프로젝트밑
servers 
web.xml클릭해서
17줄 복사해서
프로젝트의 web.xml 의 첫번째에 덮어쓰기

pom.xml
https://mvnrepository.com/ 검색해서 Mybatis 검색 추가, Mybatis-spring, spring-jdbc, commons-dbcp, ojdbc 검색해서 추가

<!-- 데이터베이스 연결관련 -->
		<!-- https://mvnrepository.com/artifact/org.mybatis/mybatis -->
		<dependency>
    	<groupId>org.mybatis</groupId>
    	<artifactId>mybatis</artifactId>
    	<version>3.4.6</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.mybatis/mybatis-spring -->
		<dependency>
    	<groupId>org.mybatis</groupId>
    	<artifactId>mybatis-spring</artifactId>
    	<version>1.3.2</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.springframework/spring-jdbc -->
		<dependency>
    	<groupId>org.springframework</groupId>
    	<artifactId>spring-jdbc</artifactId>
    	<version>${org.springframework-version}</version>
		</dependency>
	<!-- https://mvnrepository.com/artifact/commons-dbcp/commons-dbcp -->
		<dependency>
	<groupId>commons-dbcp</groupId>
    	<artifactId>commons-dbcp</artifactId>
    	<version>1.4</version>
	</dependency>
	<!-- https://mvnrepository.com/artifact/com.oracle/ojdbc -->
	<!-- https://mvnrepository.com/artifact/com.oracle/ojdbc -->
	<dependency>
	<groupId>com.oracle</groupId>
	<artifactId>ojdbc</artifactId>
	<version>6</version>
	</dependency>


window - perspective - customize perspective - shorcuts - web - CSS,JSP,HTML 추가

JSP template 추가

--------------
<%@ page language="java" contentType="text/html; charset=${encoding}"
    pageEncoding="${encoding}"%>
<!DOCTYPE html>
<html>
<head>
<meta charset=${encoding}">
<title>Insert title here</title>
<script scr="http://code.jquery.com/jquery-3.3.1.min.js"></script>
</head>
<body>
${cursor}
</body>
</html>
--------------

