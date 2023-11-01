
## MVVM (Model-View-ViewModel)
![[attachments/Pasted image 20231101180129.png]]

MVVM is another architecture that separates the presentation logic from the View. In this architecture, the ViewModel is responsible for presenting the data to the View. It acts as an intermediary between the View and Model, and it also handles the user’s input.

- A connecting link between Model and View here is a **ViewModel**.
- ViewModel is just like Presenter. It has access to View and can update it. The only difference here that we don't need to do it manually. The update performed by binding mechanism through events.
- Use in situations where access to view from program is always present and binding is a thing.
- An example where MVVM is possible is WPF.

The ViewModel exposes the data to the View through data bindings. When the data in the ViewModel changes, it automatically updates the View. Similarly, when the user interacts with the View, the ViewModel updates the Model.

### **Why it has been developed?**

- To provide the XAML platforms with a natural pattern with its key enablers that are data binding.
- To keep all the concerns separated and avoid clustering. 
- To establish a workflow between the developers and designers. 
- To enhance the testability of the application.

### **Advantages of MVVM Model**

- It facilitates users to swap components.
- It allows modifications in internal implementation without affecting others.
- Independent components are available for work.
- It offers the feature of isolated testing of the units.

### **Disadvantages of MVVM Model**

- The communication between various MVVM components is complex.
- The process of binding the data is crucial.
- It doesn’t easily allow codes to be reused.
- It’s quite difficult for beginners to learn and start working with.

**Under what conditions are the use of MVVM appropriate?**

- When you want to build a code that is easy to understand and troubleshoot.
- When you want to avoid the cost of UI testing.
- To build a test-driven development platform.
- When you need to decouple the view from ViewModel.
- When our screen holds many views.

## Code example
Our ViewModel is doing the same that Controller and Presenter did. The only difference here is that all the work is done behind the scene, and we don't need to worry about it. In WPF, binding is possible through `INotifyPropertyChanged` interface. You can implement it yourself, or use a data structure that already did it, like `ObservableCollection` in our example:
```csharp
public class OrderViewModel
{
	private readonly IOrdersModel ordersModel;

	// collection, that can fire events about changes
	public ObservableCollection<string> Orders { get; set; } = new ObservableCollection<string>();

	public OrderViewModel(IOrdersModel ordersModel)
	{
		this.ordersModel = ordersModel;
	}

	// method-handler, executes during interaction of user with View
	public ICommand LoadOrders => new RelayCommand((object sender) =>
	{
		// manipulates Model
		var orders = ordersModel.LoadOrders();

		// update collection that is bind to a View
		foreach (var order in orders)
		{
			Orders.Add(order.Name);
		}
	});
}
```

## Sources:
- https://medium.com/@akash.patel2520/mvvm-vs-mvc-vs-mvp-vs-viper-ios-development-dac50f67f1b4#:~:text=and%20business%20requirements.-,MVC%20is%20an%20excellent%20choice%20for%20small%20to%20medium%2Dsized,choice%20for%20large%2C%20complex%20applications
- https://medium.com/@iamprovidence/mvc-vs-mvp-vs-mvvm-with-c-examples-8013745e3c4c
- https://www.techaheadcorp.com/blog/mvc-vs-mvvm-vs-mvp-vs-viper/