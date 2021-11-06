# AWS CloudWatch Logging

## Step-1: Pre-requisites
- You must have activated aws.amazon.com account.
- You have the sample tomcat application.Download it to the tomcat windows machine.
  Download -  https://github.com/cloudnloud/AWS-Solution-Architect-Training/blob/129231177f6f3c9b0f4590306ffd7aaffd3e9b3a/Day33/gameoflife.war

 
## Step-2: CloudWatch
 - **What is CloudWatch:** Amazon CloudWatch is a monitoring and management service that provides data and actionable insights for AWS, hybrid, and on-premises applications and infrastructure resources. With CloudWatch, you can collect and access all your performance and operational data in form of logs and metrics from a single platform. 

## Step-2: CloudWatch Implementation Steps
 - ** Please find an overview of the steps to install\configure the CloudWatch Agent on Windows Instance per your request as below:**
     1.	Attach the required IAM permission policy to the EC2 instance profile [1].
     2.	Download\install CloudWatch Unified Agent on EC2 instance [2]
     3.	Configure CloudWatch Agent to publish Metrics\Logs to CloudWatch Console [3] and [4].
     4.	Run CloudWatch Agent [5].
 
 
## Step-2.1: Setup Centos 7 Machine

In AWS - launch instances and search the below AMI ID.

Centos 7 Image ID - ami-0015b9ef68c77328d

Docker Installation in CentOS

sudo yum install -y yum-utils device-mapper-persistent-data lvm2

sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo


sudo yum install docker-ce docker-ce-cli containerd.io -y

sudo systemctl start docker

sudo systemctl enable docker



## Step-3: Pre-requisites
- Install required CLI on the desktop where we build our docker images.
- **Install AWS CLI V1.x**
   - Documentation Reference: https://aws.amazon.com/cli/
```
Mac & Linux
Requires Python 2.6.5 or higher.
yum install wget git awscli -y
```   
- **Install AWS CLI V2.x**
   - Documentation Reference: https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html
```
Mac OS (for all users)
$ curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
$ sudo installer -pkg AWSCLIV2.pkg -target /
$ which aws
/usr/local/bin/aws 
$ aws --version
aws-cli/2.0.6 Python/3.7.4 Darwin/18.7.0 botocore/2.0.0
```   

- **Install Docker CLI** 
   - Docker Desktop for MAC: https://docs.docker.com/docker-for-mac/install/
   - Docker Desktop for Windows: https://docs.docker.com/docker-for-windows/install/
   - Docker on Linux: https://docs.docker.com/install/linux/docker-ce/centos/

- **On AWS Console**
   - Create Authorization Token for admin user if not created
- **Configure AWS CLI with Authorization Token**
```
aws configure
AWS Access Key ID: ****
AWS Secret Access Key: ****
Default Region Name: ap-south-1
```   

## Step-4: Create ECR Repository
- Create simple ECR repo via AWS Console 
- Repository Name: aws-ecr-nginx
- Explore ECR console. 
- **Create ECR Repository using AWS CLI**
```
aws ecr create-repository --repository-name aws-ecr-nginx --region us-east-1

```

## Step-5: Create Docker Image locally
```
wget https://raw.githubusercontent.com/cloudnloud/AWS-Solution-Architect-Training/main/Day30/index.html
wget https://raw.githubusercontent.com/cloudnloud/AWS-Solution-Architect-Training/main/Day30/Dockerfile
```

```
docker build -t 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx:1.0.0 . 
docker run -dit --name cloudnloud-web -p 80:80 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx:1.0.0
```


## Step-6: Push Docker Image to AWS ECR
- Push the docker image to ECR
- **AWS CLI Version 1.x**
```
AWS CLI Version 1.x
aws ecr get-login --no-include-email --region <your-region>
aws ecr get-login --no-include-email --region us-east-1
Use "docker login" command from previous command output
docker push 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx:1.0.0
```
- **AWS CLI Version 2.x**
```
AWS CLI Version 2.x
aws ecr get-login-password --region <your-region> | docker login --username AWS --password-stdin <your-ecr-repo-url>

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx

docker push 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx:1.0.0
```


## Step-7: Using ECR Image with Amazon ECS
- Create Task Definition: aws-ecr-nginx
   - Container Image: 456774515540.dkr.ecr.us-east-1.amazonaws.com/aws-ecr-nginx:1.0.0
   - Container Port - 80
- Create Service: aws-ecr-nginx-svc
- Test it


## Now delete all images and containers (Stop and Delete)


## Step-8: To stop any running container
```
docker stop $(docker ps -q)  
```

## Step-9: To remove all the containers

```
docker rm $(docker ps -a -q)
```

## Step-10: To remove all docker images in a single command
```
docker rmi $(docker images -a -q)
```

## Step-11: Now you have clean environment

```
docker pull cloudnloud/nginxapp2:latest

docker run -dit --name cloudnloud-web -p 80:80 cloudnloud/nginxapp2:latest
```
