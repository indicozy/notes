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
In MVP, Product defines only the 
```java
public class Product {
    private String name;
    private String description;
    private Double price;
    
   //getters & setters
}
```

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

## Sources
- https://github.com/ByteByteGoHq/system-design-101#why-is-nginx-called-a-reverse-proxy
- https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications.