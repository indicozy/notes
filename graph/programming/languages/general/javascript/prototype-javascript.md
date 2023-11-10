The prototype pattern is a useful way to share properties among many objects of the same type. The prototype is an object that's native to JavaScript, and can be accessed by objects through the prototype chain. The prototype pattern in javascript is more [[graph/programming/design-patterns/structural-patterns/flyweight|flyweight]] pattern than [[graph/programming/design-patterns/creational-patterns/prototype|prototype]].

![[attachments/Pasted image 20231110231850.png]]

The prototype pattern is very powerful when working with objects that should have access to the same properties. Instead of creating a duplicate of the property each time, we can simply add the property to the prototype, since all instances have access to the prototype object.

## Prototyping after creation
Since all instances have access to the prototype, it's easy to add properties to the prototype even after creating the instances. Say that our dogs shouldn't only be able to bark, but they should also be able to play! We can make this possible by adding a play property to the prototype.

![[attachments/Pasted image 20231110232034.png]]

## Creating a subclass
Let's create another type of dog, a super dog! This dog should inherit everything from a normal Dog, but it should also be able to fly. We can create a super dog by extending the Dog class and adding a fly method.
![[attachments/Pasted image 20231110232308.png]]

We have access to the bark method, as we extended the Dog class. The value of __proto__ on the prototype of SuperDog points to the Dog.prototype object!

It gets clear why it's called a **prototype chain**: when we try to access a property that's not directly available on the object, JavaScript recursively walks down all the objects that __proto__ points to, until it finds the property!

## Creating prototype from object.create
[[graph/programming/languages/general/javascript/object/Object|Object.create]] can become handy to set object properties.
![[attachments/Pasted image 20231110232533.png]]
Pet 1 now has dog as prototype.

## Conclusion
The prototype pattern allows us to easily let objects access and inherit properties from other objects. Since the prototype chain allows us to access properties that aren't directly defined on the object itself, we can avoid duplication of methods and properties, thus reducing the amount of memory used.