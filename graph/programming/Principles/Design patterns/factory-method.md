# Factory Method

Factory provides interface which subclasses will follow to create objects, but subclasses have their own autonomy on implementation.

![[attachments/Pasted image 20231030171941.png]]

## When to use it?
IDK

## How to implement?
1. Make all products follow the interface of the Factory. Interface should make sense for every product.
2. Add builder for creator classes. Return type of the method should match the common product interface.
3. In the creator's code find all references which match with product's constructor. Replace the product's constructor code and move it to the creator's code.
*At this point, the code of the factory method may look pretty ugly. It may have a large `switch` statement that picks which product class to instantiate. But don’t worry, we’ll fix it soon enough.*
4. Create a set of creator subclasses for each type of product listed in the factory method. Override the factory method of each subclass and move the common construction code to the factory method.
5. *If there are too many product types and it doesn’t make sense to create subclasses for all of them, you can reuse the control parameter from the base class in subclasses.*
6. 1. If the base factory method has become empty, you can make it abstract. *If there’s something left, you can make it a [[graph/programming/OOP/default-behaviors|default behaviors]] of the method.* (But I don't like default behaviors)

## Relations with other patterns
- Many start using Factory Method, which is less complicated and more customizable via subclasses, and then evolve it to [[graph/programming/Principles/Design patterns/abstract-factory|abstract-factory]], [[graph/programming/Principles/Design patterns/prototype|prototype]] or [[graph/programming/Principles/Design patterns/builder|builder]], which are more compllicated.
- [[graph/programming/Principles/Design patterns/abstract-factory|abstract-factory]] classes are based on a set of factory methods, but you can also use [[graph/programming/Principles/Design patterns/prototype|prototype]] to compose methods on these classes. (I didn't really get that)
- You can add [[graph/programming/Principles/Design patterns/iterator|iterator]] abstract method to collection creators to return different types of iterators which are compatible to their own collections.
- [[graph/programming/Principles/Design patterns/prototype|prototype]] requires initialization, but it isn't based on inheritance. Factory method is inversed: it is based on inheritance but doesn't require an initialization step.
- Factory method is a specialization of [[graph/programming/Principles/Design patterns/template-method]]. So factory method can be evolved to a large [[graph/programming/Principles/Design patterns/template-method|template-method]].