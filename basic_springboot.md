## 스프링부트
1. Framework - 틀 안에서 동작한다

2. 오픈 소스 - 소스코드가 공개되어 있다. 내부 소스를 뜯어 고칠 수 있는 것

3. IoC 컨테이너 
\- Inversion Of Control(제어의 역전) : 주도권이 스프링에게 있다!
- class(설계도), object(실체화가 가능한 것), instance(실체화된 것)
- 스프링이 object를 스캔해서 heap 메모리 공간에 알아서 만들어줌.

4. DI 지원 
- Dependency Injection(의존성 주임)
- 스프링이 관리하는 객체를 원하는 모든 클래스, 메소드에서 가져와서 사용할 수 있음.
- 싱글톤

5. 엄청나게 많은 필터를 가짐
- 스프링 자체가 기능을 가지고 있음. 사용자가 설정하거나 직접 만들 수도 있음
- 톰케의 필터 - 필터(web.xml 파일), 스프링 컨테이너 필터 - 인터센터(AOP, 권한 체크)

6. 엄청나게 많은 어노테이션을 가짐
- 어노테이션: 컴파일러가 무시하지않는 주석, 컴파일러 할때 힌트를 주는 기능
- 어노테이션을 통해 객체 생성을 함
- @Compont(클래스 메모리에 로딩),@Autowired(코딩된 객체 해당 변수에 집어 넣어), @Bean, @Controller
- 리플래셕: 분석하는 기법, run 타임 시 분석

7. MessageConverter를 가짐. 현재 기본값은 json
- 자바 object를 -> json으로 변경하여 전송 -> Python object로 변경
8. BufferedReader와 BufferedWriter를 쉽게 사용할 수 있음
9. 계속해서 발전하는 중임.