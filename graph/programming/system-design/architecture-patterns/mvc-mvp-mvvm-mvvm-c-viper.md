![[attachments/Pasted image 20231101160901.png]]

## Model-View-Controller (MVC)
MVC is the most popular and widely used architecture in iOS development. In this architecture, the application is divided into three distinct components:

- Model: Represents the data and business logic of the application.
- View: Represents the user interface and user experience of the application.
- Controller: Sits between the Model and View, acts as an intermediary, and handles the logic of the application.

As the application grows, MVC can lead to a massive View and bloated Controller, making it hard to maintain and test.
## Model-View-Presenter (MVP)
MVP is an alternative to MVC that separates the presentation logic from the View. In this architecture, the Presenter handles the communication between the Model and View. The Model remains unchanged, and the Presenter manipulates the View’s data to present it to the user.

MVP is a good choice for applications where the View contains a lot of business logic or the business logic is complex. By separating the presentation logic, MVP helps keep the View and Model simple and easy to maintain.

## MVC vs. MVP

### Common View Class
```java
public class ProductView {
    public void printProductDetails(String name, String description, Double price) {
        log.info("Product details:");
        log.info("product Name: " + name);
        log.info("product Description: " + description);
        log.info("product price: " + price);
    }
}
```
### MVP Model and Presenter Classes
In MVP, Product class defines only the model and business logic:
```java
public class Product {
    private String name;
    private String description;
    private Double price;
    
   //getters & setters
}
```
Presenter class in MVP fetches the data from the model and passes it to the view:

```java
public class ProductPresenter {
    private final Product product;
    private final ProductView view;
    
     //getters,setters & constructor
    
    public void showProduct() {
        productView.printProductDetails(product.getName(), product.getDescription(), product.getPrice());
    }
}
```

### MVC Model Class
For MVC, the difference is that **the view will get the data from the model class instead of the presenter class in MVP**.

```java
public class Product {
    private String name;
    private String description;
    private Double price;
    private ProductView view;
    
    //getters,setters
    
    public void showProduct() {
        view.printProductDetails(name, description, price);
    }
}

```
Personally, MVP sound better than MVC
## Comparison between MVC and MVP
- Coupling: The view and the model are tightly coupled in MVC but loosely coupled in MVP
- Communication: In MVP, communication between the View-Presenter and Presenter-Model happens via an **interface**, which makes it more flexible. However, the controller and view layer falls in the same activity/fragment in MVC.
- User Input: **In MVC, user inputs are handled by the** **Controller** that instructs the model for further operations. But **in MVP,** **user inputs are** **handled by the view** that instructs the presenter to call appropriate functions
- Type of Relation: A **many-to-one** **relationship** **exists between the controller and view**. One Controller can select different views based upon required operations in MVC. On the other hand, the presenter and view have a one-to-one relationship in MVP, where one presenter class manages one view at a time
## Sourcesa
- https://github.com/ByteByteGoHq/system-design-101#why-is-nginx-called-a-reverse-proxy
- https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications.