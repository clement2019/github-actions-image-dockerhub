### project title 
github-actions--docker-image-dockerhub

#### Project overview

1.Docker Setup: Create an accout in Dockerhub to be able to deploy and store docker images activities.

2.Github: Through the imagecreation.yml file script we are able to build and push docker images to dockerhub 

4.Github Configuration: We are oushing the code to gihub so it makes sens if other activities will be halppening on the gihub self hosted runner. We can specify which operating system we are connecting to in aws if its ubuntun, amazon etc

5.Docker - installed docker on the server, to enable you build docker images


#### Prerequisites:

Before starting the project, ensure you have the following prerequisites:

-An AWS account with the necessary permissions to create resources.

-AWS CLI installed on your local machine.

-Basic familiarity with  Docker and DevOps principles.

-Vscode - code editor installed locally on your machine.

- GitHub - a repository for your project code

https://github.com/clement2019/github-actions-image-dockerhub.git


### Project Workflow
============
#### STAGE 1
==============
#### step 1: httpd application

### creating the .github/workflows/image-build.yml
I have to first create the 
touch .gihub folder 
cd .github
cd workflows
touch image-build.yml


<img width="1876" height="1264" alt="Image" src="https://github.com/user-attachments/assets/ba93578b-5bcb-4025-8446-270e428dab5c" />

### below find the dockerfile

# Use the official Apache HTTP Server image from the Docker Hub

FROM httpd:latest

# Copy a custom 'index.html' into the Apache server's root directory for hosting

COPY ./index.html /usr/local/apache2/htdocs/

### shown below is the index.html

<img width="1886" height="642" alt="Image" src="https://github.com/user-attachments/assets/75b666dc-54bf-4562-97e5-4bf32ea37291" />



### push the code to giuhub to trigger gihub actions


**📌 Step 1: Create IAM User**
Create **IAM user** and attached **AdministratorAccess** policy.

**📌 Step 2: Configure AWS CLI**
Now, configure the AWS CLI on local machine using the IAM credentials:

```bash
Run: aws configure
```

**Provide the following details:**
- **AWS Access Key ID**: `YOUR_ACCESS_KEY`
- **AWS Secret Access Key**: `YOUR_SECRET_KEY`
- **Default region**: (e.g., `eu-west-2`)
- **Output format**: (default: `json`)

Verify authentication:
```bash
aws sts get-caller-identity
```
If correctly configured, you should see your AWS **Account ID, User ID, and ARN**

**📌 Step 3: push code to dockerhube**
Before applying the configure dockerhub credentials configuration:


*📌 Step 3: Initialize image build**
Next, initialize the image in **root directory** where `dockerfile` is located.


**📌 Step 7: push image**


**📌 Step 9: final output **


---