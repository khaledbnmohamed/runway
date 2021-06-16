CET-013

# Task Summary

* Create a Web API that List/save/get countries in/from DynamoDB using NodeJS and serverless framework  **Which is CloudFormation stack under the hood**

![Schema](schema.png)1

## :large_blue_diamond: Implementaion Guide
1) Use runway to Deploy the 2 stacks from CET-005
2) Create a seprate EC2 Instance and install jenkins on it

# Make it Work 
a
## :large_orange_diamond: Resources :
1) DynamoDB Table
2) S3 Deployment Bucket
   1) S3::BucketPolicy
3) 3 IAM::Roles
4) API Gateway
   1) ApiGateway::RestApi
   2) 2 ApiGateway::Resource
   3) ApiGateway::Deployment
   4) Logs::LogGroup
   5) 4 ApiGateway::Methods
5) Lambda Function

## :large_blue_diamond: Implementaion Guide
1) Deploy `sls deploy`

    You should see something similar to this:aaaa
    ![](deploy.png)

    Result API Gateway URL
    ` https://q6g0kpq5s9.execute-api.us-east-1.amazonaws.com/dev/countries `

 ## :large_orange_diamond: Result


### [**Postman Documentation**](https://documenter.getpostman.com/view/16150979/TzeTKA1e)


  1) Get Countries Endpoint

      Url : `https://q6g0kpq5s9.execute-api.us-east-1.amazonaws.com/dev/countries`
      ![](countries.png)
  2) Create Country Endpoint

      Url : `https://q6g0kpq5s9.execute-api.us-east-1.amazonaws.com/dev/countries`

      Data :
      ```
      --data-raw '{
         "id": "4",
         "name": "Spain"
      }'
      ```
      ![](create-country.png)

  3) Get Country Endpoint

      Url : `https://5kpe7z4ewh.execute-api.us-east-1.amazonaws.com/dev/country?name=egypt`

      ![](get-country.png)

# References
[Jenkins on AWS](https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/)
[Setting up a CI/CD pipeline by integrating Jenkins with AWS CodeBuild and AWS CodeDeploy](https://aws.amazon.com/blogs/devops/setting-up-a-ci-cd-pipeline-by-integrating-jenkins-with-aws-codebuild-and-aws-codedeploy/)

[Blog Post](https://www.serverless.com/blog/node-rest-api-with-serverless-lambda-and-dynamodb)

# Hints
How to define dependicies in the runway stacks file?

[Blog Post](https://www.serverless.com/blog/node-rest-api-with-serverless-lambda-and-dynamodb)
