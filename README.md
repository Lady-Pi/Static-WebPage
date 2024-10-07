# Static-WebPage
## Hosting a simple webpage on AWS 

The goal of this project is the deployment of a simple static webpage on Amazon Web Services (AWS). The project includes the design of the cloud architecture and deploying it. 
The web page itself is a  static 'Hello World' file for demonstration purposes only.

## Cloud Architecture:
1. User Access
Global visitors access the website via the CloudFront distribution URL
https://d2pftt2xeh25n7.cloudfront.net

2. Traffic Routing: 
CloudFront acts as the CDN, routing user requests to the nearest edge location to reduce latency. 

3.  Content delivery
The S3 bucket hosts the static HTML page. CloudFront fetches the static content (HTML file) from the S3 bucket. 
Origin Access Identity ensures that only CloudFront can access the S3 bucket, preventing direct access by users.

## Prerequisites

- AWS Command Line Interface installed and configured.
- IAM user with permissions to create and manage CloudFormation stacks, S3 buckets, and CloudFront distributions.

## Installation instructions

1. Clone the repository:

   ```bash
   git clone https://github.com/Lady-Pi/Static-WebPage.git

2.  Navigate to the project directory:
  
  ```bash
   cd <project-folder>

3. Deploy the CloudFormation stack:

```bash
aws cloudformation create-stack --stack-name my-secure-static-website --template-body file://cloudformation-template.yaml --capabilities CAPABILITY_NAMED_IAM

4. Wait until the stack creation is complete. You can check the status using:

   aws cloudformation describe-stacks --stack-name my-secure-static-website

5. Access the website using the CloudFront distribution URL:

  ```bash
 https://d2pftt2xeh25n7.cloudfront.net
