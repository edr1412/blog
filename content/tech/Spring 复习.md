---
title: "Spring 复习"
gitinfo: true
share: true
comments: true
slug: "Srping_renew"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "复习资料... 博客园是加密的 不过这边就算了吧"
tags: ["Spring", "Java"]
date: 2020-07-07T14:07:04+08:00
---



1. John is working in an IT firm and he created a web application for online shopping. He wants to use spring security to create the login form for this application. You are an expert in spring security so help John to create the login page.

   When a user enters the login credential and clicks the login button, it will authenticate and authorized the user on the basis of the user's role and display its accessible page. Which one of the following code snippets will you use to implement the desired functionality in the Spring security configuration class?

   

   @Spring security

   注意 .and 的连接

   

   ```java
   @Override
   
    protected void configure(HttpSecurity http) throws Exception {
   
    http.authorizeRequests()
   
     .antMatchers("/").hasRole("EMPLOYEE")
   
     .antMatchers("/leaders/**").hasRole("MANAGER")
   
     .antMatchers("/systems/**").hasRole("ADMIN")
   
     .and()
   
     .formLogin()
   
     .loginPage("/showMyLoginPage")
   
     .loginProcessingUrl("/authenticateTheUser")
   
     .permitAll()
   
     .and()
   
     .logout().permitAll()
   
     .and()
   
     .exceptionHandling().accessDeniedPage("/access-denied");
   
    }
   ```

   

 



2. You are creating a web application for booking hotel rooms. You are using spring to create this application using the default login page feature. This application required authentication during login. When the user login with a valid username “marry” and password “marry123” role, it will validate the user from in-memory data and will send him on the home page.

   Which one of the following code snippets will you use to implement the desired functionality in the spring security configuration class?

   

   @Spring security

   调用的是 auth 的 ==inMemoryAuthentication== 方法

   ```java
   **@Autowired**
   
    **PasswordEncoder passwordEncoder;**
   
    
   
    **@Override**
   
    **protected void configure(AuthenticationManagerBuilder auth) throws Exception {**
   
    
   
    **auth.inMemoryAuthentication()**
   
    **.withUser("marry").password(passwordEncoder.encode("marry123")).roles("user");**
   
    
   
    **}**
   ```

   



3. You are a software engineer working in a software company. A client meeting held with you for the development of a brand promotional application. He wants when a user will log in with his credential he can see his role on his profile page. You have used the spring security framework to implement this concept. 

   Which one of the following code snippets will you use to implement the desired functionality in the spring view page?

   

   @Spring security

   搜索关键词 <security: 首先是 authentication (认证) 其次对应变量名   ~~authorization (授权)~~

   ```xml
    **User: <security:authentication property="principal.username" />**
    **Role(s): <security:authentication property="principal.authorities" />**
   ```

   

4. Which of the following class used to initialize spring security in spring MVC application?

   

   @配置类

   

   ```java
   AbstractSecurityWebApplicationInitializer
   ```



5. which one of the following Allows for easily building in memory or JDBC based authentication?

   

   @Spring security

   ```java
   AuthenticationManagerBuilder
   ```



6. Which one of the following class provides a set of methods that are used to enable specific web security configuration?

   

   @Spring security

   ```java
   WebSecurityConfigurerAdapter
   ```

   

7. CSRF stands for:

   

   @Spring security

   ```java
   Cross Site Request forgery
   ```

   



8. you are a working as a software developer and you had developed a web application for a hotel room booking. When user login through the application he got following error page:

   HTTP Status 403 – Forbidden

   _____________________________________

   Type Status Report

   Message Forbidden

   Description The server understood the request but refuses to authorize it.

   _____________________________________

   Apache Tomcat/9.0.31

   Which of the following approach will you use to remove this error?

   

   @Spring security

   authorize  被拒绝

   ```html
   <input type="hidden" name="${_csrf.parameterName}" value="${_csrf.token}" />
   ```



9. john what to apply spring security in his application, Which class spring will register to use the springSecurityFilterChain before any other registered Filter?

   

   @Spring security

   关键词 springSecurityFilterChain 

   ```java
   DelegatingFilterProxy
   ```

   

10. John wants to apply spring security in his web application but does not want in-memory data validation, he wants to store user credentials in the MySQL database. what code snippet will he use to get the desired result?

    

    @Spring security

    jdbcAuthentication

    ```java
    @Autowired
    
     private DataSource securityDataSource;
    
     @Override
    
     protected void configure(AuthenticationManagerBuilder auth) throws Exception {
    
     auth.jdbcAuthentication().dataSource(securityDataSource);
    
     }
    ```

    

11. What is JSON data binding?

    

    @json

    ```
    Serialization/deserialization
    
    Marshalling/Unmarshalling
    
    conversion of JSON data to java POJO and vice versa
    ```

    

12. John is a software developer in FIS technology and he has used REST API in his web Application, now he wants to access a single student object in result on the basis of given ID What code snippet will he use to get the desired result?

    

    @REST API

    获取 单个 数据

    ```java
    @GetMapping("/student/{studentId}")
    
    public StudentBo getStudentById(@PathVariable int studentId)
    
    ```

    

13. REST API will only accept JSON requests and respond back with JSON responses for that ________________ library is used?

    

    @REST API

    只使用了 Jackson

    ```
    Jackson library
    ```

    

14. The most important class in REST web service is _______________ which acts as the interface for client/server communication.

    

    @REST API

    Controller 是 接口

    ```
    Controller
    ```

    

15. For implementing REST web Service john had used @RestController annotation. Which one of the following is true about @RestController?

    

    @REST API

    ```
    @RestController annotation marks the class as a Resource
    
    it defines implicitly both @Controller and @ResponseBody MVC annotations
    ```

    

16. Which one of the following annotation is used to load application.properties file in the REST web application?

    

    @REST API

    ```
    @PropertySource
    ```

    

17. John is working in Software Company as a developer, he has developed a web application following client-server architecture and he wants to implement Spring REST API on client application for getting the list of the students from the database. Which of the following code snippet he will use to get the desired result?

    

    @REST API

    获取 列表 数据

    ```java
    @Override
    
    public List<Student> getStudent() {
    
    
     ResponseEntity<List<Student>> responseEntity = restTemplate.exchange(studentRestUrl, HttpMethod.GET, null,new ParameterizedTypeReference<List<Student>>() {});
    
    List<Student> students = responseEntity.getBody();
    
    return students;
    
    }
    ```

    



18. Mr. Ben working in an IT firm developed a web application following the client-server architecture of the spring framework. He had configured REST client but on execution did not get the correct result. You are a spring Developer so which of the code snippet will you suggest to MR. Ben to get the desired result?

    

    @REST API @配置类

    ```java
    @ComponentScan(basePackages = {"com.niit"})
    
    @PropertySource("classpath:application.properties")
    
    @Configuration
    
    @EnableWebMvc
    
    public class WebConfig implements WebMvcConfigurer {
    
     @Bean
    
     public RestTemplate restTemplate() {
    
      return new RestTemplate();
    
     }
    
    }
    ```

    



19. Which one of the following annotations are used on a controller to handle all kind of exception in Spring web application?

    

    @Controller

    全局异常处理

    ```
    @ControllerAdvice
    ```



20. John has developed a web application. But when he was testing his application he got the ugly result as an output. He wants to return a meaningful result on exception raised. He wants to use @ResponseStatus annotation on custom exception class handling class to return the meaningful result. which one of the following code snippets satisfied his need?

    

@ResponseStatus 

```java
org.springframework.http.HttpStatus;

import org.springframework.web.bind.annotation.ResponseStatus;

 

@ResponseStatus(value = HttpStatus.NOT_FOUND, reason = "No such Keyword")

public class KeywordNotFoundException extends RuntimeException {

public KeywordNotFoundException(String key){

super(key+" not available");
```



21. In how many ways exception can be handled in spring application?

    

    @异常处理 @exception 

    ```
    4
    ```

    

22. In Spring MVC application on which layer @ResponseStatus annotation is applied? 

    

    @ResponseStatus

    ```
    Custome exception classs
    Controller’s method
    ```



23. John has developed a web application but for unexpected failure he wants to handle Exception in his spring web application using ExceptionResolver class. Which one of the following code snippets John will use to configure Exception bean in spring configuration file?

    

    @异常处理 @exception @ExceptionResolver 

    ```java
    @Bean
    
    public SimpleMappingExceptionResolver resolveException() {
    
     SimpleMappingExceptionResolver resolver= new SimpleMappingExceptionResolver();
    
     Properties erpProperties= new Properties();
    
     erpProperties.setProperty("DataLostException", "globalError");
    
     erpProperties.setProperty("BadDataException", "error");
    
     erpProperties.setProperty("NullPointerException", "globalError");
    
     resolver.setExceptionMappings(erpProperties);
    
     resolver.setDefaultErrorView("404-page");
    
     resolver.setExceptionAttribute("exc");
    
     return resolver;
    
    } 
    ```

    



24. Marry has developed web application and also applied spring exception handling using HandlerMappingExceptionResolver. She wants to map error type with the view name. Which of the following HandlerMappingExceptionResolver class she will use to map the exception type with the view name?

    

    @HandlerMappingExceptionResolver

    ```
    SimpleMappingExceptionResolver
    ```

    

25. John working in a software company as a Spring developer. He developed an web application for ticket booking. Since he is new in spring framework he does not know how to handle global exception using spring exception handling API. You are an expert in spring framework so what code snippet you will suggest john to handle global exception? 

26. 

    @异常 @全局异常

    ```java
    org.springframework.web.bind.annotation.ControllerAdvice
    
    org.springframework.web.bind.annotation.ExceptionHandler
    
     
    
    @ControllerAdvice
    
    public class GlobalExceptionHandlerController {
    
     @ExceptionHandler(IOException.class)
    
     public ModelAndView handleMyException(Exception ex) {
    
    
     ModelAndView model= new ModelAndView();
    
     model.addObject("exc", ex);
    
     model.setViewName("globalError");
    
     return model;
     
     }
    
    
     @ExceptionHandler(RecordNotFoundException.class)
    
     public String handleNotFound() {
    
     return"404-page";
    
     }
    ```

    



26. Which one of the following package can be used to implement global exception controller in spring web application?

    

    @异常 @ControllerAdvice

    ```
    org.springframework.web.bind.annotation.ControllerAdvice
    ```

    

27. The Spring framework promotes the concept of loose coupling through _______________.

    

    @解耦

    ```
    DI
    ```

    

28. __________ is used to load the bean configuration file located at the specified class path.

    

    @配置

    ```
    ClassPathXmlApplicationContext
    ```

    

29. Daniel has to create a Web application in such a way that there is clear separation between the application model and the application logic from the application's UI. Which module of the Spring framework should he use to enable this segregation?

    

    @模式 @逻辑与UI

    ```
    MVC
    ```



30. You have implemented a type of autowiring in your application, such that the Spring framework attempts to wire the bean by first using constructor, and then byType, if there is a default no-args constructor. Which type of autowiring is this?

    

    @Autowire

    ```
    byType
    ```

    

31. The Spring framework is a popular non-standard open source framework developed by ______________.

    

    @Spring

    ```
    Interface21 Inc
    ```

    



32. When _________ property is set to byName, Spring will attempt to find a bean whose name matches the name of the property being wired.

    

    @Autowire

    ```
    Autowire
    ```

    

33. You have created a Web application, where you are required to apply enterprise services, such as transaction management, security, logging, and messaging services with the help of java configuration files. Which module of the Spring framework should you use to do this? 

    > 您已经创建了一个Web应用程序，您需要在java配置文件的帮助下应用企业服务，如事务管理、安全、日志和消息服务。您应该使用Spring框架中的哪个模块来实现这一点？

    

    @模式

    ```
    AOP
    ```

    

34. You have declared a bean named ball in the Spring configuration file. Now, you have to pass this bean as a reference to another bean. Which attribute of the <property> tag will you use to accomplish this task?

    

    @property

    ```
    Ref
    ```

    

35. State whether the given statements as true or false :

    [A] Spring is a layered architecture framework that allows you to create tightly coupled business logic components

    [B] In traditional J2EE approach, any change in the business logic is likely to impact the entire application code.

    

    ```
    A is false, B is true
    ```

    

36. Consider the following statements:

    Statement A: Spring aims to minimize the dependence of the application code on its framework.

    Statement B: Spring applications are not required to perform API lookup.

    

    ```
    Both A and B is true
    ```

 

37. Which of the following features of Spring framework allows you to associate business layer objects with each other, using XML configuration files?

    

    @XML

    ```
    Pluggability
    ```

    

38. Which of the following statements regarding Spring framework is not true?

    ```
     True:
     
     The Spring MVC framework provides a clear seperation between the controllers, models and views.
     // Spring MVC框架在控制器、模型和视图之间提供了一个清晰的分界。
     The Spring MVC supports several view technologies such as JSP, Velocity , Tiles and JSF.
     // Spring MVC支持多种视图技术，如JSP、Velocity、Tiles和JSF。
     The Spring MVC Web applications are easier to test than the Struts MVC Web applications.
     //与Struts MVC Web应用相比，Spring MVC Web应用更容易测试
     
     False:
     In Spring-enabled Web applications, the validation is implemented with the help of the validate() method of the ActionForm class
     //在支持Spring的Web应用程序中，验证是在ActionForm类的validate()方法的帮助下实现的。
    ```

    



39. Which of the following layers of the Spring Architecture provides an exception hierarchy for managing database connections and handling exceptions and complicated error messages?

    @Database 

    ```
    DAO
    ```



40. Which of the following values of the scope attribute of the bean element within the bean configuration file, provides a single instance of a bean with a particular name and places it in the factory?

    

    @scope

    ```
    Prototype
    ```

    

41. Dorothy is working in a spring application where she has stored the Spring-Config-xml file within the Sports folder located at the class path of the application. Now she wishes to create a BeanFactory object with the given configuration file. Which of the following code do you think would be correct in this case?

    

    @配置

    ```
    Resource res = new ClassPathResource(Sports/Spring-Config.xml);
    
    BeanFactory factory = new XMLBeanFactory(res);
    ```

    

42. In Which of the following stages of the lifecycle of a bean inside a Bean Factory container, we perform certain types of initialization tasks before the beans are ready to be used. These include opening a file, opening a network or database connection, and allocating memory.

    

    @Bean 

    ```
    Initialize Beans
    ```

    

43. Which of the following implementation of the application context container is used to load the bean configuration file from the location specified by the contextConfigLocation context parameter n the web.xml file?

    

    @配置

    ```
    XmlWebApplicationContext
    ```

    

44. State whether the following statements are true or false.

    Statement A: In a Spring-enabled application, the objects are not responsible for searching or creating other dependent objects.

    Statement B: The Spring container manager creation that manages creation of the objects, their life cycle and collaboration with other objects.

    ```
    Both A and B is true
    ```

    



45. Which of the following MVC component accepts a user request and pass it to a proper model for process, and present a proper view to the user based on the result?

    ```
    Controller
    ```

    

46. Please select the right order of the life cycle of a Spring MVC request

    1) Request goes through the front-end controller, i.e, DispatcherServlet

    2) Render view pages, and deliver model data, and render response in the browser.

    3) Request goes through the service layer, and real business logic processing the request is implemented.

    4) Revert a request to a proper controller based on the mapping handler.

    5) The controller send the request to the DispatcherServlet with a view name and data to be presented on the view.

    

    @排序

    ```
    1 > 4 > 3 > 5 > 2
    ```

    

47. Which implementation of the Resource Interface can be used for defining a resource, retrieved from the specified class path?

    

    @ClassPathResource

    ```
    org.springframework.core.io.ClassPathResource
    ```

    

48. Please select the right order of the life cycle of a Spring MVC request

    1) Request goes through the front-end controller, i.e, DispatcherServlet

    2) Render view pages, and deliver model data, and render response in the browser.

    3) Request goes through the service layer, and real business logic processing the request is implemented.

    4) Revert a request to a proper controller based on the mapping handler.

    5) The controller send the request to the DispatcherServlet with a view name and data to be presented on the view.

    

    @排序

    ```
    4 > 1 > 5 > 3 > 2
    ```

    

49. Which of the following code snippet can be placed in front of a method to map a method to a post request?

    此处直接注意 RequestMethod.POST

    ```
    @RequestMapping(value="/addProduct" , method=RequestMethod.POST)
    ```

    

50. Spring provides rich support for ______ that separates the application logic from the system-level services, such as transaction management, logging, and security.

    

    @log

    ```
    AOP
    ```

    

51. You can wire the bean properties in a Spring-enabled application by declaring a _________ element for the bean in the configuration file within the <bean> tag.

    

    @Bean

    ```xml
    <property>
    ```



52. You need to create a Spring-enabled web application for ToyZone Inc. In addition, you need to use Hibernate to provide data persistence. Which module of the Spring framework will you use to integrate Spring with Hibernate?

    

    @Hibernate 

    ```
    ORM
    ```

    

53. Which of the following is used to map a user request to a proper controller object directly and is one of the simplest HandlerMapping ?

    

    @HandlerMapping 

    ```
    SimpleUrlHandlerMapping
    ```

    

54. Which of the following code snippet maps the request “/addStudent.htm” to a controller named AddController under the com.niit.controller package?

    

    @map

    ```xml
    <bean id="handlerMapping" class="org.springframework.web.servlet.handler.BeanNameUrlHandlerMappin</bean>
    
    <bean name="/addStudent.htm" class="com.niit.controller.AddController"></bean>
    ```

    

55. Which of the following options helps you to bind a bean property to a form component?

    

    @bind 

    ```xml
    <spring:bind>
    ```

    



56. Which of the following is not an advantage of Spring MVC Framework?

    ```
     True:
     
     Reusable code
    
     Easy to test
    
     Simple and powerful tag library
     
     False:
     
     Heavy-weight development environment
     
    ```

    

57. Which of the following component in Spring MVC enables the DispatcherServlet to send request to a proper controller?

    

    @Controller

    ```
    Mapping Handler
    ```

    

58. Which of the following class represents the DispatcherServlet class?

    

    @DispatcherServlet

    ```
    org.springframework.web.servlet.DispatcherServlet
    ```

    

59. Victor has created a spring application where she wants to inject the dependency of the application objects using setter method. She has written the following code:

    

    @setter code

    ```java
    class finance{
    
     ManagementStudent managementStudent;
    
     public ManagementStudent getManagementStudent() {
    
      return managementStudent;
    
     }
    
     
    
     @Autowired
    
     public void setManagementStudent(ManagementStudent managementStudent) {
    
      this.managementStudent = managementStudent;
    
     }
    
     
    
    class HumanResource{
    
     ManagementStudent managementStudent;
    
     public ManagementStudent getManagementStudent() {
    
      return managementStudent;
    
     }
    
    
     @Autowired
    
     public void setManagementStudent(ManagementStudent managementStudent) {
    
      this.managementStudent = managementStudent;
    
     }
    ```

    

60. Issac wants to implement constructor injection for the property “type” of the Games class defined in the Gaming Package as given in the following code :

    ```java
    package Gaming;
    
     public class Games{
    
     String type;
    
     public Games(String type){
     
     	this.type = type;
     }
    }
    ```

    Which of the following code should Issac use in the given scenario ?

    

    @type code

    ```
    <bean id="racing" class="Gaming.Games">
    
     <constructor-arg value="Racing">
    
    </bean>
    ```

    

 

61. In which of the following autowiring technique, Spring will find a bean by the property name of the property being wired?

    ```
    byname
    ```

    

62. Consider the following statements:

    Statement A:  Autowiring through Autodetect is a type of autowiring that you can use when you cannot decide which type of wiring is to be used for wiring a bean and its property.

    Statement B: Spring provides default autowiring mode that will be used for wiring all the beans to their respective bean properties in your application.

    ```
    Both A and B is true
    ```

    

63. Rain has written the given code in her Spring Application.

    ```java
    63. package Work;
    
     interface Engineer{
    
     public void build();
    
     }
     
     public class MechanicalEngineer implements Engineer
    
     {
    
     String tool;
    
     public MechanicalEngineer(String tool)
    
     {
    
     this.tool = tool;
    
     }
    
     @Override
    
     public void build()
    
     {
    
     System.out.println("I am building with a"+tool);
    
     }
    
     public void setTool(String tool)
    
     {
    
     this.tool = tool;
    
     }
    
     }
    ```

    

    Now she wants to create a MechanicalEnginner objects using the Spring wiring for which she has written the following code:

    ```xml
    <bean id="ME" class="Work.Engineer">
    
    	<constructor-arg value="Hammer">
    
    	<property name="tool" value="Axle">
    </bean>
    ```

    

    In the main method she has written the following code :

    ```java
    public static void main(String[] args){
    
    ApplicationContext ac = new ClassPathXmlApplicationContext("Spring-Config.xml") ; 
    
    MechanicalEngineer ob = (MechanicalEngineer)ac.getBean("ME");
    
    ob.build();
    
    }
    ```

    

    What according to you should be the output of the given code?

    ```
    Throw an exception
    ```

    

 

64. Which type of exception is thrown if more than one matching bean is found whose type matches with the type of the property being wired in case of “byType” autowiring?

    

    @byType

    ```
    org.springframework.beans.factory.UnsatisfiedDependencyException
    ```

    

65. Which of the following functionalities is provided by a bean factory container?

    ```
    //不提供
     It provides a generic way to load file resources, such as images.
    
     It provides a means for resolving text messages, including support for internationalization of those messages.
     
     It publishes events to beans, which are registered as listeners.
     
    //提供 It is used to define relationships between different objects, as and when they are instantiated.
    ```

    

66. Which method of the ApplicationContextAware interface is called during the SetApplicationContext phase of the Life Cycle of a bean in the Application Context?

    

    @SetApplicationContext 

    ```
    setApplicationContext()
    ```

    

67. Arrange the given phases of the life cycle of a bean inside the ApplicationContext Container in order of their execution?

    I. Pre-Initialization 

    II. SetApplicationContext

    III. Initialize Beans

    IV. Set Bean Factory

    

    @排序

    ```
    Iv ii I iii
    ```

    

68. Regan has created a spring-config.xml in his local drive in the D:\Sports directory. Now he wants to load the Config file into his WebApplication with a particular ApplicationContext implementation? 

    Which of the following code would be appropriate for him?

    

    @配置

    @ApplicationContext 

    ```java
    ApplicationContext ac = new FileSystemXmlApplicationContext("D:/Sports/spring-config.xml");
    ```

    

69. Which of the following file in Spring MVC Framework is used to send a request to the DispatcherServlet to begin processing the user’s request?

    

    @配置

    ```
    web.xml
    ```

    

70. Which of the following is not a supported ViewResolver type in Spring MVC Framework?

    ```
    XMLViewResolver // ML 小写就对了
    
    //支持
    BeanNameViewResolver
    InternalResourceViewResolver
    ResourceBundleViewResolver
    
    ```

    

71. Which of the following component implements real business logic for processing a Spring request?

    ```
    Service Component
    ```

    

72. Which of the following configuration implements configuring the view resolver correctly?

    

    @配置 @配置类

    ```java
    @Bean
    
    public ViewResolver resolveView() {
    
    
    InternalResourceViewResolver viewResolver= new InternalResourceViewResolver();
    
    viewResolver.setPrefix("/WEB-INF/jsp/");
    
    viewResolver.setSuffix(".jsp");
    
    return viewResolver;
    
    }
    ```

    



73. Which of the following code snippet can be used in web.xml to specify the location of a spring xml file named spring-config.xml under the com.niit.config package and notifies application to load the file once the application starts?

    

    @配置

    ```xml
    <servlet>
    
      
    
      <init-param>
    
       <param-name>contextConfigLocation</param-name>
    
       <param-value>/WEB-INF/spring-config.xml</param-value>
    
      </init-param>
    
      <load-on-startup>1</load-on-startup>
    
     
    
    </servlet>
    ```

    



74. Which of the following is not an advantage of Spring MVC framework?

    @advantage 

    ```
    Heavy weight development environment
    ```

    

75. ____________ receives the request from dispatcher servlet, and forwards it to service classes for processing.

    ```
    Controller
    ```

    

76. _____________ is an implementation of the Map interface. It is used when you want to encapsulate business data into a model.

    

    @map 

    ```
    ModelMap
    ```

    

77. Consider the following code snippet:

    ```xml
    <servlet>
    
      <servlet-name>dispatcher</servlet-name>
    
      <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    
      <load-on-startup>1</load-on-startup>
    
     </servlet>
    ```

    

    The load-on-startup element defines :

    

    ```
    Which servlet is initialized first
    ```

    

 

78. Consider the following code snippet:

    ```xml
    <servlet>
    
      <servlet-name>TicketDispatcher</servlet-name>
    
      <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    
     <load-on-startup>1</load-on-startup>
    
    </servlet>
    ```

    The springapplication context is loaded from a file named ________________.

    

    ```
    TicketDispatcher-Servlet.xml
    ```

    

79. Statement A: AOP feature of Spring Framework attempts to solve the problem of cross-cutting concerns by allowing developer to express in modules called aspects

    Statement B: After identifying aspects, developers need to identify advice, joinpoint, and pointcuts.

    

    @AOP

    ```
    Both A and B is true
    ```

    

80. What does JSF use to locate the beans that are managed within the JSF application?

    

    @JSF

    ```
    Bean variable resolver
    ```

    

81. Keane needs to create an application where he has to integrate Spring with Hibernate. While creating this application, he felt the need for using a design pattern in his application that would enable him to perform the following tasks easily:

    - To communicate with the database layer and to separate persistence code from the application logic. 
    - To create maintainable application code.
    - To easily change the ORM tool without any need for changing the application code.

    Which of the following design patterns should he implement in his application so as to perform the preceding tasks easily ?

    

    @模式

    ```
    DAO
    ```

    



82. You are creating a Web application for the book shop by using Spring MVC. When a user sends a request for the URL, /SearchBook.htm page in this Web application, the request needs to be handled by the SearchBookController class defined in the controller package of the Web application. For this, you used the following code snippet:

    ```xml
    <beans>
    
    	<bean id="ControllerHandlerMapping" class="org.springframework.web.servlet.mvc.support.SimpleUrlHandlerMapping"/>
    
    	<bean class="controller.SearchBookController">
    
    </beans>
    ```

    

    However, the preceding code snippet does not forward the request to the SearchBookController class. Analyze the problem and provide the correct code snippet.

    

    ```xml
    <beans>
    
    	<bean id="ControllerHandlerMapping" class= "org.springframework.web.servlet.mvc.support.ControllerClassNameHandlerMapping"/>
    
    	<bean class="controller.SearchBookController"/>
    
    </beans>
    ```

    



83. You are creating a Web application for booking hotel rooms online. You are using Spring to create this application. When a user accesses the BookRoom.htm Web page of this application, the dispatcher servlet needs to forward the request for accessing this Web page to the BookRoomController class defined in the controller package. For this, you need to map the URL, /BookRoom.htm, with the BookRoomController class. Which of the following code snippets should you use to implement this functionality?

    

    @map

    ```xml
    <beans>
    
    <bean id="beanhandlermapping" class= "org.springframework.web.servlet.handler.BeanNameUrlHandlerMapping"/>
    
    <bean name="/BookRoom.htm" class="controller.BookRoomController"/>
    
    </beans>
    ```

    



84. When a server receives a request, it reads the web.xml file of the Web application and forwards the request to the dispatcher servlet. What action is now performed by the dispatcher servlet?

    

    @dispatcher

    ```
    The dispatcher servlet consults one or more of its handler mappings to determine the appropriate controller of the request.
    
    //调度器servlet参考其一个或多个处理程序映射来确定请求的适当控制器。
    ```

    

85. For an online banking Web application, the primary logic is to transfer funds, which is implemented in the transferFunds() method. You need to specify that the location where the advices of this application can be applied is the transferFunds() method. Which of the following options will you use to perform this task?

    

    @AOP

    ```
    Define pointcut
    ```



86. Which feature of Spring increases modularity by isolating secondary logic from the primary logic?

    

    @AOP

    ```
    Aspect-oriented programming
    ```

    

87. How many attribute does the @AfterReturning contain?

    

    @AfterReturning

    ```
    2
    ```

    

88. You are creating a Web application by using JSF. After creating the user interfaces, you created a bean named Student in the application. Then, you configured this bean using @ManagedBean annotation as in the following code snippet:

    ```java
    @Component
    
    @ManagedBean
    
    @SessionScoped
    
    public class Student {
    
     @Autowired
    
     StudentDao studnetDao;
    
     public void setStudnetDao(StudentDao studnetDao) {
    
     this. studnetDao = studentDao;
    
     }
    
     public List<String> fetchStudentDetails() {
    
     return studnetDao.getStudenDetails();
    
     }
    }
    
    
    ```

    

    However, the Student bean is not accessible by the user interface of the application. Analyze the problem and provide the solution.

    

    @JSF

    ```xml
    You should use the following code snippet to resolve the bean in the faces-config.xml file 
      
      <application>
       <el-resolver> org.springframework.web.jsf.el.SpringBeanFacesELResolver </el-resolver>
      </application>
    ```

    

89. You have written the following code snippet to declare a bean in the JSF application:

    ```java
    @ManagedBean
    
    @RequestScoped
    
    public class Auther {
    
     }
    ```

    You have to declare the preceding bean in a Spring configuration xml file. Which of the following code snippets should you use to perform this task?

    

    @JSF

    ```xml
    <bean id="author" class="Author" scope="request"></bean>
    ```

    

 

90. Sharapova has integrated her JSF Web application with the Spring framework and has loaded the Spring application context file into her application. She now needs to call the Spring beans annotated with @ManagedBean from the JSF environment. Which one of the following code snippets should Sharapova use to do this?

    

    @JSF

    ```xml
    <application>
    
    <el-resolver> org.springframework.web.jsf.el.SpringBeanFacesELResolver</el-resolver>
    
    </application>
    ```

    



91. You have been asked to use the Hibernate framework for managing transactions in your Spring-enabled Web application. However, before using this transaction manager, you need to declare it as a bean in the configuration file. Which one of the following code snippets will you use to declare the transaction manager?

    

    @Hibernate

    ```xml
    <bean id="txMgr" class="org.springframework.orm.hibernate4.HibernateTransactionManager">
    
    <property name="sessionFactory" ref="mySessionFactory" />
    
    </bean>
    ```

    

92. Mary is creating a Web application for the book shop by using Spring MVC. She has configured the dispatcher servlet. Now, she needs to define a controller for the Web application by setting the following properties:

    Name of the bean class is Book.

    Name of the new form is OrderBook.

    Name of the form that is displayed after successful submission of the data entered in the OrderBook page is Payment. To accomplish the preceding requirements, she uses the following code snippet in the controller class:

    ```java
    @RequestMapping(method=RequestMethod.GET)
    
    public String showView(ModelMap model)
    
    {
    
    Book b = new Book();
    
    model.addAttribute("Book", b);
    
    return "Payment";
    
    }
    
    @RequestMapping(method=RequestMethod.POST)
    
    public String processForm(@ModelAttribute(value="Book") Book b, ModelMap model) {
    
    return "OrderBook";
    
    }
    ```

    

    However, the preceding code snippet does not fulfill the desired requirements. Analyze the problem and provide the correct code snippet.

    

    @RequestMapping

    ```java
    //注意 get和 post 方法
    
    @RequestMapping(method=RequestMethod.GET)
    
    public String showView(ModelMap model)
    
    {
    
     Book b = new Book();
    
     model.addAttribute("Book", b);
    
     return "OrderBook";
    
     }
    
    @RequestMapping(method=RequestMethod.POST)
    
    public String processForm(@ModelAttribute(value="Book") Book b, ModelMap model )
    
    {
    
     return "Payment";
    
     }
    ```

    

 

93. You are creating a Web application for booking hotel rooms online. You are using Spring to create this application. This application contains a Web page named BookRoom. You need to define a controller class for this Web page. When a user enters the information about the room to be booked on this page and clicks the submit button, the BookingConfirmation page is displayed on successful booking of the room. The data entered by the user on the BookRoom page is stored in a bean named Booking. Which one of the following code snippets will you use to implement the desired functionality in the controller class?

    

    @RequestMapping

    ```java
    //先GET 后 POST
    
    @RequestMapping(method=RequestMethod.GET)
    
    public String showView(ModelMap model)
    
    {
    
     customer p = new Customer();
    
     model.addAttribute("Customer", p);
    
     return "BookRoom";
    
     }
    
    @RequestMapping(method=RequestMethod.POST)
    
    public String processForm(@ModelAttribute(value="Customer") Customer p, ModelMap model )
    
    {
    
     return "BookingConfirmation";
    
     }
    ```

    



94. To call the Spring beans, declared in the Spring application context, the Spring framework provides the ___________________ class.

    

    @Bean

    ```
    org.springframework.web.jsf.el.SpringBeanFacesELResolver
    ```

    

95. Which of the following statements define the ORM process?

    

    @ORM

    ```
    The process of mapping data representations in an object model having Java data types to a relational data model having SQL data type.
    ```

    

 

96. John has created a Spring-enabled Web application, in which he has implemented transactions. While implementing transactions, he has to ensure the prevention of all the problems, such as dirty read, non-repeatable read, and phantom read. Which isolation level should he use accomplish this task?

    

    @隔离等级

    ```
    ISOLATION_SERIALIZABLE
    ```

    

97. Mary has been assigned the task to create a Web application for the book shop. She decided to create the Web application by using Spring MVC. To handle Web requests for such a Web application, she has to first configure the dispatcher servlet named BookDispatcher in the web.xml file. For this, she writes the following code:

    ```xml
    <servlet>
    
    <servlet-name>dispatcher</servlet-name>
    
    <servlet-class>org.springframework.web.servlet.BookDispatcher</servlet-class>
    
    <load-on-startup>1</load-on-startup>
    
    </servlet>
    ```

    

    However, Mary is not able to configure the dispatcher servlet by using the preceding code snippet. Analyze and provide the correct code snippet.

    

    @dispatcher 

    ```xml
    <servlet>
    
    <servlet-name>BookDispatcher</servlet-name>
    
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    
    <load-on-startup>1</load-on-startup>
    
    </servlet>
    ```

    

98. You are creating a Web application for a bank by using Spring. You have implemented AOP in this application to separate the secondary logic from the primary logic. You created a class named SecondaryJob that contains the following methods to perform the secondary logic of the application: --authenticate() 

    \- checkBalance()

    \- updateBalance()

    The preceding methods are referred to as advices for the Web application. The authenticate() and checkBalance() methods should be executed before a joinpoint method withdraw(). The updateBalance() method should be executed after a joinpoint method withdraw(). You used the following code snippet to define the execution of the preceding methods:

    ```java
    @Before("withdraw()")
    
     public void Authenticate() {
    
    
     }
    
     @Before("withdraw()")
    
     public void checkBalance() {
    
    
     }
    
     @AfterThrowing(pointcut="withdraw()", throwing="ex")
    
     public void updateBalance() {
    
     }
    ```

    

    Analyze and predict if the preceding code snippet fulfills the desired requirements of the application. If not, then provide the correct code snippet.

    

    @AOP

    ```java
    The correct code snippet is:
    
       @Before("withdraw()")
    
     public void Authenticate() {
    
    
     }
    
     @Before("withdraw()")
    
     public void checkBalance() {
    
    
     }
    
     @AfterReturning(pointcut="withdraw()",returning = "result")
    
     public void updateBalance() {
    
    
     }
    ```

    

 

99. The _____________ element in the web.xml file specifies the location of the applicationContext.xml file to look for declaration of beans.

    

    @配置

    ```
    contextConfigLocation
    ```

    

100. The dispatcher servlet consults one or more of its handler mappings to determine the appropriate ______________ of the request

     

     @dispatcher 

     ```
     Controller
     ```

     

101. If you are using a single data source in your Spring application and accessing it using JDBC, you need to use the ______________ interface.

     

     @JDBC

     ```
     DataSourceTransactionManager
     ```

     

102. ___________________ occurs when a transaction (T1) reads several rows of data, and a concurrent transaction (T2) inserts additional rows simultaneously. Upon subsequent queries, the first transaction, T1, finds the additional rows that were not there before.

     @隔离等级

     ```
     Phantom read //幻读
     ```

     

103. Frank is developing an ORM application using both Spring and Hibernate. He has declared the bean for DAO in a configuration file spring-hibernate.xml under configs folder. He now wants to load the passengerDetailsDAO bean to initiate the session and work with database entities. Find the correct code for this requirement.

     

     @DAO @配置

     ```java
     ApplicationContext apc = new ClassPathXmlApplicationContext("configs/spring-hibernate.xml");
     
     PassengerDetailsDAO passengerDtls =(PassengerDetailsDAO) apc.getBean("passengerDetailsDAO");
     
     .........
     ```

     

104. The ___________ propagation behavior indicates that the current method must run within a transaction and if an existing transaction is in progress, the method will run that transaction. Otherwise a new transaction will be started.

     

     @PROPAGATION

     ```
     PROPAGATION_REQUIRED
     ```

     

105. __________ is a feature of transaction which states that all rules in a relational database must be applied to the modification in a transaction in order to maintain complete data integrity.

     > __________是事务的一个特点，它规定关系数据库中的所有规则必须应用于事务中的修改，以保持完整的数据完整性

     

     @database

     ```
     Consistency //一致性 而非原子性
     ```

     

106. Which one of the following files needs to be created first, for configuring the SessionFactory object?

     

     @SessionFactory @Hibernate

     ```
     spring-hibernate.xml
     ```

     

107. Ronald is creating a Spring-enabled Web application, which processes the admission fees paid by students for his school. In this application, he has implemented transactions and needs to ensure that when a transaction is running, then either all the data modifications being made by it should be performed or none of them should be performed. Which property of a transaction does the preceding statement refer to?

     

     @database

     ```
     Atomicity //原子性
     ```

     

108. You have been asked to configure transactions in your Web application using annotations. To do this, you have defined the @Transactional element on the methods or classes that have to be declared as transactional. Which class of the Spring framework do you need to import in your application to use the @Transactional element?

     

     @Transactional 

     ```
     org.springframework.transaction.annotation.Transactional
     ```

     



109. Statement A : JSF has disadvantage of scattered code, tightly coupled and difficult to implement system services, such as transactions and security.

     Statement B : When implemented in the business layer, Spring can modularize the secondary concern of a JSF Application.

     

     @JSF

     ```
     Both statements are true
     ```

     

110. What modifications do we need to make in web.xml while integrating Spring with JSF?

     

     @JSF

     ```
     The mapping of applicationContext.xml should be included.
     ```

     

111. Which one is the correct convention for naming a configuration file for dispatcher servlet?

     

     @dispatcher

     ```
     dispatcher-servlet.xml
     ```

     

112. Statement A: A transaction attribute is a description of how the transaction policies should be applied to the methods that implement transaction.

     Statement B: A transaction groups an arbitrary number of simple operations, making the whole process appear as a single logical unit of work.

     

     @transaction 

     ```
     Both statements are true
     ```

     

113. Statement A: PROPAGATION_SUPPORTS indicates that the current method does not necessarily require a transaction to run. If a transaction is in progress, the current method can run within it.

     Statement B: PROPAGATION_NESTED indicates that the nested transaction is independent in its features from the enclosing transaction

     

     @PROPAGATION

     ```
     Both statements are true
     ```

     

114. Statement A: Dirty Read occurs when the transaction reads data from an uncommitted transaction.

     Statement B: Phantom Read occurs when the subsequent queries produce additional rows which were not there before; due to a parallel running transaction.

     

     @database

     ```
     Both statements are true
     ```

     

115. Statement A: The EL resolver needs to be declared to call the Spring Beans from Spring Application Context.

     Statement B: The JSF managed bean are declared in faces-config.xml while integrating with Spring.

     

     @JSF

     ```
     Statement A is true, Statement B is false
     ```

     

116. Statement A: The Hibernate application depends on its own API objects to access the database, such as Configuration, SessionFactory and Session.

     Statement B: Integrating Spring with Hibernate helps to use the Hibernate objects as Spring beans.

     ```
     Both statements are true
     ```

     

117. You have to integrate the Spring framework in the application developed using JSF and Hibernate. For this, you have configured the SessionFactory object in the Spring configuration file as a bean named studSessionFactory. Then, you created a DAO class named StudentDAO in the admin package. Which of the following code snippets should you use to declare to get list of student from the database?

     

     @DAO

     ```java
     @Repository
     
     public class StudentDao{
     
      @Autowired
     
      private SessionFactory sessionFactory;
     
     
      @Transactional
     
      public List<Student> getStudent() {
     
      Session currentSession= sessionFactory.getCurrentSession();
     
      Query<Student> query= currentSession.createQuery("from  Student",Student.class );
     
      List<Student> students= query.getResultList();
     
      return students;
     
      }
     ```

     

118. You have created a Web application by using JSF. Now, you need to integrate this application with the Spring framework. Therefore, you added the Spring framework and provided mapping of the applicationContext.xml file in the web.xml file of the application. Now, you need to configure the dispatcher servlet named TicketDispatcher in the web.xml file of the application. Which of the following code snippets should you use to perform this task?

     

     @JSF

     ```xml
     <servlet><servlet-name>TicketDispatcher</servlet-name>
     
     <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
     
     <load-on-startup>2</load-on-startup>
     
     </servlet>
     
     <servlet-mapping>
     
     <servlet-name>TicketDispatcher</servlet-name>
     
     <url-pattern>\*.htm</url-pattern>
     
     </servlet-mapping>
     ```

     

119. While integrating Spring with Hibernate one should take care of managing the SessionFactory. What is the correct way of declaring a SessionFactory in this case?

     

     @SessionFactory

     ```xml
     Create a new xml configuration file and declare a bean as shown below
     
     <bean id="mySessionFactory" class="org.springframework.orm.hibernate5.LocalSessionFactoryBean">
     
     <property name="configLocation" value="hibernate.cfg.xm"></bean>
     ```

     

     

120. Emanuel is working to configure a transaction manager for his web application. For this purpose he has used Hibernate Framework integrated to Spring MVC. Help him to identify the correct configuration code to enable transaction management.

     

     @Hibernate  @集成 @配置

     ```xml
     <bean id="txManager" class="org.springframework.orm.hibernate5.HibernateTransactionManager">
     
     <property name="sessionFactory" ref="mySessionFactory">
     
     </bean>
     ```

     

121. Li Na has been asked to create a Web application, in which she has to integrate the Spring framework with Hibernate. To do this, Li Na has to configure the SessionFactory object in the Spring configuration file. For this, she has created a Spring configuration file named Spring-Hibernate.xml. Which of the following code snippets should she use to configure the SessionFactory object?

     @集成 @Hibernate 

     ```java
     @Bean
     
      public LocalSessionFactoryBean sessionFactory(){
     
      // create session factorys
     
      LocalSessionFactoryBean sessionFactory = new LocalSessionFactoryBean();
     
      // set the properties
     
      sessionFactory.setDataSource(myDataSource());
     
      sessionFactory.setPackagesToScan(env.getProperty("hibernate.packagesToScan"));
     
      sessionFactory.setHibernateProperties(getHibernateProperties());
     
      return sessionFactory;
     
      }
     ```

     

122. Roddick has created a Spring-enabled Web application, which he has integrated with Hibernate for providing data persistence. He now wants to implement transactions in his application. For this, Roddick has to create a data source bean in the configuration file to enable the application connect with the database. The application needs to connect with the derby database named TechDB having user name as tech and password as \<a href="mailto:pass@123">pass@123\</a>. Which one of the following code snippets should he use to create a data source bean?

     

     @DataSource @Database

     ```java
      @Bean
     
      public DataSource myDataSource() {
     
      try {
     
       myDataSource.setDriverClass("org.apache.derby.jdbc.ClientDriver"); 
     
      }
     
      catch (Exception exc) {
     
       System.out.println(exc);
     
      }
     
      myDataSource.setJdbcUrl("jdbc:derby://localhost:1527/TechDB");
     
      myDataSource.setUser("tech");
     
      myDataSource.setPassword("<a href=\"mailto:pass@123\">pass@123</a>" );
     
      }
     ```

     

123. You have created a Web application by using JSF and Hibernate. Now, you need to integrate this application with the Spring framework. For this, you first need to define a transaction manager for Hibernate. Which of the following code snippets will you use to define a transaction manager?

     

     @Hibernate

     ```java
     @Autowired 
     
     @Bean
     
     public HibernateTransactionManager transactionManager(SessionFactory sessionFactory) {
      
     HibernateTransactionManager txManager = new HibernateTransactionManager();
     
      txManager.setSessionFactory(sessionFactory);
      
      return txManager;
     
      } 
     ```

     

124. ndrea has developed a JSF application which is based on Managed Bean empDateBean for Employee Class. The empData.jsp is to accept either of empID or the department, so as to display the list of employees on to empList.jsp. Below is the code from faces-config.xml :

     ```xml
     <?xml version='1.0' encoding='UTF-8'>
     
     <!DOCTYPE faces-config PUBLIC >
     
     
     <faces-config>
     
     <navigation-rule>
     
     <from-view-id>/empData.jsp</from-view-id> 
     
     <navigation-case> 
     
     <from-outcome>showEmpList</from-outcome> 
     
     <to-view-id>/WEB-INF/results/empList.jsp></to-view-id>
     
     </navigation-case>
     
     </navigation-rule>
     
     </faces-config>
     
      
     ```

     

     When he deploys the application; the application throws a NullPointerException. What could be the correct reason?

     

     @NullPointerException

     ```
     The faces-config.xml is missing <managed-bean> declaration
     ```

     

125. Sandra is facing the problem of missing reference to applicationContext.xml; though she has added the file at /WEB-INF/Configs/applicationContext.xml . Find the correct code resolve the issue.

     

     @配置

     ```xml
     <init-param>
     
       <param-name>contextConfigLocation</param-name>
     
       <param-value>/WEB-INF/Configs/applicationContext.xml</param-value>
     
       </init-param>
     ```

     

126. Samuel has to configure datasource for transaction management with EmployeeDB database. For the same he has added hibernate with Java Derby Database to the spring web application. Help Samuel to configure the datasource.

     

     @Hibernate  @Database 

     ```java
     @Bean
     
      public DataSource myDataSource() {
     
      try {
     
       myDataSource.setDriverClass("org.apache.derby.jdbc.ClientDriver"); 
     
      }
     
      catch (Exception exc) {
     
       System.out.println(exc);
     
      }
     
      myDataSource.setJdbcUrl("jdbc:derby://localhost:1527/EmployeeDB");
     
      myDataSource.setUser("admin");
     
      myDataSource.setPassword("<a href=\"mailto:pass@123\">pass@123</a>" );
     
      }
     ```

     

