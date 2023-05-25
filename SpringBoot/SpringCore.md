# SPRING BEANS:
- class whose lifecycle is managed by the Inversion of Control (IoC) container is commonly referred to as a Spring bean.
- Spring bean is a POJO assembled using metadata such as XML File, Annotations or configuration class.
- Spring IOC releases and destroys these beans also.
- By Lifecycle of class that means we are talking about the object of the class that is instantiated.
## Life-Cycle of Spring Bean:
- Instantiation-> Uses a Constructor of a factory method like XMLConfig factory etc
- Initialization->sets the properties and dependencies
- Usage->Calls the class methods by object or Bean
- Destruction->Calls the destruction methods in bean config file or xml file and releases the resources.

## BEAN SCOPE
**Singleton Scope**: 
- This is the default scope in Spring. 
- container creates only one instance of the bean and reuses that instance whenever the bean is requested. 
- suitable for stateless beans or beans that **can be shared across the application like DB Connections.**
    -   **Stateless Beans**: meaning that it does not maintain any data or state between method calls. 
        - Each method invocation on a stateless bean is independent of any previous or subsequent invocations, and the bean is not affected by any external factors.
        - used in a concurrent and distributed environment where multiple threads or processes can access the same bean instance at the same time. 
        - they are thread-safe and can be shared across multiple threads.
