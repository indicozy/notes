Let's say we want to create an application that fetches 6 dog images, and renders these images on the screen. Ideally, we want to enforce separation of concerns by separating this process into two parts:
1. Presentational Components: Components that care about how data is shown to the user. In this example, that's the rendering the list of dog images.
2. Container Components: Components that care about what data is shown to the user. In this example, that's fetching the dog images.
Similar to [[graph/programming/system-design/architecture-patterns/mvc-mvp-mvvm-mvvm-c-viper|mvc-mvp-mvvm-mvvm-c-viper]]
### Presenter
![[attachments/Pasted image 20231110233620.png]]

### Container
![[attachments/Pasted image 20231110233602.png]]

Instead of having the data fetching logic in the DogsImagesContainer component, we can create a custom hook that fetches the images, and returns the array of dogs.

![[attachments/Pasted image 20231110233728.png]]

Still, we can enforce the separation of concerns by making a custom hook:
![[attachments/Pasted image 20231110233928.png]]

