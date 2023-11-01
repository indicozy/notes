# Model-View-Controller (MVC)
![[attachments/Pasted image 20231101174742.png]]

MVC is the most popular and widely used architecture in iOS development. In this architecture, the application is divided into three distinct components:

- Model: Represents the data and business logic of the application.
- View: Represents the user interface and user experience of the application.
- Controller: Sits between the Model and View, acts as an intermediary, and handles the logic of the application.

- A connecting link between Model and View here is a **Controller**.
- The Controller receives an input (events) from View and passes it to Model. Controller can not update View without user interaction.
- Apply it when view is disconnected from a program. A great example for it would be web page which is separated from server.
- This pattern is a heavily used by ASP.


### Advantages of the MVC Model

- It offers simultaneous development and allows multiple users to work on the model, controller, and views. 
- It provides high cohesion and enables the grouping of related actions on a single controller and that too logically, also grouping the views of a specific model. 
- This model has loose coupling helping in low coupling among models, views or controllers. 
- It has ease of modification as all the responsibilities are separate, simplifying the future development or modification.
- It allows a model to have multiple views.

### Disadvantages of MVC Model

- The introduction of new layers of abstraction makes the navigation of the framework complex and it becomes necessary for users to adopt the decomposition criteria of MVC.
- While decomposing a feature into 3 artifacts, developers face the problem of scattering and inconsistency in representing multiple artifacts. 
- The interaction between what the user uses and what he sees is quite heavy which increases the chances of clustering.
- The clustering state de-generates other parts into boilerplate shims or the code it’s based upon. 
- It requires extensive knowledge of multiple technologies making it necessary for the developers to be experts at various technologies.  
- UI components are generally factored into components that leave no scope for incremental benefits.
 - As the application grows, MVC can lead to a massive View and bloated Controller, making it hard to maintain and test.

### **When we can use the MVC Model?**

- When you need a faster development process.
- When you want to provide multiple views.
- When you want to build a support system for asynchronous techniques.
- When you don’t want the modification to disturb the entire model.
- When you want data results without formatting.
- When you want to build an SEO friendly platform.
- When our screen has a one-directional flow of instructions.

## Comparizons
- In MVP, View is just a state in which presenter makes all view logic. In MVC, view can have some logic but then sends events to controller

## Code example
```csharp
public class OrderController : Controller
{
	private readonly IOrdersModel _ordersModel;

	public OrderController()
	{
		_ordersModel = new OrdersModel();
	}

	// method-handler, executes during interaction of user with view
	public IActionResult GetOrders()
	{
		// manipulates model
		var orders = _ordersModel.LoadOrders();

		// select a view
		return View("OrdersView", orders);
	}
}
```

```csharp
// View class basically
@model MVC.Controllers.OrderDto[]

<ul>
    @foreach(var order in Model)
    {
        <li>@order.Name</li>
    }
</ul>
```
When you create a new ASP project you will notice a Model folder contain **data models** and not **domain model** (P.S. [[graph/programming/system-design/architecture-patterns/model|Models]] should contain ONLY domain models). You can not blame Microsoft for that. They were creating a generic template that would suit any domain. To not to leave that folder empty they got to put just anything there. Little did they know what a disservice they will do for entiry developers community. Since there is no place for logic to put in, developers start not only misunderstanding MVC but also writing business logic directly inside controllers. But that’s another story to tell…

## Sources:
https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications
- https://medium.com/@iamprovidence/mvc-vs-mvp-vs-mvvm-with-c-examples-8013745e3c4c