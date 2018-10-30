# HW2
========
##CLOUD BEGINNER
----------------
###AWS Tutorial: Launch a VM - 1hr
pics
---------------------------------
###Introduction to Amazon Simple Storage Service S3-12:20-1:15
new to S3? watch this [intro to S3](https://www.youtube.com/watch?v=77lMCiiMilo).
---------------------------------
> **Use cases** of S3
1. Frequently accessed data
2. S3 Standard-*Infrequent Access*
3. S3 One Zone-*Infrequent Access* for long-lived, but less frequently accessed data.
4. Amazon Glacier for *long-term archive*.
> **reliable**- use ssl and management policies
> **flexibility**- to use as much storage as required

#### Hands-On practice on [awseducate-qwiklabs](https://awseducate.qwiklabs.com/focuses/30?parent=catalog) took *29 minutes*
>**create a bucket in Amazon S3**
>**Add an object to your bucket**
>**Manage access permissions on an object**

>**Create a bucket policy**
{
    "Version": "2012-10-17",
    "Id": "Policy1540400907130",
    "Statement": [
        {
            "Sid": "Stmt1540400902968",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObjectVersion",
            "Resource": "arn:aws:s3:::(mybucket223344)/*"
        }
    ]
}
so that each object inside the bucket can publicly shared.
>**Use bucket versioning**
========
Save multiple versions of a same object
"Action": "s3:GetObjectVersion" -- different versions of the same object can be accessed through this policy.

## CLOUD iNTERMEDIATE
### Virtual Machines, Websites, and Databases:
(https://www.youtube.com/watch?v=GIdVRB5yNsk)describes virtualization and why it needds more and more implimentation everyday.
======================
### Install a Lamp Web Server on Amazon Linux2
> ran linux instance
>establisihing connection through putty
>*ID instance*- i-093bd0ab14b25df00
>*public DNS name*-(ipv4) 54.202.153.202
>C:\Users\akshay\.ssh\mykeypair.pem(personal)
>ec2-user 
>Connect to your instance. 
>ensure that all of your software packages are up to date *sudo yum update -y*
>Install the lamp-mariadb10.2-php7.2 and php7.2 *sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2*
>install the Apache web server, MariaDB, and PHP software packages. *sudo yum install -y httpd mariadb-server*
>Start the Apache web server*Start the Apache web server*
>Use the systemctl command to configure the Apache web server to start at each system boot. *sudo systemctl enable httpd*
>*sudo systemctl is-enabled httpd* (enable verification)
>added inbound rules
>sudo usermod -a -G apache ec2-user- *Add your user (in this case, ec2-user) to the apache group. *
>exit
>verify membership *groups*

###On your own: Compare the performance, functionality, and price when serving web content from S3 versus an EC2 VM 
**S3 vs EC2**

|Types                            | Performance                       |Functionality                    |Serving Web content              |
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|S3                               | --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|EC2                              | --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
|---------------------------------| --------------------------------- |---------------------------------|---------------------------------|
 Only Static web content can be served through S3. S3 is a object based storage system. It is highly available and by defaults it is duplicated across availability zone. Also S3 storage is much cheaper than EBS- block storage. By serving the static contents from S3, one can save on IOPs of the EC2 as the request for S3 static links isnt served through EC2. Also it create a highly available environment, the static content which often are media files which consumes much higher storage need not be stored in all the EC2 instances
Thus EC2 EBS storage requirement is reduced considerably

***Amazon DynamoDB*-- is a fast and flexible NoSQL database service for all applications.
>created an Amazon DynamoDB table
>Entered data into an Amazon DynamoDB table
*i.e by adding sequential items* plus edited the table data.
>Query  an Amazon DynamDB table
*using scan/query* we can easily find data. It's certain that query is faster than scaning
>**complete it**

## Deploy a Node.js Web App
>learn how to deploy a high-availability Node.js web app using AWS Elastic Beanstalk and Amazon DynamoDB
>
### Serverless and Edge Computing:

## Intro to AWS lambda
>errors
##QwikLab: Intro to Amazon API Gateway - 35 min
*https://developer.spotify.com/documentation/web-api/*  was good example to understand RESTFUL API.

##Build a serverless web App
#Host a static website
http://wildrydes-akshay-gupta.s3-website-us-west-2.amazonaws.com(s3 stattic host end point)
#Manage users

Pool Id us-west-2_QwfIuQsvA
607gktk0nr9leupbrn5c6nhsiu

#Serverless Service Backend
Amazon Resource Name (ARN)
	arn:aws:dynamodb:us-west-2:566965401352:table/Rides
##Deploy Rest API
auth token: eyJraWQiOiJuTnA4NUVcL2tnS1Q3VmkxZ0kyRW5xVjlaZEdpTEFSYW5KenV0N01nNzd0ST0iLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiIxMGRkZWM3Ni0xOWU3LTQ1YjctYmNjNC1jOTlmYmZjMjA3ZjYiLCJhdWQiOiI2MDdna3RrMG5yOWxldXBicm41YzZuaHNpdSIsImVtYWlsX3ZlcmlmaWVkIjp0cnVlLCJldmVudF9pZCI6ImY3ZmQxMDE2LWRiMDAtMTFlOC1iNWIyLTc5YzdiNTZkMjQ1ZiIsInRva2VuX3VzZSI6ImlkIiwiYXV0aF90aW1lIjoxNTQwNzY1Nzg0LCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtd2VzdC0yLmFtYXpvbmF3cy5jb21cL3VzLXdlc3QtMl9Rd2ZJdVFzdkEiLCJjb2duaXRvOnVzZXJuYW1lIjoiYWtzaGF5Lmd1cHRhMDcxMkBnbWFpbC5jb20iLCJleHAiOjE1NDA3NjkzODQsImlhdCI6MTU0MDc2NTc4NCwiZW1haWwiOiJha3NoYXkuZ3VwdGEwNzEyQGdtYWlsLmNvbSJ9.Wf8mpVtwtbODlFQA8tQyhGC0yz6I-z4xD8yFmrfSggs30s5mJL8YiiRxWg03ZuOmsjBco5XMMduIqu0va7T4FpTYSrCAq9m1uAoCrOfUbuBD3MQFFGuJ2geJgi8tMoEmWtaLz32LBHBNERMq3-6MmMqkT3tRqLyb7GI0_FyNIvHvQok_gZUWquR98Ny9FKn4pkYf7ApbZgw9jqWlIHDZAT8EKVQYslTk32dkuvYgugO1lj-aHWDY5zl7Q0D-TLPHOLSI2CarNi7e4VhwcliiXktYCmZnI_qieCBFOcq8HndBVpgSkPXOkAK4AUvujBdUK3SekGZcXMyDjgYDyGMfdA
>arn:aws:lambda:us-west-2:566965401352:function:RequestUnicorn
>https://2x01cqllu1.execute-api.us-west-2.amazonaws.com/prod(deployed api)

##Build a Modern Web Application in python
**Goal:**
: *To create a website that enables visitors to a adopt a fantasy creature.*(www.mythicalmysfits.com)
>*host the weapp on a front-end web server*
>*connnect to backend database*
>*user authentication*
>*collect and analyze user behavior*
>*gathers insight for fututre analysis*
#Application architecture
pic
#Modules
>Create Static website-*building static website i.e storing static objects in S3 *
>Build Dynamic Website-*hosting application logic on a web server-using API backend microservice deployed(as a container)--aws fargate*
>Store Mysfit Data-*manage via NoSQl databse i.e. Amazon DynamoDB*
>Add User Registration-*API Gateway/Amazon Cognito*
>Capture User Clicks-*capture user analysi using AWS lambda/kenesis Firehose*
>create the required infrastructure components, which includes a fully managed CI/CD stack utilizing AWS CodeCommit, CodeBuild, and CodePipeline. Finally, you will complete the development tasks required all within your own browser using the cloud-based IDE, AWS Cloud9.

>Modue1-(static hosting)
1.Cloud 9 created
mythical-mysfits-bucket01(S3 bucket creaated)
aws s3 mb s3://mythical-mysfits-bucket-02
2.basic static site created
>module 2(host your app on web server)
*creating microservice hosted with aws fargatevto integrate website with backend*
**Fargate** is reliable for long running process for web/mobile and PaaS platform
>Module 2a *Setup Core Infrastructure*
>Deploy Cloud Formation Templates

    An Amazon VPC - a network environment that contains four subnets (two public and two private) in the 10.0.0.0/16 private IP space, as well as all the needed Route Table configurations.
    Two NAT Gateways (one for each public subnet) - allows the containers we will eventually deploy into our private subnets to communicate out to the Internet to download necessary packages, etc.
    A DynamoDB Endpoint - our microservice backend will eventually integrate with Amazon DynamoDB for persistence (as part of module 3).
    A Security Group - Allows your Docker containers to receive traffic on port 8080 from the Internet through the Network Load Balancer.
    IAM Roles - Identity and Access Management Roles are created. These will be used throughout the workshop to give AWS services or resources you create access to other AWS services like DynamoDB, S3, and more.
cloud finished provisioning all of the core networking and security resources as described above.
>Module 2B: Deploy A Service With AWS Fargate
*creating Docker image that will contain all of the code and configuration required to run mythical mysts backend as a microservice API created with Flask*
--creating Docker image using cloud 9 and pushing it in Elastic Container Registery(to make it available when we create our service using Fargate).
cd ~/environment/aws-modern-application-workshop/module-2/app *create docker image *
getting
{
    "Account": "566965401352", 
    "UserId": "566965401352", 
    "Arn": "arn:aws:iam::566965401352:root"
}
after bulding docker image 
we get(image tags that are required later) 
Successfully built 18bcefda98c8
Successfully tagged 566965401352.dkr.ecr.us-west-2.amazonaws.com/mythicalmysfits/service:latest
#test the service locally
#Push the Docker Image to Amazon ECR 
---------------------------------------------------
### Big Data and Machine Learning

## Beginner
# Intro to Hadoop
>hadoop is the solution to complexities arised due to use of distributed systems.
>Four Key characteristics are:
1.Economical(any computer can be used)
2.Reliable(reistant to hard ware failure )
3.Scalable(follows both horizontal and vertical scaling) 
4.Flexible(slexibilty to use of structured/unstructured data)

>here program goes into data instead of vice versa(conventional approach(rdbms)-overloadig)
>hadoop ecosystem comprises of 12 components(which can be classified under Data Ingestion, Data Analysis, Data Processing,Data Exploration,Workflow System, No SQl)
#analyze BigData With Hadoop
>

![image](https://raw.githubusercontent.com/agsrc/resorces/master/images/2.PNG)