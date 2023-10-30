Produces related object without specifying concrete classes. It's basically abstraction over factories. Used for creating related (as in families) groups of products.

![[attachments/Pasted image 20231030182312.png]]

## When it's used?
- When you need to work with various families of related products, but you don't want to depend on concrete classes of those products - they might not be implemented beforehand and you want to have future extensibility.
- If you want to combine a set of similar [[graph/programming/design-patterns/creational-patterns/factory-method|factory-methods]] that blur its primary responsibility (?)

## Relations with other patterns
- Yes, it can start from a single [[graph/programming/design-patterns/creational-patterns/factory-method|factory-method]].
- [[graph/programming/design-patterns/creational-patterns/builder|builder]] is focused on constructing complex objects step-by-step, while abstract factory specializes in returning the product immediately.
- Abstract factory can be an alter
- Yes, it can be a [[graph/programming/design-patterns/creational-patterns/singleton|singleton]].