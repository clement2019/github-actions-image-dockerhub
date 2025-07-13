### project title: Gihub Actins Docker image Dockerhub
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



### push the code to github to trigger github actions

<img width="1626" height="654" alt="Image" src="https://github.com/user-attachments/assets/2ab6376e-3359-4970-82a1-fb1dd5c4d52f" />

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

**📌 Step 2: click on githubactions**

<img width="2562" height="1096" alt="Image" src="https://github.com/user-attachments/assets/3285d231-7c7f-4e6b-a749-cb15c76227a6" />



**📌 Step 3: Github actions troiggers output**

<img width="2546" height="938" alt="Image" src="https://github.com/user-attachments/assets/324135c7-b519-48f9-8e32-0c796f5a20f2" />



**📌 Step 4:  Enter Dockerhub crentials in envionment variabnle s of github**
Before applying the configure dockerhub credentials configuration:

<img width="2484" height="1344" alt="Image" src="https://github.com/user-attachments/assets/ea65b53d-2588-41e5-a916-f18f2c10dac7" />

**📌 Step 5: Enter the Credentials**

<img width="2422" height="1272" alt="Image" src="https://github.com/user-attachments/assets/cf897580-5279-40f2-8a03-445ba1dc3155" />

**📌 Step 7: Code workkkfile**

<img width="2456" height="1374" alt="Image" src="https://github.com/user-attachments/assets/7b869b95-b93c-451a-8dff-f259e27efe44" />

**📌 Step 9: final output of the pushed docker image on Dockergub Repo **

<img width="2562" height="978" alt="Image" src="https://github.com/user-attachments/assets/b8125209-6792-4053-9e3d-2b548f1d4410" />
