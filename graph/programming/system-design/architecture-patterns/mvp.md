# Model-View-Presenter (MVP)
![[attachments/Pasted image 20231101163605.png]]
MVP is an alternative to MVC that separates the presentation logic from the View. In this architecture, the Presenter handles the communication between the Model and View. The Model remains unchanged, and the Presenter manipulates the View’s data to present it to the user.

- A connecting link between Model and View here is a **Presenter**.
- Presenter is doing all the same job that Controller did. The only difference here, that with Presenter we have access to view and can **update** it manually.
- Use in situations where access to view from program is always present, but there is no binding mechanism.
- Windows Forms is a perfect example of this.

MVP is a good choice for applications where the View contains a lot of business logic or the business logic is complex. By separating the presentation logic, MVP helps keep the View and Model simple and easy to maintain.

### **Advantages of MVP Model**

- This model is easier to understand as it has a separate application model.
- There is no conceptual relationship between application components.
- The isolated testing of components is easier.

### **Disadvantages of MVP Model**

- It has a one to one mapping between the presenter and the view.
- It uses controllers for manipulating the data models which causes cluttering in the backend.
- It’s necessary to have its own controllers for a model. Hence, an application with increased models can’t withstand MVP if the number of controllers is not increased as well.

### **When we can use the MVP Model?**

- When our screen has a bi-directional flow of actions.
- When the result of the instruction given by the user affects the UI.
- When we have limited UI elements.

## Code example
- P.S. Presenter has View in it, View ALSO has presenter as dependency...
```csharp
// interface to simplify unit tests and restrict access to all the methods
public interface IOrdersView
{
	void Display(OrderDto[] orders);
}

// concrete View
public partial class OrdersForm : Form, IOrdersView
{
	private OrdersPresenter presenter;

	public OrdersForm()
	{
		InitializeComponent();
		presenter = new OrdersPresenter(this, new OrdersModel());
	}

	// passing calls from View to Presenter
	private void LoadOrdersButton_Click(object sender, EventArgs e)
	{
		presenter.LoadOrders();
	}

	// updates View from Presenter
	void IOrdersView.Display(OrderDto[] orders)
	{
		var orderNames = orders.Select(x => x.Name).ToArray();

		this.orderListBox.Items.AddRange(orderNames);
	}
}
```

And our Presenter similarly to Controller manipulates Model. The key point here that it has direct reference to the View as well and can update it whenever it likes, which gives us live experience:

```csharp
public class OrdersPresenter
{
	private readonly IOrdersView view;
	private readonly IOrdersModel model;

	public OrdersPresenter(IOrdersView view, IOrdersModel model)
	{
		this.view = view;
		this.model = model;
	}

	// method-handler, executes during interaction of user with view
	public void LoadOrders()
	{
		// manipulates model
		var orders = model.LoadOrders();

		// updates view
		view.Display(orders);
	}
}
```
## Sources:
- https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications
- https://medium.com/@iamprovidence/mvc-vs-mvp-vs-mvvm-with-c-examples-8013745e3c4c