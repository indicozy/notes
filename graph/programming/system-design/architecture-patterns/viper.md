
# **VIPER Architecture**
![[attachments/Pasted image 20231101181249.png]]

- **View** is the user interface. This layer is the ViewController together with the UIView(or xib/storyboard)
    
- **Interactor** contains business logic related to the data (Entities) or networking, like creating new instances of entities or fetching them from the server. For those purposes you’ll use some Services and Managers which are not considered as a part of VIPER module but rather an external dependency
    
- **Presenter** is directing data between the view and interactor, taking user actions and calling to router to move the user between views.The only class to communicate with all the other components.
    
- **Entity** is your plain data objects, not the data access layer, because that is a responsibility of the Interactor.
    
- **Router** handles navigation between the VIPER modules.

### **Advantages of VIPER Model**

- It simplifies complex projects hence making it an ideal choice large teams.
- It makes the process scalable and enables developers to work simultaneously on a project.
- It allows the reusability of codes by decoupling it.
- It segments various applications based on their roles and distributes the responsibilities.
- The new features can be added easily such as writing [automated tests](https://www.techaheadcorp.com/blog/automation-testing-best-practices/).

### **Disadvantages of VIPER Model**

- Lack of availability of resources to learn the VIPER [design](https://www.techaheadcorp.com/services/design/).
- It’s still not common in [iOS developers](https://www.techaheadcorp.com/hire/ios-developers/) and requires a certain level of knowledge and expertise to use it.
- It has a lot of files and a steep learning curve.

### **When can we use the VIPER Model?**

- When you want to keep all the modules isolated.
- When you need a good testing environment.
- When you want to maintain low coupling.
- When the application requirements are well-formed.
- Should be used only when the developers completely understand the project.

## Sources
- https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications
- https://www.techaheadcorp.com/blog/mvc-vs-mvvm-vs-mvp-vs-viper/
- https://dev.to/marwan8/getting-started-with-the-viper-architecture-pattern-for-ios-application-development-2oee