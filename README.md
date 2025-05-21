Just like application code can be hosted on EC2 instance, businesses can also host their 
application code on lambda functions. 
EC2 instances can be provisioned to host business applications. However, the maintenance 
procedures which involves patching, scaling up or down based on demand, or any procedure 
that is needed to keep the instance up and running lies in the hands of the client.


Lambda which is a Platform as a service provides a serverless compute option which allows 
client focus on providing innovations to their applications. For lambda, after setting up your 
configuration, AWS handles all the maintenance and procedures behind the hood to ensure 
that you have the platform ready and available at all times to run your business application. 
All you have to do is to run your code or application on the platform. This is the why lambda 
is termed as serverless. lambda can be used in a development environment or a production 
environment.  


The lambda function will be able to run a business application if it is triggered by an event. 
Lambda function will need to assume a role to be able to interact with other resources for it 
to run the business application successfully. 


This lab demonstrates how a lambda function can be invoked when it is triggered by an 
event where a document is placed in an s3 bucket. The lambda function will assume a role to 
be able to access an s3 bucket. After the lab, I was able to deduce that lambda does not only 
provide the compute platform needed to run a business application. The lambda function 
can be edited at any time to modify uploaded document in the s3 bucket.

Step by step procedure in invoking a lambda function on the AWS console 

The configuration of the lambda function which included the name and the runtime was specified as shown below. 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094504.png)

The lambda function was also given an execution role with permission to read from S3 bucket.
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094532.png)

The lambda function was successfully created 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094548.png)

An s3 bucket was created.  
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094606.png)

The lambda function was updated to modify the file which will be uploaded in the s3 bucket 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094624.png)

A trigger for the lambda function was also added. 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094639.png)

![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094639.png)

This was the state of the cloudwatch metrics before a file was uploaded in the S3 bucket. The lambda function was not invoked because it was not triggered 
by any event.
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094820.png)

Two files were successfully uploaded in the S3 bucket . 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094838.png)

The status of the cloudwatch changed indicating that the lambda function was invoked when two files were uploaded in the S3 bucket. 
![image alt](https://github.com/Gertrudechichi/AWS-lambda/blob/0d8f9f0ea280b19b67363d6f4cc782e5708eeee1/Screenshot%202025-05-21%20094900.png)
