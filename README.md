## Dockerize Nodejs application and push to private Docker registry: AWS ECR

This app shows a simple user profile app set up using

- index.html with pure js and css styles
- nodejs backend with express module
- mongodb for data storage

All components are docker-based

### Technologies used:

Docker, Node.js,HTML, CSS, JavaScript, AWS ECR

### Project Description:

1- Write Dockerfile to build a Docker image for a Nodejs application

2- Create private Docker registry on AWS (Amazon ECR)

3- Push Docker image to this private repository

### With Docker

#### To start the application

Step 1: Create Dockerfile

![Alt text](app/images/dockerfile.png?raw=true)

Step 2: Create a image repository at AWS ECR

![Alt text](app/images/create-repository.png?raw=true)
Step 3: docker login to AWS ECR using the AWS CLI
![Alt text](app/images/view-docker-login-command.png?raw=true)
![Alt text](app/images/docker-login-command.png?raw=true)

Step 4: Build node-app image with version

    build build -t node-app:1.0 .

Step 5: Re-tag the image with repository domain and repository image name

    build tag node-app:1.0 118381122830.dkr.ecr.ap-southeast-2.amazonaws.com/node-app:1.0

![Alt text](app/images/re-tag-docker-image.png?raw=true)

Step 6: Push image to private AWS ECR

    build push 118381122830.dkr.ecr.ap-southeast-2.amazonaws.com/node-app:1.0

![Alt text](app/images/push-to-aws-ecr.png?raw=true)

![Alt text](app/images/image1.0.png?raw=true)

Step 7: update the Dockerfile

![Alt text](app/images/update-dockerfile.png?raw=true)

Step 8: Rebuild the image and push it to AWS ECR

     build -t node-app:1.1 .

![image](app/images/rebuild.png?raw=true)

     build tag node-app:1.1 118381122830.dkr.ecr.ap-southeast-2.amazonaws.com/node-app:1.1

![image](app/images/re-tag-docker-image.png?raw=true)

     build push 118381122830.dkr.ecr.ap-southeast-2.amazonaws.com/node-app:1.1

![image](app/images/image1.1.png?raw=true)
