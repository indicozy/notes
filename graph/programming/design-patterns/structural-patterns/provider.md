Rather than passing that data down each layer through props, we can wrap all components in a Provider. A Provider is a higher order component provided to us by the a Context object. We can create a Context object, using the createContext method that React provides for us. It helps to avoid [[graph/programming/design-patterns/antipatterns/prop-drilling|prop-drilling]].
	
The components that aren't using the data value won't have to deal with data at all. We no longer have to worry about passing props down several levels through components that don't need the value of the props, which makes refactoring a lot easier
## Example
![[attachments/Pasted image 20231110225137.png]]

## Use cases
1. Sharing a theme UI state with many components