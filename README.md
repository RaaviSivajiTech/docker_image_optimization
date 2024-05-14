# **Docker Optimization**

## Methods to optimize and achieve smaller Docker images

<img width="800" height="600" style="display: block; margin: 0 auto" alt="Docker_screen" src="image.png">

### When it comes to building Docker containers, you should always strive for smaller images. Images that share layers and are smaller in size are quicker to transfer and deploy

### But how do you keep the size under control when every **RUN** statement creates a new layer, and you need intermediate artifacts before the image is ready?

### You may have noticed that most of the **Dockerfiles** in the wild have some weird tricks like this

<img width="800" height="600" style="display: block; margin: 0 auto" alt="Docker_screen" src="image-1.png">

### Why the **&&**? Why not running two **RUN** statements like this?

<img width="800" height="600" style="display: block; margin: 0 auto" alt="Docker_screen" src="image-2.png">

Since Docker 1.10 the **COPY**, **ADD** and **RUN** statements add a new layer to your image. The previous example created two layers instead of just one.

<img width="800" height="600" style="display: block; margin: 0 auto" alt="Docker_screen" src="image-3.png">