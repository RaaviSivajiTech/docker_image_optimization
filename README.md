# docker_image_optimization

# Methods to optimize and achieve smaller Docker images

https://static.learnk8s.io/553d74fb0904984a84abefffdb5957af.svg

### When it comes to building Docker containers, you should always strive for smaller images. Images that share layers and are smaller in size are quicker to transfer and deploy.
### But how do you keep the size under control when every RUN statement creates a new layer, and you need intermediate artefacts before the image is ready?
### You may have noticed that most of the Dockerfiles in the wild have some weird tricks like this: