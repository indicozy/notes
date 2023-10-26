> Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.

> A class is closed, since it may be compiled, stored in a library, baselined, and used by client classes. But it is also open, since any new class may use it as parent, adding new features. When a descendant class is defined, there is no need to change the original or to disturb its clients.

That’s why Robert C. Martin and others redefined the Open/Closed Principle to the [Polymorphic](https://stackify.com/oop-concept-polymorphism/) Open/Closed Principle. It uses interfaces instead of superclasses to allow different implementations which you can easily substitute without changing the code that uses them.
# Steps
- Extract the interface
- Adapt the class
- Add implementations