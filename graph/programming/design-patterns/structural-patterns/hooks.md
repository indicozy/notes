We can create a hook to provide context to components. Instead of having to
import useContext and the Context in each component, we can use a
hook that returns the context we need. 

![[attachments/Pasted image 20231110225658.png]]

Instead of wrapping the components directly with the ThemeContext.Provider component, we can create a HOC that wraps this component to provide its values. This way, we can separate the context logic from the rendering components, which improves the reusability of the provider.

![[attachments/Pasted image 20231110225818.png]]
## Use cases
- When you want to simplify and reuse the interface of hook.