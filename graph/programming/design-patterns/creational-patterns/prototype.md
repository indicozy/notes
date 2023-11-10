To understand how javascript uses protoype pattern, see [[graph/programming/languages/general/javascript/prototype-javascript|prototype-javascript]] 

Prototype lets classes to implement how they would clone their instances. It is useful because only object knows its private variables, so object can clone itself.

![[attachments/Pasted image 20231030175621.png]]

## When it's applicable
1. When your code shouldn't depend on the concrete classes of objects that you are copying (?).
2. *Use the pattern when you want to reduce the number of subclasses that only differ in the way they initialize their respective objects.* (?)

## Relations with other patterns
- Prototype usually starts by using [[graph/programming/design-patterns/creational-patterns/factory-method|factory-method]]
- [[graph/programming/design-patterns/creational-patterns/prototype|prototype]] can help when you need to save copies of [[graph/programming/design-patterns/behavioral-patterns/commands|commands]] into history.
- Designs which heavily use [[graph/programming/design-patterns/structural-patterns/composite|composite]] and [[graph/programming/design-patterns/structural-patterns/decorator|decorator]] 
- prototype is not based inheritance, but requires initialization step. [[graph/programming/design-patterns/creational-patterns/factory-method|factory-method]] is based on inheritance, but doesn't require an initialization step.
- Yes, it can be implemented as [[graph/programming/design-patterns/creational-patterns/singleton|singleton]].
