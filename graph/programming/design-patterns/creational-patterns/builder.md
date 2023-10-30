Builder lets you construct complex objects step by step. You can get different types of instances by using the same creation code. It is similar to [[graph/programming/functional-programming/currying|currying]] in [[graph/programming/functional-programming/functional-programming|functional-programming]]

![[attachments/Pasted image 20231030180042.png]]


## When to use it?
1. When you need to create different representation of the product (like house with wooden or stone roof).
2. When you are constructing a complex object of [[graph/programming/design-patterns/structural-patterns/composite|composite]] tree
3. When you want to get rid of "telescoping constructor":
``` js
class Pizza {
    Pizza(int size) { ... }
    Pizza(int size, boolean cheese) { ... }
    Pizza(int size, boolean cheese, boolean pepperoni) { ... }
    // ...
```

## Relations with other patterns
- Many builders start by using [[graph/programming/design-patterns/creational-patterns/factory-method|factory-method]] and then evolving towards builder.
- 