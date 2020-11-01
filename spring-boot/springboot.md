Spring boot 
Rapid  application devlopment
Removes much of the boiler plate code
Cloud native- 12 factor app - the way it is structured
Automatic servlet mapping
Auto-config and component scanning in an appropriate application context
Use of spring-actuator and its endpoints
@SpringBootApplication - used for :
- It provide base package for component scanning
- It provides a classs file for static configurations of the application context
- It provides a place for autoconfiguration to start applying default behaviors
Spring Annotations
------------------------
- @component - states that spring to manage that particular bean! IoC container will manage that bean
- @autowired - will scan for matching implementation of that that variable/setter/constructor element
application.prop:
logging.level.org.springframework: DEBUG
springboottutorial.com