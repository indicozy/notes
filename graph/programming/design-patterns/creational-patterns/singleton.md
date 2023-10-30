# Singleton
Singleton ensures that class has only one instance so everyone is working with a **single**, global object. Better to use [[graph/programming/design-patterns/dependency-injection]]
![[attachments/Pasted image 20231030174642.png]]

## When to use it?
- When a class should have only a single instance. Useful for database connections, windows and so on.
- When you need a global variable across different modules. It's basically a global variable.

## Why is it bad
1. They don't follow [[graph/programming/functional-programming/functional-programming|functional-programming]]: singletons are always a [[graph/programming/functional-programming/side-effect|side-effect]].
2. Violates [[graph/programming/Principles/SOLID/single-responsibility-principle|single-responsibility-principle]]. This pattern solves two problems at the same time.
3. This principle masks behind the bad implementation, goes away from [[graph/programming/functional-programming/functional-programming|functional-programming]]. 
4. Therefore, it is hard to work with it in [[graph/programming/multithreading/multithreading]]

## Sources
- https://refactoring.guru/design-patterns/singleton
- https://www.yegor256.com/2016/06/27/singletons-must-die.html