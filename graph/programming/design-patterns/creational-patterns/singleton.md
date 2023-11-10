# Singleton
Singleton ensures that class has only one instance so everyone is working with a **single**, global object. Better to use [[graph/programming/design-patterns/dependency-injection|dependency-injection]]
![[attachments/Pasted image 20231030174642.png]]

## Example
![[attachments/Pasted image 20231110222429.png]]

## Example - simplified
![[attachments/Pasted image 20231110221917.png]]

## Testing
![[attachments/Pasted image 20231110222419.png]]

## When to use it?
- When a class should have only a single instance. Useful for database connections, windows and so on.
- When you need a global variable across different modules. It's basically a global variable.

## Why is it bad
1. They don't follow [[graph/programming/functional-programming/functional-programming|functional-programming]]: singletons are always a [[graph/programming/functional-programming/side-effect|side-effect]].
2. Violates [[graph/programming/Principles/SOLID/single-responsibility-principle|single-responsibility-principle]]. This pattern solves two problems at the same time.
3. This principle masks behind the bad implementation, goes away from [[graph/programming/functional-programming/functional-programming|functional-programming]]. 
4. Therefore, it is hard to work with it in [[graph/programming/multithreading/multithreading|multithreading]]. 
5. Also,it is hard to do unit test with it, because unit test was made SPECIFICALLY to test things independently.
6. Global scope pollution can end up in accidentally overwriting the value of a global variable, which can lead to a lot of unexpected behavior.

## Dependency hiding
When importing another module, superCounter.js in this case, it may not be
obvious that that module is importing a Singleton. In other, such
as index.js in this case, we may be importing that module and invoke its
methods. This way, we accidentally modify the values in the Singleton. This
can lead to unexpected behavior, since multiple instances of the Singleton can
be shared throughout the application, which would all get modifed as well.

![[attachments/Pasted image 20231110222609.png]]



## Relations with other patterns
- [[graph/programming/design-patterns/structural-patterns/facade|facade]] is usually transformed into a singleton since a single facade is enough for most cases.
- [[graph/programming/design-patterns/structural-patterns/flyweight|flyweight]] resembles singleton. it's mostly a hash map of **immutable** singletons.
- [[graph/programming/design-patterns/creational-patterns/abstract-factory|abstract-factory]], [[graph/programming/design-patterns/creational-patterns/builder|builder]], [[graph/programming/design-patterns/creational-patterns/prototype|prototype]] can be implemented as singletons.

## Sources
- https://refactoring.guru/design-patterns/singleton
- https://www.yegor256.com/2016/06/27/singletons-must-die.html
- Learning patterns book